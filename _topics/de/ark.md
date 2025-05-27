---
title: Ark
lang: de

## Optional. Kürzer Name für Referenzstil-Links, z.B. "foo"
## ermöglicht die Verwendung des Links [topic foo][]. Nicht case-sensitive
# shortname: foo

## Optional. Ein Eintrag wird im Themenindex für jeden Alias hinzugefügt
#title-aliases:
#  - Foo

## Erforderlich. Mindestens eine Kategorie, zu der dieses Thema gehört.
topic-categories:
  - Contract Protocols

## Optional. Erzeugt einen Markdown-Link entweder als "[title][]" oder "[title](link)"
primary_sources:
    - title: "Basis Of Ark Technology (BOATs)"
      link: https://github.com/ark-network/boats

## Optional. Jeder Eintrag benötigt "title" und "url". Kann auch "feature: true" verwenden, um den Eintrag hervorzuheben und "date"
optech_mentions:
  - title: Vorschlag für ein verwaltetes Joinpool-Protokoll
    url: /en/newsletters/2023/05/31/#proposal-for-a-managed-joinpool-protocol
    feature: true

  - title: Verbesserung der LN-Skalierbarkeit mit Covenants ähnlich wie bei Ark
    url: /en/newsletters/2023/09/27/#using-covenants-to-improve-ln-scalability

  - title: "Implementierung von Ark auf Mainnet demonstriert"
    url: /en/newsletters/2024/10/18/#bark-ark-implementation-announced

  - title: "Ark Wallet SDK veröffentlicht"
    url: /en/newsletters/2025/02/21/#ark-wallet-sdk-released

  - title: "Bark-Implementierung von Ark ist jetzt auf Signet verfügbar"
    url: /en/newsletters/2025/03/21/#bark-launches-on-signet

  - title: "Zusammenfassung und Kritik an den Vorteilen von CTV + CSFS für Ark"
    url: /en/newsletters/2025/04/04/#ark

## Optional. Gleiches Format wie "primary_sources" oben
see_also:
  - title: Joinpools
    link: topic joinpools

  - title: Covenants
    link: topic covenants

## Optional. Erzwingt die Anzeige (true) oder Nichtanzeige (false) des Stub-Themenhinweises.
## Standard ist die Anzeige, wenn page.content unter einer Schwellenwort-Anzahl liegt
#stub: false

## Erforderlich. Markdown-Formatierung verwenden. Nur ein Absatz. Keine Links erlaubt.
## Sollte weniger als 500 Zeichen sein
excerpt: >
  **Ark** ist ein vertrauensloses Joinpool-Protokoll, bei dem eine große Anzahl
  von Benutzern einen UTXO teilen, indem sie einen Geschäftspartner als Co-Signer
  für alle Transaktionen innerhalb eines bestimmten Zeitraums akzeptieren.
  Dies verteilt die Kosten für Onchain-Gebühren bei der Verwendung dieses UTXO
  auf viele Benutzer und minimiert deren individuelle Kosten.

---
Die Benutzer können entweder ihre Bitcoins nach Ablauf des Zeitraums einseitig onchain abheben oder sie vor Ende des Zeitraums sofort und vertrauenslos offchain an den Geschäftspartner übertragen. Normalerweise wird ein Benutzer seine Bitcoins einfach in einen weiteren Vertrag mit dem Geschäftspartner übertragen, was sehr gebühreneffizient sein kann, wenn es gleichzeitig mit vielen anderen Benutzern durchgeführt wird. Alternativ kann der Geschäftspartner dem Benutzer helfen, eine Zahlung onchain, über LN oder über ein anderes vom Geschäftspartner unterstütztes Protokoll zu tätigen. Vermutlich würde der Geschäftspartner alle Gebühren, die er für die Verwendung des Zahlungsprotokolls zahlen musste, an den Benutzer weitergeben, z.B. Weiterleitungsgebühren, wenn LN verwendet wurde.

Ark kann auf Bitcoin ohne erforderliche Konsensänderungen implementiert werden, aber es unterstützt eine größere Anzahl von Benutzern - was es viel gebühreneffizienter macht - wenn eine [Covenant][topic covenants]-Funktion wie [OP_CHECKTEMPLATEVERIFY][topic op_checktemplateverify] zu Bitcoin hinzugefügt wird.

{% include references.md %}
{% include linkers/issues.md issues="" %}
