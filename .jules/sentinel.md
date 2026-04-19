# Sentinel Security Journal

## 2026-04-19 - Initial security audit and dependency remediation
**Vulnerability:** Transitive vulnerabilities in `brace-expansion`, `picomatch`, `smol-toml`, and `yaml` reported by `npm audit`.
**Learning:** Even with pinned top-level devDependencies, transitive dependencies can introduce security risks like ReDoS and DoS.
**Prevention:** Use npm `overrides` to force secure versions of transitive dependencies and document them in `package.json`.
