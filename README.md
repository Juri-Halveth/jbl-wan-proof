[Deutsch](README.md) · [English](README.en.md) · [Русский](README.ru.md)

# JBL WAN-Prüfablauf – ergänzende Forschung zu CERT@VDE #642251

**Finder: Juri Janovski — HALVETH · Stand: 27. November 2026**

**Laut dem vom Finder bereitgestellten Korrespondenztext teilte CERT@VDE am 24. September 2026 mit, dass das Engineering-Team den zugrunde liegenden lokalen Sicherheitsbefund validiert hat und JBL QuantumENGINE 2.7.8 betroffen ist.** Dieses Repository enthält zusätzliche Netzwerkprüfungen zu diesem Fall.

**[Vollständiger Bericht](https://github.com/Juri-Halveth/jbl-owner-external-witness-20260901/blob/main/REPORT.md)** · **[CERT@VDE-Bestätigung](https://github.com/Juri-Halveth/jbl-owner-external-witness-20260901/blob/main/evidence/CERT-VDE-CORRESPONDENCE.md)** · [Erratum](https://github.com/Juri-Halveth/jbl-owner-external-witness-20260901/blob/main/ERRATUM-20261127.md)

## Hauptbefund und zusätzliche Versuche

Der gemeldete lokale Befund betrifft einen Prozess ohne erhöhte Rechte, der über JBLs Remote-Control-IPC auf vorhandenen Pairing-Zustand zugreifen und diesen zur Änderung einer Headset-Einstellung wiederverwenden konnte. Die Engineering-Bestätigung dieses Falls ist von den hier untersuchten Netzwerkwegen zu unterscheiden.

Die erhaltenen September-Belege zeigen außerdem **75 → 74 → 75** für einen Gain-Wert über einen vom Eigentümer eingerichteten Tunnel mit bereitgestellten Pairingdaten. Der separate direkte TCP-Versuch endete im Timeout. Diese direkte Verbindungsprobe widerlegt den lokalen Befund nicht.

## Was dieser Workflow erfasst

Der manuell gestartete [Workflow](.github/workflows/jbl-wan-proof.yml) versucht eine TCP-Verbindung von einem GitHub-Runner zum angegebenen Ziel auf Port 57120. Bei aufgebauter Verbindung sendet er eine WebSocket-Upgrade-Anfrage und liest die erste HTTP-Statuszeile. Die in [PR #2](https://github.com/Juri-Halveth/jbl-wan-proof/pull/2) übernommene Präzisierung kennzeichnet eine HTTP-101-Statuszeile als solche; ein vollständiger Handshake oder die JBL-Dienstidentität sind damit nicht geprüft.

Die Joblogs der zwei August-Läufe waren am 27. November mit HTTP 410 nicht mehr abrufbar. Der Workflow kann bei fehlgeschlagenem TCP-Aufbau mit Exitcode 0 enden. Ein grüner Actions-Status ist deshalb kein Nachweis erfolgreicher Erreichbarkeit.

## Koordination, Finder-Nennung und Prämie

CERT@VDE sagte am **19. Oktober 2026** die Finder-Nennung zu. HARMANs separate Entscheidung, dass diese Einreichung nicht für eine Prämie unter dessen Bug-Bounty-Programm qualifiziert, widerruft die technische Bestätigung nicht. Der am 24. September genannte Fixrelease im **Dezember 2026** war eine Planung; eine ausgelieferte Fixversion und eine konkrete CVE-Nummer sind in der vorgelegten Korrespondenz nicht genannt. Alle maßgeblichen Auszüge stehen im verlinkten Bericht.
