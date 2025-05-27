---
title: Unbeabsichtigte Konfiszierung
lang: de

## Optional. Kürzer Name für Referenzstil-Links, z.B. "foo"
## ermöglicht die Verwendung des Links [topic foo][]. Nicht case-sensitive
# shortname: foo

## Optional. Ein Eintrag wird im Themen-Index für jeden Alias hinzugefügt
#title-aliases:
#  - Foo

## Erforderlich. Mindestens eine Kategorie, zu der dieses Thema gehört
topic-categories:
  - Soft Forks
  - Transaction Relay Policy

## Optional. Erzeugt einen Markdown-Link mit "[title][]" oder "[title](link)"
#primary_sources:
#    - title: Test
#    - title: Beispiel
#      link: https://example.com

## Optional. Jeder Eintrag benötigt "title" und "url". Kann auch "feature: true" verwenden, um den Eintrag fett darzustellen sowie "date"
optech_mentions:
  - title: "Ungültigmachung von `OP_CODESEPARATOR` könnte verhindern, dass existierende UTXOs ausgegeben werden"
    url: /en/newsletters/2019/03/12/#cleanup-soft-fork-proposal-discussion

  - title: "Amnestie vorgeschlagen für potentielle alte Verwendungen von `OP_CODESEPARATOR` in neuem Cleanup-Vorschlag"
    url: /en/newsletters/2024/04/03/#revisiting-consensus-cleanup

## Optional. Gleiches Format wie "primary_sources" oben
see_also:
  - title: Soft Fork-Aktivierung
    link: topic soft fork activation

## Optional. Erzwingt die Anzeige (true) oder Nicht-Anzeige (false) des Stub-Themen-Hinweises.
## Standard ist die Anzeige, wenn page.content unter einer Schwellenwortanzahl liegt
#stub: false

## Erforderlich. Markdown-Formatierung verwenden. Nur ein Absatz. Keine Links erlaubt.
## Sollte weniger als 500 Zeichen umfassen
excerpt: >
  **Unbeabsichtigte Konfiszierung** kann auftreten, wenn ein schlecht gestalteter
  Soft Fork dauerhaft verhindert, dass ein Nutzer eine Transaktion bestätigen lassen kann.

---
Ein Soft Fork ist eine Einschränkung der vorherigen Konsensregeln. Wenn ein Soft
Fork die Nutzung einer Funktion übermäßig einschränkt, die ein Nutzer benötigt,
um einige zuvor erhaltene Bitcoins auszugeben, werden diese Bitcoins nicht ausgebbar,
es sei denn, das Verhalten des Soft Forks wird in einem späteren Hard Fork geändert.

Eine solche Konfiszierung kann absichtlich erfolgen, wobei die Betreiber der
wirtschaftlichen Full Nodes, die die Konsensregeln durchsetzen, entscheiden müssen,
ob die Vorteile eines konfiskatorischen Soft Forks seine Probleme überwiegen. Aber
es kann auch versehentlich passieren, wenn ein Soft Fork schlecht konzipiert ist oder
wenn die Kommunikation zwischen Konsensentwicklern und Entwicklern von Vertragsprotokollen
mangelhaft ist. Drei besondere Risiken stechen hervor:

- **Unbekannte Verwendung von Upgrade-Funktionen:** Einige Funktionen des Konsens-Protokolls,
  wie die `OP_NOPx`- und `OP_SUCCESSx`-Opcodes, sind für zukünftige Soft Forks reserviert.
  Wenn jemand beginnt, sie vor einem Soft Fork zu verwenden, könnte er Opfer einer
  unbeabsichtigten Konfiszierung werden. Aus diesem Grund empfiehlt Bitcoin Optech
  *sehr nachdrücklich*, dass jeder, der die Verwendung einer für Soft Fork-Upgrades reservierten
  Funktion in Betracht zieht, seine Pläne öffentlich in den Kommunikationskanälen der
  Protokoll-Entwickler ankündigt und proaktiv alle Diskussionen über neue Soft Forks
  auf Änderungen an den verwendeten Funktionen überwacht.

- **Vorsignierte Transaktionen:** Einige Vertragsprotokolle und Verwendungszwecke von
  Bitcoin können erfordern, dass ein Benutzer eine Ausgabetransaktion generiert, sie mit den
  notwendigen privaten Schlüsseln signiert und dann die privaten Schlüssel löscht.
  Dies verhindert, dass sie alternative Versionen der Transaktion signieren können.
  Wenn die Bitcoin-Konsensregeln geändert werden, um die Ausgabetransaktion ungültig
  zu machen, gehen die Gelder des Benutzers verloren. Optech empfiehlt, dass vorsignierte
  Transaktionsprotokolle gut dokumentiert sind, sie gegen Standardregeln geprüft werden
  (siehe unten) und dass jeder, der sie verwendet, alle Diskussionen über neue Soft
  Fork-Vorschläge auf Änderungen überwacht, die diese Transaktionen ungültig machen würden.

- **Festgelegte Skripte:** P2SH-, P2WSH- und P2TR-Skriptpfade sind alle Skripte,
  die nicht auf der Blockchain erscheinen, wenn der Benutzer sich verpflichtet,
  sie möglicherweise zu verwenden. Jede Soft Fork-Einschränkung der Skriptsprache
  kann ein zuvor erfüllbares Skript in eines verwandeln, das nicht erfüllt werden kann.
  Optech macht hier die gleiche Empfehlung wie für vorsignierte Transaktionen.

## Beziehung zur Transaktions-Standardheitsrichtlinie

Full Nodes wie Bitcoin Core leiten bestimmte Transaktionen nicht weiter,
lassen sie nicht in ihre Mempools zu oder fügen sie nicht in Block-Templates ein
– selbst wenn diese Transaktionen nach den aktuellen Konsensregeln gültig sind.
Es gibt eine Vielzahl von Gründen für die Transaktions-Relay-Richtlinien, aber
einige dieser Richtlinien existieren, um jeden davon abzuhalten, Funktionen zu
verwenden, die für zukünftige Soft Fork-Upgrades reserviert sind.

Wenn du beispielsweise gegenwärtig eine Transaktion erstellst, die `OP_NOP9` ausführt,
wird diese Transaktion als nicht standardmäßig betrachtet und nicht weitergeleitet,
während sie unbestätigt ist. Sie ist immer noch in einem Block gültig, und alle
Full Nodes müssen sie in einem Block akzeptieren, um im Konsens zu bleiben.

Das Ziel ist, dass jeder, der beginnt, eine reservierte Funktion zu verwenden, schnell
entdeckt, dass Transaktionen, die diese Funktion verwenden, schwer zu minen sind.
Sie können dann entweder zu einer alternativen Methode wechseln, um dasselbe zu erreichen,
oder sie können Full-Node-Entwickler davon überzeugen, ihre Relay-Policy zu ändern, was
hoffentlich als ausreichende öffentliche Benachrichtigung dient, dass die Funktion
verwendet wird, und eine spätere unbeabsichtigte Konfiszierung verhindert.

{% include references.md %}
{% include linkers/issues.md issues="" %}
