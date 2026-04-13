# Sentinel Security Journal

## 2026-04-18 - Resolving Transitive Vulnerabilities with Nested Overrides
**Vulnerability:** Transitive vulnerabilities in `picomatch` (GHSA-c2c7-rcm5-vvqj, GHSA-3v7f-55p6-f55p), `smol-toml` (GHSA-v3rj-xjv7-4jmq), `yaml` (GHSA-48c2-rrv3-qjmp), and `brace-expansion` (GHSA-f886-m6hf-6m8v).
**Learning:** When multiple versions of a package are required by different tools (e.g., `picomatch` 2.3.x for `micromatch` and 4.x for newer tools), npm `overrides` must be carefully structured. Using a flat override for the latest version and a nested override for the legacy-compatible version ensures both security and functionality.
**Prevention:** Regularly use `npm audit` and apply surgical `overrides` in `package.json`. Document the vulnerability IDs to maintain context for future updates.
