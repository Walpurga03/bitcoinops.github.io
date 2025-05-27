---
title: Adaptor-Signaturen
lang: de

## Optional. Kürzer Name für Referenzstil-Links, z.B. "foo"
## ermöglicht die Verwendung des Links [topic foo][]. Nicht case-sensitive
# shortname: foo

## Optional. Ein Eintrag wird im Themen-Index für jeden Alias hinzugefügt
title-aliases:
  - Signature-Adaptoren
  - Scriptless Scripts

## Erforderlich. Mindestens eine Kategorie, zu der dieses Thema gehört
topic-categories:
  - Contract Protocols
  - Privacy Enhancements
  - Scripts and Addresses

## Erforderlich. Markdown-Formatierung verwenden. Nur ein Absatz. Keine Links erlaubt.
## Sollte weniger als 500 Zeichen umfassen
excerpt: >
  **Adaptor-Signaturen** (auch **Signature-Adaptoren** genannt) sind
  zusätzliche Signaturdaten, die sich auf einen versteckten Wert festlegen.
  Wenn ein Adaptor mit einer entsprechenden Signatur kombiniert wird, enthüllt er
  den versteckten Wert. Alternativ enthüllt der Adaptor, wenn er mit dem versteckten Wert
  kombiniert wird, die Signatur. Andere Personen können sekundäre
  Adaptoren erstellen, die das Commitment wiederverwenden, auch wenn sie den versteckten Wert
  nicht kennen. Dies macht Adaptoren zu einem mächtigen Werkzeug für die Implementierung von Sperrfunktionen
  in Bitcoin-Verträgen.

## Optional. Erzeugt einen Markdown-Link mit "[title][]" oder "[title](link)"
primary_sources:
    - title: Scriptless scripts slides (PDF)
      link: https://download.wpsoftware.net/bitcoin/wizardry/mw-slides/2017-05-milan-meetup/slides.pdf

    - title: One-time verifiably encrypted signatures (PDF)
      link: https://github.com/LLFourn/one-time-VES/blob/master/main.pdf

    - title: Documentation for scriptless script protocols
      link: https://github.com/BlockstreamResearch/scriptless-scripts

