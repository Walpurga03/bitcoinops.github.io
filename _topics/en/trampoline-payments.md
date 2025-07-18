---
title: Trampoline payments

## Optional.  An entry will be added to the topics index for each alias
#title-aliases:
#  - Foo

## Required.  At least one category to which this topic belongs.  See
## schema for options
topic-categories:
  - Lightning Network

## Required.  Use Markdown formatting.  Only one paragraph.  No links allowed.
excerpt: >
  **Trampoline payments** are a proposed type of payment where the
  spender routes the payment to an intermediate node who can select the
  rest of the path to the final receiver.

## Optional.  Produces a Markdown link with either "[title][]" or
## "[title](link)"
primary_sources:
    - title: Outsourcing route computation with trampoline payments
      link: https://gnusha.org/url/https://lists.linuxfoundation.org/pipermail/lightning-dev/2019-March/001939.html

## Optional.  Each entry requires "title", "url", and "date".  May also use "feature:
## true" to bold entry
optech_mentions:
  - title: Trampoline payments for LN
    url: /en/newsletters/2019/04/02/#trampoline-payments-for-ln

  - title: BOLT PR and discussion about trampoline payments
    url: /en/newsletters/2019/08/07/#trampoline-payments

  - title: "Eclair #1209 adds experimental support for trampoline onion format"
    url: /en/newsletters/2019/11/20/#eclair-1209

  - title: "2019 year-in-review: trampoline payments"
    url: /en/newsletters/2019/12/28/#trampoline

  - title: Electrum 4.1.0 adds support for trampoline payments
    url: /en/newsletters/2021/05/19/#electrum-4-1-0-enhances-lightning-features

  - title: "Summary of LN developer conference, including discussion of trampoline payments"
    url: /en/newsletters/2021/11/10/#ln-summit-2021-notes

  - title: "Discussion about combining trampoline routing with first-hop payment holds"
    url: /en/newsletters/2022/06/15/#trampoline-routing-and-mobile-payments

  - title: "Eclair #2435 adds support for basic async payments for trampoline relay"
    url: /en/newsletters/2022/10/05/#eclair-2435

  - title: "Eclair #2810 allows trampoline routing infomation to use more than 400 bytes"
    url: /en/newsletters/2024/01/24/#eclair-2810

  - title: "Eclair #2811 allows trampoline payments to use a blinded path for the ultimate receiver"
    url: /en/newsletters/2024/01/31/#eclair-2811

  - title: "LDK #2756 adds support for including a trampoline routing packet in its messages"
    url: /en/newsletters/2024/03/27/#ldk-2756

  - title: "LDK #3446 adds support for including a trampoline payment flag in a BOLT12 invoice"
    url: /en/newsletters/2024/12/13/#ldk-3446

  - title: "LDK #3670 adds support for handling and receiving trampoline payments"
    url: /en/newsletters/2025/04/04/#ldk-3670

  - title: "Eclair #3109 extends its attributable failures support to trampoline payments"
    url: /en/newsletters/2025/06/27/#eclair-3109

## Optional.  Same format as "primary_sources" above
see_also:
  - title: "BOLTs PR #654: Trampoline Routing"
    link: https://github.com/lightningnetwork/lightning-rfc/pull/654
---
Using a single trampoline node necessarily reveals the destination to
it.  To regain privacy, a spender may require a payment be routed
through multiple trampoline nodes so that none of them knows whether
they're routing the payment to the final receiver or just another
intermediate trampoline node.

Although allowing trampoline nodes to select part of the path likely
requires paying more routing fees, it means the spender doesn't
need to know how to route payments to any arbitrary node---it's
sufficient for the spender to know how to route a payment to any
trampoline-compatible node.  This is advantageous for lightweight
LN clients that aren't able to track the full network graph because
they're often offline or run on underpowered mobile hardware.

{% include references.md %}
