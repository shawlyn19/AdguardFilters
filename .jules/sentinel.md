# Sentinel Security Journal

## 2025-05-22 - [Transitive Dependency Remediation]
**Vulnerability:** Transitive dependencies `picomatch`, `brace-expansion`, `smol-toml`, and `yaml` were found to have ReDoS, method injection, or stack overflow vulnerabilities (GHSA-c2c7-rcm5-vvqj, GHSA-3v7f-55p6-f55p, GHSA-f886-m6hf-6m8v, GHSA-v3rj-xjv7-4jmq, GHSA-48c2-rrv3-qjmp).
**Learning:** Even with up-to-date direct dependencies, transitive dependencies can introduce significant risks. The use of `overrides` in `package.json` is a powerful tool for enforcing secure versions across the entire dependency tree.
**Prevention:** Regularly run `npm audit` and use the `overrides` field in `package.json` to pin secure versions of transitive dependencies. Maintain strict CRLF compliance for `package.json` and `package-lock.json` in this repository to avoid noisy diffs.