## Optional. Jeder Eintrag benötigt "title", "url" und "date". Kann auch "feature: true" verwenden, um den Eintrag fett darzustellen
optech_mentions:
  - title: "Präsentation: Blockchain-Designmuster: Schichten und Skalierungsansätze"
    url: /en/newsletters/2019/09/18/#blockchain-design-patterns-layers-and-scaling-approaches
    date: 2019-09-18

  - title: "Taproot-Datenschutzgewinne, einschließlich der von Signature-Adaptoren"
    url: /en/newsletters/2020/02/19/#tap1
    date: 2020-02-19

  - title: "Boomerang-Verträge mit Signature-Adaptoren für LN-Latenz & Durchsatz"
    url: /en/newsletters/2020/02/26/#boomerang-redundancy-improves-latency-and-throughput-in-payment-channel-networks
    date: 2020-02-26

  - title: ECDSA-Signature-Adaptoren für Statechains mit sicherer Mehrparteien-Berechnung
    url: /en/newsletters/2020/04/01/#implementing-statechains-without-schnorr-or-eltoo
    date: 2020-04-01

  - title: Arbeit an PTLCs für LN mit vereinfachten ECDSA-Signature-Adaptoren
    url: /en/newsletters/2020/04/08/#work-on-ptlcs-for-ln-using-simplified-ecdsa-adaptor-signatures
    date: 2020-04-08

  - title: Zahlung für einen PTLC-Pointlock mittels Signature-Adaptoren
    url: /en/newsletters/2020/06/24/#continued-discussion-about-ln-atomicity-attack
    date: 2020-06-24

  - title: Mehrparteien-ECDSA für scriptless LN-Kanäle
    url: /en/newsletters/2018/10/09/#multiparty-ecdsa-for-scriptless-lightning-network-payment-channels
    date: 2018-10-09

  - title: Schnelles Mehrparteien-ECDSA, kompatibel mit Signature-Adaptoren
    url: /en/newsletters/2018/10/23/#two-papers-published-on-fast-multiparty-ecdsa
    date: 2018-10-23

  - title: Diskussion über Probleme in LN, die mit Signature-Adaptoren lösbar sind
    url: /en/newsletters/2018/11/06/#discussion-about-improving-lightning-payments
    date: 2018-11-06

  - title: libsecp256k1-zkp-Bibliothek mit Unterstützung für Signature-Adaptoren aktualisiert
    url: /en/newsletters/2019/02/26/#schnorr-ready-fork-of-libsecp256k1-available
    date: 2019-02-26

  - title: "Q&A: Was ist der Unterschied zwischen Taproot und Signature-Adaptoren?"
    url: /en/newsletters/2019/02/26/#taproot-and-scriptless-scripts-both-use-schnorr-but-how-are-they-different
    date: 2019-02-26

  - title: "Verwendung von Signature-Adaptoren für asymmetrische Witness-Zahlungskanäle"
    url: /en/newsletters/2020/09/02/#witness-asymmetric-payment-channels

  - title: Überarbeiteter Vorschlag für asymmetrische Witness-Kanäle mit Signature-Adaptoren
    url: /en/newsletters/2020/10/14/#updated-witness-asymmetric-payment-channel-proposal

  - title: "Jahresrückblick 2020: Signature-Adaptoren für LN-Kanal-Commitments"
    url: /en/newsletters/2020/12/23/#ptlcs

  - title: "Libsecp256k1-zkp #117 fügt Unterstützung für vereinfachte ECDSA-Signature-Adaptoren hinzu"
    url: /en/newsletters/2021/04/28/#support-for-ecdsa-signature-adaptors-added-to-libsecp256k1-zkp

  - title: "Frage: Warum verhindert blockweite Signatur-Aggregation Adaptor-Signaturen?"
    url: /en/newsletters/2021/06/30/#why-does-blockwide-signature-aggregation-prevent-adaptor-signatures

  - title: "Vorbereitung auf Taproot: Signature-Adaptoren"
    url: /en/newsletters/2021/08/18/#preparing-for-taproot-9-signature-adaptors

  - title: Verwendung von Signature-Adaptoren zum Nachweis der Akzeptanz einer LN-Async-Zahlung
    url: /en/newsletters/2023/02/01/#ln-async-proof-of-payment

  - title: "Analyse der Sicherheit von Signature-Adaptoren"
    url: /en/newsletters/2023/05/03/#analysis-of-signature-adaptor-security

  - title: "LN-Entwicklerdiskussion über Variationen von Signature-Adaptoren zur Hinzufügung von PTLC-Unterstützung"
    url: /en/newsletters/2024/10/18/#ptlcs

## Optional. Gleiches Format wie "primary_sources" oben
see_also:
  - title: Schnorr-Signaturen
    link: topic schnorr signatures

  - title: MuSig-Schlüssel- und Signaturaggregation
    link: topic musig

  - title: Verwendung von Schnorr-Subtraktion zur Erstellung privaterer Coinswaps
    link: https://joinmarket.me/blog/blog/flipping-the-scriptless-script-on-schnorr/

  - title: Adaptor-Signaturen für Discreet Log Contracts
    link: https://lists.launchpad.net/mimblewimble/msg00485.html
---
Verträge in Bitcoin erfordern oft einen Sperrmechanismus, um die
Atomizität einer Reihe von Zahlungen sicherzustellen – entweder alle Zahlungen sind erfolgreich oder
alle schlagen fehl. Diese Sperre wurde traditionell dadurch realisiert, dass
alle Zahlungen in der Menge sich auf das gleiche Hash-Digest-Preimage festlegen; wenn
die Partei, die das Preimage kennt, es on-chain offenlegt, erfahren alle anderen es
und können ihre eigenen Zahlungen entsperren. Üblicherweise verwendete *Hashlocks*
in Bitcoin verbrauchen etwa 67 Bytes <!-- push32:1, preimage:32,
push32:1, hash:32, OP_CHECKEQUALVERIFY:1 --> und enthüllen die Verbindung
zwischen den Zahlungen, weil sie alle dasselbe Preimage und
denselben Digest verwenden.

Im Vergleich dazu müssen Signature-Adaptoren nie on-chain veröffentlicht werden. Für jeden,
der keinen entsprechenden Adaptor hat, sieht eine mit einem Adaptor erstellte Signatur
wie jede andere digitale Signatur aus, was Adaptoren erhebliche Effizienz-
und Datenschutzvorteile gegenüber Hashlocks verschafft.

