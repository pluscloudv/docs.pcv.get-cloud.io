---
title: "Backup"
linkTitle: "Backup"
weight: 6
---

<link rel="stylesheet" type="text/css" href="/de/docs/quickstart_guide/css/style.css">

## Anmeldung

Die Anmeldung zum Selfservice-Backupportal ist im Portal des vCloud Directors verlinkt und über folgenden Menüpunkt erreichbar:

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/backup/datensicherung_mit_veeam.png">
  </li>
</div>

## Dashboard

Im Dashboard sind die Statistiken zu den Backups einzusehen. Insbesondere zu VMs, Backupjobs und Backupstorage. Es gibt jeweils eine Ansicht für die letzten 24 Stunden bzw. die letzten 7 Tage (Hier: Die letzten 24 Stunden).

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/backup/datensicherung_mit_veeam_übersicht.png">
  </li>
</div>

Das Protected-Widget zeigt Informationen zur Anzahl der erfolgreich erfolgten Backups von vApps und VMs sowie die Gesamtgröße aller erfolgreich gesicherten VMs für den gewählten Zeitraum.

<div class="mini-img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/backup/übersicht_protected.png">
  </li>
</div>

Das Jobs-Widget gibt Auskunft über die Anzahl an angelegten Backupjobs, die maximale Dauer und die durchschnittliche Datensicherungsgeschwindigkeit.

<div class="mini-img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/backup/übersicht_jobs.png">
  </li>
</div>

Das Backup-Storage-Widget gibt Auskunft über die zugewiesene Quota und die benutzte Datenmenge. Der Status signalisiert folgende Füllgrade:
- Grün: Mehr als 10 % Backupstorage ist noch verfügbar
- Gelb: Weniger als 10 % Backupstorage ist noch verfügbar
- Rot: Es ist kein Speicher mehr frei

<div class="mini-img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/backup/übersicht_backup_storage.png">
  </li>
</div>

## Jobs

Im Job-Tab können Sie Backupjobs anlegen, editieren, löschen, aktivieren und deaktivieren. Außerdem können Sie sich detaillierte Informationen zu den einzelnen Jobs anzeigen lassen.

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/backup/jobs.png">
  </li>
</div>

### Create
Der Wizard fordert einen Namen für den anzulegenden Backupjob. Außerdem definieren Sie die Anzahl der Wiederherstellungspunkte (Hier: 14).

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/backup/jobs_create.png">
  </li>
  <li>
    <img src="/de/docs/quickstart_guide/images/backup/jobs_create_job_settings.png">
  </li>
</div>

Des Weiteren bestimmen Sie die zu sichernden Objekte (VMs/ vApps).

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/backup/jobs_create_virtual_machines.png">
  </li>
  <li>
    <img src="/de/docs/quickstart_guide/images/backup/jobs_create_virtual_machines_add_objects.png">
  </li>
</div>

Außerdem definieren Sie, in welcher Reihenfolge die Objekte gesichert werden sollen (Up/Down-Pfeile). Auch können einzelne VMs einer vApp vom Backup ausgeschlossen werden.
Die Guest-Processing-Einstellungen sind hier nachlesbar: <a href="https://helpcenter.veeam.com/docs/backup/em/step_4_configure_guest_settings.html?ver=100"> Sicherungsoptionen für laufende VMs (Datenbanken, Dateiindizierung, ...) </a>

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/backup/jobs_create_job_settings_guest_processing.png">
  </li>
</div>

Unter Email Notifications können Sie eine E-Mail-Adresse hinterlegen, an die bestimmte Status-E-Mails eines Jobs geschickt werden: 

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/backup/jobs_create_job_settings_email_notification.png">
  </li>
</div>

Die Jobs werden automatisch in einem Backupzeitfenster von 22:00 Uhr bis 8:00 Uhr geplant. 

### Start, Stop und Retry

Um einen Job manuell zu starten, zu stoppen oder zu wiederholen, markieren Sie diesen und wählen die gewünschte Aktion aus.

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/backup/jobs_start.png">
  </li>
</div>

### Disable, Enable und Edit
Um einen Job zu editieren, auszusetzen oder wieder zu reaktivieren, können Sie die entsprechende Aktion über das Dropdownmenu Job auswählen.

<div class="img-effect">
  <li>
    <img src="/de/docs/quickstart_guide/images/backup/jobs_disable.png">
  </li>
</div>

## VMs

Grundsätzlich werden zwei Arten der Wiederherstellung unterschieden: Das Wiederherstellen einer VM und das Wiederherstellen einer vApp.

### VM Restore

Im Reiter VMs suchen Sie die VM heraus, die Sie wiederherstellen möchten. Dazu können Sie auch das Suchfeld nutzen. Dann wählen Sie Restore VM. Nun bieten sich zwei Optionen an: Keep oder Overwrite. Anschließend suchen Sie den passenden Wiederherstellungspunkt aus und bestätigen den Restore-Auftrag.

Während Overwrite die VM überschreibt, erzeugt Keep eine weitere VM mit dem Suffix _restored in der vApp.