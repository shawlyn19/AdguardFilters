## 2025-05-22 - Dependency Security Remediation
**Vulnerability:** ReDoS in `picomatch` and `brace-expansion`, DoS in `yaml`, and Prototype Pollution in `smol-toml`.
**Learning:** High-severity vulnerabilities were identified in transitive dependencies. `picomatch` required a split override (2.3.2 for `micromatch` and 4.0.4 globally) to maintain compatibility with `@adguard/aglint` and `lint-staged`.
**Prevention:** Use `overrides` in `package.json` to pin secure versions of transitive dependencies and remove carets from `devDependencies` to ensure build reproducibility. Document GHSA IDs in a top-level `//` key for auditability.
