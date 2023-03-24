---
title: "Quickstart_Guide"
linkTitle: "Quickstart_Guide"
weight: 1
date: 2023-02-21
description: >
  Dieses Dokument dient Ihnen zum schnellen Einstieg in die pluscloud v und die damit verbundenen Selfservice-Funktionen. Für die umfangreichen Selfservices sowie das Netzwerk-, Storage- und VM-Management nutzen Sie hier den VMware vCloud Director.
  
  > **Work in progress!!**
---

<link rel="stylesheet" type="text/css" href="style.css">

# Schnelleinstieg

Dieses Dokument dient Ihnen zum schnellen Einstieg in die pluscloud v und die damit verbundenen Selfservice-Funktionen. Für die umfangreichen Selfservices sowie das Netzwerk-, Storage- und VM-Management nutzen Sie hier den VMware vCloud Director.

Dieser Artikel behandelt Schritt für Schritt, wie nach dem initialen Netzwerksetup VMs/vApps erstellt werden und diese final in externe Netze oder an das Internet angebunden werden. Umfangreiche Hilfe in technischen Portaldetails können Sie über das Fragezeichen in der oberen rechten Ecke bei VMware Online einsehen. Bei diesem und anderen Themen steht natürlich unser Support ebenfalls zur Verfügung.

<div class="my-list">
  <li>
    <img src="/de/docs/quickstart_guide/images/hilfe.png">
  </li>
</div>

Dieses Dokumentation setzt voraus, dass Sie sowohl Ihre Zugangsdaten (Benutzername und Kennwort) als auch Ihre Mandanten-URL bereits vorliegen haben. Mit diesen Daten kommen Sie direkt in das pluscloud vCloud Director Portal. Zusätzlich ist es hilfreich, Ihre weiteren öffentlichen IP-Adressen griffbereit zu haben. Diese können Sie auch im plusserver-Kundenportal einsehen.

> **Initiales Passwort ändern** Es wird aus Sicherheitsgründen empfohlen, das Administrator-Kennwort beim ersten Login zu ändern.

<div class="my-list">
  <li>
    <img src="/de/docs/quickstart_guide/images/kundenportal.png">
  </li>
</div>

Nach dem Login in die pluscloud sehen Sie eine Übersicht über das virtuelle Datacenter:

<div class="my-list">
  <li>
    <img src="/de/docs/quickstart_guide/images/vdcs.png">
  </li>
</div>

Mit einem Klick auf den im obigen Screenshot grün markierten Bereich gelangen Sie in das virtuelle Datacenter und können dieses administrieren:

<div class="my-list">
  <li>
    <img src="/de/docs/quickstart_guide/images/dcverwaltung.png">
  </li>
</div>

# Basis-Netzwerkkonfiguration 

Ihrer pluscloud-Umgebung wird automatisch eine VMware Edge-Gateway Appliance zugewiesen. Diese stellt für Ihre Umgebung den Zugang zum Internet zur Verfügung. Des weiteren bietet es diverse Dienste an, z. B. Firewall, Loadbalancing, NAT und VPN. Zu diesem Zeitpunkt erstellte virtuelle Maschinen haben keine Verbindung zur Außenwelt und müssen zunächst über passende NAT- und Firewall-Regeln im Edge-Gateway verbunden werden. 

## Übersicht Organisations-VDC-Netzwerke
 
Wenn Sie unter Netzwerk auf den Menüpunkt Netzwerke im linken Navigationsmenü klicken, sehen Sie alle bestehenden Netzwerke. Hier sollte bereits ein Organisationsnetzwerk verfügbar sein.

<div class="my-list">
  <li>
    <img src="/de/docs/quickstart_guide/images/netzwerke.png">
  </li>
</div>

Ihr Organisationsnetzwerk sollte im Namen Ihre Kundennummer enthalten und bei Netzwerktyp den Status Weitergeleitet aufweisen. Die erste Adresse des verwendeten Subnetzes ist hierbei an die Edge-Gateway Appliance gebunden.

<div class="my-list">
  <li>
    <img src="/de/docs/quickstart_guide/images/netzwerk_config.png">
  </li>
</div>

Ein fehlendes Organisationsnetzwerk sowie weitere Netze können Sie über die Schaltfläche Neu anlegen.

<div class="my-list">
  <li>
    <img src="/de/docs/quickstart_guide/images/neues_netzwerk.gif">
  </li>
</div>

