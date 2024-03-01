---
title: Reduzierung der Lücke zwischen Aufgabenliste und Fußzeile in Aspose.Tasks
linktitle: Reduzierung der Lücke zwischen Aufgabenliste und Fußzeile in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie mit Aspose.Tasks für Java die Lücke zwischen MS Project-Aufgabenlisten und Fußzeilen verringern. Optimieren Sie mühelos das Layout von Projektdokumenten.
type: docs
weight: 10
url: /de/java/project-file-operations/reduce-gap-tasks-list-footer/
---
## Einführung
In diesem Tutorial befassen wir uns mit der Reduzierung der Lücke zwischen der Aufgabenliste und der Fußzeile in Microsoft Project-Dateien mithilfe von Aspose.Tasks für Java. Wenn Sie diese Schritte befolgen, können Sie das Layout Ihrer Projektdokumente mühelos optimieren.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1. Java Development Kit (JDK): Stellen Sie sicher, dass JDK auf Ihrem System installiert ist.
2.  Aspose.Tasks for Java-Bibliothek: Laden Sie die Aspose.Tasks for Java-Bibliothek herunter und fügen Sie sie in Ihr Projekt ein. Sie können es herunterladen unter[Hier](https://releases.aspose.com/tasks/java/).

## Pakete importieren
Bevor wir in den Codierungsteil eintauchen, importieren wir die erforderlichen Pakete:
```java
import com.aspose.tasks.HtmlSaveOptions;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.PageSize;
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```
## Schritt 1: Geben Sie den Pfad zu Ihrem Datenverzeichnis an
```java
String dataDir = "Your Data Directory";
```
 Unbedingt austauschen`"Your Data Directory"` mit dem Pfad zu Ihrem tatsächlichen Datenverzeichnis, in dem sich Ihre Microsoft Project-Datei befindet (`HomeMovePlan.mpp` in diesem Beispiel) liegt.
## Schritt 2: Lesen Sie die MPP-Datei
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
 Diese Codezeile liest die Microsoft Project-Datei mit dem Namen`HomeMovePlan.mpp`.
## Schritt 3: ImageSaveOptions festlegen
```java
ImageSaveOptions imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
imageSaveOptions.setReduceFooterGap(true);
imageSaveOptions.setRenderToSinglePage(false);
imageSaveOptions.setPageSize(PageSize.A0);
imageSaveOptions.setTimescale(Timescale.Days);
```
 Konfigurieren Sie die Optionen und Einstellungen zum Speichern von Bildern`ReduceFooterGap` Zu`true` um die Lücke zwischen der Aufgabenliste und der Fußzeile zu verringern.
## Schritt 4: Als Bild speichern
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.png", (SaveOptions) imageSaveOptions);
```
Speichern Sie das Projekt als Bild mit den konfigurierten Optionen.
## Schritt 5: PdfSaveOptions festlegen
```java
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.setReduceFooterGap(true);
pdfSaveOptions.setSaveToSeparateFiles(true);
pdfSaveOptions.setPageSize(PageSize.A0);
pdfSaveOptions.setTimescale(Timescale.Days);
```
 Definieren Sie PDF-Speicheroptionen und stellen Sie sicher, dass sie festgelegt werden`ReduceFooterGap` Zu`true`.
## Schritt 6: Als PDF speichern
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.pdf", (SaveOptions) pdfSaveOptions);
```
Speichern Sie das Projekt als PDF mit den konfigurierten Optionen.
## Schritt 7: HtmlSaveOptions festlegen
```java
HtmlSaveOptions htmlSaveOptions = new HtmlSaveOptions();
htmlSaveOptions.setReduceFooterGap(true); // auf true gesetzt
htmlSaveOptions.setIncludeProjectNameInPageHeader(false);
htmlSaveOptions.setIncludeProjectNameInTitle(false);
htmlSaveOptions.setPageSize(PageSize.A0);
htmlSaveOptions.setTimescale(Timescale.Days);
```
 Geben Sie die HTML-Speicheroptionen und -Einstellungen an`ReduceFooterGap` Zu`true`.
## Schritt 8: Als HTML speichern
```java
project.save(dataDir + "ReducingGapBetweenTasksListAndFooter_out.html", htmlSaveOptions);
```
Speichern Sie das Projekt als HTML-Datei mit den konfigurierten Optionen.

## Abschluss
Zusammenfassend lässt sich sagen, dass die Reduzierung der Lücke zwischen der Aufgabenliste und der Fußzeile in Microsoft Project-Dateien mit Aspose.Tasks für Java ein unkomplizierter Prozess ist. Indem Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie das Layout Ihrer Projektdokumente effizient optimieren.

## FAQs

### F: Ist Aspose.Tasks mit allen Versionen von Microsoft Project kompatibel?

A: Aspose.Tasks unterstützt die Formate Microsoft Project 2003–2019 und gewährleistet so die Kompatibilität zwischen verschiedenen Versionen.

### F: Kann ich das Erscheinungsbild der Fußzeile in meinen Projektdokumenten anpassen?

A: Ja, Aspose.Tasks bietet umfangreiche Optionen zum Anpassen des Erscheinungsbilds von Fußzeilen, einschließlich der Reduzierung von Lücken und der Anpassung der Inhaltsplatzierung.

### F: Unterstützt Aspose.Tasks das Speichern von Projekten in anderen Formaten als PNG, PDF und HTML?

A: Ja, Aspose.Tasks unterstützt eine Vielzahl von Formaten, darunter unter anderem XLSX, XML und MPP.

### F: Gibt es eine Testversion für Aspose.Tasks?

 A: Ja, Sie können eine kostenlose Testversion von Aspose.Tasks herunterladen[Hier](https://releases.aspose.com/).

### F: Wo kann ich Unterstützung erhalten, wenn bei der Verwendung von Aspose.Tasks Probleme auftreten?

 A: Sie können Hilfe vom Aspose.Tasks-Community-Forum erhalten[Hier](https://forum.aspose.com/c/tasks/15).