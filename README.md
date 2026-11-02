# RustXNG public-information smoke test

A one-off, non-production evaluation of upstream RustXNG v0.26.0. No private data, secrets, API keys, or business repository inputs are used. Results are public. This is not a security audit or a statistically representative search benchmark.

Execution is intended only in a fresh GitHub-hosted Ubuntu VM, in a non-root, read-only Docker container with all Linux capabilities dropped, no host ports, no host home or Docker socket mounts, and no injected GitHub credentials. No paid APIs are used. The runner is destroyed after the job; the test container is removed on exit.

The release binary is verified against the fixed SHA256 published by GitHub for the upstream asset. This verifies downloaded bytes, not trustworthiness of the upstream code. Web results remain untrusted data and are not executed. Search denial or rate-limiting is recorded, never bypassed.

Queries are deliberately generic (Python documentation, Rust documentation, Tokyo public tourism). Output includes URLs, counts and timing, not full copyrighted page text. Only three cold searches and one repeated search are intended. Built-in upstream search-engine retries may occur.
