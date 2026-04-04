## 2026-04-04 - [Transitive Dependency Vulnerabilities]
**Vulnerability:** Transitive dependencies `brace-expansion`, `picomatch`, `smol-toml`, and `yaml` were found to have vulnerabilities (GHSA-f886-m6hf-6m8v, GHSA-3v7f-55p6-f55p, GHSA-c2c7-rcm5-vvqj, GHSA-v3rj-xjv7-4jmq, GHSA-48c2-rrv3-qjmp).
**Learning:** Even when top-level devDependencies like `markdownlint-cli` and `lint-staged` are updated, their transitive dependencies may still be pinned to vulnerable versions.
**Prevention:** Use `overrides` in `package.json` to explicitly pin vulnerable transitive dependencies to secure versions. Document the GHSA IDs in the `package.json` for future reference. Always verify with `npm audit` and maintain CRLF line endings.
