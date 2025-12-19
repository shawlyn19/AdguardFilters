## 2024-09-06 - Proactive Removal of Dependency with CLI Vulnerability

**Vulnerability:** A high-severity command injection vulnerability (GHSA-5j98-mcp5-4vw2) was present in the CLI of the `glob` package, a transitive dependency of `markdownlint-cli`. While this project does not directly invoke the vulnerable CLI command, the presence of a dependency with a critical flaw in the toolchain represents an unnecessary security risk.

**Learning:** Auditing dependencies is not just about fixing currently exploitable vulnerabilities, but also about reducing the overall attack surface. A vulnerable package, even if not exploited by current usage patterns, could become a threat if code changes in the future, or if another vulnerability is discovered. Proactively removing or updating such dependencies hardens the build process.

**Prevention:** Treat `npm audit` findings seriously, even for development dependencies. Investigate high-severity warnings to understand their direct impact. When a dependency has a history of vulnerabilities, prioritize replacing it with a more secure alternative as a defense-in-depth measure. The fix was to update `markdownlint-cli` to a version that no longer depends on `glob`.
