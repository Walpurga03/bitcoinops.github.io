---
title: Anonymitätsnetzwerke
lang: de

## Optional. Kürzer Name für Referenzstil-Links, z.B. "foo"
## ermöglicht die Verwendung des Links [topic foo][]. Nicht case-sensitive
# shortname: foo

## Optional. Ein Eintrag wird im Themenindex für jeden Alias hinzugefügt
title-aliases:
  - Tor
  - I2P

## Erforderlich. Mindestens eine Kategorie, zu der dieses Thema gehört
topic-categories:
  - Privacy Enhancements

## Optional. Erzeugt einen Markdown-Link mit "[title][]" oder "[title](link)"
#primary_sources:
#    - title: Test
#    - title: Example
#      link: https://example.com

## Optional. Jeder Eintrag benötigt "title", "url" und "date". Kann auch "feature: true" verwenden, um Einträge hervorzuheben
optech_mentions:
  - title: "Bitcoin Core #21594 fügt dem `getnodeaddresses` RPC ein Netzwerktyp-Feld hinzu"
    url: /en/newsletters/2021/04/14/#bitcoin-core-21594

  - title: "Bitcoin Core #20197 aktualisiert die Eviction-Logik, um langlebige Onion-Peers beizubehalten"
    url: /en/newsletters/2021/04/07/#bitcoin-core-20197

  - title: "Frage: Wie verwende ich I2P mit Bitcoin Core?"
    url: /en/newsletters/2021/03/31/#how-can-i-use-bitcoin-core-with-the-anonymous-network-protocol-i2p

  - title: "Bitcoin Core #20685 fügt Unterstützung für das I2P-Privatsphärenetzwerk hinzu"
    url: /en/newsletters/2021/03/10/#bitcoin-core-20685

  - title: "Bitcoin Core GUI #162 fügt Netzwerktyp-Informationen zum GUI-Peers-Fenster hinzu"
    url: /en/newsletters/2021/01/06/#bitcoin-core-gui-162

  - title: "Bitcoin Core #19954 vervollständigt die BIP155 addr v2-Implementierung"
    url: /en/newsletters/2020/10/14/#bitcoin-core-19954

  - title: Bitcoin Core PR Review Club zu einer vorgeschlagenen Implementierung von BIP155 addr v2
    url: /en/newsletters/2020/08/12/#bitcoin-core-pr-review-club

  - title: BIP für neue Adressweiterleitung zur Unterstützung von Tor v3 Onion-Adressen
    url: /en/newsletters/2019/03/12/#version-2-addr-message-proposed

  - title: Bitcoin Core 0.21.0 veröffentlicht mit Unterstützung für Tor v3 Onion-Adressen
    url: /en/newsletters/2021/01/20/#bitcoin-core-0-21-0

  - title: "Jahresrückblick: Unterstützung für Tor v3 Onion-Adressen"
    url: /en/newsletters/2020/12/23/#addrv2

  - title: "Bitcoin Core #19991 ermöglicht die Verfolgung eingehender Verbindungen von Onion-Peers"
    url:  /en/newsletters/2020/10/07/#bitcoin-core-19991

  - title: Desktop-Version von Blockstream Green mit Tor-Unterstützung veröffentlicht
    url: /en/newsletters/2020/06/17/#desktop-version-of-blockstream-green-wallet

  - title: Präsentation zu Verbesserungen in LND 0.10, einschließlich besserer Tor-Unterstützung
    url: /en/newsletters/2020/05/06/#lnd-v0-10

  - title: "BOLTs #751 aktualisiert BOLT7, um besser mit Multi-Netzwerk-Knotenankündigungen umzugehen"
    url: /en/newsletters/2020/03/25/#bolts-751

  - title: CKBunker ermöglicht die Festlegung von Ausgabebedingungen für eine Tor-fähige Coldcard
    url: /en/newsletters/2020/02/19/#ckbunker-using-psbts-for-an-hsm

  - title: "Eclair #1278 erlaubt Benutzern, SSL zu überspringen, wenn sie einen Onion-Service verwenden"
    url: /en/newsletters/2020/02/05/#eclair-1278

  - title: "C-Lightning #3155 fügt Option für die Verwendung einer statischen Onion-Service-Adresse hinzu"
    url: /en/newsletters/2019/12/11/#c-lightning-3155

  - title: "Blockstream Green mit eingebauter Tor-Unterstützung für iOS und Android"
    url: /en/newsletters/2019/10/23/#blockstream-green-tor-support

  - title: "BIPs #766 weist BIP155 dem addr v2-Vorschlag für v3 Onion-Adressen zu"
    url: /en/newsletters/2019/07/31/#bips-766

  - title: "Bitcoin Core #15651 bindet immer an den Standardport, wenn auf Tor gehört wird"
    url: /en/newsletters/2019/06/26/#bitcoin-core-15651

  - title: "Eclair #736 fügt Unterstützung für die Verwendung und das Einrichten eines Onion-Service hinzu"
    url: /en/newsletters/2019/02/12/#eclair-736

  - title: "LND #1516 fügt Unterstützung für die automatische Einrichtung eines v3 Onion-Service hinzu"
    url: /en/newsletters/2018/09/18/#lnd-1516

  - title: "Bitcoin Core #22050 entfernt die Unterstützung für veraltete Version 2 Tor Onion-Services"
    url: /en/newsletters/2021/06/09/#bitcoin-core-22050

  - title: "Bitcoin Core #22112 ändert den angenommenen Port für I2P-Adressen auf 0 statt 8333"
    url: /en/newsletters/2021/07/21/#bitcoin-core-22112

  - title: "Bitcoin Core 22.0 fügt Unterstützung für I2P-Verbindungen hinzu und entfernt v2 Tor-Verbindungen"
    url: /en/newsletters/2021/09/15/#bitcoin-core-22-0

  - title: "Bitcoin Core #23077 ermöglicht Adressweiterleitung über CJDNS"
    url: /en/newsletters/2021/11/17/#bitcoin-core-23077

  - title: "Bitcoin Core #25355 fügt Unterstützung für transiente I2P-Adressen hinzu"
    url: /en/newsletters/2022/09/07/#bitcoin-core-25355

  - title: "Bitcoin Core #27411 hört auf, die lokale Tor- oder I2P-Adresse des Knotens in anderen Netzwerken bekannt zu geben"
    url: /en/newsletters/2023/07/19/#bitcoin-core-27411

  - title: "Bitcoin Core #29200 ermöglicht I2P, Verbindungen zu verwenden, die sowohl mit ECIES-X25519 als auch mit ElGamal verschlüsselt sind"
    url: /en/newsletters/2024/01/17/#bitcoin-core-29200

  - title: "DNS-Seeding für Knoten in Anonymitätsnetzwerken"
    url: /en/newsletters/2024/09/20/#dns-seeding-for-non-ip-addresses

