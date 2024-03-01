---
title: Als PDF in Aspose.Tasks speichern
linktitle: Als PDF in Aspose.Tasks speichern
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie Projektdateien mit Aspose.Tasks für Java in PDF konvertieren. Einfache Schritte für eine effiziente Konvertierung.
type: docs
weight: 17
url: /de/java/project-file-operations/save-as-pdf/
---
## Einführung
In diesem Tutorial führen wir Sie durch den Prozess des Speicherns eines Projekts als PDF mit Aspose.Tasks für Java. Mit Aspose.Tasks können Sie Ihre Projektdateien effizient in das PDF-Format konvertieren und so Kompatibilität und einfache Weitergabe gewährleisten. Lassen Sie uns in die einzelnen Schritte eintauchen:
## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1. Java Development Kit (JDK): Stellen Sie sicher, dass JDK auf Ihrem System installiert ist.
2.  Aspose.Tasks für Java-Bibliothek: Laden Sie die Aspose.Tasks-Bibliothek herunter und installieren Sie sie. Den Download-Link finden Sie hier[Hier](https://releases.aspose.com/tasks/java/).
3. Eine Projektdatei: Halten Sie eine Projektdatei (z. B. HomeMovePlan.mpp) bereit, die Sie in PDF konvertieren möchten.

## Pakete importieren
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```
## Schritt 1: Lesen Sie die Eingabeprojektdatei
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 Stellen Sie sicher, dass Sie ersetzen`"Your Data Directory"` mit dem Pfad zu Ihrem Datenverzeichnis, das die Projektdatei enthält.
## Schritt 2: Speichern Sie das Projekt als PDF
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
Dieses Code-Snippet speichert das Projekt als PDF-Datei mit dem Namen „Project5.pdf“.
## Schritt 3: Inhalt an Zellengröße anpassen
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
Hier legen wir Optionen zum Speichern der PDF-Datei fest, einschließlich passender Inhalte, Zeitrahmen und Präsentationsformat.
## Schritt 4: Legenden ausblenden
```java
o.setLegendOnEachPage(false);
```
Dieser Schritt verbirgt Legenden auf jeder Seite der PDF-Datei.
## Schritt 5: Speichern Sie das Projekt mit den angewendeten Optionen
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
Schließlich speichert dieser Code das Projekt mit den angewendeten Optionen in einer PDF-Datei.

## Abschluss
In diesem Tutorial haben wir gelernt, wie man Aspose.Tasks für Java verwendet, um ein Projekt als PDF zu speichern. Wenn Sie diese einfachen Schritte befolgen, können Sie Ihre Projektdateien effizient konvertieren, um sie einfach zu teilen und zu verteilen.
## FAQs
### F: Ist Aspose.Tasks mit allen Java-Versionen kompatibel?
A: Ja, Aspose.Tasks unterstützt Java-Versionen ab JDK 6 und höher.
### F: Kann ich das Erscheinungsbild der PDF-Ausgabe anpassen?
A: Auf jeden Fall! Aspose.Tasks bietet verschiedene Optionen, um die PDF-Ausgabe entsprechend Ihren Anforderungen anzupassen.
### F: Unterstützt Aspose.Tasks andere Dateiformate für die Konvertierung?
A: Ja, Aspose.Tasks unterstützt eine Vielzahl von Dateiformaten, darunter MPP, XML, XLSX und mehr.
### F: Gibt es eine Testversion für Aspose.Tasks?
 A: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks erhalten[Hier](https://releases.aspose.com/).
### F: Wo kann ich Unterstützung für Aspose.Tasks erhalten?
 A: Für Unterstützung und Unterstützung können Sie die besuchen[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15).