---
id: 'sample-deep-research-mcp-001'
title: 'sample-deep-research-mcp'
type: 'component-documentation'
status: 'development'
owner: '@team-placeholder'
related_components: []
tech_stack: []
summary: 'A brief description of the sample-deep-research-mcp component.'
---


# Cupcake MCP for Deep Research

This is a minimal example of a Deep Research style MCP server for searching and fetching cupcake orders.

## Set up & run

Python setup:

```shell
python -m venv env
source env/bin/activate
pip install -r requirements.txt
```

Run the server:

```shell
python sample_mcp.py
```

The server will start on `http://127.0.0.1:8000` using SSE transport.

## Files

- `sample_mcp.py`: Main server code
- `records.json`: Cupcake order data (must be present in the same directory)

---
summary: |
    This project is a minimal Model Context Protocol server for a sample cupcake ordering domain. Setup instructions create a Python virtual environment, install requirements, and run `sample_mcp.py` to start a server on localhost using SSE. The README notes that `records.json` contains order data needed by the server.
---
