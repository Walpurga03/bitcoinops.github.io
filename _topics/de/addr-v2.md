---
title: Addr v2
lang: de

## Optional. Ein Eintrag wird im Themenindex für jeden Alias hinzugefügt
#title-aliases:
#  - Foo

## Erforderlich. Mindestens eine Kategorie, zu der dieses Thema gehört.
topic-categories:
  - P2P Network Protocol

## Erforderlich. Markdown-Formatierung verwenden. Nur ein Absatz. Keine Links erlaubt.
## Sollte weniger als 500 Zeichen umfassen
excerpt: >
  **addr v2** ist eine vorgeschlagene neue Version der `addr`-Nachricht im
  Bitcoin P2P-Netzwerkprotokoll, die zum Bekanntmachen der Adressen
  von Knoten verwendet wird, die eingehende Verbindungen akzeptieren.

## Optional. Erzeugt einen Markdown-Link mit entweder "[title][]" oder "[title](link)"
primary_sources:
    - title: BIP155

## Optional. Jeder Eintrag benötigt "title", "url" und "date". Kann auch "feature: true" verwenden, um den Eintrag fett darzustellen
optech_mentions:
  - title: Version 2 `addr`-Nachricht vorgeschlagen
    url: /en/newsletters/2019/03/12/#version-2-addr-message-proposed

  - title: Version 2 `addr`-Nachricht als BIP155 zugewiesen
    url: /en/newsletters/2019/07/31/#bips-766

  - title: Vorgeschlagene knotenspezifische Signalisierung für Adressweiterleitung mit v2 `addr`-Nachrichten
    url: /en/newsletters/2019/11/06/#signaling-support-for-address-relay

  - title: Zusammenfassung der Bitcoin Core PR Review Club-Diskussion zu einem `addr` v2 PR
    url: /en/newsletters/2020/08/12/#bitcoin-core-pr-review-club

  - title: "BIPs #907 aktualisiert BIP155-Nachrichten, um Adressen bis zu 512 Bytes zu erlauben"
    url: /en/newsletters/2020/09/30/#bips-907

  - title: "Bitcoin Core #19954 implementiert BIP155 und Tor v3-Unterstützung"
    url: /en/newsletters/2020/10/14/#bitcoin-core-19954

  - title: "Bitcoin Core #20564 sendet addrv2 nur an Peers mit Protokollversion 70016"
    url: /en/newsletters/2020/12/16/#protocol-version

  - title: BIP155 aktualisiert, um zu verlangen, dass die `sendaddrv2`-Nachricht vor `verack` gesendet wird
    url: /en/newsletters/2020/12/16/#bips-1043

  - title: "Jahresrückblick 2020: Version 2 `addr`-Nachricht"
    url: /en/newsletters/2020/12/23/#addrv2

  - title: "Bitcoin Core 0.21.0 veröffentlicht mit Unterstützung für Version 2 `addr`"
    url: /en/newsletters/2021/01/20/#bitcoin-core-0-21-0

  - title: "Rust Bitcoin 0.26.0 veröffentlicht mit Unterstützung für Version 2 `addr`"
    url: /en/newsletters/2021/01/20/#rust-bitcoin-0-26-0

  - title: "Bitcoin Core #20685 fügt I2P-Unterstützung hinzu, einschließlich addrv2-Gossipping"
    url: /en/newsletters/2021/03/10/#bitcoin-core-20685

  - title: "BIPs #1134 verdeutlicht die BIP155-Verwendung der P2P-Feature-Verhandlungsnachricht `sendaddr2`"
    url: /en/newsletters/2021/07/07/#bips-1134

  - title: "BTCD v0.23.2 fügt Unterstützung für addr v2 hinzu"
    url: /en/newsletters/2022/10/19/#btcd-v0-23-2-released

## Optional. Gleiches Format wie "primary_sources" oben
see_also:
  - title: P2P-Protokoll `addr`-Nachricht
    link: https://btcinformation.org/en/developer-reference#addr

  - title: Anonymitätsnetzwerke
    link: topic anonymity networks
---
Die ursprüngliche `addr`-Nachricht erlaubt die Weiterleitung von 128-Bit-IPv6-Adressen
mit Rückwärtskompatibilität für IPv4 und [onioncat-kodierte][onioncat-encoded] Version
2 (v2) Tor Hidden Service (.onion)-Adressen. Allerdings sind v3 Tor Hidden
Service-Adressen 256 Bit groß, ebenso wie Adressen für verschiedene
andere datenschutzfördernde Netzwerkprotokolle. Da diese neueren Adresstypen
nicht mit der bestehenden `addr`-Nachricht verwendet werden können, wurde eine neue Version
der Nachricht vorgeschlagen. Darüber hinaus könnte das Update erlauben,
andere Aspekte der Nachricht oder das Verhalten von Knoten und
Clients, die sie verarbeiten, anzupassen.

{% include references.md %}
[onioncat-encoded]: https://web.archive.org/web/20121122003543/http://www.cypherpunk.at/onioncat/wiki/OnionCat
