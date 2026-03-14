## 2025-05-15 - Dependency Override Compatibility
**Vulnerability:** Regular Expression Denial of Service (ReDoS) in `brace-expansion` and `minimatch`.
**Learning:** Overriding transitive dependencies can lead to runtime errors if version compatibility is not carefully checked. Specifically, `minimatch@10.x` requires `brace-expansion@5.x` due to ESM named exports.
**Prevention:** Always verify that overridden versions are compatible with their parent packages by running the full toolchain (e.g., `npm run lint`) after `npm install`.