### Beispiel

Die vielfältigen Verwendungen von Signature-Adaptoren lassen sich an einem einfachen
Coinswap-Protokoll erkennen. Zum Beispiel kann Alice Bob einen Adaptor
für eine unsignierte Transaktion geben, die ihm 1 BTC verspricht. Ein
Adaptor allein kann nicht als BIP340-Signatur verwendet werden, also
hat Alice Bob noch nicht bezahlt.

Was der Adaptor Bob bietet, ist eine Verpflichtung auf Alices versteckten
Wert. Dieses Commitment enthält einen Parameter, mit dem Bob einen
zweiten Adaptor erstellen kann, der sich auf denselben versteckten Wert wie Alices
Adaptor festlegt. Bob kann diese Verpflichtung eingehen, selbst ohne Alices
versteckten Wert oder seine eigene Signatur für diese Verpflichtung zu kennen. Bob gibt
Alice seinen Adaptor und eine entsprechende unsignierte Transaktion, die
ihr 1 BTC verspricht.

Alice kennt den versteckten Wert schon immer, sie kann also den versteckten
Wert mit Bobs Adaptor kombinieren, um seine Signatur für die
Transaktion zu erhalten, die sie bezahlt. Sie überträgt die Transaktion und
erhält Bobs Zahlung. Wenn Bob diese Transaktion on-chain sieht, kann er
deren Signatur mit dem Adaptor, den er Alice gegeben hat, kombinieren,
was ihm ermöglicht, den versteckten Wert abzuleiten. Dann kann er
diesen versteckten Wert mit dem Adaptor kombinieren, den Alice ihm zuvor gab.
Bob überträgt diese Transaktion, um Alices Zahlung zu erhalten und vervollständigt so den Coinswap.

Neben Coinswaps gibt es mehrere andere [vorgeschlagene Anwendungen][scriptless
scripts repo] für Adaptor-Signaturen.

<div class="qa_details">
<details markdown="1">

<summary>Klicken Sie, um dasselbe Coinswap-Beispiel in mathematischen Begriffen anzuzeigen</summary>

*Im folgenden Beispiel gehen wir von der Verwendung von BIP340-
Schnorr-Signaturen aus. Wir verwenden Kleinbuchstaben für Skalare und
Großbuchstaben für elliptische Kurvenpunkte. Wir stellen
Verkettung mit `||` dar und die Hash-Funktion mit `H()`.*

Alice erstellt eine gültige Signaturverpflichtung (`s`) für die Transaktion, die Bob bezahlt
(`m`), unter Verwendung ihres privaten Schlüssels (`p`), der ihrem öffentlichen Schlüssel
entspricht (`P = pG`). Sie verwendet auch einen privaten Zufallswert (`r`), einen versteckten Wert
(`t`) und die elliptischen Kurvenpunkte dafür (`R = rG, T = tG`):

    s = r + t + H(R + T || P || m) * p

Sie subtrahiert `t` von der Signaturverpflichtung, um einen Signatur-Adaptor zu erzeugen:

    s' = s - t

Sie gibt Bob den Adaptor, der aus den folgenden
Daten besteht:

    s', R, T

Bob kann den Adaptor überprüfen:

    s' * G ?= R + H(R + T || P || m) * P

Aber der Adaptor ist keine gültige BIP340-Signatur. Für eine gültige Signatur erwartet BIP340
`x` und `Y`, die mit dem Ausdruck verwendet werden:

    x * G ?= Y + H(Y || P || m) * P

Jedoch:

- Wenn Bob `Y = R` setzt, damit es mit dem `s'` übereinstimmt, das er im
  Adaptor erhalten hat, dann wird BIP340 bei `H(R || P || m)`
  fehlschlagen, da Alice ihren Hash mit `H(R + T || P || m)` berechnet hat.

- Wenn Bob `Y = R + T` setzt, damit es mit `H(R + T || P || m)` übereinstimmt, wird BIP340
  beim anfänglichen `Y` fehlschlagen, da Bob `R + T`
  anstelle des benötigten `R` bereitstellt.

