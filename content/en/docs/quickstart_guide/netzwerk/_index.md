---
title: "Basis-Netzwerkkonfiguration"
linkTitle: "Basis-Netzwerkkonfiguration"
weight: 8
date: 2023-02-21
description: >
  Show your user how to work through some end to end examples.
---
Ihrer pluscloud-Umgebung wird automatisch eine VMware Edge-Gateway Appliance zugewiesen. Diese stellt für Ihre Umgebung den Zugang zum Internet zur Verfügung. Des weiteren bietet es diverse Dienste an, z. B. Firewall, Loadbalancing, NAT und VPN. Zu diesem Zeitpunkt erstellte virtuelle Maschinen haben keine Verbindung zur Außenwelt und müssen zunächst über passende NAT- und Firewall-Regeln im Edge-Gateway verbunden werden. 

---
Wenn Sie unter Netzwerk auf den Menüpunkt Netzwerke im linken Navigationsmenü klicken, sehen Sie alle bestehenden Netzwerke. Hier sollte bereits ein Organisationsnetzwerk verfügbar sein.

<img src="./images/netzwerke.png" width="400">

---
Ihr Organisationsnetzwerk sollte im Namen Ihre Kundennummer enthalten und bei Netzwerktyp den Status Weitergeleitet aufweisen. Die erste Adresse des verwendeten Subnetzes ist hierbei an die Edge-Gateway Appliance gebunden.

<img src="./images/netzwerk_config.png" width="400">

---
Ein fehlendes Organisationsnetzwerk sowie weitere Netze können Sie über die Schaltfläche Neu anlegen.

<img src="./images/neues_netzwerk.gif" width="400">


Beim Typ des zu erstellenden Netzwerks bietet die Option weitergeleitet die Möglichkeit, Ihr Edge-Gateway auszuwählen und externe Kommunikation zu ermöglichen. Isolierte Netzwerke stehen nur Ihren virtuellen Maschinen zur Verfügung und sind von externen Verbindungen abgekoppelt.

Im Wizard für weitergeleitete Netzwerke sind folgende Parameter relevant:

- Typ:  Unterscheidet, ob ein Netz weitergeleitet oder isoliert ist. Nur weitergeleitete Netzwerke bieten eine Konnektivität nach außen und eine Anbindung an das Edge-Gateway.
- Edge-Gateway: Unter diesem Punkt kann die Verbindung zum bereits bestehenden Edge-Gateway hergestellt werden. Als Schnittstellentyp ist im Normalfall "Intern" auszuwählen.
- Gast-VLAN zulassen: Ermöglicht die Erstellung von VLANs mit eigenen Sub-Interfaces. Diese Option wird im Regelfall nicht benötigt und wird nicht empfohlen.
- Distributed Routing:
- Name: Frei definierbarer Name für das zu erstellende Netzwerk. Dient als Referenz, um VMs mit dem Netzwerk zu verbinden.
- Beschreibung: Optionaler Freitext, um weitere Informationen zu hinterlegen (z. B. Zweck und Verwendung des Netzwerks).
- Doual Stack Modus: …
- Gateway CIDR: Angabe der internen IP-Adressen des Gateways, gefolgt von der Angabe des Subnetzes in CIDR Notation (/Maske). 
- Gemeinsame Nutzung mit anderen vDCs in der Organisation: Option, um Netzwerke über mehrere virtuelle pluscloud DCs gemeinschaftlich zu nutzen. Im Regelfalle deaktiviert.
- Statischer IP Pool:  Reservierung von statischen IP-Adressen.
- Primary und Secondary DNS: Die IP-Adressen der zu verwendenden DNS Server. Üblicherweise das Edge-Gateway.
- DNS Suffix: Falls ein spezifischer DNS Suffix benötigt wird, kann dieser hier eingetragen werden und wird automatisch bei den angeschlossenen VMs verwendet.

> **Bitte überarbeiten (Reihenfolge angepasst)** Heißt scheinbar Edge-Verbindung

---


---
[**Nächste Seite**](/docs/quickstart_guide/vm)