## Optional. Gleiches Format wie "primary_sources" oben
see_also:
  - title: Dandelion
    link: topic dandelion

  - title: Addr v2
    link: topic addr v2

## Erforderlich. Markdown-Formatierung verwenden. Nur ein Absatz. Keine Links erlaubt.
## Sollte weniger als 500 Zeichen sein
excerpt: >
  **Anonymitätsnetzwerke** sind Systeme, die Netzwerkkommunikation ermöglichen,
  ohne dass Sender oder Empfänger ihre IP-Adressen gegenseitig preisgeben müssen.
  Die bekanntesten davon sind Tor und I2P.

---

Die Verwendung von Anonymitätsnetzwerken kann erheblich zur Verbesserung der Privatsphäre von Bitcoin-Software beitragen. Besonders vorteilhaft ist es beim Senden eigener Transaktionen. Dies gilt insbesondere für Lightweight-Clients, die keine Transaktionen für andere Peers weiterleiten, sodass jede von ihrer IP-Adresse gesendete Transaktion leicht mit ihrer Netzwerkidentität verknüpft werden kann.

Die Verwendung eines Anonymitätsnetzwerks kann jedoch in einigen Fällen auch ein Nachteil sein; zum Beispiel:

- **Der besten Blockchain folgen** ist eine große Herausforderung für Full Nodes und Lightweight-Clients in Anonymitätsnetzwerken. Da Anonymitätsnetzwerke die Erstellung einer großen Anzahl falscher Identitäten ermöglichen, sind Systeme, die ausschließlich diese nutzen, anfällig für Sybil-Angriffe, die zu [Eclipse-Angriffen][topic eclipse attacks] werden können, bei denen Clients und Nodes eine andere Blockchain angezeigt bekommen als die, die vom Rest des Netzwerks verwendet wird, was möglicherweise zu Geldverlust führen kann.

- **Latenz** kann ein Problem für geroutete Vertragsprotokollsysteme sein, die für Schnelligkeit konzipiert sind, wie LN. Dennoch ist es für viele Endbenutzer in Ordnung, etwas langsamere Geschwindigkeit gegen deutlich verbesserte Privatsphäre einzutauschen.

Anonymitätsnetzwerke, die von Bitcoin getrennt sind, wie Tor und I2P, können auch mit privatsphärenverbessernden Techniken in Bitcoin kombiniert werden, wie [Dandelion][topic dandelion].

Hinweis: Tor-Onion-Services sollten nicht mit der Onion-Verschlüsselung verwechselt werden, die in LN verwendet wird. Obwohl beide von denselben Ideen zum Schutz der Privatsphäre abgeleitet sind, handelt es sich um zwei verschiedene Systeme.

{% include references.md %}
{% include linkers/issues.md issues="" %}
