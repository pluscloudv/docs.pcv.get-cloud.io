---
title: "Quickstart_Guide"
linkTitle: "Quickstart_Guide"
weight: 1
description: >
  Dieses Dokument dient Ihnen zum schnellen Einstieg in die pluscloud v und die damit verbundenen Selfservice-Funktionen. Für die umfangreichen Selfservices sowie das Netzwerk-, Storage- und VM-Management nutzen Sie hier den VMware vCloud Director.
  
  > **Work in progress!!**
---

<link rel="stylesheet" type="text/css" href="/de/docs/quickstart_guide/style.css">

Dieses Dokument dient Ihnen zum schnellen Einstieg in die pluscloud v und die damit verbundenen Selfservice-Funktionen. Für die umfangreichen Selfservices sowie das Netzwerk-, Storage- und VM-Management nutzen Sie hier den VMware vCloud Director.

Dieser Artikel behandelt Schritt für Schritt, wie nach dem initialen Netzwerksetup VMs/vApps erstellt werden und diese final in externe Netze oder an das Internet angebunden werden. Umfangreiche Hilfe in technischen Portaldetails können Sie über das Fragezeichen in der oberen rechten Ecke bei VMware Online einsehen. Bei diesem und anderen Themen steht natürlich unser Support ebenfalls zur Verfügung.

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/hilfe.png">
  </li>
</div>

Dieses Dokumentation setzt voraus, dass Sie sowohl Ihre Zugangsdaten (Benutzername und Kennwort) als auch Ihre Mandanten-URL bereits vorliegen haben. Mit diesen Daten kommen Sie direkt in das pluscloud vCloud Director Portal. Zusätzlich ist es hilfreich, Ihre weiteren öffentlichen IP-Adressen griffbereit zu haben. Diese können Sie auch im plusserver-Kundenportal einsehen.

> **Initiales Passwort ändern** Es wird aus Sicherheitsgründen empfohlen, das Administrator-Kennwort beim ersten Login zu ändern.

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/kundenportal.png">
  </li>
</div>

Nach dem Login in die pluscloud sehen Sie eine Übersicht über das virtuelle Datacenter:

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/vdcs.png">
  </li>
</div>

Mit einem Klick auf den im obigen Screenshot grün markierten Bereich gelangen Sie in das virtuelle Datacenter und können dieses administrieren:

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/dcverwaltung.png">
  </li>
</div>



## VM erstellen und verwalten

Innerhalb des vCloud Directors werden VMs üblicherweise in vApps verpackt. Eine vApp kann als Gruppe für mehrere VMs dienen, wobei eine einzelne Zuordnung meist die empfehlenswerte Vorgehensweise ist.

Für den täglichen operativen Betrieb ist die vApp-Hülle unsichtbar. Lediglich die Zuweisung von Netzwerken zu vApps muss bei der initialen Einrichtung beachtet werden, damit Netzwerke den VMs zur Verfügung stehen.

### vApps erstellen

Über den Menüpunkt vApp können Sie die bestehenden vApps einsehen und neue erstellen.