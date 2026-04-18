# Sentinel Security Journal

## 2026-04-18 - [Transitive Vulnerabilities Remediated]
**Vulnerability:** Moderate and High severity vulnerabilities (ReDoS, Stack Overflow, DoS) in transitive dependencies `picomatch`, `brace-expansion`, `smol-toml`, and `yaml`.
**Learning:** Even with pinned top-level dependencies, vulnerabilities can surface in the transitive tree. In this repository, `npm audit` reveals issues in packages like `tinyglobby` and `micromatch`.
**Prevention:** Regularly run `npm audit` and use the `overrides` field in `package.json` to enforce secure versions of transitive dependencies without waiting for parent packages to update.
