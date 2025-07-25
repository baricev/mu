---
id: 'redis-py-001'
title: 'redis-py'
type: 'component-documentation'
status: 'development'
owner: '@team-placeholder'
related_components: []
tech_stack: []
summary: 'A brief description of the redis-py component.'
---


# redis-py

The Python interface to the Redis key-value store.

[![CI](https://github.com/redis/redis-py/workflows/CI/badge.svg?branch=master)](https://github.com/redis/redis-py/actions?query=workflow%3ACI+branch%3Amaster)
[![docs](https://readthedocs.org/projects/redis/badge/?version=stable&style=flat)](https://redis-py.readthedocs.io/en/stable/)
[![MIT licensed](https://img.shields.io/badge/license-MIT-blue.svg)](./LICENSE)
[![pypi](https://badge.fury.io/py/redis.svg)](https://pypi.org/project/redis/)
[![pre-release](https://img.shields.io/github/v/release/redis/redis-py?include_prereleases&label=latest-prerelease)](https://github.com/redis/redis-py/releases)
[![codecov](https://codecov.io/gh/redis/redis-py/branch/master/graph/badge.svg?token=yenl5fzxxr)](https://codecov.io/gh/redis/redis-py)

[Installation](#installation) |  [Usage](#usage) | [Advanced Topics](#advanced-topics) | [Contributing](https://github.com/redis/redis-py/blob/master/CONTRIBUTING.md)

---------------------------------------------

**Note:** redis-py 5.0 will be the last version of redis-py to support Python 3.7, as it has reached [end of life](https://devguide.python.org/versions/). redis-py 5.1 will support Python 3.8+.

---------------------------------------------

## How do I Redis?

[Learn for free at Redis University](https://redis.io/learn/university)

[Try the Redis Cloud](https://redis.io/try-free/)

[Dive in developer tutorials](https://redis.io/learn)

[Join the Redis community](https://redis.io/community/)

[Work at Redis](https://redis.io/careers/)

## Installation

Start a redis via docker:

``` bash
docker run -p 6379:6379 -it redis/redis-stack:latest
```

To install redis-py, simply:

``` bash
$ pip install redis
```

For faster performance, install redis with hiredis support, this provides a compiled response parser, and *for most cases* requires zero code changes.
By default, if hiredis >= 1.0 is available, redis-py will attempt to use it for response parsing.

``` bash
$ pip install "redis[hiredis]"
```

Looking for a high-level library to handle object mapping? See [redis-om-python](https://github.com/redis/redis-om-python)!

## Supported Redis Versions

The most recent version of this library supports redis version [5.0](https://github.com/redis/redis/blob/5.0/00-RELEASENOTES), [6.0](https://github.com/redis/redis/blob/6.0/00-RELEASENOTES), [6.2](https://github.com/redis/redis/blob/6.2/00-RELEASENOTES), [7.0](https://github.com/redis/redis/blob/7.0/00-RELEASENOTES), [7.2](https://github.com/redis/redis/blob/7.2/00-RELEASENOTES) and [7.4](https://github.com/redis/redis/blob/7.4/00-RELEASENOTES).

The table below highlights version compatibility of the most-recent library versions and redis versions.

| Library version | Supported redis versions |
|-----------------|-------------------|
| 3.5.3 | <= 6.2 Family of releases |
| >= 4.5.0 | Version 5.0 to 7.0 |
| >= 5.0.0 | Version 5.0 to current |


## Usage

### Basic Example

``` python
>>> import redis
>>> r = redis.Redis(host='localhost', port=6379, db=0)
>>> r.set('foo', 'bar')
True
>>> r.get('foo')
b'bar'
```

The above code connects to localhost on port 6379, sets a value in Redis, and retrieves it. All responses are returned as bytes in Python, to receive decoded strings, set *decode_responses=True*.  For this, and more connection options, see [these examples](https://redis.readthedocs.io/en/stable/examples.html).


#### RESP3 Support
To enable support for RESP3, ensure you have at least version 5.0 of the client, and change your connection object to include *protocol=3*

``` python
>>> import redis
>>> r = redis.Redis(host='localhost', port=6379, db=0, protocol=3)
```

### Connection Pools

By default, redis-py uses a connection pool to manage connections. Each instance of a Redis class receives its own connection pool. You can however define your own [redis.ConnectionPool](https://redis.readthedocs.io/en/stable/connections.html#connection-pools).

``` python
>>> pool = redis.ConnectionPool(host='localhost', port=6379, db=0)
>>> r = redis.Redis(connection_pool=pool)
```

Alternatively, you might want to look at [Async connections](https://redis.readthedocs.io/en/stable/examples/asyncio_examples.html), or [Cluster connections](https://redis.readthedocs.io/en/stable/connections.html#cluster-client), or even [Async Cluster connections](https://redis.readthedocs.io/en/stable/connections.html#async-cluster-client).

### Redis Commands

There is built-in support for all of the [out-of-the-box Redis commands](https://redis.io/commands). They are exposed using the raw Redis command names (`HSET`, `HGETALL`, etc.) except where a word (i.e. del) is reserved by the language. The complete set of commands can be found [here](https://github.com/redis/redis-py/tree/master/redis/commands), or [the documentation](https://redis.readthedocs.io/en/stable/commands.html).

## Advanced Topics

The [official Redis command documentation](https://redis.io/commands)
does a great job of explaining each command in detail. redis-py attempts
to adhere to the official command syntax. There are a few exceptions:

-   **MULTI/EXEC**: These are implemented as part of the Pipeline class.
    The pipeline is wrapped with the MULTI and EXEC statements by
    default when it is executed, which can be disabled by specifying
    transaction=False. See more about Pipelines below.

-   **SUBSCRIBE/LISTEN**: Similar to pipelines, PubSub is implemented as
    a separate class as it places the underlying connection in a state
    where it can\'t execute non-pubsub commands. Calling the pubsub
    method from the Redis client will return a PubSub instance where you
    can subscribe to channels and listen for messages. You can only call
    PUBLISH from the Redis client (see [this comment on issue
    #151](https://github.com/redis/redis-py/issues/151#issuecomment-1545015)
    for details).

For more details, please see the documentation on [advanced topics page](https://redis.readthedocs.io/en/stable/advanced_features.html).

### Pipelines

The following is a basic example of a [Redis pipeline](https://redis.io/docs/manual/pipelining/), a method to optimize round-trip calls, by batching Redis commands, and receiving their results as a list.


``` python
>>> pipe = r.pipeline()
>>> pipe.set('foo', 5)
>>> pipe.set('bar', 18.5)
>>> pipe.set('blee', "hello world!")
>>> pipe.execute()
[True, True, True]
```

### PubSub

The following example shows how to utilize [Redis Pub/Sub](https://redis.io/docs/manual/pubsub/) to subscribe to specific channels.

``` python
>>> r = redis.Redis(...)
>>> p = r.pubsub()
>>> p.subscribe('my-first-channel', 'my-second-channel', ...)
>>> p.get_message()
{'pattern': None, 'type': 'subscribe', 'channel': b'my-second-channel', 'data': 1}
```


--------------------------

### Author

redis-py is developed and maintained by [Redis Inc](https://redis.io). It can be found [here](
https://github.com/redis/redis-py), or downloaded from [pypi](https://pypi.org/project/redis/).

Special thanks to:

-   Andy McCurdy (<sedrik@gmail.com>) the original author of redis-py.
-   Ludovico Magnocavallo, author of the original Python Redis client,
    from which some of the socket code is still used.
-   Alexander Solovyov for ideas on the generic response callback
    system.
-   Paul Hubbard for initial packaging support.

[![Redis](./docs/_static/logo-redis.svg)](https://redis.io)
