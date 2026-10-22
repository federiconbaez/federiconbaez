# Federico Nicolás Báez Rizzo

**ES:** Ingeniero de sistemas. Trabajo en Rust y C++ sobre Linux: concurrencia lock-free, eBPF/XDP, sandboxes, IPC y memoria. Los repos abajo muestran el estado real de cada auditoría — lo que pasó y lo que no.
**EN:** Systems engineer. I work in Rust and C++ on Linux: lock-free concurrency, eBPF/XDP, sandboxes, IPC and memory. The repos below show each project's honest audit status — what passed and what did not.

- Site: [federicobaez.com](https://federicobaez.com)
- X: [@Cortex9Sur](https://x.com/Cortex9Sur)
- LinkedIn: [f-baez](https://www.linkedin.com/in/f-baez)

## Low-level / concurrency

| Repo | What | Status |
|------|------|--------|
| [lockfree-mpmc](https://github.com/federiconbaez/lockfree-mpmc) | Bounded lock-free MPMC queue (Vyukov), loom + Miri | Measured on box; see BENCH.md |
| [cortex9-shm-ring-bus](https://github.com/federiconbaez/cortex9-shm-ring-bus) | Lock-free SPSC ring over `/dev/shm` (Rust + C/C++/Go/Python clients) | Not independently audited; benches in BENCH.md |
| [cortex9-memoria-unificada](https://github.com/federiconbaez/cortex9-memoria-unificada) | C++20 tiered GPU/RAM/disk memory manager | Audited: passes threshold #5 on random access (B+) |

## Linux security / sandboxing

| Repo | What | Status |
|------|------|--------|
| [cortex9-elf-zk-loader](https://github.com/federiconbaez/cortex9-elf-zk-loader) | Signed-only ELF loader + seccomp supervisor (Rust) | Audited **FAIL**: 122/143 in scope (85.3%) vs 100% threshold; v0.3 measurement (149/149) **not audited** |
| [cortex9-xdp-semantic-firewall](https://github.com/federiconbaez/cortex9-xdp-semantic-firewall) | XDP semantic firewall for MCP/gRPC (eBPF + aya) | Audited: **fails** its value threshold |
| [cortex9-jitter-exfil](https://github.com/federiconbaez/cortex9-jitter-exfil) | Timing-jitter covert-channel detector on SSL writes | Value **not audited** |

## Kernel / agents / desktop

| Repo | What | Status |
|------|------|--------|
| [cortex9-sched-entropia](https://github.com/federiconbaez/cortex9-sched-entropia) | `sched_ext` scheduler weighting threads by prompt entropy | Value **not audited** |
| [cortex9-snapshots-enjambre](https://github.com/federiconbaez/cortex9-snapshots-enjambre) | Memory snapshot/restore for a swarm of agent processes | Audited: **fails** its threshold in general |
| [cortex9-fwm-x11-rust](https://github.com/federiconbaez/cortex9-fwm-x11-rust) | X11 window manager grouping by title/class/OCR affinity | Value **not audited** |
| [cortex9-termica-predictiva](https://github.com/federiconbaez/cortex9-termica-predictiva) | C daemon predicting CPU temp to cap frequency | Hardware control **not verified** |
| [cortex9-poincare-fs](https://github.com/federiconbaez/cortex9-poincare-fs) | Read-only FUSE FS with Poincaré-ball embeddings | Audited: value **not demonstrated** |

## Focus

Rust · C++20 · Linux · lock-free · eBPF/XDP · seccomp · IPC · memory allocators

Apache-2.0 on all Cortex9 / lockfree work above.
