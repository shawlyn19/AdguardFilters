## 2025-05-15 - Transitive Dependency Hardening and Workflow Protection

**Vulnerability:** Transitive dependencies in `picomatch`, `brace-expansion`, `smol-toml`, and `yaml` were found to have moderate to high severity vulnerabilities including ReDoS, command injection, and prototype pollution. Additionally, GitHub Action workflows lacked explicit permissions and were not pinned to commit SHAs.

**Learning:** `npm audit` identifies these transitive issues, but fixing them in a repository with specific tool requirements (like `@adguard/aglint`) requires a layered approach to `overrides` in `package.json` to ensure compatibility across different dependency branches. Workflow hardening is a critical defense-in-depth measure to prevent supply chain attacks.

**Prevention:** Regularly run `npm audit` and use `overrides` to pin secure versions of transitive dependencies. Document security-related overrides in `package.json`. Always specify `permissions` and use commit SHAs for third-party actions in GitHub workflows. Maintain CRLF line endings when modifying project files in this environment.
