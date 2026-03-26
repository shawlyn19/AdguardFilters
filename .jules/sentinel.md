## 2025-05-22 - [Dependency Security Update]
**Vulnerability:** Transitive dependency vulnerabilities in `picomatch`, `smol-toml`, and `yaml`.
- `picomatch` (ReDoS): GHSA-c2c7-rcm5-vvqj, GHSA-3v7f-55p6-f55p
- `smol-toml` (DoS): GHSA-v3rj-xjv7-4jmq
- `yaml` (Stack Overflow): GHSA-48c2-rrv3-qjmp
**Learning:** Even when top-level devDependencies are relatively recent, their transitive dependencies can still contain high/moderate severity vulnerabilities.
**Prevention:** Regularly run `npm audit` and use the `overrides` field in `package.json` to enforce patched versions of transitive dependencies without waiting for upstream maintainers.