Beim Typ des zu erstellenden Netzwerks bietet die Option weitergeleitet die Möglichkeit, Ihr Edge-Gateway auszuwählen und externe Kommunikation zu ermöglichen. Isolierte Netzwerke stehen nur Ihren virtuellen Maschinen zur Verfügung und sind von externen Verbindungen abgekoppelt.

Im Wizard für weitergeleitete Netzwerke sind folgende Parameter relevant:

<table class="tableformat">
  <tr>
    <th class="tableformat">Typ</th>
    <td class="tableformat">Unterscheidet, ob ein Netz weitergeleitet oder isoliert ist. Nur weitergeleitete Netzwerke bieten eine Konnektivität nach außen und eine Anbindung an das Edge-Gateway.</td>
  </tr>
  <tr>
    <th>Edge-Gateway</th>
    <td>Unter diesem Punkt kann die Verbindung zum bereits bestehenden Edge-Gateway hergestellt werden. Als Schnittstellentyp ist im Normalfall "Intern" auszuwählen.</td>
  </tr>
  <tr>
    <th>Gast-VLAN zulassen</th>
    <td>Ermöglicht die Erstellung von VLANs mit eigenen Sub-Interfaces. Diese Option wird im Regelfall nicht benötigt und wird nicht empfohlen.</td>
  </tr>
  <tr>
    <th>Distributed Routing</th>
    <td>…</td>
  </tr>
  <tr>
    <th>Name</th>
    <td>Frei definierbarer Name für das zu erstellende Netzwerk. Dient als Referenz, um VMs mit dem Netzwerk zu verbinden.</td>
  </tr>
  <tr>
    <th>Beschreibung</th>     
    <td>Optionaler Freitext, um weitere Informationen zu hinterlegen (z. B. Zweck und Verwendung des Netzwerks).</td>
  </tr>
  <tr>
    <th>Dual Stack Modus</th>
    <td>…</td>
  </tr>
  <tr>
    <th>Gateway CIDR</th>
    <td>Angabe der internen IP-Adressen des Gateways, gefolgt von der Angabe des Subnetzes in CIDR Notation (/Maske). </td>
  </tr>
  <tr>
    <th>Gemeinsame Nutzung mit anderen vDCs in der Organisation</th>
    <td>Option, um Netzwerke über mehrere virtuelle pluscloud DCs gemeinschaftlich zu nutzen. Im Regelfalle deaktiviert.</td>
  </tr>
  <tr>
    <th>Statischer IP Pool</th>
    <td>Reservierung von statischen IP-Adressen.</td>
  </tr>
  <tr>
    <th>Primary und Secondary DNS</th>
    <td>Die IP-Adressen der zu verwendenden DNS Server. Üblicherweise das Edge-Gateway.</td>
  </tr>
  <tr>
    <th>DNS Suffix</th>
    <td> Falls ein spezifischer DNS Suffix benötigt wird, kann dieser hier eingetragen werden und wird automatisch bei den angeschlossenen VMs verwendet.</td>
  </tr>
</table>



> <span style="color:red"> **Bitte überarbeiten (Reihenfolge angepasst)** </span> Heißt scheinbar Edge-Verbindung

## Edge-Gateway-Konfiguration
Die Konfiguration der Edge-Gateway Appliance und ihrer Verbindungen erfolgt über den Menüpunkt Edges im linken Menü.

Durch das Klicken auf den Namen des Edge-Gateways aus der Liste wird das Verwaltungsmenü des Edge-Gateways geöffnet. In diesem  stehen Ihnen die einzelnen Parameter zur Konfiguration des Edge-Gateways zur Verfügung. Einige Standards werden durch plusserver bereits vorkonfiguriert ausgeliefert.

<div class="my-list">
  <li>
    <img src="/de/docs/quickstart_guide/images/edges.gif">
  </li>
</div>

Damit Kommunikation zwischen VMs und dem Internet möglich wird, sind ein paar Firewall-Regeln, Anwendungsportprofile und NAT-Regeln notwendig.

### Anwendungsportprofile verwalten

Wir empfehlen Ihnen, zuerst die Anwendungsportprofile zu setzen. Dazu muss der Reiter "Anwendungsportprofile" in der Edge-Gateway-Konfiguration gewählt werden.

<div class="my-list">
  <li>
    <img src="/de/docs/quickstart_guide/images/anwendungsportprofile.png">
  </li>
</div>

Die Anwendungsportprofile werden benötigt, um Ports für Anwendungen in einer Entität zusammenzufassen.

