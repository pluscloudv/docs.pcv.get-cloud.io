---
title: "Netzwerk"
linkTitle: "Netzwerk"
weight: 200
date: 2023-03-05
description: >
  Konfiguration des virtuellen Netzwerks
---

In jedem virtuellen Datecenter (vDC) steht Ihnen ein eigenständigs virtuelles Netzwerk zur Verfügung.
Dieses wird mit einer minimalen Vorkonfiguration ausgeliefert um Ihnen größtmögliche Flexibilität zu ermöglichen.
Sie können natürlich auch gegebenenfalls bereits angelegte Netze löschen oder umkonfigurieren.


Wir empfehlen innerhalb des virtuellen Datacenters nur [RFC1918](https://www.ietf.org/rfc/rfc1918)-Netze zu verwenden.
Das sind diejenigen Netze, die für die lokale Nutzung reserviert sind und nicht im Internet geroutet werden.
Außerdem sollten Sie bei Ihren Planung bereits berücksichtigen, ob und welche Netze sie gegebenenfalls per VPN mit den Cloudnetzen verbinden möchten. 
Hier empfehlen wir mögliche Adresskonflikte zu identifizieren und auf die mehrfache Vergabe von IP-Adressen an verschiedene Endpunkte zu verzichten.


Standardmäßig ist keine Kommunikationmöglichkeit zwischen dem oder den Netzen der virtuellen Datacenter mit der Außenwelt.
Diese müssen Sie bei Bedarf selbst konfigurieren. 
Hierzu können Sie für ausgehenden Datenverkehr [SNAT-Regeln]({{< relref "edge-gateway/snat" >}})
und für eingehenden Datenverkehr [DNAT-Regeln]({{< relref "edge-gateway/dnat" >}}) verwenden.
Wir empfehlen Ihnen außerdem die Nutzung der im [Edge-Gateway]({{< relref "edge-gateway" >}}) enthaltenen [Firewall]({{< relref "edge-gateway/firewall" >}}) .
