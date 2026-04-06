# Sentinel Security Journal

## 2026-04-22 - Transitive ReDoS and DoS Vulnerabilities Fix
**Vulnerability:** ReDoS in `picomatch` and `brace-expansion`, and DoS in `smol-toml` and `yaml` transitive dependencies.
**Learning:** `npm audit` revealed multiple moderate to high severity vulnerabilities in transitive dependencies of `markdownlint-cli`, `lint-staged`, and `@adguard/aglint`. Some packages required specific nested overrides (e.g., `picomatch` under `micromatch`) to resolve conflicts between different version requirements while maintaining security.
**Prevention:** Regularly run `npm audit` and use the `overrides` field in `package.json` to pin secure versions of transitive dependencies. Document GHSA/CVE IDs in `package.json` for clarity.
