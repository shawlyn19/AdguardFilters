# Sentinel Security Journal

## 2025-05-19 - Dependency Security Remediation
**Vulnerability:** Multiple vulnerabilities identified in transitive dependencies:
- `picomatch` (<=2.3.1, 4.0.0-4.0.3): Method Injection (GHSA-3v7f-55p6-f55p) and ReDoS (GHSA-c2c7-rcm5-vvqj).
- `brace-expansion` (4.0.0-5.0.4): ReDoS via zero-step sequences (GHSA-f886-m6hf-6m8v).
- `smol-toml` (<1.6.1): DoS via thousands of consecutive commented lines (GHSA-v3rj-xjv7-4jmq).
- `yaml` (2.0.0-2.8.2): Stack Overflow via deeply nested collections (GHSA-48c2-rrv3-qjmp).

**Learning:** Transitive dependencies can introduce significant security risks even when direct dependencies appear up-to-date. In this case, `picomatch` was pulled in by both legacy and modern tools, requiring a dual-version override strategy to maintain compatibility while ensuring security.

**Prevention:** Regularly run `npm audit` and use the `overrides` field in `package.json` to pin transitive dependencies to secure versions. Document the reason for each override using GHSA identifiers to facilitate future maintenance.
