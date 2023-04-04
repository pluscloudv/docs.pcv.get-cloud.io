---
title: "Organisationsadministration"
linkTitle: "Organisationsadministration"
weight: 5
---

<link rel="stylesheet" type="text/css" href="/de/docs/quickstart_guide/css/style.css">

Unter dem Menüpunkt Administration gelangen Sie in die Übersicht für Benutzer, Gruppen und Account-Einstellungen. Hier können Sie Ihrer Organisation weitere Benutzer hinzufügen und deren Rechte (Rollen) verwalten.

## Rollen, Benutzer und Gruppen
Unter dem Menüpunkt Zugriffssteuerung befinden sich die Unterpunkte Benutzer, Gruppen und Rollen.

Über Benutzer und den Button Neu können Sie weitere Benutzer zum Login in den vCloud Director anlegen. 


<div class="img-effect">
  <li>
    <p>1</p>
    <img src="/de/docs/quickstart_guide/images/organisationsadministration/neuer_benutzer.png">
  </li>
  <li>
    <p>2</p>
    <img src="/de/docs/quickstart_guide/images/organisationsadministration/neuer_benutzer_erstellen.png">
  </li>
</div>

Die nachfolgenden Parameter können konfiguriert werden:

<table class="tableformat">
  <tr>
    <th class="tableformat">Benutzername</th>
    <td class="tableformat">Benutzername für den Login</td>
  </tr>
  <tr>
    <th>Kennwort</th>
    <td>Passwort für den Login</td>
  </tr>
  <tr>
    <th>Kennwort bestätigen</th>
    <td>Bestätigung des Passworts</td>
  </tr>
  <tr>
    <th>Aktivieren</th>
    <td>Benutzeraccount nach dem Erstellen aktivieren oder deaktivieren</td>
  </tr>
  <tr>
    <th>Verfügbare Rollen</th>
    <td>Benutzerrechte über eine vorgefertigte Rolle bestimmen</td>
  </tr>
  <tr>
    <th>Vollständiger Name</th>
    <td>Name des Benutzers (optional)</td>
  </tr>
  <tr>
    <th>E-Mail-Adresse</th>
    <td>E-Mail-Adresse des Benutzers (optional)</td>
  </tr>
  <tr>
    <th>Telefonnummer</th>
    <td>Telefonnummer des Benutzers (optional)</td>
  </tr>
  <tr>
    <th>IM</th>
    <td>Informationen über einen Instant Messenger (optional)</td>
  </tr>
  <tr>
    <th>Kontingent aller VMs</th>
    <td>Mögliches Limit für zu erstellende VMs</td>
  </tr>
  <tr>
    <th>Kontingent ausgeführter VMs</th>
    <td>Mögliches Limit für laufende VMs</td>
  </tr>
</table>

Unter Gruppen wären generell Gruppierungen von Benutzern einzurichten. Der Reiter ist im derzeitigen Release noch ohne Funktion.

Unter Rollen befinden sich bereits vorgefertigte Rollen. Eine Rolle beinhaltet immer eine Sammlung von Rechten für einen Benutzer. Über den Button Neu können Sie weitere benutzerdefinierte Rollen anlegen, die dann für neue Benutzer verwendet werden können.

<div class="img-effect">
  <li>
    <p>1</p>
    <img src="/de/docs/quickstart_guide/images/organisationsadministration/neue_rollen.png">
  </li>
  <li>
    <p>2</p>
    <img src="/de/docs/quickstart_guide/images/organisationsadministration/neue_rollen_erstellen.png">
  </li>
</div>

Die Rechte können pro Menüpunkt individuell zusammengestellt werden.

## Limitierung auf einzelne Instanzen

Mit der Konfiguration von Usern auf der Rolle vApp User ist es möglich, auch den Zugang auf einzelne vApps und damit indirekt VMs zu begrenzen.

