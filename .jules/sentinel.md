## 2026-04-09 - Resolving Transitive Vulnerabilities via Overrides
**Vulnerability:** Moderate and High severity vulnerabilities (ReDoS, DoS, Stack Overflow) were found in transitive dependencies: `brace-expansion`, `picomatch`, `smol-toml`, and `yaml`.
**Learning:** Even when top-level devDependencies are up-to-date, their nested dependencies can remain on vulnerable versions. `npm audit` is essential for identifying these deep-seated risks.
**Prevention:** Use the `overrides` field in `package.json` to force-patch transitive dependencies to secure versions. Document addressed GHSA IDs in the same file to provide context for the overrides. Maintain CRLF line endings for compatibility in this repository using `unix2dos`.
