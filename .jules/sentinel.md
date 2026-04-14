## 2026-04-14 - Transitive Dependency Vulnerabilities Resolved

**Vulnerability:** Transitive dependencies `picomatch`, `brace-expansion`, `smol-toml`, and `yaml` were found to have various vulnerabilities including Regular Expression Denial of Service (ReDoS), Method Injection, and Stack Overflow. Specifically:
- `picomatch` (GHSA-3v7f-55p6-f55p, GHSA-c2c7-rcm5-vvqj)
- `brace-expansion` (GHSA-f886-m6hf-6m8v)
- `smol-toml` (GHSA-v3rj-xjv7-4jmq)
- `yaml` (GHSA-48c2-rrv3-qjmp)

**Learning:** Transitive vulnerabilities can persist even when top-level devDependencies appear relatively modern. Standard `npm audit` identifies these, but they often require manual `overrides` in `package.json` when the parent packages haven't yet updated their own dependency constraints.

**Prevention:** Regularly run `npm audit` and use the `overrides` field in `package.json` to enforce secure versions of transitive dependencies. Document the reason for these overrides using a `//` key to provide context for future maintenance.
