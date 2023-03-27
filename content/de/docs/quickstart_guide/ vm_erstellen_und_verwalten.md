---
title: "Basis-Netzwerkkonfiguration"
linkTitle: "Basis-Netzwerkkonfiguration"
weight: 3
---

<link rel="stylesheet" type="text/css" href="/de/docs/quickstart_guide/style.css">

## vApps erstellen
Über den Menüpunkt vApp können Sie die bestehenden vApps einsehen und neue erstellen.

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/v-apps.png">
  </li>
</div>

Die Erstellung läuft über den Button Neue vApp oder vApp aus einer OVF-Datei hinzufügen. Ersteres fügt eine leere vApp für ein Standard-Deployment hinzu. Letzteres eine vorkonfigurierte Umgebung aus einer OVF-Container-Datei. 

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/neue_v-apps.png">
  </li>
</div>

Bei der Erstellung einer vApp ist nur der Name obligatorisch. Alles weitere erfolgt im Nachgang oder auf VM-Ebene.

In der vApp-Übersicht können Sie über den Menüpunkt Aktionen ein Netzwerk hinzufügen.

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/v-appvm_netzwerk.png">
  </li>
</div>

### Virtuelle Maschinen erstellen

Virtuelle Maschinen können über zwei Wege erstellt werden.

Zum einen können Sie in der zuletzt erstellten vApp den Menüpunkt Aktionen und dann VM hinzufügen nutzen.

Optional kann unter "Lease verlängern" ein Ablaufdatum für die vApp eingestellt werden, standardmäßig laufen vApps aber nicht ab.

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/v-app_neue_vm.png">
  </li>
</div>

Die zweite Möglichkeit bietet sich im Menüpunkt Virtuelle Maschinen. Hier können Sie die bestehenden VMs einsehen und über den Button Neue VM weitere erstellen.

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/neue_vm.png">
  </li>
</div>

In beiden Fällen sehen Sie dann einen identischen Wizard.

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/neue_vm_nicht_einschalten.png">
  </li>
</div>

Bei der Erstellung der Virtuellen Maschinen können Sie grundsätzlich zwischen zwei Alternativen wählen: Erstellung aus einer Vorlage (Vorlage = Verbindung aus Template mit Betriebssystem, Ressourcen und Konfiguration) oder Erstellung einer neuen VM. VMs, die direkt über die vApp erstellt werden, werden dieser auch direkt logisch zugeordnet. VMs, die über den Menüpunkt Virtuelle Maschinen erstellt werden, sind zunächst keiner vApp zugeordnet. Sie können aber nachträglich über Aktionen und Verschieben nach... einer vApp zugeordnet werden.



Wenn Sie die Ressourcen der VM vor dem Einschalten anpassen möchten, deaktivieren Sie bitte die Checkbox Einschalten. Dies ist meist sinnvoll, wenn VMs über Vorlagen erstellt werden, da die Vorlagen mit einem Minimum an Ressourcen vorkonfiguriert sind.

Die Checkbox finden Sie nicht im vApp-Dialog. Die VM übernimmt hier den Power-Status der vApp. Um die Checkbox zu erhalten, müssen Sie den oben beschriebenen Weg über "Virtuelle Maschinen" → "Neue VM" wählen.



Je nach Auswahl unterscheiden sich die betreffenden Parameter.

Die nachfolgenden Parameter können Sie bei VMs konfigurieren, die aus einer Vorlage erstellt werden (default).

Vorbereitete VM-Templates finden Sie im Katalog selfservice.

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/neue_vm_konfiguration.png">
  </li>
</div>

Scrollen Sie herunter, um alle Optionen sehen zu können.

<table class="tableformat">
  <tr>
    <th class="tableformat">Name</th>
    <td class="tableformat">Name der VM in der vApp.</td>
  </tr>
  <tr>
    <th>Computername</th>
    <td>Name des Computers. Ggf. notwendig bei Namensauflösung.</td>
  </tr>
  <tr>
    <th>Beschreibung</th>
    <td>Freitextfeld zur Beschreibung</td>
  </tr>
  <tr>
    <th>Typ</th>
    <td>Aus Vorlage</td>
  </tr>
  <tr>
    <th>Einschalten</th>
    <td>Status der VM nach dem Erstellen </td>
  </tr>
  <tr>
    <th>Vorlagen</th>     
    <td>Liste aus Vorlagen aus dem Katalog</td>
  </tr>
  <tr>
    <th>Benutzerdefinierte Speicherrichtlinie verwenden</th>
    <td>Bestimmt das Performancelevel des Storages (Performance oder High Performance)</td>
  </tr>
  <tr>
    <th>Netzwerkadapter</th>
    <td>Konnektivität zu bestehendem Netzwerk einrichten und Entscheidung, ob die IP per DHCP oder manuell vergeben wird (Netzwerkadapter können Sie im Nachhinein über die Hardwaredetails hinzufügen)</td>
  </tr>
