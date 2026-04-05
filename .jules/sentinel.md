# Sentinel's Journal - Critical Security Learnings

## 2025-05-15 - Transitive Dependency Overrides for ReDoS and Method Injection
**Vulnerability:** ReDoS and Method Injection in `picomatch` (GHSA-c2c7-rcm5-vvqj, GHSA-3v7f-55p6-f55p), ReDoS in `brace-expansion` (GHSA-f886-m6hf-6m8v), DoS in `smol-toml` (GHSA-v3rj-xjv7-4jmq), and Stack Overflow in `yaml` (GHSA-48c2-rrv3-qjmp).
**Learning:** Even when direct dependencies are updated, transitive dependencies can still carry vulnerabilities. In this case, `markdownlint-cli` and `aglint` pull in vulnerable versions of `picomatch`, `brace-expansion`, `smol-toml`, and `yaml`.
**Prevention:** Use the `overrides` field in `package.json` to force-resolve transitive dependencies to secure versions. For `picomatch`, multiple versions may need to be pinned if different parts of the dependency tree require different major versions (e.g., `micromatch` needing `2.3.2` while others can use `4.0.4`).
