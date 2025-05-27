---
title: Anchor Outputs
lang: de

## Optional. Ein Eintrag wird im Themenindex für jeden Alias hinzugefügt
title-aliases:
  - Simplified commitments

## Erforderlich. Mindestens eine Kategorie, zu der dieses Thema gehört
topic-categories:
  - Lightning Network
  - Fee Management
  - Transaction Relay Policy

## Erforderlich. Markdown-Formatierung verwenden. Nur ein Absatz. Keine Links erlaubt.
excerpt: >
  **Anchor outputs** sind eine Verbesserung der Lightning-Network-Commitment-Transaktionen,
  die es ermöglichen, Transaktionsgebühren anzupassen, nachdem die Transaktion signiert wurde,
  indem zusätzliche kleine Outputs hinzugefügt werden, die mit Child Pays For Parent (CPFP) ausgegeben werden können.

## Optional. Erzeugt einen Markdown-Link mit entweder "[title][]" oder "[title](link)"
primary_sources:
  - title: "BOLTs PR #688: Anchor outputs"
    link: https://github.com/lightning/bolts/pull/688

## Optional. Jeder Eintrag benötigt "title", "url"
optech_mentions:
  - title: LN entwickelt sich in Richtung anchor outputs
    url: /en/newsletters/2019/10/30/#ln-simplified-commitments

  - title: Ankeroutputs vorgeschlagen, um beim Absichern von HTLCs zu helfen
    url: /en/newsletters/2019/11/06/#proposed-safety-improvement-for-ln-payment-atomicity

  - title: Anwendung von anchor outputs in LND
    url: /en/newsletters/2020/01/29/#lnd-3829

  - title: LND 0.10 unterstützt experimentelle Anchor-Kanäle
    url: /en/newsletters/2020/05/06/#lnd-0-10-0-beta

  - title: Ankeroutputs machen es einfacher, RBF für Commitment-Transaktionen zu verwenden
    url: /en/newsletters/2020/12/09/#using-anchor-outputs-by-default-in-lnd

  - title: LND 0.13.0-beta aktualisiert Anchor-Outputs für bessere Privatsphäre
    url: /en/newsletters/2021/10/13/#lnd-0-13-1-beta

  - title: "LND 0.15.0-beta unterstützt Anker-Outputs mit Zero-Fee-HTLC-Transaktionen"
    url: /en/newsletters/2022/08/03/#lnd-0-15-0-beta

## Optional. Gleiches Format wie "primary_sources" oben
see_also:
  - title: Package relay
    link: topic package relay

  - title: CPFP carve out
    link: topic cpfp carve out

  - title: Ephemeral anchors
    link: topic ephemeral anchors

  - title: V3 transaction relay
    link: topic version 3 transaction relay
---
Bei der ursprünglichen Design von Lightning-Network-Commitment-Transaktionen musste die Gebühr zum Zeitpunkt der Unterzeichnung für alle Commitment-Transaktionen und HTLC-Transaktionen festgelegt werden. Dies machte das Protokoll anfällig für verschiedene Arten von Angriffen und Einschränkungen:

- **Zeitliche Pinning-Angriffe:** Böswillige Akteure konnten Commitment-Transaktionen mit niedrigen Gebühren senden, die viele Blöcke lang im Mempool steckten, was die Abwicklung von HTLCs verzögerte.

- **Unflexible Gebühren:** Da Gebühren bei der Unterzeichnung festgelegt werden mussten, war es schwierig, auf sich ändernde Mempoolbedingungen zu reagieren.

- **Komplexität bei kooperativen Schließungen:** Unterschiedliche Gebührenschätzungen zwischen Peers führten zu zusätzlichen Austauschvorgängen, um eine für beide Seiten akzeptable Gebühr zu finden.

Anchor Outputs lösen diese Probleme, indem sie zwei kleine Outputs zu Commitment-Transaktionen hinzufügen, einen für jede Partei des Kanals, die jeweils mit [Child Pays For Parent (CPFP)][topic cpfp] ausgegeben werden können. Dies ermöglicht es jeder Partei, die Transaktionsgebühr nach der Unterzeichnung zu erhöhen, was mehrere Vorteile bietet:

1. **Dynamische Gebührenanpassung:** Gebühren können entsprechend den aktuellen Mempoolbedingungen angepasst werden, wenn eine Commitment-Transaktion tatsächlich veröffentlicht wird.

2. **Schutz vor Pinning-Angriffen:** Beide Parteien können unilateral die Gebühren erhöhen, wodurch ein böswilliger Peer keine Commitment-Transaktionen mit niedrigen Gebühren erzwingen kann.

3. **Vereinfachte Schließvorgänge:** Kooperative Schließungen erfordern keine langwierigen Verhandlungen über Gebühren mehr.

Die Implementierung von Anchor Outputs erforderte andere Änderungen am Lightning-Protokoll und an der Bitcoin-Core-Relaying-Politik:

- **CPFP Carve-out:** Diese Änderung in Bitcoin Core (in Version 0.19 eingeführt) ermöglicht [CPFP für eine Transaktion mit bis zu einem untergeordneten Element pro Elternelement][topic cpfp carve out], auch wenn andere Regeln zur Verhinderung von Pinning gelten würden.

- **Zero-Fee HTLC-Transaktionen:** Neuere Implementierungen erlauben HTLC-Transaktionen mit Gebühren von Null, wobei erwartet wird, dass sie mit CPFP-Anker-Ausgaben gebündelt werden.

- **Package Relay:** Um Zero-Fee-Transaktionen zu unterstützen, arbeitet die Community an [Package Relay][topic package relay], das die Übertragung einer Gruppe verwandter Transaktionen als Einheit ermöglicht.

Einige LN-Implementierungen unterstützen inzwischen eine vereinfachte Version namens "simplified commitments" oder "anchor outputs without HTLC fees". Dieser Ansatz nutzt Zero-Fee HTLCs und vereinfacht das Protokoll, indem er die Notwendigkeit beseitigt, HTLC-Gebühren während der Kanaloperationen neu zu verhandeln.

Im April 2023 begann [version 3 (v3) transaction relay][topic version 3 transaction relay] die Entwicklung mit dem Ziel, sowohl Anchor Outputs als auch allgemeinere Anwendungsfälle wie [ephemeral anchors][topic ephemeral anchors] besser zu unterstützen.

{% include references.md %}