Hier können Sie mit der Schaltfläche "NEU" ein neues Anwendungsportprofil anlegen oder sich die Standardanwendungen und die benutzerdefinierten Anwendungen überprüfen.

<div class="my-list">
  <li>
    <img src="/de/docs/quickstart_guide/images/anwendungsportprofile-übersicht.png">
  </li>
</div>

#### Neues Anwendungsportprofil anlegen

Die nachfolgenden Parameter sollten Sie konfigurieren:

<div class="my-list">
  <li>
    <img src="/de/docs/quickstart_guide/images/neues-anwendungsportprofil.png">
  </li>
</div>

<table class="tableformat">
  <tr>
    <th class="tableformat">Name</th>
    <td class="tableformat">Frei definierbarer Name für das zu erstellende Anwendungsportprofil.</td>
  </tr>
  <tr>
    <th>Beschreibung</th>     
    <td>Optionaler Freitext, um weitere Informationen zu hinterlegen (z. B. Zweck und Verwendung des Anwendungsportprofils).</td>
  </tr>
  <tr>
    <th>Portprofil hinzufügen</th>     
    <td>…</td>
  </tr>
  <tr>
    <th>Port</th>     
    <td>…</td>
  </tr>
  <tr>
    <th>Beschreibung</th>     
    <td>…</td>
  </tr>
</table>

### NAT Regeln verwalten
Wir empfehlen Ihnen, als nächstes die NAT-Regeln zu setzen. Dazu muss der Reiter NAT in der Edge-Gateway-Konfiguration gewählt werden.

<div class="my-list">
  <li>
    <img src="/de/docs/quickstart_guide/images/nat.png">
  </li>
</div>

> **Wenn eine Adresse über mehrere NAT-Regeln verfügt, wird die Regel mit der höchsten Priorität angewendet. Ein niedrigerer Wert bedeutet eine höhere Priorität für diese Regel.**
> Die Regeln können Sie mit den Buttons "NACH OBEN VERSCHIEBEN" und "NACH UNTEN VERSCHIEBEN" verschieben, um die passende Reihenfolge festzulegen. Alternativ können Sie aber auch mit "VERSCHIEBEN NACH" die Regeln an eine definierte Stelle verschieben.

#### NAT Regel erstellen

<div class="my-list">
  <li>
    <img src="/de/docs/quickstart_guide/images/neu-nat.gif">
  </li>
</div>

<div class="accordion">
  <input type="checkbox" id="SNAT">
  <label class="accordion-header" for="SNAT">Source Network Address Translation Regel erstellen</label>
  <div class="accordion-content">
    <p>Die nachfolgenden Parameter sollten Sie konfigurieren:</p>
    <table class="tableformat">
      <tr>
        <th class="tableformat">Name</th>
        <td class="tableformat">Frei definierbarer Name für die zu erstellende NAT-Regel.</td>
      </tr>
      <tr>
        <th>Beschreibung</th>     
        <td>Optionaler Freitext, um weitere Informationen zu hinterlegen (z. B. Zweck und Verwendung der NAT-Regel).</td>
      </tr>
      <tr>
        <th>Schnittstellentyp</th>
        <td>Um eine DNAT Regel zu erstellen muss hier SNAT gewählt werden.</td>
      </tr>
      <tr>
        <th>Externe IP</th>     
        <td>Hier verwenden Sie die Ihnen zugeordneten öffentlichen IP-Adressen oder Subnetze.</td>
      </tr>
      <tr>
        <th>Externer Port </th>     
        <td>Der "externe Port" definiert den Port, von der definierten externe IP-Adresse, welcher genutzt wird, um auf den SNAT-Dienst zuzugreifen.</td>
      </tr>
      <tr>
        <th>Interne IP</th>     
        <td>Dies ist das vorher definierte IP-Subnetz, welches Sie intern verwenden.</td>
      </tr>
      <tr>
        <th>Anwendung</th>     
        <td>Hier wird ein Anwendungsprofil gewählt.</td>
      </tr>
      <p>Die nachfolgenden Parameter können Sie zusätzlich konfigurieren:</p>   
    <table class="tableformat">
      <tr>
        <th class="tableformat">Zustand</th>
        <td class="tableformat">Der Schalter muss aktiviert sein, um die Regel nutzen zu können.</td>
      </tr>
      <tr>
        <th>Protokollierung</th>     
        <td>Über diese Option kann das im Edge-Gateway integrierte Logging des gesamten Traffics zu dieser Regel aktiviert werden.</td>
      </tr>
      <tr>
        <th>Priorität</th>     
        <td>Wenn eine Adresse über mehrere NAT-Regeln verfügt, wird die Regel mit der höchsten Priorität angewendet. Ein niedrigerer Wert bedeutet eine höhere Priorität für diese Regel.</td>
      </tr>
      <tr>
        <th>Firewall-Übereinstimmung</th>     
        <td>
          Legt fest, wie die Firewall während der NAT eine Adressübereinstimmung ermittelt, wenn die Firewallphase nicht übersprungen wird. Im Folgenden sind gültige Werte aufgeführt:
        </td>
      </tr>
      <tr>
        <th>- Interne Adressübereinstimmung:</th>     
        <td>
          Gibt an, dass die Firewall auf die interne Adresse einer NAT-Regel angewendet wird. Für SNAT ist die interne Adresse die ursprüngliche Quelladresse, bevor NAT durchgeführt wird. Für DNAT ist die interne Adresse die übersetzte Zieladresse, nachdem NAT durchgeführt wurde.
        </td>
              <tr>
        <th>- Externe Adressübereinstimmung:</th>     
        <td>
          Gibt an, dass die Firewall auf die externe Adresse einer NAT-Regel angewendet wird. Für SNAT ist die externe Adresse die übersetzte Quelladresse, nachdem NAT durchgeführt wurde. Für DNAT ist die externe Adresse die ursprüngliche Zieladresse, bevor NAT durchgeführt wird.
        </td>
              <tr>
        <th>- Bypass:</th>     
        <td>
          Firewallphase wird übersprungen.
        </td>
      </tr>
      </tr>
      </tr>
      <tr>
        <th>Interne IP</th>     
        <td>Hier verwenden Sie die Ihnen zugeordneten öffentlichen IP-Adressen oder Subnetze.</td>
      </tr>
      <tr>
        <th>Anwendung</th>     
        <td>Hier wird ein Anwendungsprofil gewählt.</td>
      </tr>  
    </table>
  </div>
