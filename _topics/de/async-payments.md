---
title: Asynchrone Zahlungen
lang: de

## Optional. Kürzer Name für Referenzstil-Links, z.B. "foo"
## ermöglicht die Verwendung des Links [topic foo][]. Nicht case-sensitive
# shortname: foo

## Optional. Ein Eintrag wird im Themenindex für jeden Alias hinzugefügt
#title-aliases:
#  - Foo

## Erforderlich. Mindestens eine Kategorie, zu der dieses Thema gehört
topic-categories:
  - Lightning Network

## Optional. Erzeugt einen Markdown-Link entweder als "[title][]" oder "[title](link)"
#primary_sources:
#    - title: Test
#    - title: Example
#      link: https://example.com

## Optional. Jeder Eintrag benötigt "title" und "url". Kann auch "feature: true" verwenden, um den Eintrag hervorzuheben und "date"
optech_mentions:
  - title: Zahlung an Offline-Knoten
    url: /en/newsletters/2021/10/20/#paying-offline-ln-nodes

  - title: Trampoline-Routing und asynchrone Mobile-Zahlungen
    url: /en/newsletters/2022/06/15/#trampoline-routing-and-mobile-payments

  - title: "Eclair #2435 fügt Unterstützung für eine grundlegende Form asynchroner Zahlungen bei Verwendung von Trampoline-Relay hinzu"
    url: /en/newsletters/2022/10/05/#eclair-2435

  - title: "Jahresrückblick 2022: Asynchrone Zahlungen"
    url: /en/newsletters/2022/12/21/#async-payments

  - title: "Eclair #2464 fügt einen Trigger hinzu, der es einem Knoten ermöglicht, eine asynchrone Zahlung an einen Peer zu liefern"
    url: /en/newsletters/2023/01/04/#eclair-2464

  - title: "Idee für nicht-interaktive Kanal-Öffnungs-Commitments könnte schnelle Neuausrichtung für asynchrone Zahlungen ermöglichen"
    url: /en/newsletters/2023/01/11/#non-interactive-ln-channel-open-commitments

  - title: Anfrage nach Beweis, dass eine asynchrone Zahlung akzeptiert wurde
    url: /en/newsletters/2023/01/25/#request-for-proof-that-an-async-payment-was-accepted

  - title: Verwendung von Adaptor-Signaturen zum Nachweis, dass eine asynchrone Zahlung akzeptiert wurde
    url: /en/newsletters/2023/02/01/#ln-async-proof-of-payment

  - title: "LDK #2973 fügt Unterstützung für das Abfangen von Onion-Nachrichten zur Erleichterung asynchroner Zahlungen hinzu"
    url: /en/newsletters/2024/05/17/#ldk-2973

  - title: "LDK #3125 führt Unterstützung für Kodierung und Parsing von Nachrichten ein, die für asynchrone Zahlungen benötigt werden"
    url: /en/newsletters/2024/07/05/#ldk-3125

  - title: "Eclair #2865 ermöglicht das Aufwecken eines getrennten mobilen Peers für asynchrone Zahlungen oder Onion-Nachrichten"
    url: /en/newsletters/2024/09/06/#eclair-2865

  - title: "LDK #3140 fügt Unterstützung für die Zahlung statischer BOLT12-Rechnungen zum Senden asynchroner Zahlungen hinzu"
    url: /en/newsletters/2024/09/20/#ldk-3140

## Optional. Gleiches Format wie "primary_sources" oben
see_also:
  - title: Trampoline-Zahlungen
    link: topic trampoline payments

  - title: PTLCs
    link: topic ptlc

  - title: Signature-Adaptoren
    link: topic adaptor signatures

  - title: Zahlungsnachweis
    link: topic proof of payment

## Optional. Erzwingt die Anzeige (true) oder Nichtanzeige (false) des Stub-Themenhinweises.
## Standard ist die Anzeige, wenn page.content unter einer Schwellenwort-Anzahl liegt
#stub: false

## Erforderlich. Markdown-Formatierung verwenden. Nur ein Absatz. Keine Links erlaubt.
## Sollte weniger als 500 Zeichen sein
excerpt: >
  **Asynchrone Zahlungen** sind Zahlungen, die getätigt werden, wenn der
  Empfänger offline ist. Onchain-Zahlungen sind asynchron, aber interaktive
  Protokolle wie LN erfordern möglicherweise die Zusammenarbeit eines
  Dritten, um asynchrone Zahlungen zu ermöglichen.

---
Traditionelle Onchain-Bitcoin-Zahlungen sind asynchron, da der Empfänger
zu jeder Zeit ein Output-Skript (Bitcoin-Adresse) generieren und diese
Adresse an den Spender weitergeben kann, und dann kann der Spender diese
Adresse zu jeder Zeit bezahlen – auch wenn der Empfänger offline ist.
Der Prozess der Sicherung dieser Zahlung (Erhalten von Blockbestätigungen)
erfordert keine Aktion vom Empfänger.

Bei LN muss der Empfänger zum Zeitpunkt des Zahlungsempfangs ein Geheimnis
preisgeben, um diese Zahlung zu sichern. Dies erfordert, dass sowohl der
Sender als auch der Empfänger einer Zahlung gleichzeitig online sind.
In vielen Fällen ist es kein großes Problem für einen Spender, online zu sein,
da er den Ausgabeprozess initiiert hat und Aktionen auslösen kann, um
sicherzustellen, dass die Zahlung gesendet wird. Aber für einige Empfänger
ist es eine größere Herausforderung, online zu sein, um eine Zahlung zu
empfangen. Zum Beispiel könnte ein LN-Knoten, der auf einem Mobiltelefon läuft,
manchmal völlig vom Internet getrennt sein und zu anderen Zeiten keinen
Zugang zum Netzwerk haben, weil die App des Knotens im Hintergrund läuft.

Eine [Diskussion von 2021][offline ln] über die Verbesserung dieser Benutzererfahrung
führte zu mehreren Ideen darüber, wie ein Weiterleitungsknoten eine Zahlung
für einen empfangenden Knoten halten könnte, bis bekannt ist, dass der
Empfänger online ist. Die am besten beschriebene vertrauenslose Methode
in dieser Diskussion erforderte die Verwendung von [PTLCs][topic ptlc],
die bis Ende 2022 noch nicht zu LN hinzugefügt wurden. Eine alternative
[Methode][trampoline method], die im bestehenden Protokoll implementiert
werden könnte, beinhaltete die Verwendung von Trampoline-Relays.

Asynchrone Zahlungen sind auch ein Schlüsselmerkmal des [Ark][topic ark]-Protokolls.

{% include references.md %}
{% include linkers/issues.md issues="" %}
[offline ln]: https://gnusha.org/url/https://lists.linuxfoundation.org/pipermail/lightning-dev/2021-October/003307.html
[trampoline method]: /en/newsletters/2022/06/15/#trampoline-routing-and-mobile-payments
