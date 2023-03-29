---
title: "VM erstellen und verwalten"
linkTitle: "VM erstellen und verwalten"
weight: 3
---

<link rel="stylesheet" type="text/css" href="/de/docs/quickstart_guide/css/style.css">

## vApps erstellen
Über den Menüpunkt vApp können Sie die bestehenden vApps einsehen und neue erstellen.

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/vm_erstellen_und_verwalten/v-apps.png">
  </li>
</div>

Die Erstellung läuft über den Button Neue vApp oder vApp aus einer OVF-Datei hinzufügen. Ersteres fügt eine leere vApp für ein Standard-Deployment hinzu. Letzteres eine vorkonfigurierte Umgebung aus einer OVF-Container-Datei. 

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/vm_erstellen_und_verwalten/neue_v-apps.png">
  </li>
</div>

Bei der Erstellung einer vApp ist nur der Name obligatorisch. Alles weitere erfolgt im Nachgang oder auf VM-Ebene.

In der vApp-Übersicht können Sie über den Menüpunkt Aktionen ein Netzwerk hinzufügen.

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/vm_erstellen_und_verwalten/v-app_netzwerk.png">
  </li>
</div>

## Virtuelle Maschinen erstellen

Virtuelle Maschinen können über zwei Wege erstellt werden.

Zum einen können Sie in der zuletzt erstellten vApp den Menüpunkt Aktionen und dann VM hinzufügen nutzen.

Optional kann unter "Lease verlängern" ein Ablaufdatum für die vApp eingestellt werden, standardmäßig laufen vApps aber nicht ab.

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/vm_erstellen_und_verwalten/v-app_neue_vm.png">
  </li>
</div>

Die zweite Möglichkeit bietet sich im Menüpunkt Virtuelle Maschinen. Hier können Sie die bestehenden VMs einsehen und über den Button Neue VM weitere erstellen.

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/vm_erstellen_und_verwalten/neue_vm.png">
  </li>
</div>

In beiden Fällen sehen Sie dann einen identischen Wizard.

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/vm_erstellen_und_verwalten/neue_vm_nicht_einschalten.png">
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
    <img src="/de/docs/quickstart_guide/images/vm_erstellen_und_verwalten/neue_vm_konfiguration.png">
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
    <img src="/de/docs/quickstart_guide/images/vm_erstellen_und_verwalten/neue_vm_konfiguration_vorlage.png">
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
    <img src="/de/docs/quickstart_guide/images/vm_erstellen_und_verwalten/vm_details.png">
  </li>
  <li>
    <img src="/de/docs/quickstart_guide/images/vm_erstellen_und_verwalten/vm_gastbetriebssystemanpassung.png">
  </li>
  <li>
    <img src="/de/docs/quickstart_guide/images/vm_erstellen_und_verwalten/vm_password.png">
  </li>
</div>

Um das Passwort zu ändern, muss die VM heruntergefahren und der Haken bei "Kennwort automatisch erstellen" entfernt werden. Dann können Sie ein beliebiges Passwort eingeben.

Damit das Passwort final gesetzt wird, muss die VM mit der Aktion "Einschalten und Neuanpassungen des Gastbetriebssystems durchführen" eingeschaltet werden.

Wichtig ist, dass die VM vorher ausgeschaltet ist. Die vAPP herunterzufahren reicht nicht aus.

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/vm_erstellen_und_verwalten/einschalten,_neuanpanpassung_erzwingen.png">
  </li>
</div>

Die Netzwerkanbindung kann nachträglich in der Virtuellen Maschine über Details, Hardware und dann Netzwerkadapter hergestellt werden.

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/vm_erstellen_und_verwalten/vm_details.png">
  </li>
  <li>
    <img src="/de/docs/quickstart_guide/images/vm_erstellen_und_verwalten/vm_netzwerkadapter.png">
  </li>
</div>

Unter Netzwerkadapter und Hinzufügen wird der VM ein neues virtuelles Netzwerkinterface zu geordnet, welches wiederum einem bestehenden Netzwerk zugewiesen werden kann. Eine IP kann per DHCP oder manuell vergeben werden.

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/vm_erstellen_und_verwalten/vm_netzwerk-mgmt.png">
  </li>
</div>

In den Details einer VM im Bereich Hardware können Sie dieser weitere Festplatten mittels Hinzufügen zuordnen. Achten Sie beim Anlegen/Bearbeiten von Festplatten auf die korrekte gewünschte Einheit: MB oder GB. Bei der (Storage)-Richtlinie kann man sich an den bereits existierenden Festplatten orientieren oder eine andere auswählen. Das gleiche gilt für den Festplatten-(Controller)-Bus-Typ. Jeder Controller bekommt eine Bus-Nummer, maximal vier Controller sind möglich. Die Einheitennummer muss je Bus-Nummer eindeutig sein (SCSI IDs je Controller). Die Änderungen müssen noch durch Klick auf Speichern bestätigt werden.

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/vm_erstellen_und_verwalten/vm_festplatten.png">
  </li>
  <li>
    <img src="/de/docs/quickstart_guide/images/vm_erstellen_und_verwalten/vm_festplatten_mgmt.png">
  </li>
