## 2025-05-22 - CI Failure due to invalid Action versions and runners
**Vulnerability:** Broken CI toolchain.
**Learning:** Some GitHub Actions were using non-existent major versions (e.g., actions/checkout@v6) or invalid runner labels (ubuntu-slim), leading to immediate job failures.
**Prevention:** Always pin GitHub Actions to full 40-character commit SHAs retrieved from the official repository and use standard runner labels (e.g., ubuntu-latest).
