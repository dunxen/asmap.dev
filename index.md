---
layout: default
title: ASMap
---

Currently opt-in [since Bitcoin Core v0.20], ASMap is a change to how Bitcoin Core ensures that it connects to a diverse set of outbound peers
beyond just netgroup bucketing. It considers IP-to-ASN mappings to further improve diversity of peers. ASNs (Autonomous System Numbers) are
a scarcer resource than netgroups, and the mapping passed to Bitcoin Core by default, map the gateway ASNs (bottlenecks) for IPs which have
sole control over what a node with that IP would see (since P2P connections are currently not encrypted). Essentially, it's an effective
mitigation against the Erebus attack, an eclipse attack where the attacker spoofs a part of the internet.

## Background reading

  * Gleb Naumenko's [BitMEX blog post]. Some of the tooling mentioned in the post is outdated/unmaintained. See [tools](##Tools) for more.

## Tools

* [Kartograf]: An auditable and repeatable IP to ASN mapping tool. Kartograf pulls in data from various public of internet routing data
  and combines them in a purely functional way to minimize the possibility of accidental BGP leaks. (Experimental)
* [Tools to explore BGP] by Julia Evans which also describes ASs, BGP and  BGP routes.

## Research

  * Some [insights] into the Bitcoin P2P network, by [virtu]. In _Insights 2: Autonomous systems & ASMAP_, Kartograf is used for generating asmaps for
    Bitcoin Core.

[since Bitcoin Core v0.20]: https://github.com/bitcoin/bitcoin/blob/322ec63b01499c1ec52d3912ee382ebd59f2366b/doc/release-notes/release-notes-0.20.0.md?plain=1#L163
[BitMEX blog post]: https://blog.bitmex.com/call-to-action-testing-and-improving-asmap/
[Tools to explore BGP]: https://jvns.ca/blog/2021/10/05/tools-to-look-at-bgp-routes/
[Insights]: https://raw.githubusercontent.com/virtu/talks/master/2023-03-02-advancing-bitcoin/slides.pdf
[virtu]: https://github.com/virtu