</div>

## Benannte Festplatten
Benannte Festplatten sind eigenständige virtuelle Festplatten, die Sie innerhalb Ihres Organisations-VDCs erstellen. Organisationsadministratoren und -benutzer mit den entsprechenden Rechten können Benannte Festplatten erstellen, entfernen und aktualisieren und mit virtuellen Maschinen verbinden. Man kann sich eine Benannte Festplatte ähnlich wie eine Wechselfestplatte/USB-Platte vorstellen.

Wenn Sie eine Benannte Festplatte erstellen, wird diese mit einem Organisations-VDC, nicht aber direkt mit einer virtuellen Maschine verknüpft. Nach dem Erstellen der Festplatte in einem VDC kann der Festplattenbesitzer oder ein Administrator die Festplatte an eine beliebige im VDC bereitgestellte virtuelle Maschine anhängen bzw. von ihr trennen. In der virtuellen Maschine wird die Festplatte dann sichtbar und muss bei der ersten Benutzung mit einem vom OS der VM unterstützen Filesystem formatiert werden.

Achtung: Benannte Festplatten werden nicht in VM Snapshots aufgenommen! Deshalb werden sie auch bei einem Backup NICHT mitgesichert! Soll einer VM eine normale zusätzliche Festplatte zugeordnet werden, so ist dies in den Hardwareeinstellungen der jeweiligen VM möglich (siehe 3.2).

Benannte Festplatten erstellen Sie im Menü unter Speicher durch einen Klick auf Neu.

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/vm_erstellen_und_verwalten/benannte_festplatten.png">
  </li>
  <li>
    <img src="/de/docs/quickstart_guide/images/vm_erstellen_und_verwalten/benannte_festplatten_neu.png">
  </li>
  <li>
    <img src="/de/docs/quickstart_guide/images/vm_erstellen_und_verwalten/benannte_festplatten_anhaengen.png">
  </li>
</div>


<table class="tableformat">
  <tr>
    <th class="tableformat">Name</th>
    <td class="tableformat">Name der Benannten Festplatte</td>
  </tr>
  <tr>
    <th>Beschreibung</th>
    <td>Freitextfeld zur Beschreibung</td>
  </tr>
  <tr>
    <th>Speicherrichtlinie</th>
    <td>Bestimmung des Performancelevels des Storages (Performance, High Performance)</td>
  </tr>
  <tr>
    <th>Festplattengröße</th>
    <td>Bestimmung der Größe der Benannten Festplatte in MB oder GB</td>
  </tr>
  <tr>
    <th>Bus-Typ</th>
    <td>Bestimmung des Bus-Typs: SCSI, SATA oder IDE</td>
  </tr>
  <tr>
    <th>Bus-Subtyp</th>
    <td>Bei SCSI-Festplatte: Auswahl des SCSI-Controllers</td>
  </tr>
  <tr>
    <th>Freigabetyp</th>
    <td>Siehe unten</td>
  </tr>
</table>

Zustände:
- Wenn „Keine“ ausgewählt ist, ist die erstellte benannte Festplatte nicht freigabefähig. 
- Wenn „Datenträger“ ausgewählt ist, kann der erstellte benannte Datenträger an mehrere VMs auf Festplattenebene angehängt werden. 
- Wenn „Controller“ ausgewählt ist, kann der erstellte benannte Datenträger an mehrere VMs auf Controller-Ebene angehängt werden. 

## Speicherrichtlinien

Unter dem Menüpunkt Speicherrichtlinien ist einsehbar, wie viel von welcher Storageklasse zur Verfügung steht und was belegt ist. In der Spalte Standard sehen Sie, welche Storageklasse beim Erstellen einer VM als Standard ausgewählt wird. Grundsätzlich steht Storage unbegrenzt zur Verfügung. Es werden aber Sicherheitslimits eingestellt, die jederzeit erhöht werden können. Die Limits sollen nur sicherstellen, dass fehlerhafte Skripte keine unnötigen Ressourcen belegen und Kosten verursachen.

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/vm_erstellen_und_verwalten/speicherrichtlinien.png">
  </li>
</div>

## Affinitätsregeln

Unter dem Menüpunkt Affinitätsregeln können Sie Abhängigkeiten von VMs bzgl. ihrer physikalischen Nähe bestimmen. Jeweils unter dem Punkt Neu lassen sich daher Affinitätsregeln erstellen, welche die ausgewählten VMs auf den gleichen physikalischen Backends zusammenziehen (z.B. für Latenzoptimierung) oder unter Anti-Affinitätsregeln bewusst separieren (z.B. Risiko-Diversifizierung).

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/vm_erstellen_und_verwalten/affinitätsregel.png">
  </li>
  <p>Affinitätsregel erstellen</p>
  <li>
    <img src="/de/docs/quickstart_guide/images/vm_erstellen_und_verwalten/neu_anti-affinitätsregel.png">
  </li>
  <p>Anti-Affinitätsregel erstellen</p>
  <li>
    <img src="/de/docs/quickstart_guide/images/vm_erstellen_und_verwalten/neu_affinitätsregel.png">
  </li>
</div>
