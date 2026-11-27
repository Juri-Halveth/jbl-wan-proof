[Deutsch](README.md) · [English](README.en.md) · [Русский](README.ru.md)

# JBL WAN-Prüfablauf – Forschung von Juri

**Juri (Juri-Halveth) · Stand 27. November 2026**

Dieses Repository enthält den historischen externen TCP-/HTTP-Prüfablauf zu Juris JBL-Untersuchung. Der vollständige Bericht, die späteren Witness-Skripte und die vier erhaltenen September-Belege stehen im ergänzenden Repository:

**[Forschungsbericht und Belege öffnen](https://github.com/Juri-Halveth/jbl-owner-external-witness-20260901/blob/main/REPORT.md)**

## Was der Workflow erfasst

Der manuell gestartete [Workflow](.github/workflows/jbl-wan-proof.yml) versucht von einem GitHub-Runner aus eine TCP-Verbindung zum angegebenen Ziel auf Port 57120. Bei aufgebauter Verbindung sendet er eine WebSocket-Upgrade-Anfrage und liest die erste HTTP-Statuszeile.

Die aktuelle Ausgabe unterscheidet eine aufgebaute Verbindung, eine nicht aufgebaute Verbindung und eine beobachtete HTTP-101-Statuszeile. **Eine Statuszeile allein verifiziert weder den vollständigen WebSocket-Handshake noch einen JBL-Dienst.** Die dafür vorgenommene Präzisierung ist in [PR #2](https://github.com/Juri-Halveth/jbl-wan-proof/pull/2) dokumentiert.

## Historische Ergebnisse richtig lesen

Die Joblogs der zwei August-Läufe waren bei der Prüfung am 27. November mit HTTP 410 nicht mehr abrufbar. Der Workflow kann auch bei fehlgeschlagenem TCP-Aufbau mit Exitcode 0 enden. Ein grüner Actions-Status ist deshalb kein Beleg für erfolgreiche Erreichbarkeit.

Die später erhaltenen September-Logs im ergänzenden Repository zeigen einen getrennten Befund: **75 → 74 → 75** für einen Gain-Wert über einen vom Eigentümer eingerichteten Tunnel mit bereitgestellten Pairingdaten. Der separate direkte TCP-Versuch endete im Timeout. Die Zusammenhänge, offene Versionszuordnung und der nicht bestätigte aktuelle Fixstatus sind im vollständigen Bericht erklärt.

Für die Veröffentlichung wurden vorhandene Quellen und Logs ausgewertet. Es wurde kein neuer Workflow und keine neue Netzwerkprobe gestartet.
