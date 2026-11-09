# Federico Nicolas Baez Rizzo

**EN:** Linux security engineer working in C, Rust, .NET and Go. Focus areas: seccomp, Landlock, eBPF, io_uring, and OIDC/OAuth2 (DPoP, PKCE, mTLS). Public repos publish measurements, CI, and — for Cortex-9 systems — an honest audit status (pass or fail). Offline educational models of known CVEs are listed below; they are not exploit kits and do not contact third-party targets.

**ES:** Seguridad en Linux con C, Rust, .NET y Go. Enfoque: seccomp, Landlock, eBPF, io_uring y OIDC/OAuth2 (DPoP, PKCE, mTLS). Los repos publican mediciones, CI y el estado de auditoría de Cortex-9. Abajo hay modelos offline educativos de CVEs conocidos (no son kits de explotación).

[federicobaez.com](https://federicobaez.com) · [X @Cortex9Sur](https://x.com/Cortex9Sur) · [LinkedIn](https://www.linkedin.com/in/f-baez) · [![GitHub](https://img.shields.io/badge/GitHub-federiconbaez-181717?logo=github)](https://github.com/federiconbaez)

## Background

- **Teaching:** former instructor at EducacionIT (Java, MongoDB, Git).
- **Industry:** Tsoft, Gobierno de la Ciudad de Buenos Aires, Naranja X, Telecom.
- **Studies:** UTN and FIUBA.
- **Certifications:** 17 verified HackerRank certifications.
- **Freelance:** Upwork — Linux and Rust security audits (no rates listed here).

## Selected Cortex-9 systems

Smaller, purpose-built tools that match the focus above. Full audit status for the older Cortex-9 set is in the table further down.

| Repo | Notes |
|---|---|
| [cortex9-framework](https://github.com/federiconbaez/cortex9-framework) | One policy, four kernel enforcement points: classifier, XDP, cgroup v2, fanotify exec guard |
| [cortex9-ask-sandbox](https://github.com/federiconbaez/cortex9-ask-sandbox) | seccomp_unotify supervisor with supervisor-opens + ADDFD (no path TOCTOU) |
| [cortex9-ebpf-tracer](https://github.com/federiconbaez/cortex9-ebpf-tracer) | Syscall tracer in Rust/aya: ring buffer, pid/comm/syscall filters |
| [cortex9-dpop-vs-mtls-bench](https://github.com/federiconbaez/cortex9-dpop-vs-mtls-bench) | Measured cost of DPoP vs mTLS vs bearer on loopback |
| [cortex9-dpop-server-antireplay](https://github.com/federiconbaez/cortex9-dpop-server-antireplay) | Server-side DPoP anti-replay behaviour across verifiers |
| [cortex9-attenuable-mcp](https://github.com/federiconbaez/cortex9-attenuable-mcp) | Attenuable MCP capability tokens with DPoP-bound delegation |
| [cortex9-sigstore-exec-gate](https://github.com/federiconbaez/cortex9-sigstore-exec-gate) | Exec gate tied to Sigstore-style verification |
| [cortex9-landlock-genprof-attack](https://github.com/federiconbaez/cortex9-landlock-genprof-attack) | Landlock+seccomp profile learner with an adversarial escape suite |
| [cortex9-pidfd-seccomp-auditor](https://github.com/federiconbaez/cortex9-pidfd-seccomp-auditor) | pidfd / seccomp surface auditor |

## CVE practice models (47 offline educational repos)

Differential, offline models of **already-patched** vulnerabilities. Each repo ships `PRACTICE.md` (Spanish), positive/negative/adversarial cases, regenerable `results/`, and GitHub Actions CI with no external network targets. **A model is not a finding and not a reproduction against live systems.**

### JWT / OIDC / signature validation

| Repo | CVE |
|---|---|
| [cortex9-pyjwt-pem-detection-alg-confusion-model](https://github.com/federiconbaez/cortex9-pyjwt-pem-detection-alg-confusion-model) | CVE-2026-102268 |
| [cortex9-fastjwt-empty-key-unsigned-accept-model](https://github.com/federiconbaez/cortex9-fastjwt-empty-key-unsigned-accept-model) | CVE-2026-107720 |
| [cortex9-authlib-jws-json-empty-signatures-model](https://github.com/federiconbaez/cortex9-authlib-jws-json-empty-signatures-model) | CVE-2026-96760 |
| [cortex9-vikunja-oidc-email-verified-linking-model](https://github.com/federiconbaez/cortex9-vikunja-oidc-email-verified-linking-model) | CVE-2026-62367 |
| [cortex9-keycloak-jwt-grant-alg-confusion-model](https://github.com/federiconbaez/cortex9-keycloak-jwt-grant-alg-confusion-model) | CVE-2026-11800 |

### Path traversal, routing and static-file bypass

| Repo | CVE / class |
|---|---|
| [cortex9-traefik-replacepathregex-normalization-model](https://github.com/federiconbaez/cortex9-traefik-replacepathregex-normalization-model) | CVE-2026-65600 |
| [cortex9-echo-static-encoded-segment-bypass-model](https://github.com/federiconbaez/cortex9-echo-static-encoded-segment-bypass-model) | CVE-2026-118650 |
| [cortex9-nbconvert-output-filename-traversal-model](https://github.com/federiconbaez/cortex9-nbconvert-output-filename-traversal-model) | CVE-2026-114140 |
| [cortex9-node-tar-path-sanitization-model](https://github.com/federiconbaez/cortex9-node-tar-path-sanitization-model) | CVE-2021-32804, CVE-2021-37713 |
| [cortex9-archive-path-escape-validator](https://github.com/federiconbaez/cortex9-archive-path-escape-validator) | Zip Slip-class path validator (teaching tool; not a single CVE) |
| [cortex9-git-case-insensitive-symlink-checkout-model](https://github.com/federiconbaez/cortex9-git-case-insensitive-symlink-checkout-model) | CVE-2021-21300 |
| [cortex9-git-safe-directory-discovery-model](https://github.com/federiconbaez/cortex9-git-safe-directory-discovery-model) | CVE-2022-24765 |

### SSRF and DNS rebinding

| Repo | CVE |
|---|---|
| [cortex9-mlflow-webhook-dns-rebinding-toctou-model](https://github.com/federiconbaez/cortex9-mlflow-webhook-dns-rebinding-toctou-model) | CVE-2026-64849 |
| [cortex9-phpspreadsheet-redirect-whitelist-ssrf-model](https://github.com/federiconbaez/cortex9-phpspreadsheet-redirect-whitelist-ssrf-model) | CVE-2026-108360 |

### Injection, deserialization and unsafe loaders

| Repo | CVE / note |
|---|---|
| [cortex9-pillow-ghostscript-argv-injection-model](https://github.com/federiconbaez/cortex9-pillow-ghostscript-argv-injection-model) | CVE-2026-112900 |
| [cortex9-argocd-git-ssh-proxy-url-injection-model](https://github.com/federiconbaez/cortex9-argocd-git-ssh-proxy-url-injection-model) | CVE-2026-55797 |
| [cortex9-trivy-action-envfile-source-injection-model](https://github.com/federiconbaez/cortex9-trivy-action-envfile-source-injection-model) | CVE-2026-26189 |
| [cortex9-freeform-attribute-twig-render-model](https://github.com/federiconbaez/cortex9-freeform-attribute-twig-render-model) | CVE-2026-73858 |
| [cortex9-shell-quote-comment-line-terminator-model](https://github.com/federiconbaez/cortex9-shell-quote-comment-line-terminator-model) | CVE-2026-102422 |
| [cortex9-nltk-pickle-allowlist-prefix-model](https://github.com/federiconbaez/cortex9-nltk-pickle-allowlist-prefix-model) | CVE-2026-79657 |
| [cortex9-seroval-node-id-type-confusion-model](https://github.com/federiconbaez/cortex9-seroval-node-id-type-confusion-model) | CVE-2026-116580 |
| [cortex9-pyyaml-unsafe-loader-astlint](https://github.com/federiconbaez/cortex9-pyyaml-unsafe-loader-astlint) | CVE-2017-18342, CVE-2020-1747, CVE-2020-14343 (AST lint) |
| [cortex9-lodash-defaultsdeep-prototype-pollution-model](https://github.com/federiconbaez/cortex9-lodash-defaultsdeep-prototype-pollution-model) | CVE-2019-10744 |
| [cortex9-rust-batbadbut-args-model](https://github.com/federiconbaez/cortex9-rust-batbadbut-args-model) | CVE-2024-24576 |

### Memory, integer and crypto-library bugs

| Repo | CVE |
|---|---|
| [cortex9-heartbleed-heartbeat-bounds-model](https://github.com/federiconbaez/cortex9-heartbleed-heartbeat-bounds-model) | CVE-2014-0160 |
| [cortex9-openssl-sm2-plaintext-size-model](https://github.com/federiconbaez/cortex9-openssl-sm2-plaintext-size-model) | CVE-2021-3711 |
| [cortex9-openssl-asn1-string-nul-scanner](https://github.com/federiconbaez/cortex9-openssl-asn1-string-nul-scanner) | CVE-2021-3712 |
| [cortex9-openssl-bn-mod-sqrt-loop-model](https://github.com/federiconbaez/cortex9-openssl-bn-mod-sqrt-loop-model) | CVE-2022-0778 |
| [cortex9-openssl-x400-generalname-type-confusion-model](https://github.com/federiconbaez/cortex9-openssl-x400-generalname-type-confusion-model) | CVE-2023-0286 |
| [cortex9-libwebp-huffman-table-sizing-model](https://github.com/federiconbaez/cortex9-libwebp-huffman-table-sizing-model) | CVE-2023-4863 |
| [cortex9-libxml2-strncat-length-wrap-model](https://github.com/federiconbaez/cortex9-libxml2-strncat-length-wrap-model) | CVE-2016-1834 |
| [cortex9-brotli-uncompressed-copy-narrowing-model](https://github.com/federiconbaez/cortex9-brotli-uncompressed-copy-narrowing-model) | CVE-2020-8927 |
| [cortex9-glibc-getaddrinfo-dual-buffer-state-model](https://github.com/federiconbaez/cortex9-glibc-getaddrinfo-dual-buffer-state-model) | CVE-2015-7547 |
| [cortex9-expat-utf8-name-validation-model](https://github.com/federiconbaez/cortex9-expat-utf8-name-validation-model) | CVE-2022-25235 |
| [cortex9-expat-namespace-separator-model](https://github.com/federiconbaez/cortex9-expat-namespace-separator-model) | CVE-2022-25236 |
| [cortex9-lz4java-tmp-native-lib-predictable-name-model](https://github.com/federiconbaez/cortex9-lz4java-tmp-native-lib-predictable-name-model) | CVE-2026-106451 |
| [cortex9-rust-str-repeat-capacity-overflow-model](https://github.com/federiconbaez/cortex9-rust-str-repeat-capacity-overflow-model) | CVE-2018-1000810 |
| [cortex9-rust-zip-size-hint-overflow-model](https://github.com/federiconbaez/cortex9-rust-zip-size-hint-overflow-model) | CVE-2021-28879 |
| [cortex9-rust-regex-empty-repetition-size-limit-model](https://github.com/federiconbaez/cortex9-rust-regex-empty-repetition-size-limit-model) | CVE-2022-24713 |

### Races, TOCTOU and protocol state machines

| Repo | CVE |
|---|---|
| [cortex9-dirtycow-gup-cow-state-model](https://github.com/federiconbaez/cortex9-dirtycow-gup-cow-state-model) | CVE-2016-5195 |
| [cortex9-tmpfiles-hardlink-chown-race-model](https://github.com/federiconbaez/cortex9-tmpfiles-hardlink-chown-race-model) | CVE-2017-18078 |
| [cortex9-time-crate-env-race-interleaving-model](https://github.com/federiconbaez/cortex9-time-crate-env-race-interleaving-model) | CVE-2020-26235 |
| [cortex9-filelock-sqlite-symlink-follow-model](https://github.com/federiconbaez/cortex9-filelock-sqlite-symlink-follow-model) | CVE-2026-112936 |
| [cortex9-ksmbd-preauth-info-race-model](https://github.com/federiconbaez/cortex9-ksmbd-preauth-info-race-model) | CVE-2026-72422 |
| [cortex9-terrapin-strict-kex-model](https://github.com/federiconbaez/cortex9-terrapin-strict-kex-model) | CVE-2023-48795 |
| [cortex9-http2-rapid-reset-stream-accounting-model](https://github.com/federiconbaez/cortex9-http2-rapid-reset-stream-accounting-model) | CVE-2023-44487 |
| [cortex9-http2-priority-churn-cost-model](https://github.com/federiconbaez/cortex9-http2-priority-churn-cost-model) | CVE-2019-9513 |

<!-- repo-forge:start -->
## Bajo nivel / Low-level systems

Rust y C++ con loom, Miri y sanitizers en CI. / Rust and C++ with loom, Miri and sanitizers in CI.

| Repo | Lenguaje / Language | Descripción / Description | CI |
|---|---|---|---|
| [lockfree-mpmc](https://github.com/federiconbaez/lockfree-mpmc) | Rust | Bounded lock-free MPMC queue (Vyukov); loom + Miri; Criterion vs crossbeam/std. | [![CI](https://github.com/federiconbaez/lockfree-mpmc/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/lockfree-mpmc/actions/workflows/ci.yml) |
| [arena-slab-cpp](https://github.com/federiconbaez/arena-slab-cpp) | C++ | C++20 arena + slab allocators with ASan/TSan/fuzz and honest benches vs malloc/jemalloc. | [![CI](https://github.com/federiconbaez/arena-slab-cpp/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/arena-slab-cpp/actions/workflows/ci.yml) |
| [spsc-c11](https://github.com/federiconbaez/spsc-c11) | C | Lock-free single-producer/single-consumer ring in C11: cached indices, batching, TSan-verified with a negative control, x86-64 and AArch64 CI | [![CI](https://github.com/federiconbaez/spsc-c11/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/spsc-c11/actions/workflows/ci.yml) |
| [intrusive-list-cpp](https://github.com/federiconbaez/intrusive-list-cpp) | C++ | Header-only C++20 intrusive doubly linked list: allocation-free push/pop/splice, stable sort, safe and auto-unlink hooks, multi-list tags | [![CI](https://github.com/federiconbaez/intrusive-list-cpp/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/intrusive-list-cpp/actions/workflows/ci.yml) |
| [crc32c-portable](https://github.com/federiconbaez/crc32c-portable) | C++ | CRC-32C in C++20: slicing-by-8, SSE4.2 and ARMv8 CRC backends with runtime dispatch, combine(), fuzzed and sanitized | [![CI](https://github.com/federiconbaez/crc32c-portable/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/crc32c-portable/actions/workflows/ci.yml) |
| [bptree-wal](https://github.com/federiconbaez/bptree-wal) | Rust | On-disk B+tree with a redo WAL of page images: atomic transactions, checkpoints, and recovery tested against truncation, bit flips and real SIGKILL | [![CI](https://github.com/federiconbaez/bptree-wal/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/bptree-wal/actions/workflows/ci.yml) |
| [mmap-wal-log](https://github.com/federiconbaez/mmap-wal-log) | Rust | Append-only log on a memory-mapped file: CRC32C per record, torn-tail recovery, salvage reader, SIGKILL-tested | [![CI](https://github.com/federiconbaez/mmap-wal-log/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/mmap-wal-log/actions/workflows/ci.yml) |
| [tiny-jit-x64](https://github.com/federiconbaez/tiny-jit-x64) | C++ | Minimal x86-64 JIT for integer expressions: hand-emitted machine code, W^X pages, differential tests against an interpreter | [![CI](https://github.com/federiconbaez/tiny-jit-x64/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/tiny-jit-x64/actions/workflows/ci.yml) |
| [ffi-cbindgen-demo](https://github.com/federiconbaez/ffi-cbindgen-demo) | Rust | O(1) LRU cache in Rust exposed to C and C++ via cbindgen: panic-safe C ABI, ownership rules, RAII wrapper, ASan/UBSan + Miri. | [![CI](https://github.com/federiconbaez/ffi-cbindgen-demo/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/ffi-cbindgen-demo/actions/workflows/ci.yml) |

## Redes / Networking

Sin runtime async ni crates de red; CI sin red externa (loopback y respuestas grabadas). / No async runtime or networking crates; CI without external network (loopback and recorded responses).

| Repo | Lenguaje / Language | Descripción / Description | CI |
|---|---|---|---|
| [uring-http](https://github.com/federiconbaez/uring-http) | Rust | Minimal HTTP/1.1 server in Rust on raw io_uring, no async runtime. Tested with Miri and ASan. | [![CI](https://github.com/federiconbaez/uring-http/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/uring-http/actions/workflows/ci.yml) |
| [dns-stub-rs](https://github.com/federiconbaez/dns-stub-rs) | Rust | Stub DNS resolver for A/AAAA: strict UDP response matching, TCP fallback, CNAME chains, positive and negative TTL cache; std only | [![CI](https://github.com/federiconbaez/dns-stub-rs/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/dns-stub-rs/actions/workflows/ci.yml) |

## Seguridad de sandbox / Sandbox security

seccomp y Landlock probados contra el kernel real en CI. / seccomp and Landlock tested against the real kernel in CI.

| Repo | Lenguaje / Language | Descripción / Description | CI |
|---|---|---|---|
| [seccomp-trace-diff](https://github.com/federiconbaez/seccomp-trace-diff) | Rust | Analyze and diff seccomp-bpf filters (x86_64): reachable actions per syscall, arch/x32 bypass checks, CI regression gate. Verified against the Linux kernel. | [![CI](https://github.com/federiconbaez/seccomp-trace-diff/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/seccomp-trace-diff/actions/workflows/ci.yml) |
| [landlock-smoke](https://github.com/federiconbaez/landlock-smoke) | Rust | Landlock LSM over raw syscalls: sandboxing exec wrapper and a kernel self-test matrix (fs, REFER, TRUNCATE, TCP, IPC scopes) | [![CI](https://github.com/federiconbaez/landlock-smoke/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/landlock-smoke/actions/workflows/ci.yml) |
| [proc-maps-guard](https://github.com/federiconbaez/proc-maps-guard) | Rust | Audits /proc/<pid>/maps for W^X violations, executable anonymous memory, memfd/deleted code and aliased write+exec mappings | [![CI](https://github.com/federiconbaez/proc-maps-guard/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/proc-maps-guard/actions/workflows/ci.yml) |

## Embebido / Embedded

Firmware bare-metal en QEMU y código freestanding para Cortex-M. / Bare-metal firmware on QEMU and freestanding code for Cortex-M.

| Repo | Lenguaje / Language | Descripción / Description | CI |
|---|---|---|---|
| [qemu-riscv32-uart](https://github.com/federiconbaez/qemu-riscv32-uart) | C | Bare-metal RV32 firmware for QEMU virt: own startup, NS16550A UART driver, CLINT timer interrupts, trap handling, exit codes for CI. | [![CI](https://github.com/federiconbaez/qemu-riscv32-uart/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/qemu-riscv32-uart/actions/workflows/ci.yml) |
| [qemu-cortex-m-blink](https://github.com/federiconbaez/qemu-cortex-m-blink) | C | Bare-metal Cortex-M3 firmware: Morse SOS on the LM3S6965 LED from SysTick, self-checking in QEMU with a semihosting exit code | [![CI](https://github.com/federiconbaez/qemu-cortex-m-blink/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/qemu-cortex-m-blink/actions/workflows/ci.yml) |
| [cobs-frame](https://github.com/federiconbaez/cobs-frame) | C | COBS + CRC-16 framing for serial links in freestanding C99: streaming receiver, 11 canonical vectors, fuzzed, 600 B on Cortex-M0 | [![CI](https://github.com/federiconbaez/cobs-frame/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/cobs-frame/actions/workflows/ci.yml) |

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
| [cortex9-raft-sim](https://github.com/federiconbaez/cortex9-raft-sim) | Rust | Raft (election, replication, snapshots) under deterministic simulation: seeded drops/reorders/partitions/crashes + Porcupine-style linearizability checker. Rust, zero deps. | [![CI](https://github.com/federiconbaez/cortex9-raft-sim/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/cortex9-raft-sim/actions/workflows/ci.yml) | Valor no auditado / Value not audited |
| [cortex9-lsm-engine](https://github.com/federiconbaez/cortex9-lsm-engine) | Rust | LSM-tree storage engine in Rust: WAL, memtable, SSTables with bloom filters, leveled compaction; crash-tested at every write point | [![CI](https://github.com/federiconbaez/cortex9-lsm-engine/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/cortex9-lsm-engine/actions/workflows/ci.yml) | Valor no auditado / Value not audited |
| [cortex9-wal-btree](https://github.com/federiconbaez/cortex9-wal-btree) | Rust | Crash-consistent B+tree on a redo WAL with fsync discipline; crashed at every write point with torn writes; proptest vs BTreeMap. Rust. | [![CI](https://github.com/federiconbaez/cortex9-wal-btree/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/cortex9-wal-btree/actions/workflows/ci.yml) | Valor no auditado / Value not audited |
| [cortex9-wasm-vm](https://github.com/federiconbaez/cortex9-wasm-vm) | WebAssembly | WebAssembly 1.0 (MVP) interpreter in Rust: decoder, validator, stack machine; passes the official wg-1.0 spec tests, fuzzed with cargo-fuzz | [![CI](https://github.com/federiconbaez/cortex9-wasm-vm/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/cortex9-wasm-vm/actions/workflows/ci.yml) | Valor no auditado / Value not audited |
| [cortex9-epoch-gc](https://github.com/federiconbaez/cortex9-epoch-gc) | Rust | Epoch-based memory reclamation + lock-free hash map (Harris-Michael) in Rust, checked with loom, Miri and ThreadSanitizer. Part of Cortex-9. | [![CI](https://github.com/federiconbaez/cortex9-epoch-gc/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/cortex9-epoch-gc/actions/workflows/ci.yml) | Valor no auditado / Value not audited |

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
| [crate-audit-checklist](https://github.com/federiconbaez/crate-audit-checklist) | Rust | Reproducible Rust crate review checklist: tests, clippy, fmt, cargo-audit, unsafe SAFETY hygiene, metadata and Miri, scored JSON report with a schema | [![CI](https://github.com/federiconbaez/crate-audit-checklist/actions/workflows/ci.yml/badge.svg)](https://github.com/federiconbaez/crate-audit-checklist/actions/workflows/ci.yml) |

<!-- repo-forge:end -->

Low-level / MCP / tooling tables above are rendered with [repo-forge](https://github.com/federiconbaez/repo-forge) `profile render` ([config](repo-forge.toml)). Apache-2.0 on those repos. CVE practice models are maintained separately and each carries its own LICENSE and `LIMITATIONS.md`.
