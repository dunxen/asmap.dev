---
layout: default
title: ASMap
---

## ASMap Project

Currently opt-in since Bitcoin Core 0.20, asmap is a change to how Bitcoin Core ensures that it connects to a diverse set of outbound peers
beyond just netgroup bucketing. It considers IP-to-ASN mappings to further improve diversity of peers. ASNs (Autonomous System Numbers) are
a scarcer resource than netgroups, and the mapping passed to Bitcoin Core by default, map the gateway ASNs (bottlenecks) for IPs which have
sole control over what a node with that IP would see (since P2P connections are currently not encrypted). Essentially, it's an effective
mitigation against the Erebus attack, an eclipse attack where the attacker spoofs a part of the internet.

### Background reading

  * Gleb Naumenko's [BitMEX blog post]. Some of the tooling mentioned in the post is outdated/unmaintained. See [tools](###Tools) for more

### Tools

### Resources

  * If you're curious to learn more about BGP, see these [tools to explore BGP]

### Research


[BitMEX blog post]: https://blog.bitmex.com/call-to-action-testing-and-improving-asmap/
[Tools to explore BGP]: https://jvns.ca/blog/2021/10/05/tools-to-look-at-bgp-routes/