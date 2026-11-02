# Results — 2026-11-02 UTC

[Completed run #1](https://github.com/zhidoukunjuexing-ship-it/rustxng-public-smoke-test/actions/runs/41394622781), workflow commit `959a9f8a68e57fa71243293063a26ff54ee87c7d`.

## Observed results

| Query | Seconds | Top-5 results | Expected official domain at rank 1 | Returned page-text characters |
|---|---:|---:|---|---:|
| python dict get documentation | 2.798 | 5 | Yes | 32004 |
| Rust ownership documentation | 2.045 | 5 | Yes | 32400 |
| 東京 観光 公式 | 3.464 | 5 | Yes | 13928 |
| python dict get documentation (repeat) | 0.219 | 5 | Yes | 32004 |

Rank-1 URLs were Python's official tutorial, the Rust Book, and GO TOKYO, respectively. This checks domain presence and successful text retrieval, **not semantic correctness or completeness of the page text**. The repeated query was faster; cache-hit instrumentation was not collected, so the result is not a universal cache-speed guarantee.

## Safety and provenance

- Official upstream RustXNG v0.26.0 Linux-musl asset SHA256 verification passed:
  `250c75f2bb623c99065087b06d40550cd802b48c7ada265e2d7448bbf1d7f839`.
- GitHub-hosted Ubuntu 24.04 disposable runner; all steps completed successfully, approximately 25 seconds of job activity.
- Application process UID 65534 verified. Read-only container, capabilities dropped, no-new-privileges, 512 MiB/1 CPU, no host ports, no Docker socket/home mount.
- Clean application environment; GitHub/API tokens not passed to the container. Runner's platform token had metadata-read permission only.
- No private data, paid APIs, service deployment or persistent runtime.
- Container removed on completion; GitHub decommissions its hosted job VM.
- Standard public-repository runner usage is listed as free by GitHub. No billing settings changed; account invoice was not inspected.
- Runtime image resolved to `python@sha256:e697c81897302a4c4333bade000d98038fbb21eb064f8ee1fd42d02ebcd9d337`.

## Limits and decision

Several upstream engines reported access denial, CAPTCHA or rate limiting (including Google, DuckDuckGo and Brave). These were **not bypassed**; RustXNG returned results from remaining engines.

The assistant's existing web search also found official sources for all three queries. Its execution environment and ranking interface differ, so this is a qualitative reference, **not a fair head-to-head speed or quality benchmark**.

Conclusion: this limited smoke test supports trying RustXNG as a public-web retrieval component for a self-built agent. It does not establish superiority over existing search, production availability, privacy of queries, absence of security vulnerabilities, or performance on business workloads. No business integration was performed.

The workflow only triggers when its own YAML changes. Publishing this results file does not request another test run.
