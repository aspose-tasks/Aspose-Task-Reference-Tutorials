---
title: Lesen Sie Gruppendefinitionsdaten in Aspose.Tasks
linktitle: Lesen Sie Gruppendefinitionsdaten in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie mit Aspose.Tasks für Java Gruppendefinitionsdaten aus Microsoft Project-Dateien lesen. Folgen Sie unserer Schritt-für-Schritt-Anleitung.
type: docs
weight: 10
url: /de/java/project-data-reading/read-group-definition/
---
## Einführung
Aspose.Tasks für Java ist eine leistungsstarke Bibliothek, die Entwicklern die einfache Bearbeitung von Microsoft Project-Dateien ermöglicht. In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess des Lesens von Gruppendefinitionsdaten aus einer Projektdatei mit Aspose.Tasks für Java.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Java Development Kit (JDK): Stellen Sie sicher, dass JDK auf Ihrem System installiert ist.
2.  Aspose.Tasks for Java-Bibliothek: Laden Sie die Aspose.Tasks for Java-Bibliothek herunter und installieren Sie sie von[Hier](https://releases.aspose.com/tasks/java/).
3. Integrierte Entwicklungsumgebung (IDE): Wählen Sie Ihre bevorzugte IDE wie IntelliJ IDEA oder Eclipse.

## Pakete importieren
Importieren wir zunächst die notwendigen Pakete, um mit Aspose.Tasks für Java arbeiten zu können.
```java
import com.aspose.tasks.*;
```
## Schritt 1: Richten Sie Ihr Datenverzeichnis ein
```java
String dataDir = "Your Data Directory";
```
 Ersetzen`"Your Data Directory"` mit dem Pfad zu dem Verzeichnis, das Ihre Projektdatei enthält.
## Schritt 2: Laden Sie die Projektdatei
```java
Project project = new Project(dataDir + "project.mpp");
```
 Laden Sie Ihre Projektdatei mit`Project` Klassenkonstruktor und übergibt den Pfad zu Ihrer Projektdatei.
## Schritt 3: Anzahl der Aufgabengruppen abrufen
```java
System.out.println("Task Groups Count: " + project.getTaskGroups().size());
```
 Rufen Sie die Anzahl der Aufgabengruppen im Projekt mithilfe von ab`getTaskGroups()` Methode.
## Schritt 4: Informationen zur Aufgabengruppe abrufen
```java
Group taskGroup = project.getTaskGroups().toList().get(1);
System.out.println("Percent Complete:" + taskGroup.getName());
System.out.println("Group Criteria count: " + taskGroup.getGroupCriteria().size());
```
Rufen Sie Informationen zu einer bestimmten Aufgabengruppe ab, z. B. ihren Namen und die Anzahl der Gruppenkriterien.
## Schritt 5: Informationen zu Gruppenkriterien abrufen
```java
GroupCriterion criterion = taskGroup.getGroupCriteria().toList().get(0);
System.out.println("Criterion Field: " + criterion.getField());
System.out.println("Criterion GroupOn: " + criterion.getGroupOn());
System.out.println("Criterion Cell Color: " + criterion.getCellColor());
System.out.println("Criterion Pattern: " + criterion.getPattern());
```
Rufen Sie Informationen zu den Gruppenkriterien ab, z. B. das Feld, die Gruppe, die Zellenfarbe und das Muster.
## Schritt 6: Überprüfen Sie die übergeordnete Gruppe
```java
if (taskGroup == criterion.getParentGroup())
    System.out.println("Parent Group is equval to task Group.");
```
Überprüfen Sie, ob die übergeordnete Gruppe mit der Aufgabengruppe übereinstimmt.
## Schritt 7: Rufen Sie die Schriftartinformationen von Criterion ab
```java
System.out.println("Font Family Name: " + criterion.getFont().getFontFamily());
System.out.println("Font Size: " + criterion.getFont().getSize());
System.out.println("Font Style: " + criterion.getFont().getStyle());
System.out.println("Ascending/Descending: " + criterion.getAscending());
```
Rufen Sie Schriftartinformationen für das Kriterium ab, z. B. Schriftartfamilie, -größe, -stil und Sortierreihenfolge.

## Abschluss
In diesem Tutorial haben wir gelernt, wie man mit Aspose.Tasks für Java Gruppendefinitionsdaten aus einer Microsoft Project-Datei liest. Wenn Sie diese Schritte befolgen, können Sie Aufgabengruppeninformationen effektiv extrahieren und in Ihren Java-Anwendungen nutzen.
## FAQs
### F: Kann ich Aspose.Tasks für Java verwenden, um Projektdateien zu ändern?
A: Ja, Aspose.Tasks für Java bietet umfangreiche Funktionen zum programmgesteuerten Lesen und Ändern von Microsoft Project-Dateien.
### F: Ist Aspose.Tasks für Java mit allen Versionen von Microsoft Project-Dateien kompatibel?
A: Aspose.Tasks für Java unterstützt verschiedene Versionen von Microsoft Project-Dateien, einschließlich MPP- und XML-Formate.
### F: Wie kann ich mit Fehlern bei der Arbeit mit Aspose.Tasks für Java umgehen?
A: Sie können Fehlerbehandlungsmechanismen mithilfe von Try-Catch-Blöcken implementieren, um Ausnahmen, die während der Dateibearbeitung auftreten können, ordnungsgemäß zu behandeln.
### F: Bietet Aspose.Tasks für Java Unterstützung für den Export von Projektdaten in andere Formate?
A: Ja, mit Aspose.Tasks für Java können Sie Projektdaten in Formate wie PDF, XLSX und CSV exportieren.
### F: Wo finde ich zusätzliche Ressourcen und Unterstützung für Aspose.Tasks für Java?
 A: Sie können die besuchen[Aspose.Tasks für Java-Dokumentation](https://reference.aspose.com/tasks/java/) Ausführliche Anleitungen finden Sie im[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) für die Unterstützung der Gemeinschaft.