<div class="img-effect">
  <li>
    <p>1</p>
    <img src="/de/docs/quickstart_guide/images/organisationsadministration/neuer_benutzer_erstellen.png">
  </li>
  <li>
    <p>2</p>
    <img src="/de/docs/quickstart_guide/images/organisationsadministration/vdcs.png">
  </li>
  <li>
    <p>3</p>
    <img src="/de/docs/quickstart_guide/images/organisationsadministration/vm_details.png">
  </li>
  <li>
    <p>4</p>
    <img src="/de/docs/quickstart_guide/images/organisationsadministration/gemeinsame_nutzung.png">
  </li>
  <li>
    <p>5</p>
    <img src="/de/docs/quickstart_guide/images/organisationsadministration/gemeinsame_nutzung_anpassen.png">
  </li>
</div>

## Gast-Anpassung

Unter dem Menüpunkt Administration und Gast-Anpassung lässt sich global für die Organisation ein Domänenbeitritt für Windows VMs konfigurieren, sodass die Konfiguration nicht pro VM erforderlich ist.

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/organisationsadministration/gast-anpassung.png">
  </li>
</div>

Hierfür gehen Sie auf den Button bearbeiten.

In dem sich öffnenden Dialog lassen sich die nötigen Zugangsdaten für einen Domänenbeitritt eintragen.

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/organisationsadministration/gast-ampassung_mgmt.png">
  </li>
</div>

## Richtlinien

Unter dem Menüpunkt Richtlinien im Bereich Administration können Sie einige Voreinstellungen bzw. Limits für Ihre Organisation konfigurieren.

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/organisationsadministration/richtlinien.png">
  </li>
</div>

Die nachfolgenden Parameter können bearbeitet werden:

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/organisationsadministration/richtlinien_mgmt.png">
  </li>
</div>

- vApp-Leases
  - Maximale Laufzeit-Leases: Voreinstellung, nach wie vielen Stunden oder Tagen eine vApp ausläuft und die Laufzeitablaufaktion ausgeführt wird. Die automatische Ausführung der Laufzeitablaufaktion bei Fristerreichnung bewirkt, dass die vApp (inkl. VMs) nicht mehr erreichbar ist. Der Standard-Wert in der Voreinstellung ist: Läuft nie ab
  - Laufzeitablaufaktion: Bestimmt, was nach Ablauf des Leases mit der vApp passiert. Anhalten oder Stoppen sind mögliche Parameter. Hinweis: Nur für laufende virtuelle Server fallen Computekosten an.
  - Maximaler Speicher-Lease: Definiert die Frist, nach der der belegte vApp-Speicher (Festplatten) von ausgeschalteten vApps bereinigt wird. Dies kann durch Verschieben oder endgültiges Löschen passieren. Standard ist: Läuft nie ab
  - Speicher bereinigen: Mögliche Optionen sind: Speicher verschieben oder löschen
- vApp-Vorlage-Lease
  - Maximaler Speicher-Lease: Standard ist: Läuft nie ab. Es können aber auch Stunden oder Tage definiert werden, in denen eine vApp-Vorlage abläuft und die Laufzeitablaufaktion ausgeführt wird.
  - Speicher bereinigen: Mögliche Optionen sind: Speicher verschieben oder löschen
- Standardkontingente
  - Kontingent aller VMs: Mögliches Limit für zu erstellende VMs
  - Kontingent ausgeführter VMs: Mögliches Limit für laufende VMs 
- Kennwortrichtlinien
  - Kontosperrung: Kontosperrung aktivieren oder deaktivieren zum Schutz des Kontos bei unzulässigen Zugriffen
  - Ungültige Anmeldungen vor der Sperrung: Definiert die Anzahl der fehlgeschlagenen Logins bevor der Benutzer gesperrt wird
  - Kontosperrungsintervall: Definiert, wie lange das Konto gesperrt bleibt, bis ein Login wieder möglich ist