</table>

Die nachfolgenden Parameter können Sie bei neuen VMs konfigurieren.

Hier gibt es schon vor dem Erstellen deutlich mehr Einstellungsmöglichkeiten.

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/neue_vm_konfiguration_vorlage.png">
  </li>
</div>

<table class="tableformat">
  <tr>
    <th class="tableformat">Name</th>
    <td class="tableformat">Name der VM in der vApp.</td>
  </tr>
  <tr>
    <th>Computername</th>
    <td>Name des Computers. Ggf. notwendig bei Namensauflösung.</td>
  </tr>
  <tr>
    <th>Beschreibung</th>
    <td>Freitextfeld zur Beschreibung</td>
  </tr>
  <tr>
    <th>Typ</th>
    <td>Freitextfeld zur Beschreibung</td>
  </tr>
  <tr>
    <th>Einschalten</th>
    <td>Status der VM nach dem Erstellen</td>
  </tr>
  <tr>
    <th>Betriebssystem-Familie</th>
    <td>Grundsätzliche Unterscheidung ob Linux, Microsoft Windows oder andere</td>
  </tr>
  <tr>
    <th>Betriebssystem</th>
    <td>Detaillierte Auswahl der Distribution und Version, bspw. Debian 9 64bit</td>
  </tr>
  <tr>
    <th>Startimage</th>
    <td>Auswahl des ISOs</td>
  </tr>
  <tr>
    <th>Größe</th>
    <td>Vordefinierte oder benutzerdefinierte Auswahl der VM-Größe (Anzahl virtuelle CPUs, Kerne pro CPU, Arbeitsspeicher)</td>
  </tr>
  <tr>
    <th>Speicher</th>
    <td>Anzahl und Größe der angefügten Festplatten, Wahl der Speicherrichtlinie</td>
  </tr>
  <tr>
    <th>Netzwerkadapter</th>
    <td>Einrichten der Konnektivität zu bestehendem Netzwerk, festlegen des Netzwerkkartentyps (bevorzugt VMXNET3) und Entscheidung, ob die IP per DHCP oder manuell vergeben wird; hinzufügen weiterer Netzwerkadapter </td>
  </tr>
</table>

Die gesetzten Größen für Arbeitspeicher und CPU können über den Bearbeiten Button im Nachgang jederzeit angepasst werden. Je nach Konfiguration und Betriebssystem ist hierzu ein Reboot des Gastsystems erforderlich.

Das Admin/Root Password wird von VMware generiert und ist unter "Virtuelle Maschinen" → "Details"→ "Gastbetriebssystemanpassung"→ "Bearbeiten" zu finden

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/vm_details.png">
  </li>
  <li>
    <img src="/de/docs/quickstart_guide/images/vm_gastbetriebssystemanpassung.png">
  </li>
  <li>
    <img src="/de/docs/quickstart_guide/images/vm_password.png">
  </li>
</div>

Um das Passwort zu ändern, muss die VM heruntergefahren und der Haken bei "Kennwort automatisch erstellen" entfernt werden. Dann können Sie ein beliebiges Passwort eingeben.

Damit das Passwort final gesetzt wird, muss die VM mit der Aktion "Einschalten und Neuanpassungen des Gastbetriebssystems durchführen" eingeschaltet werden.

Wichtig ist, dass die VM vorher ausgeschaltet ist. Die vAPP herunterzufahren reicht nicht aus.

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/einschalten,_neuanpanpassung_erzwingen.png">
  </li>
</div>

Die Netzwerkanbindung kann nachträglich in der Virtuellen Maschine über Details, Hardware und dann Netzwerkadapter hergestellt werden.

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/vm_details.png">
  </li>
  <li>
    <img src="/de/docs/quickstart_guide/images/vm_netzwerkadapter.png">
  </li>
</div>

Unter Netzwerkadapter und Hinzufügen wird der VM ein neues virtuelles Netzwerkinterface zu geordnet, welches wiederum einem bestehenden Netzwerk zugewiesen werden kann. Eine IP kann per DHCP oder manuell vergeben werden.

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/vm_netzwerk-mgmt.png">
  </li>
</div>
