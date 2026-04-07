## 2025-05-15 - [MEDIUM] Fix Transitive Dependency Vulnerabilities
**Vulnerability:** Transitive dependencies `picomatch`, `brace-expansion`, `smol-toml`, and `yaml` had multiple vulnerabilities including ReDoS, Stack Overflow, and Method Injection.
**Learning:** Even with up-to-date direct dependencies, deep transitive dependencies can remain vulnerable if they are not explicitly pinned via `overrides`.
**Prevention:** Use `npm audit` to identify vulnerabilities and apply `overrides` in `package.json` for transitive dependencies that are not updated by parent packages.
