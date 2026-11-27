[Deutsch](README.md) · [English](README.en.md) · [Русский](README.ru.md)

# JBL WAN observation workflow

**Research and finder credit: Juri Janovski — HALVETH**  
Documentation updated: 27 November 2026 · **CERT@VDE case #642251**

[Full research report, German](https://github.com/Juri-Halveth/jbl-owner-external-witness-20260901/blob/main/REPORT.md) · [Documented correspondence](https://github.com/Juri-Halveth/jbl-owner-external-witness-20260901/blob/main/evidence/CERT-VDE-CORRESPONDENCE.md) · [English overview](https://github.com/Juri-Halveth/jbl-owner-external-witness-20260901/blob/main/README.en.md)

## This workflow's role

This repository preserves a supplementary external TCP/HTTP experiment. The **main reported finding concerns local IPC access by a non-elevated Windows process and reuse of existing pairing state**, not proof of default Internet exposure.

On **24 September 2026**, CERT@VDE relayed engineering's validation of the issue, confirmed **QuantumENGINE 2.7.8** as affected and reported agreement with the proposed severity. No numerical severity score appears in the supplied correspondence. A corrective update was then planned for **December 2026**; this was a historical plan, not a fix-release confirmation.

On **19 October**, CERT@VDE relayed HARMAN's decision that the submission did not qualify for a bounty reward and separately confirmed future finder credit. The **latest supplied reply is undated**, follows the 22 October exchange and says the advisory was still unpublished with no concrete date. Advisory and CVE links were to follow publication; the supplied text contains no assigned CVE identifier.

## Reading the network records

The manual workflow attempts TCP port **57120** and, if connected, sends a WebSocket upgrade request. An HTTP 101 status line alone does not validate the complete handshake or identify a JBL service. The two August job logs returned HTTP 410 during review; a successful Actions status alone cannot establish reachability because the workflow can exit successfully after a failed connection.

The companion repository retains separate September results: **75 → 74 → 75** through an owner-created tunnel with supplied pairing material, plus a direct TCP attempt that timed out after **8009 ms**. These observations and their limits apply to the supplementary network experiments, not to the entire validated local IPC case.

No new network test was performed for this documentation update. The current release's impact and fix status remain unverified by these records.

