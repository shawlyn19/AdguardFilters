## 2026-02-14 - Dependency Override Incompatibility

**Vulnerability:** Transitive dependency vulnerabilities in `brace-expansion` and `glob`.

**Learning:** Forcing an override of `brace-expansion` to version 2.x when `minimatch` 10.x is in use (e.g., via `markdownlint-cli@0.47.0`) results in a `SyntaxError: Named export 'expand' not found`. This is because `minimatch` 10.x requires the ESM named exports introduced in `brace-expansion` 5.x.

**Prevention:** Before applying overrides for transitive dependencies, verify if the parent package (like `minimatch`) has specific version requirements or architectural changes (like ESM transition) that might be incompatible with the overridden version. In this case, upgrading the top-level package (`markdownlint-cli`) was a better approach as it correctly updated its dependency tree to use secure versions.
