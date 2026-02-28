## 2025-05-15 - [Minimatch 10.x and Brace-Expansion 5.x ESM Compatibility]
**Vulnerability:** Transitive ReDoS in `brace-expansion` (GHSA-v6h2-p8h4-qcjw) and `minimatch` (GHSA-3ppc-4f35-3m26).
**Learning:** Forcing a version override for `brace-expansion` to 2.x when `minimatch` 10.x is present leads to a `SyntaxError` (Missing named export 'expand'). `minimatch` 10.x is an ESM module that requires the named exports introduced in `brace-expansion` 5.x.
**Prevention:** When overriding transitive dependencies, always verify the module format (CJS vs ESM) and dependency requirements of the parent package. If a parent package is ESM, ensure its overridden dependencies provide the expected exports.
