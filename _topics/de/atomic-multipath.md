---
title: Atomic Multipath Payments (AMPs)
lang: de

## Optional. Kürzer Name für Referenzstil-Links z.B. "foo"
## ermöglicht die Verwendung des Links [topic foo][]. Nicht case-sensitive
shortname: amp

## Optional. Ein Eintrag wird zum Themenindex für jeden Alias hinzugefügt
title-aliases:
  - AMP
  # Obwohl üblich, bevorzuge ich es, "OG AMP" nicht in die Alias-Liste zu setzen -harding

## Erforderlich. Mindestens eine Kategorie, zu der dieses Thema gehört.
topic-categories:
  - Lightning Network
  - Privacy Enhancements

## Optional. Erzeugt einen Markdown-Link entweder als "[title][]" oder "[title](link)"
primary_sources:
    - title: Atomic Multipath Payments
      link: https://gnusha.org/url/https://lists.linuxfoundation.org/pipermail/lightning-dev/2018-February/000993.html

## Optional. Jeder Eintrag benötigt "title", "url" und "date". Kann auch "feature: true" verwenden, um den Eintrag fett darzustellen
optech_mentions:
  - title: "LN-Protokoll 1.1 Ziele: Multipath-Zahlungen"
    url: /en/newsletters/2018/11/20/#multi-path-payments

  - title: "LND #3957 fügt Code hinzu, der für Atomic Multipath Payments (AMP)-Unterstützung nützlich ist"
    url: /en/newsletters/2020/02/12/#lnd-3957

  - title: "LND #5108 fügt Unterstützung für spontane Multipath-Zahlungen mit AMP hinzu"
    url: /en/newsletters/2021/04/14/#lnd-5108

  - title: "LND #5159 fügt Unterstützung für das Senden spontaner AMPs hinzu"
    url: /en/newsletters/2021/05/05/#lnd-5159

  - title: "LND #5253 fügt Unterstützung für Atomic Multipath Payment (AMP)-Rechnungen hinzu"
    url: /en/newsletters/2021/05/19/#lnd-5253

  - title: "LND #5336 fügt die Möglichkeit hinzu, AMP-Rechnungen nicht-interaktiv wiederzuverwenden"
    url: /en/newsletters/2021/06/09/#lnd-5336

  - title: "LND 0.13.0-beta ermöglicht das Empfangen und Senden von Zahlungen mit AMP"
    url: /en/newsletters/2021/06/23/#lnd-0-13-0-beta

  - title: "LND #5803 ermöglicht mehrere spontane Zahlungen an dieselbe AMP-Rechnung"
    url: /en/newsletters/2021/11/03/#lnd-5803

  - title: "LND 0.14.0-beta ermöglicht mehrere spontane Zahlungen an dieselbe AMP-Rechnung"
    url: /en/newsletters/2021/11/24/#lnd-0-14-0-beta

  - title: "Jahresrückblick 2021: Atomic Multipath Payments"
    url: /en/newsletters/2021/12/22/#amp

## Optional. Gleiches Format wie "primary_sources" oben
see_also:
  - title: Simplified Multipath Payments (SMP)
    link: topic multipath payments

## Erforderlich. Markdown-Formatierung verwenden. Nur ein Absatz. Keine Links erlaubt.
## Sollte weniger als 500 Zeichen sein
excerpt: >
  **Atomic Multipath Payments (AMPs)**, manchmal auch als **Original AMP**
  oder **OG AMP** bezeichnet, ermöglichen es einem Zahlenden, mehrere Hashes zu bezahlen, 
  die alle von demselben Preimage abgeleitet sind - einem Preimage, das der Empfänger 
  nur rekonstruieren kann, wenn er eine ausreichende Anzahl von Anteilen erhält.
---
Im Gegensatz zu Simplified Multipath Payments ([SMP][topic multipath payments]) ermöglicht dies dem Empfänger nur dann, eine Zahlung zu akzeptieren, wenn er alle einzelnen Teile erhält. Jeder Anteil mit einem unterschiedlichen Hash erhöht die Privatsphäre, indem verhindert wird, dass die separaten Zahlungen von Dritten automatisch miteinander in Verbindung gebracht werden können. Der Nachteil des Vorschlags ist, dass der Zahlende alle Preimages auswählt, sodass das Wissen über das Preimage keinen kryptographischen Beweis dafür liefert, dass er tatsächlich an den Empfänger gezahlt hat.

Sowohl AMP als auch SMP ermöglichen es, HTLCs mit höherem Wert in mehrere HTLCs mit niedrigerem Wert aufzuteilen, die einzeln mit höherer Wahrscheinlichkeit erfolgreich sind, sodass ein Zahlender mit ausreichender Liquidität fast alle seine Mittel auf einmal verwenden kann, unabhängig davon, auf wie viele Kanäle diese Mittel verteilt sind.

{% include references.md %}
{% include linkers/issues.md issues="" %}
