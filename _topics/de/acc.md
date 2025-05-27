---
title: Rechenschaftspflichtige Computing-Verträge
lang: de

## Optional. Kürzer Name für Referenzstil-Links, z.B. "foo"
## ermöglicht die Verwendung des Links [topic foo][]. Nicht case-sensitive
shortname: ACC

## Optional. Ein Eintrag wird im Themen-Index für jeden Alias hinzugefügt
title-aliases:
  - BitVM
  - Zero-Knowledge Contingent Payments (ZKCP)

## Erforderlich. Mindestens eine Kategorie, zu der dieses Thema gehört
topic-categories:
  - Vertragsprotokole

## Optional. Erzeugt einen Markdown-Link mit "[title][]" oder "[title](link)"
#primary_sources:
#    - title: Test
#    - title: Beispiel
#      link: https://example.com

## Optional. Weniger als 500 Zeichen. Keine Links.
excerpt: >
  **Rechenschaftspflichtige Computing-Verträge (ACC)** sind Zahlungen,
  die die empfangende Partei ausgeben kann, wenn sie nachweisbar eine
  bestimmte Funktion auf einen bestimmten Eingabesatz ausführt.
  Wenn die empfangende Partei die Funktion nicht ausführt oder nicht
  korrekt ausführt, kann die zahlende Partei die Zahlung nach einer
  gewissen Zeit zurückfordern.
---
Beispielsweise behauptet Alice, sie habe eine Lösung für ein Rätsel. Bob möchte
die Lösung des Rätsels kaufen, aber Alice ist nicht bereit, ihm eine Lösung zu geben, bis
sie garantiert eine Zahlung erhält. Bob ist ebenso unwillig, Alice zu bezahlen, bis er
sicher ist, dass die Lösung korrekt ist. Sie entscheiden sich, ein Programm zu schreiben,
das true zurückgibt, wenn es überprüft, dass die Lösung korrekt ist. Dann zahlt Bob Geld
auf einen Transaktionsoutput, der es Alice ermöglicht, das Geld zu beanspruchen, wenn sie
eine Lösung vorlegt, die vom Programm überprüft wurde. Wenn die Lösung falsch ist, ist
entweder Alices Ausgabe ungültig, oder sie muss eine Strafe zahlen, die gleich oder
höher als der Betrag der Zahlung ist.

Es gab mehrere Vorschläge und Implementierungen dieser Idee für Bitcoin:

- [Zero-Knowledge Contingent Payments][zkcp] (ZKCPs) ermöglichen es Alice,
  zu beweisen, dass sie das Programm mit ihrer Rätsellösung ausgeführt hat und dass die
  Lösung einen bestimmten Hash-Digest hat. Bob kann dann einen
  [HTLC][topic HTLC] erstellen, der Alice bezahlt, wenn sie das Preimage für
  diesen Hash-Digest offenlegt. Wenn Alice es nicht offenlegt, kann Bob seine
  Mittel nach Ablauf der HTLC-Zeit zurückfordern.

- [BitVM][] ermöglicht es Bob, Geld in einen Vertrag einzuzahlen, der
  das Programm kompakt referenziert, das sie zur Überprüfung verwenden.
  Alice kann dann die Lösung bereitstellen. Wenn Bob zufrieden ist, gibt er das
  Geld an Alice weiter. Wenn er nicht handelt, kann Alice das Geld nach einer
  gewissen Zeit beanspruchen. Wenn er nicht zufrieden ist, kann er Alice herausfordern,
  zu beweisen, dass ihr Programm true zurückgibt, wenn es mit ihrer
  Lösung ausgeführt wird, und die Herausforderung in mehrere Schritte unterteilen,
  die jeweils eine On-Chain-Transaktion erfordern. BitVM ist heute auf Bitcoin verfügbar.

- [MATT][topic matt] funktioniert ähnlich wie BitVM, obwohl es einen Soft
  Fork erfordert. Als Kompromiss kann es aufgrund der Änderung der Konsensregeln,
  die diese Art des Beweisens effizient machen, viel effizienter sein als BitVM.

{% include references.md %}
{% include linkers/issues.md issues="" %}
[zkcp]: https://bitcoincore.org/en/2016/02/26/zero-knowledge-contingent-payments-announcement/
[bitvm]: /de/newsletters/2023/10/18/#payments-contingent-on-arbitrary-computation