</div>
<br>

<div class="accordion">
  <input type="checkbox" id="DNAT">
  <label class="accordion-header" for="DNAT">Destination Network Address Translation Regel erstellen</label>
  <div class="accordion-content">
    <p>Die nachfolgenden Parameter sollten Sie konfigurieren:</p>
    <table class="tableformat">
      <tr>
        <th class="tableformat">Name</th>
        <td class="tableformat">Frei definierbarer Name für die zu erstellende NAT-Regel.</td>
      </tr>
      <tr>
        <th>Beschreibung</th>     
        <td>Optionaler Freitext, um weitere Informationen zu hinterlegen (z. B. Zweck und Verwendung der NAT-Regel).</td>
      </tr>
      <tr>
        <th>Schnittstellentyp</th>
        <td>Um eine SNAT Regel zu erstellen muss hier SNAT gewählt werden.</td>
      </tr>
      <tr>
        <th>Externe IP</th>     
        <td>Hier verwenden Sie die Ihnen zugeordneten öffentlichen IP-Adressen oder Subnetze.</td>
      </tr>
      <tr>
        <th>Interne IP</th>     
        <td>Dies ist das vorher definierte IP-Subnetz, welches Sie intern verwenden.</td>
      </tr>
      <tr>
        <th>Ziel-IP</th>     
        <td>?</td>
      </tr>
      <p>Die nachfolgenden Parameter können Sie zusätzlich konfigurieren:</p>   
    <table class="tableformat">
      <tr>
        <th class="tableformat">Zustand</th>
        <td class="tableformat">Der Schalter muss aktiviert sein, um die Regel nutzen zu können.</td>
      </tr>
      <tr>
        <th>Protokollierung</th>     
        <td>Über diese Option kann das im Edge-Gateway integrierte Logging des gesamten Traffics zu dieser Regel aktiviert werden.</td>
      </tr>
      <tr>
        <th>Priorität</th>     
        <td>Wenn eine Adresse über mehrere NAT-Regeln verfügt, wird die Regel mit der höchsten Priorität angewendet. Ein niedrigerer Wert bedeutet eine höhere Priorität für diese Regel.</td>
      </tr>
      <tr>
        <th>Firewall-Übereinstimmung</th>     
        <td>
          Legt fest, wie die Firewall während der NAT eine Adressübereinstimmung ermittelt, wenn die Firewallphase nicht übersprungen wird. Im Folgenden sind gültige Werte aufgeführt:
        </td>
      </tr>
      <tr>
        <th>- Interne Adressübereinstimmung:</th>     
        <td>
          Gibt an, dass die Firewall auf die interne Adresse einer NAT-Regel angewendet wird. Für SNAT ist die interne Adresse die ursprüngliche Quelladresse, bevor NAT durchgeführt wird. Für DNAT ist die interne Adresse die übersetzte Zieladresse, nachdem NAT durchgeführt wurde.
        </td>
              <tr>
        <th>- Externe Adressübereinstimmung:</th>     
        <td>
          Gibt an, dass die Firewall auf die externe Adresse einer NAT-Regel angewendet wird. Für SNAT ist die externe Adresse die übersetzte Quelladresse, nachdem NAT durchgeführt wurde. Für DNAT ist die externe Adresse die ursprüngliche Zieladresse, bevor NAT durchgeführt wird.
        </td>
              <tr>
        <th>- Bypass:</th>     
        <td>
          Firewallphase wird übersprungen.
        </td>
      </tr>
      </tr>
      </tr>
      <tr>
        <th>Interne IP</th>     
        <td>Hier verwenden Sie die Ihnen zugeordneten öffentlichen IP-Adressen oder Subnetze.</td>
      </tr>
      <tr>
        <th>Anwendung</th>     
        <td>Hier wird ein Anwendungsprofil gewählt.</td>
      </tr>  
    </table>
  </div>