Daher kann Bob den Adaptor nicht als BIP340-Signatur verwenden.
Er kann jedoch seinen eigenen Adaptor damit erstellen. Dies ist ähnlich der
Signatur, die Alice erstellt hat, aber Bob verpflichtet sich hier nicht auf `t`, da Bob
diesen Wert nicht kennt. Alle Variablen hier außer `T` sind für Bob anders
als für Alice:

    s = r + H(R + T || P || m) * p

Im Gegensatz zu Alice muss Bob seine Signatur nicht anpassen. Bobs Signaturverpflichtung `s`
ist kein Teil einer gültigen Signatur, weil sie sich auf `r` und `R + T` festlegt, was
aus den gleichen Gründen wie zuvor beschrieben nicht die BIP340-Verifizierung bestehen wird.
Um gültig zu sein, muss die Signatur sich auf `r + t` und `R + T` festlegen,
was Bob nicht erzeugen kann, da er `t` nicht kennt.

Bob gibt Alice seinen Adaptor:

    s, R, T

Alice kannte `T` bereits, aber `(s, R, T)` ist ein Standard-Signatur-
Adaptor, daher verwenden wir seine vollständige Form. Alice kann aus diesem Adaptor eine
Signatur erzeugen, indem sie den versteckten Wert `t` verwendet, den
bisher nur sie kennt:

    (s + t) * G ?= R + T + H(R + T || P || m) * P

Alice verwendet die Signatur, um Bobs Transaktion zu übertragen, die
sie bezahlt. Wenn Bob `(s + t)` on-chain sieht, kann er den Wert von `t` erfahren:

    t = (s + t) - s

Er kann dann `t` verwenden, um den Adaptor zu lösen, den Alice ihm zuvor
gegeben hat:

    (s' + t) * G ?= R + T + H(R + T || P || m) * P

Bob verwendet diese Signatur, um die Transaktion zu übertragen, die Alice
ihm ursprünglich gegeben hat.

</details><br>
</div>

### Beziehung zu Mehrparteien-Signaturen

Signature-Adaptoren können normalerweise einen Vertrag nicht vollständig allein
absichern. Zum Beispiel könnte Alice in der obigen Beschreibung eines Coinswaps
ihre Zahlung an Bob doppelt ausgeben, nachdem sie Bobs
Signatur erfahren hat, oder Bob hätte umgekehrt dasselbe versuchen können (mit mehr
Schwierigkeit, da wir annahmen, dass Alices Transaktion eine Bestätigung hatte).
Dieses Problem wird normalerweise durch Kombination von Signature-Adaptoren mit
Mehrparteien-Signaturen gelöst. Zum Beispiel zahlt Alice ihr Geld in eine
Adresse ein, die nur ausgegeben werden kann, wenn sowohl sie als auch Bob zusammenarbeiten, um
eine gültige Signatur zu erstellen. Jetzt kann Alice Bob einen Adaptor
für ihre Hälfte der Mehrparteien-Signatur bereitstellen, den Bob in völliger
Sicherheit akzeptieren kann, da er weiß, dass Alice die Mittel nicht doppelt ausgeben könnte
ohne seine Beteiligung. Dies kann zusätzlich eine zeitlich begrenzte
Rückerstattungsoption erfordern, falls eine Partei die Signierung verweigert.

Im [Schnorr-Signaturschema][topic schnorr signatures]
werden Signature-Adaptoren üblicherweise in Kombination mit Mehrparteien-Signatur-
Schemata wie [MuSig][topic musig] vorgeschlagen, um der veröffentlichten
Signatur das Aussehen einer Einzelpartei-Signatur zu geben, was
Privatsphäre und Effizienz verbessert. Dies ist auch in ECDSA möglich, erfordert aber
neuartige Algorithmen, die entweder vergleichsweise langsam sind oder
zusätzliche Sicherheitsannahmen benötigen. Stattdessen existiert ein [alternatives Schema][otves] für Adaptor-
Signaturen für Bitcoin, das 2-von-2 `OP_CHECKSIG` Multisig verwendet;
dies ist weniger effizient und möglicherweise weniger privat – aber arguierbar
einfacher und sicherer als Mehrparteien-ECDSA.

{% include references.md %}
[otves]: https://github.com/LLFourn/one-time-VES/blob/master/main.pdf
[scriptless scripts repo]: https://github.com/ElementsProject/scriptless-scripts
