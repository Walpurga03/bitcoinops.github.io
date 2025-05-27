---
title: ASICBoost
lang: de

## Optional. Kürzer Name für Referenzstil-Links, z.B. "foo"
## ermöglicht die Verwendung des Links [topic foo][]. Nicht case-sensitive
# shortname: foo

## Optional. Ein Eintrag wird im Themenindex für jeden Alias hinzugefügt
title-aliases:
  - Overt ASICBoost
  - Covert ASICBoost

## Erforderlich. Mindestens eine Kategorie, zu der dieses Thema gehört.
topic-categories:
  - Mining

## Optional. Erzeugt einen Markdown-Link entweder als "[title][]" oder "[title](link)"
primary_sources:
    - title: AsicBoost—A Speedup for Bitcoin Mining
      link: https://arxiv.org/abs/1604.00575

## Optional. Jeder Eintrag benötigt "title", "url" und "date". Kann auch "feature: true" verwenden, um den Eintrag hervorzuheben
optech_mentions:
  - title: Overt ASICBoost-Unterstützung für S9-Miner
    url: /en/newsletters/2018/10/30/#overt-asicboost-support-for-s9-miners

  - title: "Bitcoin Core #15471 entfernt Warnung, die fälschlicherweise bei der Verwendung von overt ASICBoost ausgelöst wurde"
    url: /en/newsletters/2019/03/05/#bitcoin-core-15471

  - title: "Frage zu Block-Vorlagen im Vergleich zu tatsächlichen Blöcken: ASICBoost erklärt einen Unterschied"
    url: /en/newsletters/2021/04/28/#why-does-the-mined-block-differ-so-much-from-the-block-template

## Optional. Gleiches Format wie "primary_sources" oben
see_also:
  - title: "BIP320: nVersion bits für allgemeine Verwendung"
    link: BIP320

## Erforderlich. Markdown-Formatierung verwenden. Nur ein Absatz. Keine Links erlaubt.
## Sollte weniger als 500 Zeichen sein
excerpt: >
  **ASICBoost** ist eine Technik zum speziellen Aufbau eines Bitcoin-Block-Headers,
  um die Anzahl der Operationen, die für das Finden einer bestimmten Menge an
  Proof of Work notwendig sind, um etwa 15% zu reduzieren.

---
ASICBoost kann in zwei Formen implementiert werden:

- **Overt ASICBoost** erfordert die Manipulation des nVersion-Feldes eines Block-Headers. Dies ist auf der Blockchain deutlich sichtbar. Minern, die overt ASICBoost nutzen möchten, wird empfohlen, die Version-Bits zu verwenden, die durch [BIP320][] für den allgemeinen Gebrauch reserviert sind.

- **Covert ASICBoost** erfordert die Manipulation eines Teils des Merkle-Root-Feldes eines Block-Headers. Dies kann unerkennbar durchgeführt werden, obwohl naive Implementierungen oft Hinweise hinterlassen.

  Covert ASICBoost ist nicht kompatibel mit Blöcken, die sekundäre Commitments zu ihren Transaktionen enthalten, wie es bei jedem Block der Fall ist, der eine Segwit-Transaktion enthält. Dies führte zu [Kontroversen][segwit asicboost], als entdeckt wurde, dass ein Mining-Hardware-Hersteller, der Segwit stark ablehnte, heimlich Funktionen in seine ASICs eingebaut hatte, um covert ASICBoost zu nutzen.

[segwit asicboost]: /en/topics/soft-fork-activation/#2016-7-bip9-bip148-and-bip91-the-bip141143-segwit-activation

{% include references.md %}
{% include linkers/issues.md issues="" %}
