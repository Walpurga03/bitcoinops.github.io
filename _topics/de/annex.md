---
title: Annex
lang: de

## Optional. Kürzer Name für Referenzstil-Links, z.B. "foo"
## ermöglicht die Verwendung des Links [topic foo][]. Nicht case-sensitive
# shortname: foo

## Optional. Ein Eintrag wird im Themenindex für jeden Alias hinzugefügt
#title-aliases:
#  - Foo

## Erforderlich. Mindestens eine Kategorie, zu der dieses Thema gehört
topic-categories:
  - Scripts and Addresses

## Optional. Erzeugt einen Markdown-Link mit "[title][]" oder "[title](link)"
primary_sources:
    - title: "BIP341: Taproot"
      link: bip341

## Optional. Jeder Eintrag benötigt "title" und "url". Kann auch "feature: true" verwenden, um den Eintrag hervorzuheben, sowie "date"
optech_mentions:
  - title: "Bitcoin Inquisition #22 fügt eine `-annexcarrier`-Laufzeitoption hinzu"
    url: /en/newsletters/2023/03/29/#bitcoin-inquisition-22

  - title: Diskussion über den Taproot-Annex
    url: /en/newsletters/2023/06/14/#discussion-about-the-taproot-annex

  - title: Vorschlag zur Speicherung gebührenabhängiger Timelock-Parameter im Taproot-Annex
    url: /en/newsletters/2024/01/03/#fee-dependent-timelocks

  - title: Plan zur Weiterleitung von Transaktionen mit bestimmten Taproot-Annexen in Libre Relay
    url: /en/newsletters/2025/03/28/#plan-to-relay-certain-taproot-annexes

## Optional. Gleiches Format wie "primary_sources" oben
see_also:
  - title: Taproot
    link: topic taproot

## Optional. Erzwingt die Anzeige (true) oder Nicht-Anzeige (false) des Stub-Themenhinweises.
## Standard ist die Anzeige, wenn page.content unterhalb einer Schwellenwort-Anzahl liegt
#stub: false

## Erforderlich. Markdown-Formatierung verwenden. Nur ein Absatz. Keine Links erlaubt.
## Sollte weniger als 500 Zeichen sein
excerpt: >
  Der Taproot-**Annex** ist ein optionales Feld in der Witness-Struktur von
  Segwit v1 (Taproot)-Eingaben, das derzeit keinen definierten Zweck hat.
  Wenn ein Annex vorhanden ist, müssen alle Taproot- und Tapscript-Signaturen
  sich auf seinen Wert festlegen.

---
Mit der Implementierung und Aktivierung von Taproot wurde der Annex für zukünftige Upgrades reserviert. Transaktionen, die einen Annex enthielten, wurden standardmäßig nicht von Bitcoin Core weitergeleitet oder gemined. Es gab mehrere Ideen zur Verwendung des Annex sowie mindestens einen Versuch, eine erweiterbare Datenstruktur für das Feld zu definieren.

{% include references.md %}
{% include linkers/issues.md issues="" %}
