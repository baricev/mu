# Here are summaries of some files present in my git repository.

### Do not propose changes to these files, treat them as *read-only*.
### If you need to edit any of these files, ask me to *add them to the chat* first.

anthropic_projects/anthropic-quickstarts/computer-use-demo/computer_use_demo/tools/base.py:
⋮
│@dataclass(kw_only=True, frozen=True)
│class ToolResult:
│    """Represents the result of a tool execution."""
│
⋮
│    def __add__(self, other: "ToolResult"):
│        def combine_fields(
│            field: str | None, other_field: str | None, concatenate: bool = True
⋮
│    def replace(self, **kwargs):
⋮

anthropic_projects/anthropic-quickstarts/customer-support-agent/app/lib/utils.ts:
⋮
│export async function retrieveContext(
│  query: string,
│  knowledgeBaseId: string,
│  n: number = 3,
⋮

anthropic_projects/anthropic-sdk-python/src/anthropic/_client.py:
⋮
│class Anthropic(SyncAPIClient):
⋮

anthropic_projects/anthropic-sdk-python/src/anthropic/_compat.py:
⋮
│if TYPE_CHECKING:
│
│    def parse_date(value: date | StrBytesIntFloat) -> date:  # noqa: ARG001
⋮
│    def get_args(t: type[Any]) -> tuple[Any, ...]:  # noqa: ARG001
⋮
│    def get_origin(t: type[Any]) -> type[Any] | None:  # noqa: ARG001
⋮
│def parse_obj(model: type[_ModelT], value: object) -> _ModelT:
⋮
│def model_copy(model: _ModelT, *, deep: bool = False) -> _ModelT:
⋮
│def model_dump(
│    model: pydantic.BaseModel,
│    *,
│    exclude: IncEx | None = None,
│    exclude_unset: bool = False,
│    exclude_defaults: bool = False,
│    warnings: bool = True,
│    mode: Literal["json", "python"] = "python",
⋮

anthropic_projects/anthropic-sdk-python/src/anthropic/_files.py:
⋮
│def assert_is_file_content(obj: object, *, key: str | None = None) -> None:
⋮

anthropic_projects/anthropic-sdk-python/src/anthropic/_models.py:
⋮
│class BaseModel(pydantic.BaseModel):
│    if PYDANTIC_V2:
│        model_config: ClassVar[ConfigDict] = ConfigDict(
│            extra="allow", defer_build=coerce_boolean(os.environ.get("DEFER_PYDANTIC_BUILD", "true"
│        )
│    else:
│
│        @property
│        @override
│        def model_fields_set(self) -> set[str]:
│            # a forwards-compat shim for pydantic v2
⋮
│    if not PYDANTIC_V2:
⋮
│        @override
│        def model_dump(
│            self,
│            *,
│            mode: Literal["json", "python"] | str = "python",
│            include: IncEx | None = None,
│            exclude: IncEx | None = None,
│            by_alias: bool = False,
│            exclude_unset: bool = False,
│            exclude_defaults: bool = False,
│            exclude_none: bool = False,
⋮
│        @override
│        def model_dump_json(
│            self,
│            *,
│            indent: int | None = None,
│            include: IncEx | None = None,
│            exclude: IncEx | None = None,
│            by_alias: bool = False,
│            exclude_unset: bool = False,
│            exclude_defaults: bool = False,
│            exclude_none: bool = False,
⋮
│def construct_type(*, value: object, type_: object) -> object:
⋮

anthropic_projects/anthropic-sdk-python/src/anthropic/_streaming.py:
⋮
│class SSEDecoder:
│    _data: list[str]
⋮
│    def decode(self, line: str) -> ServerSentEvent | None:
⋮

anthropic_projects/anthropic-sdk-python/src/anthropic/_types.py:
⋮
│class NotGiven:
⋮

anthropic_projects/anthropic-sdk-python/src/anthropic/_utils/_transform.py:
⋮
│class PropertyInfo:
⋮

anthropic_projects/anthropic-sdk-python/src/anthropic/_utils/_typing.py:
⋮
│def is_annotated_type(typ: type) -> bool:
⋮
│@lru_cache(maxsize=8096)
│def strip_annotated_type(typ: type) -> type:
⋮
│def extract_type_arg(typ: type, index: int) -> type:
⋮

anthropic_projects/anthropic-sdk-python/src/anthropic/_utils/_utils.py:
⋮
│def is_given(obj: NotGivenOr[_T]) -> TypeGuard[_T]:
⋮
│def is_mapping(obj: object) -> TypeGuard[Mapping[str, object]]:
⋮
│def is_mapping_t(obj: _MappingT | object) -> TypeGuard[_MappingT]:
⋮
│def is_iterable(obj: object) -> TypeGuard[Iterable[object]]:
⋮
│def deepcopy_minimal(item: _T) -> _T:
⋮
│def human_join(seq: Sequence[str], *, delim: str = ", ", final: str = "or") -> str:
⋮
│def coerce_integer(val: str) -> int:
⋮
│def coerce_float(val: str) -> float:
⋮
│def coerce_boolean(val: str) -> bool:
⋮
│def lru_cache(*, maxsize: int | None = 128) -> Callable[[CallableT], CallableT]:
⋮
│def json_safe(data: object) -> object:
⋮

anthropic_projects/anthropic-sdk-python/src/anthropic/types/beta/beta_cache_control_ephemeral_param.
⋮
│class BetaCacheControlEphemeralParam(TypedDict, total=False):
⋮

anthropic_projects/anthropic-sdk-python/src/anthropic/types/cache_control_ephemeral_param.py:
⋮
│class CacheControlEphemeralParam(TypedDict, total=False):
⋮

anthropic_projects/claude-code-action/src/create-prompt/types.ts:
⋮
│export type EventData =
│  | PullRequestReviewCommentEvent
│  | PullRequestReviewEvent
│  | PullRequestCommentEvent
│  | IssueCommentEvent
│  | IssueOpenedEvent
│  | IssueAssignedEvent
│  | IssueLabeledEvent
⋮

anthropic_projects/claude-code-action/src/entrypoints/format-turns.ts:
⋮
│export interface ToolResult {
│  type: string;
│  tool_use_id?: string;
│  content?: any;
│  is_error?: boolean;
⋮

anthropic_projects/claude-code-action/src/github/api/client.ts:
⋮
│export type Octokits = {
│  rest: Octokit;
│  graphql: typeof graphql;
⋮

anthropic_projects/redis-py/doctests/search_vss.py:
⋮
│URL = ("https://raw.githubusercontent.com/bsbodden/redis_vss_getting_started"
⋮

anthropic_projects/redis-py/redis/_parsers/encoders.py:
⋮
│class Encoder:
│    "Encode strings to bytes-like and decode bytes-like to strings"
│
⋮
│    def decode(self, value, force=False):
⋮

anthropic_projects/redis-py/redis/asyncio/lock.py:
⋮
│class Lock:
│    """
│    A shared, distributed Lock. Using Redis for locking allows the Lock
│    to be shared across processes and/or machines.
│
│    It's left to the user to resolve deadlock issues and make sure
│    multiple clients play nicely together.
⋮
│    def extend(
│        self, additional_time: Number, replace_ttl: bool = False
⋮

anthropic_projects/redis-py/redis/cache.py:
⋮
│class CacheEntry:
⋮
│class EvictionPolicyInterface(ABC):
│    @property
│    @abstractmethod
│    def cache(self):
⋮
│    @abstractmethod
│    def evict_next(self) -> CacheKey:
⋮
│class CacheConfigurationInterface(ABC):
│    @abstractmethod
│    def get_cache_class(self):
⋮
│    @abstractmethod
│    def get_eviction_policy(self):
⋮
│    @abstractmethod
│    def is_exceeds_max_size(self, count: int) -> bool:
⋮
│    @abstractmethod
│    def is_allowed_to_cache(self, command: str) -> bool:
⋮
│class CacheInterface(ABC):
│    @property
│    @abstractmethod
│    def collection(self) -> OrderedDict:
⋮
│    @abstractmethod
│    def set(self, entry: CacheEntry) -> bool:
⋮
│    @abstractmethod
│    def is_cachable(self, key: CacheKey) -> bool:
⋮
│class DefaultCache(CacheInterface):
│    def __init__(
│        self,
│        cache_config: CacheConfigurationInterface,
⋮
│    def set(self, entry: CacheEntry) -> bool:
⋮
│    def is_cachable(self, key: CacheKey) -> bool:
⋮
│class LRUPolicy(EvictionPolicyInterface):
│    def __init__(self):
⋮
│    def evict_next(self) -> CacheKey:
⋮
│class CacheConfig(CacheConfigurationInterface):
│    DEFAULT_CACHE_CLASS = DefaultCache
⋮
│    def get_cache_class(self):
⋮
│    def get_eviction_policy(self) -> EvictionPolicy:
⋮
│    def is_exceeds_max_size(self, count: int) -> bool:
⋮
│    def is_allowed_to_cache(self, command: str) -> bool:
⋮

anthropic_projects/redis-py/redis/commands/core.py:
⋮
│class BitFieldOperation:
│    """
│    Command builder for BITFIELD commands.
⋮
│    def set(self, fmt: str, offset: BitfieldOffsetT, value: int):
⋮
│class BasicKeyCommands(CommandsProtocol):
│    """
│    Redis basic key-based commands
⋮
│    def set(
│        self,
│        name: KeyT,
│        value: EncodableT,
│        ex: Optional[ExpiryT] = None,
│        px: Optional[ExpiryT] = None,
│        nx: bool = False,
│        xx: bool = False,
│        keepttl: bool = False,
│        get: bool = False,
⋮

anthropic_projects/redis-py/redis/commands/helpers.py:
⋮
│def list_or_args(keys: KeysT, args: Tuple[KeyT, ...]) -> List[KeyT]:
⋮
│def parse_list_to_dict(response):
⋮

anthropic_projects/redis-py/redis/commands/json/commands.py:
⋮
│class JSONCommands:
│    """json commands."""
│
⋮
│    def set(
│        self,
│        name: str,
│        path: str,
│        obj: JsonType,
│        nx: Optional[bool] = False,
│        xx: Optional[bool] = False,
│        decode_keys: Optional[bool] = False,
⋮

anthropic_projects/redis-py/redis/commands/json/path.py:
│class Path:
│    """This class represents a path in a JSON value."""
│
⋮
│    @staticmethod
│    def root_path():
⋮

anthropic_projects/redis-py/redis/commands/search/_util.py:
│def to_string(s, encoding: str = "utf-8"):
⋮

anthropic_projects/redis-py/redis/commands/search/field.py:
⋮
│class Field:
│    """
│    A class representing a field in a document.
⋮
│    def append_arg(self, value):
⋮

anthropic_projects/redis-py/redis/commands/search/query.py:
⋮
│class Query:
│    """
│    Query is used to build complex queries that have more parameters than just
│    the query string. The query string is set in the constructor, and other
│    options have setter functions.
│
│    The setter functions return the query object, so they can be chained,
│    i.e. `Query("foo").verbatim().filter(...)` etc.
⋮
│    def get_args(self) -> List[str]:
⋮

anthropic_projects/redis-py/redis/commands/search/querystring.py:
⋮
│class Value:
│    @property
│    def combinable(self):
│        """
│        Whether this type of value may be combined with other values
│        for the same field. This makes the filter potentially more efficient
│        """
⋮
│    def to_string(self):
⋮
│class RangeValue(Value):
│    combinable = False
│
⋮
│    def to_string(self):
⋮
│class ScalarValue(Value):
│    combinable = True
│
⋮
│    def to_string(self):
⋮
│class TagValue(Value):
│    combinable = False
│
⋮
│    def to_string(self):
⋮
│class GeoValue(Value):
│    def __init__(self, lon, lat, radius, unit="km"):
│        self.lon = lon
│        self.lat = lat
│        self.radius = radius
⋮
│    def to_string(self):
⋮
│class Node:
│    def __init__(self, *children, **kwparams):
│        """
│        Create a node
│
│        ### Parameters
│
│        - **children**: One or more sub-conditions. These can be additional
│            `intersect`, `disjunct`, `union`, `optional`, or any other `Node`
│            type.
│
⋮
│    def to_string(self, with_parens=None):
⋮
│class BaseNode(Node):
│    def __init__(self, s):
│        super().__init__()
⋮
│    def to_string(self, with_parens=None):
⋮
│class DisjunctNode(IntersectNode):
│    """
│    Create a disjunct node. In order for this node to be true, all of its
│    children must evaluate to false
⋮
│    def to_string(self, with_parens=None):
⋮
│class OptionalNode(IntersectNode):
│    """
│    Create an optional node. If this nodes evaluates to true, then the document
│    will be rated higher in score/rank.
⋮
│    def to_string(self, with_parens=None):
⋮

anthropic_projects/redis-py/redis/commands/timeseries/commands.py:
⋮
│class TimeSeriesCommands:
│    """RedisTimeSeries Commands."""
│
⋮
│    def range(
│        self,
│        key: KeyT,
│        from_time: Union[int, str],
│        to_time: Union[int, str],
│        count: Optional[int] = None,
│        aggregation_type: Optional[str] = None,
│        bucket_size_msec: Optional[int] = 0,
│        filter_by_ts: Optional[List[int]] = None,
│        filter_by_min_value: Optional[int] = None,
⋮

anthropic_projects/redis-py/redis/crc.py:
⋮
│REDIS_CLUSTER_HASH_SLOTS = 16384
│
⋮

anthropic_projects/redis-py/redis/exceptions.py:
⋮
│class DataError(RedisError):
⋮
│class NoScriptError(ResponseError):
⋮
│class ExecAbortError(ResponseError):
⋮
│class NoPermissionError(ResponseError):
⋮
│class ModuleError(ResponseError):
⋮
│class TryAgainError(ResponseError):
⋮
│class ClusterCrossSlotError(ResponseError):
⋮
│class MasterDownError(ClusterDownError):
⋮

anthropic_projects/redis-py/redis/lock.py:
⋮
│class Lock:
│    """
│    A shared, distributed Lock. Using Redis for locking allows the Lock
│    to be shared across processes and/or machines.
│
│    It's left to the user to resolve deadlock issues and make sure
│    multiple clients play nicely together.
⋮
│    def extend(self, additional_time: Number, replace_ttl: bool = False) -> bool:
⋮

anthropic_projects/redis-py/redis/utils.py:
⋮
│def str_if_bytes(value: Union[str, bytes]) -> str:
⋮

anthropic_projects/redis-py/tests/test_asyncio/compat.py:
⋮
│def create_task(coroutine):
⋮

modelcontextprotocol_projects/inspector/client/src/components/JsonView.tsx:
⋮
│interface JsonViewProps {
│  data: unknown;
│  name?: string;
│  initialExpandDepth?: number;
│  className?: string;
│  withCopyButton?: boolean;
│  isError?: boolean;
⋮

modelcontextprotocol_projects/inspector/client/src/lib/configurationTypes.ts:
│export type ConfigItem = {
⋮

modelcontextprotocol_projects/inspector/client/src/utils/jsonUtils.ts:
│export type JsonValue =
⋮

modelcontextprotocol_projects/python-sdk/src/mcp/server/fastmcp/utilities/logging.py:
⋮
│def get_logger(name: str) -> logging.Logger:
⋮

modelcontextprotocol_projects/python-sdk/src/mcp/shared/auth.py:
⋮
│class InvalidRedirectUriError(Exception):
⋮

modelcontextprotocol_projects/python-sdk/src/mcp/types.py:
⋮
│class JSONRPCMessage(RootModel[JSONRPCRequest | JSONRPCNotification | JSONRPCResponse | JSONRPCErro
⋮

modelcontextprotocol_projects/typescript-sdk/src/server/auth/types.ts:
⋮
│export interface AuthInfo {
│  /**
│   * The access token.
│   */
│  token: string;
│
│  /**
│   * The client ID associated with this token.
│   */
│  clientId: string;
│
⋮

modelcontextprotocol_projects/typescript-sdk/src/server/completable.ts:
⋮
│export class Completable<T extends ZodTypeAny> extends ZodType<
│  T["_output"],
│  CompletableDef<T>,
│  T["_input"]
│> {
⋮
│  unwrap() {
│    return this._def.type;
⋮

modelcontextprotocol_projects/typescript-sdk/src/shared/auth.ts:
⋮
│export type OAuthErrorResponse = z.infer<typeof OAuthErrorResponseSchema>;
⋮

modelcontextprotocol_projects/typescript-sdk/src/shared/uriTemplate.ts:
⋮
│export type Variables = Record<string, string | string[]>;
│
⋮

modelcontextprotocol_projects/typescript-sdk/src/types.ts:
⋮
│export type IsomorphicHeaders = Record<string, string | string[] | undefined>;
│
⋮
│export interface RequestInfo {
│  /**
│   * The headers of the request.
│   */
│  headers: IsomorphicHeaders;
⋮
│export type JSONRPCMessage = Infer<typeof JSONRPCMessageSchema>;
│
⋮

openai_projects/RD-Agent-microsoft/rdagent/scenarios/data_science/example/eval/arf-12-hour-predictio
⋮
│class InvalidSubmissionError(Exception):
⋮

openai_projects/RD-Agent-microsoft/rdagent/utils/agent/apply_patch.py:
⋮
│class DiffError(ValueError):
⋮
│@dataclass
│class Parser:
│    current_files: dict[str, str]
⋮
│    def startswith(self, prefix: str | tuple[str, ...]) -> bool:
⋮

openai_projects/codex/.github/actions/codex/src/env-context.ts:
⋮
│export interface EnvContext {
│  /**
│   * Return the value for a given environment variable or terminate the action
│   * via `fail` if it is missing / empty.
│   */
│  get(name: string): string;
│
│  /**
│   * Attempt to read an environment variable. Returns the value when present;
│   * otherwise returns undefined (does not call `fail`).
⋮

openai_projects/codex/codex-cli/src/components/select-input/select-input.tsx:
⋮
│function SelectInput<V>({
│  items = [],
│  isFocused = true,
│  initialIndex = 0,
│  indicatorComponent = Indicator,
│  itemComponent = ItemComponent,
│  limit: customLimit,
│  onSelect,
│  onHighlight,
⋮

openai_projects/codex/codex-cli/src/text-buffer.ts:
⋮
│export type Direction =
│  | "left"
│  | "right"
│  | "up"
│  | "down"
│  | "wordLeft"
│  | "wordRight"
│  | "home"
⋮
│export interface Viewport {
│  height: number;
│  width: number;
⋮

openai_projects/codex/codex-cli/src/typings.d.ts:
⋮
│declare module "shell-quote" {
│  /**
│   * Very small subset of the return tokens produced by `shell‑quote` that are
│   * relevant for our inspection of shell operators. A token can either be a
│   * simple string (command/argument) or an operator object such as
│   * `{ op: "&&" }`.
│   */
│  export type Token = string | { op: string };
│
│  // Historically the original `shell-quote` library exports several internal
⋮
│  export type ControlOperator = "&&" | "||" | "|" | ";" | string;
│
⋮

openai_projects/codex/codex-cli/src/utils/agent/agent-loop.ts:
⋮
│export class AgentLoop {
│  private model: string;
│  private provider: string;
│  private instructions?: string;
│  private approvalPolicy: ApprovalPolicy;
│  private config: AppConfig;
│  private additionalWritableRoots: ReadonlyArray<string>;
│  /** Whether we ask the API to persist conversation state on the server */
│  private readonly disableResponseStorage: boolean;
│
⋮

openai_projects/codex/codex-cli/src/utils/agent/apply-patch.ts:
⋮
│class Parser {
│  current_files: Record<string, string>;
│  lines: Array<string>;
│  index = 0;
│  patch: Patch = { actions: {} };
│  fuzz = 0;
│
│  constructor(currentFiles: Record<string, string>, lines: Array<string>) {
│    this.current_files = currentFiles;
│    this.lines = lines;
⋮
│  private startswith(prefix: string | Array<string>): boolean {
│    const prefixes = Array.isArray(prefix) ? prefix : [prefix];
│    return prefixes.some((p) => this.lines[this.index]!.startsWith(p));
⋮

openai_projects/codex/codex-cli/src/utils/auto-approval-mode.ts:
│export enum AutoApprovalMode {
⋮
│export enum FullAutoErrorMode {
│  ASK_USER = "ask-user",
│  IGNORE_AND_CONTINUE = "ignore-and-continue",
⋮

openai_projects/codex/codex-cli/src/utils/config.ts:
⋮
│export type AppConfig = {
│  apiKey?: string;
│  model: string;
│  provider?: string;
│  instructions: string;
│  approvalMode?: AutoApprovalMode;
│  fullAutoErrorMode?: FullAutoErrorMode;
│  memory?: MemoryConfig;
│  reasoningEffort?: ReasoningEffort;
│  /** Whether to enable desktop notifications for responses */
⋮

openai_projects/codex/codex-cli/src/utils/logger/log.ts:
⋮
│class AsyncLogger implements Logger {
│  private queue: Array<string> = [];
│  private isWriting: boolean = false;
│
│  constructor(private filePath: string) {
│    this.filePath = filePath;
│  }
│
│  isLoggingEnabled(): boolean {
│    return true;
⋮
│class EmptyLogger implements Logger {
│  isLoggingEnabled(): boolean {
│    return false;
│  }
│
│  log(_message: string): void {
│    // No-op
│  }
⋮

openai_projects/codex/codex-cli/src/utils/singlepass/context_files.ts:
⋮
│interface CacheEntry {
│  /** Last modification time of the file (epoch ms). */
│  mtime: number;
│  /** Size of the file in bytes. */
│  size: number;
│  /** Entire file content. */
│  content: string;
⋮
│class LRUFileCache {
│  private maxSize: number;
│  private cache: Map<string, CacheEntry>;
│
│  constructor(maxSize: number) {
│    this.maxSize = maxSize;
│    this.cache = new Map();
│  }
│
│  /**
⋮
│  set(key: string, entry: CacheEntry): void {
│    // if key already in map, delete it so that insertion below sets recency.
│    if (this.cache.has(key)) {
│      this.cache.delete(key);
│    }
│    this.cache.set(key, entry);
│
│    // If over capacity, evict the least recently used entry.
│    if (this.cache.size > this.maxSize) {
│      const firstKey = this.cache.keys().next();
⋮

openai_projects/codex/codex-cli/tests/ui-test-helpers.tsx:
⋮
│export function renderTui(ui: React.ReactElement): any {
│  const utils = render(ui);
│
│  const lastFrameStripped = () => stripAnsi(utils.lastFrame() || "");
│
│  // A tiny helper that waits for Ink's internal promises / timers to settle
│  // so the next `lastFrame()` call reflects the latest UI state.
│  const flush = async () =>
│    new Promise<void>((resolve) => setTimeout(resolve, 0));
│
⋮

openai_projects/codex/codex-rs/core/src/config_types.rs:
⋮
│pub enum UriBasedFileOpener {
│    #[serde(rename = "vscode")]
│    VsCode,
│
│    #[serde(rename = "vscode-insiders")]
│    VsCodeInsiders,
│
│    #[serde(rename = "windsurf")]
│    Windsurf,
│
⋮

openai_projects/codex/codex-rs/execpolicy/src/arg_matcher.rs:
⋮
│impl<'v> UnpackValue<'v> for ArgMatcher {
│    type Error = starlark::Error;
│
│    fn unpack_value_impl(value: Value<'v>) -> starlark::Result<Option<Self>> {
│        if let Some(str) = value.downcast_ref::<StarlarkStr>() {
│            Ok(Some(ArgMatcher::Literal(str.as_str().to_string())))
│        } else {
│            Ok(value.downcast_ref::<ArgMatcher>().cloned())
│        }
│    }
⋮

openai_projects/codex/codex-rs/execpolicy/src/error.rs:
⋮
│pub enum Error {
│    NoSpecForProgram {
│        program: String,
│    },
│    OptionMissingValue {
│        program: String,
│        option: String,
│    },
│    OptionFollowedByOptionInsteadOfValue {
│        program: String,
⋮

openai_projects/codex/codex-rs/execpolicy/src/opt.rs:
⋮
│pub struct Opt {
│    /// The option as typed on the command line, e.g., `-h` or `--help`. If
│    /// it can be used in the `--name=value` format, then this should be
│    /// `--name` (though this is subject to change).
│    pub opt: String,
│    pub meta: OptMeta,
│    pub required: bool,
⋮
│impl<'v> UnpackValue<'v> for Opt {
│    type Error = starlark::Error;
│
│    fn unpack_value_impl(value: Value<'v>) -> starlark::Result<Option<Self>> {
│        // TODO(mbolin): It fels like this should be doable without cloning?
│        // Cannot simply consume the value?
│        Ok(value.downcast_ref::<Opt>().cloned())
│    }
⋮

openai_projects/codex/codex-rs/mcp-types/src/lib.rs:
⋮
│/// Paired request/response types for the Model Context Protocol (MCP).
│pub trait ModelContextProtocolRequest {
│    const METHOD: &'static str;
│    type Params: DeserializeOwned + Serialize + Send + Sync + 'static;
│    type Result: DeserializeOwned + Serialize + Send + Sync + 'static;
⋮
│/// One-way message in the Model Context Protocol (MCP).
│pub trait ModelContextProtocolNotification {
│    const METHOD: &'static str;
│    type Params: DeserializeOwned + Serialize + Send + Sync + 'static;
⋮
│pub enum JSONRPCMessage {
│    Request(JSONRPCRequest),
│    Notification(JSONRPCNotification),
│    BatchRequest(JSONRPCBatchRequest),
│    Response(JSONRPCResponse),
│    Error(JSONRPCError),
│    BatchResponse(JSONRPCBatchResponse),
⋮
│impl TryFrom<JSONRPCRequest> for ClientRequest {
│    type Error = serde_json::Error;
│    fn try_from(req: JSONRPCRequest) -> std::result::Result<Self, Self::Error> {
│        match req.method.as_str() {
│            "initialize" => {
│                let params_json = req.params.unwrap_or(serde_json::Value::Null);
│                let params: <InitializeRequest as ModelContextProtocolRequest>::Params =
│                    serde_json::from_value(params_json)?;
│                Ok(ClientRequest::InitializeRequest(params))
│            }
⋮
│impl TryFrom<JSONRPCNotification> for ServerNotification {
│    type Error = serde_json::Error;
│    fn try_from(n: JSONRPCNotification) -> std::result::Result<Self, Self::Error> {
│        match n.method.as_str() {
│            "notifications/cancelled" => {
│                let params_json = n.params.unwrap_or(serde_json::Value::Null);
│                let params: <CancelledNotification as ModelContextProtocolNotification>::Params =
│                    serde_json::from_value(params_json)?;
│                Ok(ServerNotification::CancelledNotification(params))
│            }
⋮

openai_projects/mle-bench/mlebench/competitions/smartphone-decimeter-2022/notebook.py:
⋮
│@dataclass
│class ECEF:
│    x: np.array
⋮
│    def to_numpy(self):
⋮

openai_projects/mle-bench/mlebench/grade_helpers.py:
⋮
│class Grader:
│    def __init__(self, name: str, grade_fn: str) -> None:
│        self.name = name
│        self.grade_fn = import_fn(grade_fn)
│        assert isinstance(self.name, str), "Grader name must be a string."
⋮
│    def rank_score(self, score: Optional[float], leaderboard: pd.DataFrame) -> dict:
│        """
│        Ranks a score based on the leaderboard.
│        Returns a dictionary of bools with the following keys:
│        - gold_medal: bool
│        - silver_medal: bool
│        - bronze_medal: bool
│        - above_median: bool
│        - gold_threshold: float
│        - silver_threshold: float
│        - bronze_threshold: float
⋮
│        def get_score_at_position(position: int) -> float:
⋮
│class InvalidSubmissionError(Exception):
⋮

openai_projects/mle-bench/mlebench/utils.py:
⋮
│def get_runs_dir() -> Path:
⋮
│def get_module_dir() -> Path:
⋮
│def get_logger(name: str, level: int = logging.INFO, filename: Optional[Path] = None) -> Logger:
⋮
│def read_csv(*args, **kwargs) -> DataFrame:
⋮

openai_projects/openai-agents-python/examples/basic/remote_image.py:
⋮
│URL = "https://upload.wikimedia.org/wikipedia/commons/0/0c/GoldenGateBridge-001.jpg"
│
⋮

openai_projects/openai-agents-python/src/agents/exceptions.py:
⋮
│class UserError(AgentsException):
⋮

openai_projects/openai-agents-python/src/agents/result.py:
⋮
│@dataclass
│class RunResultStreaming(RunResultBase):
│    """The result of an agent run in streaming mode. You can use the `stream_events` method to
│    receive semantic events as they are generated.
│
│    The streaming method will raise:
│    - A MaxTurnsExceeded exception if the agent exceeds the max_turns limit.
│    - A GuardrailTripwireTriggered exception if a guardrail is tripped.
⋮
│    async def stream_events(self) -> AsyncIterator[StreamEvent]:
⋮

openai_projects/openai-agents-python/src/agents/run.py:
⋮
│class Runner:
│    @classmethod
│    async def run(
│        cls,
│        starting_agent: Agent[TContext],
│        input: str | list[TResponseInputItem],
│        *,
│        context: TContext | None = None,
│        max_turns: int = DEFAULT_MAX_TURNS,
│        hooks: RunHooks[TContext] | None = None,
│        run_config: RunConfig | None = None,
⋮
│    @classmethod
│    def run_streamed(
│        cls,
│        starting_agent: Agent[TContext],
│        input: str | list[TResponseInputItem],
│        context: TContext | None = None,
│        max_turns: int = DEFAULT_MAX_TURNS,
│        hooks: RunHooks[TContext] | None = None,
│        run_config: RunConfig | None = None,
│        previous_response_id: str | None = None,
│        session: Session | None = None,
⋮
│class AgentRunner:
│    """
│    WARNING: this class is experimental and not part of the public API
│    It should not be used directly or subclassed.
⋮
│    def run_streamed(
│        self,
│        starting_agent: Agent[TContext],
│        input: str | list[TResponseInputItem],
│        **kwargs: Unpack[RunOptions[TContext]],
⋮

openai_projects/openai-agents-python/src/agents/run_context.py:
⋮
│TContext = TypeVar("TContext", default=Any)
│
⋮

openai_projects/openai-agents-python/src/agents/tracing/setup.py:
⋮
│GLOBAL_TRACE_PROVIDER: TraceProvider | None = None
│
⋮

openai_projects/openai-agents-python/src/agents/tracing/span_data.py:
⋮
│class SpanData(abc.ABC):
⋮

openai_projects/openai-agents-python/src/agents/voice/pipeline.py:
⋮
│class VoicePipeline:
│    """An opinionated voice agent pipeline. It works in three steps:
│    1. Transcribe audio input into text.
│    2. Run the provided `workflow`, which produces a sequence of text responses.
│    3. Convert the text responses into streaming audio output.
⋮
│    async def _run_single_turn(self, audio_input: AudioInput) -> StreamedAudioResult:
⋮
│        with TraceCtxManager(
│            workflow_name=self.config.workflow_name or "Voice Agent",
│            trace_id=None,  # Automatically generated
│            group_id=self.config.group_id,
│            metadata=self.config.trace_metadata,
│            disabled=self.config.tracing_disabled,
│        ):
│            input_text = await self._process_audio_input(audio_input)
│
⋮
│            async def stream_events():
⋮

openai_projects/openai-agents-python/src/agents/voice/utils.py:
⋮
│def get_sentence_based_splitter(
│    min_sentence_length: int = 20,
│) -> Callable[[str], tuple[str, str]]:
│    """Returns a function that splits text into chunks based on sentence boundaries.
│
│    Args:
│        min_sentence_length: The minimum length of a sentence to be included in a chunk.
│
│    Returns:
│        A function that splits text into chunks based on sentence boundaries.
⋮
│    def sentence_based_text_splitter(text_buffer: str) -> tuple[str, str]:
⋮

openai_projects/openai-agents-python/tests/fastapi/streaming_app.py:
⋮
│class StreamHandler:
│    def __init__(self, result: RunResultStreaming):
⋮
│    async def stream_events(self) -> AsyncIterator[str]:
⋮

openai_projects/openai-cookbook/examples/object_oriented_agentic_approach/resources/object_oriented_
⋮
│class ChatMessages:
│    """
│    Stores all messages in a conversation (developer, user, assistant).
⋮
│    def add_developer_message(self, content: str) -> None:
⋮

openai_projects/openai-cookbook/examples/object_oriented_agentic_approach/resources/object_oriented_
⋮
│def get_logger(name: str, level: int = logging.INFO, formatter: Optional[logging.Formatter] = None)
⋮

openai_projects/openai-cookbook/examples/object_oriented_agentic_approach/resources/registry/tools/p
⋮
│class PythonExecTool(ToolInterface):
│    """
│    A Tool that executes Python code securely in a container.
⋮
│    @staticmethod
│    def _run_code_in_container(code: str, container_name: str = "sandbox") -> Tuple[str, str]:
⋮

openai_projects/openai-cookbook/examples/voice_solutions/one_way_translation_using_realtime_api/src/
⋮
│export type WavPackerAudioType = {
│    blob: Blob;
│    url: string;
│    channelCount: number;
│    sampleRate: number;
│    duration: number;
⋮

openai_projects/openai-cookbook/examples/voice_solutions/one_way_translation_using_realtime_api/src/
⋮
│export class WavRecorder {
│    /**
│     * Decodes audio data from multiple formats to a Blob, url, Float32Array and AudioBuffer
│     * @param {Blob|Float32Array|Int16Array|ArrayBuffer|number[]} audioData
│     * @param {number} sampleRate
│     * @param {number} fromSampleRate
│     * @returns {Promise<DecodedAudioType>}
│     */
│    static decode(audioData: Blob | Float32Array | Int16Array | ArrayBuffer | number[], sampleRate?
│    /**
⋮
│    constructor({ sampleRate, outputToSpeakers, debug, }?: {
│        sampleRate?: number;
│        outputToSpeakers?: boolean;
│        debug?: boolean;
⋮
│    getSampleRate(): number;
⋮
│    getStatus(): "ended" | "paused" | "recording";
⋮
│    begin(deviceId?: string): Promise<true>;
⋮
│    pause(): Promise<true>;
⋮
│export type DecodedAudioType = {
│    blob: Blob;
│    url: string;
│    values: Float32Array;
│    audioBuffer: AudioBuffer;
⋮

openai_projects/openai-cookbook/examples/voice_solutions/one_way_translation_using_realtime_api/src/
⋮
│export class WavRecorder {
│  /**
│   * Create a new WavRecorder instance
│   * @param {{sampleRate?: number, outputToSpeakers?: boolean, debug?: boolean}} [options]
│   * @returns {WavRecorder}
│   */
│  constructor({
│    sampleRate = 44100,
│    outputToSpeakers = false,
│    debug = false,
⋮
│  static async decode(audioData, sampleRate = 44100, fromSampleRate = -1) {
│    const context = new AudioContext({ sampleRate });
│    let arrayBuffer;
│    let blob;
│    if (audioData instanceof Blob) {
│      if (fromSampleRate !== -1) {
│        throw new Error(
│          `Can not specify "fromSampleRate" when reading from Blob`,
│        );
│      }
