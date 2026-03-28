# Sentinel Security Journal

## 2025-05-15 - [Supply Chain Hardening & Transitive Vulnerability Remediation]
**Vulnerability:** Use of mutable GitHub Action version tags (e.g., @v6) and several transitive dependencies with known vulnerabilities (GHSA-f886-m6hf-6m8v, GHSA-3v7f-55p6-f55p, etc.).
**Learning:** Even with updated top-level devDependencies, many vulnerabilities persist in the transitive tree (like picomatch or brace-expansion) that require explicit 'overrides' in package.json to resolve. Mutable GHA tags are a target for tag-hopping attacks.
**Prevention:** Pin all GitHub Actions to full 40-character commit SHAs. Use the 'overrides' field in package.json to force secure versions of transitive dependencies. Maintain strict CRLF compliance in this repo to prevent massive diff noise.
