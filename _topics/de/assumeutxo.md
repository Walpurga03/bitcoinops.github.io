---
title: AssumeUTXO
lang: de

## Erforderlich. Mindestens eine Kategorie, zu der dieses Thema gehört.
topic-categories:
  - Consensus Enforcement
  - P2P Network Protocol

## Erforderlich. Markdown-Formatierung verwenden. Nur ein Absatz. Keine Links erlaubt.
excerpt: >
  **AssumeUTXO** ist ein vorgeschlagener Modus zum Bootstrapping neuer Full Nodes,
  der es ihnen ermöglicht, die Verifizierung älterer Blockchain-Historie zu verschieben,
  bis nachdem der Benutzer aktuelle Transaktionen empfangen kann.

## Optional. Erzeugt einen Markdown-Link entweder als "[title][]" oder "[title](link)"
primary_sources:
    - title: AssumeUTXO proposal
      link: https://github.com/jamesob/assumeutxo-docs/tree/2019-04-proposal/proposal

    - title: AssumeUTXO project tracker
      link: https://github.com/bitcoin/bitcoin/pull/27596

## Optional. Jeder Eintrag benötigt "title", "url" und "date". Kann auch "feature: true" verwenden, um den Eintrag hervorzuheben
optech_mentions:
  - title: Assume valid discussion
    url: /en/newsletters/2019/04/09/#discussion-about-an-assumed-valid-mechanism-for-utxo-snapshots

  - title: CoreDev.tech Demo und Diskussion von assumeutxo
    url: /en/newsletters/2019/06/12/#assume-utxo-demo

  - title: "Jahresrückblick 2019: AssumeUTXO"
    url: /en/newsletters/2019/12/28/#assumeutxo

  - title: Review Club Zusammenfassung der MuHash-Implementierung für schnelles Hashing des UTXO-Sets
    url: /en/newsletters/2020/11/11/#bitcoin-core-pr-review-club

  - title: MuHash-Funktion hinzugefügt zur Vorbereitung auf die Verfolgung von UTXO-Status-Hashes
    url: /en/newsletters/2021/01/13/#bitcoin-core-19055

  - title: "Bitcoin Core #19521 vereinfacht die Erzeugung von UTXO-Set-Hashes für alte Blöcke"
    url: /en/newsletters/2021/05/05/#bitcoin-core-19521

  - title: "Bitcoin Core #23155 erweitert den `dumptxoutset`-RPC mit neuen Informationen"
    url: /en/newsletters/2021/12/08/#bitcoin-core-23155

  - title: "Bitcoin Core #25740 ermöglicht Hintergrundvalidierung des gebootstrappten UTXO-Status"
    url: /en/newsletters/2023/03/15/#bitcoin-core-25740

  - title: Zusammenfassungen des persönlichen Treffens der Bitcoin Core-Entwickler
    url: /en/newsletters/2023/05/17/#summaries-of-bitcoin-core-developers-in-person-meeting

  - title: "Bitcoin Core #27596 fügt assumedvalid snapshot chainstate und vollständige Validierungssynchronisation im Hintergrund hinzu"
    url: /en/newsletters/2023/10/11/#bitcoin-core-27596

  - title: Bitcoin Core-Fehler in der Berechnung des UTXO-Set-Hashes gefunden
    url: /en/newsletters/2023/10/25/#bitcoin-utxo-set-summary-hash-replacement

  - title: Notizen aus der Bitcoin-Entwicklerdiskussion über assumeUTXO für Mainnet
    url: /en/newsletters/2024/05/01/#coredev-tech-berlin-event

  - title: "Bitcoin Core #30320 lädt einen AssumeUTXO-Snapshot nur, wenn er der Vorgänger der Kette mit der höchsten PoW ist"
    url: /en/newsletters/2024/07/26/#bitcoin-core-30320

  - title: "Bitcoin Core #30598 entfernt die Blockhöhe aus den Metadaten der assumeUTXO-Snapshot-Datei"
    url: /en/newsletters/2024/08/16/#bitcoin-core-30598

  - title: "Bitcoin Core #28553 fügt assumeUTXO-Snapshot-Parameter für Mainnet-Block 840.000 hinzu"
    url: /en/newsletters/2024/08/23/#bitcoin-core-28553

  - title: "Bitcoin Core #30807 lässt assumeUTXO-Knoten während der Hintergrundsynchronisation NODE_NETWORK_LIMITED signalisieren"
    url: /en/newsletters/2024/09/20/#bitcoin-core-30807

  - title: "SwiftSync schnellere Synchronisierung, kompatibel mit und komplementär zu assumeUTXO"
    url: /en/newsletters/2025/04/11/#swiftsync-speedup-for-initial-block-download

## Optional. Gleiches Format wie "primary_sources" oben
see_also:
  - title: "Bitcoin Core Issue #15605: AssumeUTXO Discussion"
    link: https://github.com/bitcoin/bitcoin/issues/15605

  - title: "[bitcoin-dev] assumeutxo and UTXO snapshots"
    link: https://gnusha.org/url/https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2019-April/016825.html
---
Im Code des Knotens wäre ein Hash des Sets aller ausgebbaren Bitcoins und der notwendigen Bedingungen für deren Ausgabe (das UTXO-Set) zu einem bestimmten, kürzlich erreichten Zeitpunkt eingebettet. Ähnlich wie bei der existierenden [assumevalid][]-Einstellung und anderen Parametern, die von Knoten zur Konsensbildung verwendet werden, würden Revisionen des assumeutxo-Hashes von Entwicklern während des Code-Reviews auf Korrektheit überprüft. Dies würde es Betreibern neuer Knoten ermöglichen, optional diesem Hash zu vertrauen und ein UTXO-Set herunterzuladen, das zu diesem Hash passt. Für Blöcke, die nach dem UTXO-Set-Hash erzeugt wurden, würde der Knoten neue Blöcke verifizieren und sein eigenes UTXO-Set wie jeder andere Knoten ohne weiteres Vertrauen aktualisieren. Nach dem aktuellen Entwurf würde der Knoten auch ältere Blöcke im Hintergrund herunterladen und verifizieren, damit er schließlich beweisen könnte, dass der Hash, mit dem er anfänglich gestartet wurde, korrekt war.

{% include references.md %}
[assumevalid]: https://bitcoincore.org/en/2017/03/08/release-0.14.0/#assumed-valid-blocks
