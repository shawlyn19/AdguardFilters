# Sentinel Security Journal

## 2026-04-22 - Transitive ReDoS and DoS Vulnerabilities Fix
**Vulnerability:** ReDoS in `picomatch` and `brace-expansion`, and DoS in `smol-toml` and `yaml` transitive dependencies.
**Learning:** `npm audit` revealed multiple moderate to high severity vulnerabilities in transitive dependencies of `markdownlint-cli`, `lint-staged`, and `@adguard/aglint`. Some packages required specific nested overrides (e.g., `picomatch` under `micromatch`) to resolve conflicts between different version requirements while maintaining security.
**Prevention:** Regularly run `npm audit` and use the `overrides` field in `package.json` to pin secure versions of transitive dependencies. Document GHSA/CVE IDs in `package.json` for clarity.

## 2026-04-22 - GitHub Actions Hardening
**Vulnerability:** Use of mutable action tags (e.g., `@v6`) and overly permissive default GITHUB_TOKEN permissions.
**Learning:** Pinning actions to a 40-character commit SHA prevents tag-hopping attacks where a tag is moved to a malicious commit. Explicitly setting `permissions: contents: read` follows the principle of least privilege.
**Prevention:** Always pin GitHub Actions to commit SHAs and define explicit permissions in workflow files.
