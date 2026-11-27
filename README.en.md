[Deutsch](README.md) · [English](README.en.md) · [Русский](README.ru.md)

# JBL WAN observation workflow — research by Juri

**Juri (Juri-Halveth) · 27 November 2026**

**[Full report and retained evidence](https://github.com/Juri-Halveth/jbl-owner-external-witness-20260901/blob/main/REPORT.md)** · [English overview](https://github.com/Juri-Halveth/jbl-owner-external-witness-20260901/blob/main/README.en.md)

The manual workflow attempts a TCP connection from a GitHub runner to the supplied target on port 57120. If connected, it sends a WebSocket upgrade request and reads the first HTTP status line. An HTTP 101 observation alone verifies neither a complete WebSocket handshake nor the identity of a JBL service. [PR #2](https://github.com/Juri-Halveth/jbl-wan-proof/pull/2) corrects the output labels accordingly.

The two August job logs were unavailable with HTTP 410 on 27 November. The workflow can exit successfully even when TCP connection establishment fails. A green Actions run therefore does not establish network reachability.

The companion repository retains separate September results: a gain-value change and restoration **75 → 74 → 75**, using an owner-created tunnel and supplied pairing material, and a direct TCP test that timed out. The report documents the precise conditions, missing product-version binding and unverified current fix status. No network test was rerun for this publication.