</div>


### Firewall Konfiguration

> **Wenn eine Adresse über mehrere Firewall-Regeln verfügt, wird die Regel mit der höchsten Priorität angewendet. Ein niedrigerer Wert bedeutet eine höhere Priorität für diese Regel.**
> Die Regeln können Sie mit den Buttons "NACH OBEN VERSCHIEBEN" und "NACH UNTEN VERSCHIEBEN" verschieben, um die passende Reihenfolge festzulegen. Alternativ können Sie aber auch mit "VERSCHIEBEN NACH" die Regeln an eine definierte Stelle verschieben.

### Firewallregeln erstellen
Hier können Sie neue Regel erstellen mit "NEUE OBEN", welches eine neue Regel am Anfang der Liste erstellt, oder indem Sie eine Vorhandene Regel Auswählen und dann "NEUE DADRÜBER" auswählen, welches eine neue Regel über der Ausgewählten erstellt. 

Die nachfolgenden Parameter sollten Sie konfigurieren:
Art | Beschreibung
----|-------------
Name | Namen für die Regle
Katekorie | Art der Regel (Nicht editierbar)
Zustand | Definiert ob die Regel aktiv oder inaktiv ist
Anwendung | Auswahl welche Anwenungsprofil angewendet werden soll (Sammlung von Freigaben für eine Anwendung)
Quelle | Quell-Netzwerk (Beispiel: DNAT - jede Quelle / SNAT - internes Netzwerk)
Ziel | Ziel-Netzwerk (Beispiel: DNAT - internes Netzwerk / SNAT - Belibiges Zeil)
Aktion | Paket Zulassen / Verwerfen
IP-Protokoll | Auswahl des für die Regel benutzen IP Protokolls
Protokollierung | Über diese Option kann das im Edge-Gateway integrierte Logging des gesamten Traffics zu dieser Regel aktiviert werden.


Mit Speichern übernehmen Sie die konfigurierten Regeln. 


Wichtig: Bitte lassen Sie die PSMANAGED-Regeln unbedingt bestehen. Diese haben einen direkten Einfluss auf die gebuchten Services. Wenn diese nicht existieren, wird das Management/die Funktion seitens plusserver eingeschränkt.

Um wieder zu übersicht des vDCs zu gelangen klicken sie oben auf "Datencenter" und wählen dann das gewünschte vDC aus.
<div class="my-list">
  <li>
    <img src="/de/docs/quickstart_guide/images/zurück_zum_vdc.gif">
  </li>
</div>


### Loadbalancing einrichten

Deaktiviert?

# VM erstellen und verwalten

Innerhalb des vCloud Directors werden VMs üblicherweise in vApps verpackt. Eine vApp kann als Gruppe für mehrere VMs dienen, wobei eine einzelne Zuordnung meist die empfehlenswerte Vorgehensweise ist.

Für den täglichen operativen Betrieb ist die vApp-Hülle unsichtbar. Lediglich die Zuweisung von Netzwerken zu vApps muss bei der initialen Einrichtung beachtet werden, damit Netzwerke den VMs zur Verfügung stehen.

## vApps erstellen

Über den Menüpunkt vApp können Sie die bestehenden vApps einsehen und neue erstellen.