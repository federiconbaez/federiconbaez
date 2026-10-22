# Federico Nicolás Báez Rizzo

**ES:** Ingeniero de sistemas. Rust y C++ sobre Linux: concurrencia lock-free, allocators, io_uring, eBPF/XDP, seccomp e IPC. Cada repo publica sus números y la máquina donde se midieron; los de Cortex-9 enlazan a su auditoría, pase o no.

**EN:** Systems engineer. Rust and C++ on Linux: lock-free concurrency, allocators, io_uring, eBPF/XDP, seccomp and IPC. Every repo publishes its numbers and the machine they were measured on; the Cortex-9 ones link to their audit, pass or fail.

[federicobaez.com](https://federicobaez.com) · [X @Cortex9Sur](https://x.com/Cortex9Sur) · [LinkedIn](https://www.linkedin.com/in/f-baez)

<!-- repo-forge:start -->
## Bajo nivel / Low-level systems

Rust y C++ con loom, Miri y sanitizers en CI. / Rust and C++ with loom, Miri and sanitizers in CI.

| Repo | Lenguaje / Language | Descripción / Description | CI |
|---|---|---|---|
| [lockfree-mpmc](https://github.com/federiconbaez/lockfree-mpmc) | Rust | Bounded lock-free MPMC queue (Vyukov); loom + Miri; Criterion vs crossbeam/std. | [![CI](https://github.com/federiconbaez/lockfree-mpmc/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/lockfree-mpmc/actions/workflows/ci.yml) |
| [arena-slab-cpp](https://github.com/federiconbaez/arena-slab-cpp) | C++ | C++20 arena + slab allocators with ASan/TSan/fuzz and honest benches vs malloc/jemalloc. | [![CI](https://github.com/federiconbaez/arena-slab-cpp/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/arena-slab-cpp/actions/workflows/ci.yml) |
| [uring-http](https://github.com/federiconbaez/uring-http) | Rust | Minimal HTTP/1.1 server in Rust on raw io_uring, no async runtime. Tested with Miri and ASan. | [![CI](https://github.com/federiconbaez/uring-http/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/uring-http/actions/workflows/ci.yml) |

## Cortex-9

Cada fila enlaza al estado de su auditoría o verificación; "no auditado" significa exactamente eso. / Each row links to its audit or verification status; "not audited" means exactly that.

| Repo | Lenguaje / Language | Descripción / Description | CI | Estado / Status |
|---|---|---|---|---|
| [cortex9-shm-ring-bus](https://github.com/federiconbaez/cortex9-shm-ring-bus) | Rust | Lock-free SPSC ring over /dev/shm (Rust) with C/C++/Go/Python clients. | [![CI](https://github.com/federiconbaez/cortex9-shm-ring-bus/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/cortex9-shm-ring-bus/actions/workflows/ci.yml) | No auditado de forma independiente / Not independently audited — [BENCH.md](https://github.com/federiconbaez/cortex9-shm-ring-bus/blob/HEAD/BENCH.md) |
| [cortex9-memoria-unificada](https://github.com/federiconbaez/cortex9-memoria-unificada) | C++ | C++20 tiered GPU/RAM/disk memory manager. | — | Auditado: pasa el umbral #5 (B+) / Audited: passes threshold #5 (B+) — [AUDIT-valor.md](https://github.com/federiconbaez/cortex9-memoria-unificada/blob/HEAD/AUDIT-valor.md) |
| [cortex9-elf-zk-loader](https://github.com/federiconbaez/cortex9-elf-zk-loader) | Rust | Signed-only ELF loader + seccomp supervisor (Rust). | — | Auditado **FAIL**: 122/143 (85.3 %) vs 100 %; v0.3 no auditado / Audited **FAIL**; v0.3 not audited — [AUDIT-valor.md](https://github.com/federiconbaez/cortex9-elf-zk-loader/blob/HEAD/AUDIT-valor.md) |
| [cortex9-xdp-semantic-firewall](https://github.com/federiconbaez/cortex9-xdp-semantic-firewall) | Python | XDP semantic firewall for MCP/gRPC payloads (eBPF + Rust/aya). | — | Auditado: **no** alcanza su umbral de valor / Audited: **fails** its value threshold — [AUDIT-valor.md](https://github.com/federiconbaez/cortex9-xdp-semantic-firewall/blob/HEAD/AUDIT-valor.md) |
| [cortex9-jitter-exfil](https://github.com/federiconbaez/cortex9-jitter-exfil) | Rust | Timing-jitter covert-channel detector on SSL writes (Rust). | [![CI](https://github.com/federiconbaez/cortex9-jitter-exfil/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/cortex9-jitter-exfil/actions/workflows/ci.yml) | Valor no auditado / Value not audited — [VALOR.md](https://github.com/federiconbaez/cortex9-jitter-exfil/blob/HEAD/VALOR.md) |
| [cortex9-sched-entropia](https://github.com/federiconbaez/cortex9-sched-entropia) | Rust | sched_ext (eBPF + Rust) scheduler weighting threads by prompt entropy. | [![CI](https://github.com/federiconbaez/cortex9-sched-entropia/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/cortex9-sched-entropia/actions/workflows/ci.yml) | Valor no auditado / Value not audited — [LIMITES.md](https://github.com/federiconbaez/cortex9-sched-entropia/blob/HEAD/LIMITES.md) |
| [cortex9-snapshots-enjambre](https://github.com/federiconbaez/cortex9-snapshots-enjambre) | Rust | Memory snapshot/restore for a swarm of agent processes (Rust). | [![CI](https://github.com/federiconbaez/cortex9-snapshots-enjambre/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/cortex9-snapshots-enjambre/actions/workflows/ci.yml) | Auditado: **no** alcanza su umbral en general / Audited: **fails** its threshold overall — [AUDIT-valor.md](https://github.com/federiconbaez/cortex9-snapshots-enjambre/blob/HEAD/AUDIT-valor.md) |
| [cortex9-fwm-x11-rust](https://github.com/federiconbaez/cortex9-fwm-x11-rust) | Rust | X11 window manager grouping windows by title/class/OCR affinity (Rust). | [![CI](https://github.com/federiconbaez/cortex9-fwm-x11-rust/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/cortex9-fwm-x11-rust/actions/workflows/ci.yml) | Valor no auditado / Value not audited |
| [cortex9-termica-predictiva](https://github.com/federiconbaez/cortex9-termica-predictiva) | C | C daemon predicting CPU temperature to cap frequency before heavy tasks. | — | Control de hardware no verificado / Hardware control not verified — [VERIFICACION.md](https://github.com/federiconbaez/cortex9-termica-predictiva/blob/HEAD/VERIFICACION.md) |
| [cortex9-poincare-fs](https://github.com/federiconbaez/cortex9-poincare-fs) | Rust | Read-only FUSE filesystem with Poincaré-ball embeddings (Rust). | [![CI](https://github.com/federiconbaez/cortex9-poincare-fs/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/cortex9-poincare-fs/actions/workflows/ci.yml) | Auditado: valor no demostrado / Audited: value not demonstrated — [AUDIT.md](https://github.com/federiconbaez/cortex9-poincare-fs/blob/HEAD/AUDIT.md) |

## Familia MCP / MCP family

Servidores MCP escritos desde cero (Python stdlib y Rust), validados entre sí por mcp-crosscheck. / MCP servers written from scratch (Python stdlib and Rust), cross-validated by mcp-crosscheck.

| Repo | Lenguaje / Language | Descripción / Description | CI |
|---|---|---|---|
| [mcp-server-rs](https://github.com/federiconbaez/mcp-server-rs) | Rust | Servidor MCP en Rust sin SDK oficial: JSON-RPC 2.0, stdio y Streamable HTTP, herramienta de ejemplo en sandbox seccomp (Linux). | [![CI](https://github.com/federiconbaez/mcp-server-rs/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/mcp-server-rs/actions/workflows/ci.yml) |
| [mcp-base](https://github.com/federiconbaez/mcp-base) | Python | Minimal MCP server from scratch in Python stdlib: JSON-RPC 2.0, stdio/HTTP, HS256 bearer auth, SQLite memory, hash-chained audit log. | [![CI](https://github.com/federiconbaez/mcp-base/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/mcp-base/actions/workflows/ci.yml) |
| [mcp-auth-hardened](https://github.com/federiconbaez/mcp-auth-hardened) | Python | MCP server with hardened (simplified) auth in Python stdlib: scopes, refresh rotation, revocation, kid rotation, hand-written RS256. | [![CI](https://github.com/federiconbaez/mcp-auth-hardened/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/mcp-auth-hardened/actions/workflows/ci.yml) |
| [mcp-memory-first](https://github.com/federiconbaez/mcp-memory-first) | Python | Memory-centric MCP server in Python stdlib: crash-safe, versioned, searchable memory with snapshots. | [![CI](https://github.com/federiconbaez/mcp-memory-first/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/mcp-memory-first/actions/workflows/ci.yml) |
| [mcp-resource-heavy](https://github.com/federiconbaez/mcp-resource-heavy) | Python | MCP server around resources and prompts in Python stdlib: subscriptions over stdio/SSE, cursor pagination, completion. | [![CI](https://github.com/federiconbaez/mcp-resource-heavy/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/mcp-resource-heavy/actions/workflows/ci.yml) |
| [mcp-crosscheck](https://github.com/federiconbaez/mcp-crosscheck) | Python | Black-box cross-validation of the mcp-family servers over real stdio/HTTP processes. Python stdlib. | [![CI](https://github.com/federiconbaez/mcp-crosscheck/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/mcp-crosscheck/actions/workflows/ci.yml) |

## Herramientas / Tooling

| Repo | Lenguaje / Language | Descripción / Description | CI |
|---|---|---|---|
| [bench-verify](https://github.com/federiconbaez/bench-verify) | Rust | Re-run a benchmark claim N times; median + bootstrap CI; PASS/FAIL vs TOML threshold (JSON). | [![CI](https://github.com/federiconbaez/bench-verify/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/bench-verify/actions/workflows/ci.yml) |
| [repo-forge](https://github.com/federiconbaez/repo-forge) | Rust | Rust CLI: husky commit lint + hook, identity check, history leak scan, Rust/C++ scaffolds, gh CI status and profile README rendering | [![CI](https://github.com/federiconbaez/repo-forge/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/repo-forge/actions/workflows/ci.yml) |

<!-- repo-forge:end -->

Tablas generadas con / Tables generated with [repo-forge](https://github.com/federiconbaez/repo-forge) `profile render` ([config](repo-forge.toml)). Licencia Apache-2.0 en todos los repos de arriba / Apache-2.0 on every repo above.
