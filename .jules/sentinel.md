## 2025-05-22 - Dependency Security Remediation and Workflow Hardening
**Vulnerability:** ReDoS in `picomatch` and `brace-expansion`, DoS in `yaml`, and Prototype Pollution in `smol-toml`. Also potential tag-hopping attacks in GitHub Actions and overly permissive `GITHUB_TOKEN` permissions.
**Learning:** High-severity vulnerabilities were identified in transitive dependencies. `picomatch` required a split override (2.3.2 for `micromatch` and 4.0.4 globally) to maintain compatibility with `@adguard/aglint` and `lint-staged`.
**Prevention:** Use `overrides` in `package.json` to pin secure versions of transitive dependencies and remove carets from `devDependencies` to ensure build reproducibility. Document GHSA IDs in a top-level `//` key for auditability.
**Harden CI:** Pin GitHub Actions to 40-character commit SHAs and define explicit `permissions` (e.g., `contents: read` or `issues: write`) to enforce the principle of least privilege.
