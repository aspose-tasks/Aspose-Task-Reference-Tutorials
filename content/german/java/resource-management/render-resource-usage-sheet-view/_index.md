---
title: Render-Ressourcennutzung und Blattansicht in Aspose.Tasks
linktitle: Render-Ressourcennutzung und Blattansicht in Aspose.Tasks
second_title: Aspose.Tasks Java-API
description: Erfahren Sie, wie Sie MS Project-Ressourcennutzungs- und Blattansichten in Aspose.Tasks für Java rendern. Befolgen Sie unsere Schritt-für-Schritt-Anleitung, um mühelos detaillierte PDF-Berichte zu erstellen.
type: docs
weight: 16
url: /de/java/resource-management/render-resource-usage-sheet-view/
---
## Einführung
In diesem Tutorial erfahren Sie, wie Sie Aspose.Tasks für Java zum Rendern von MS Project-Ressourcennutzungs- und Blattansichten verwenden. Aspose.Tasks ist eine leistungsstarke Java-Bibliothek, die es Entwicklern ermöglicht, mit Microsoft Project-Dateien zu arbeiten, ohne dass Microsoft Project installiert werden muss.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen installiert und eingerichtet sind:
1. Java Development Kit (JDK): Stellen Sie sicher, dass auf Ihrem System das Java Development Kit installiert ist. Sie können die neueste Version von JDK von der Oracle-Website herunterladen und installieren.
2.  Aspose.Tasks für Java: Laden Sie die Aspose.Tasks für Java-Bibliothek von herunter und installieren Sie sie[Download-Seite](https://releases.aspose.com/tasks/java/).

## Pakete importieren
Zunächst müssen Sie die erforderlichen Pakete in Ihr Java-Projekt importieren:
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```
## Schritt 1: Lesen Sie das Quellprojekt
```java
// Der Pfad zum Dokumentenverzeichnis.
String dataDir = "Your Data Directory";
// Lesen Sie das Quellprojekt
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```
In diesem Schritt geben wir den Pfad zur Quellprojektdatei an (`ResourceUsageView.mpp` ) und verwenden Sie die`Project` Klasse, um es zu lesen.
## Schritt 2: Definieren Sie SaveOptions mit den erforderlichen TimeScale-Einstellungen
```java
// Definieren Sie die SaveOptions mit den erforderlichen TimeScale-Einstellungen als Tage
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```
 Hier definieren wir die`SaveOptions` mit den erforderlichen`TimeScale` Einstellungen. In diesem Beispiel legen wir fest`TimeScale` bis Tage.
## Schritt 3: Stellen Sie das Präsentationsformat auf ResourceUsage ein
```java
// Legen Sie das Präsentationsformat auf ResourceUsage fest
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```
 Wir stellen das Präsentationsformat auf ein`ResourceUsage`, was angibt, dass wir die Ansicht „Ressourcennutzung“ rendern möchten.
## Schritt 4: Speichern Sie das Projekt
```java
// Speichern Sie das Projekt
project.save(dataDir + days, options);
```
Abschließend speichern wir das Projekt mit den angegebenen Optionen. In diesem Beispiel wird die Ausgabedatei unter gespeichert`result_days.pdf`.
## Schritt 5: Ansichten für andere Zeitskaleneinstellungen rendern
Wiederholen Sie die Schritte 2 bis 4, um Ansichten mit unterschiedlichen TimeScale-Einstellungen (ThirdsOfMonths und Months) zu rendern.
```java
// Legen Sie die Zeitskaleneinstellungen auf ThirdsOfMonths fest
options.setTimescale(Timescale.ThirdsOfMonths);
// Speichern Sie das Projekt
project.save(thirds, options);
// Stellen Sie die Zeitskaleneinstellungen auf Monate ein
options.setTimescale(Timescale.Months);
// Speichern Sie das Projekt
project.save(dataDir + months, options);
```
 Stellen Sie sicher, dass Sie die ändern`Timescale` Passen Sie die Einstellungen für jede Ansicht entsprechend an.

## Abschluss
In diesem Tutorial haben wir untersucht, wie Sie Aspose.Tasks für Java zum Rendern von MS Project-Ressourcennutzungs- und Blattansichten verwenden. Wenn Sie die oben beschriebenen Schritte befolgen, können Sie diese Ansichten effizient im PDF-Format generieren und so eine bessere Visualisierung und Analyse Ihrer Projektdaten ermöglichen.
## FAQs
### Kann Aspose.Tasks neben „Ressourcennutzung“ und „Blatt“ auch andere Ansichten rendern?
Aspose.Tasks unterstützt das Rendern verschiedener Ansichten wie unter anderem Gantt-Diagramm, Aufgabenverwendung und Kalenderansichten.
### Ist Aspose.Tasks mit verschiedenen Versionen von Microsoft Project-Dateien kompatibel?
Ja, Aspose.Tasks unterstützt eine Vielzahl von Microsoft Project-Dateiformaten, einschließlich MPP-, MPT- und XML-Formate.
### Kann ich das Erscheinungsbild gerenderter Ansichten mithilfe von Aspose.Tasks anpassen?
Absolut! Aspose.Tasks bietet umfangreiche Optionen zum Anpassen des Erscheinungsbilds und Layouts gerenderter Ansichten an Ihre spezifischen Anforderungen.
### Erfordert Aspose.Tasks die Installation von Microsoft Project auf dem System?
Nein, Aspose.Tasks ist eine eigenständige Bibliothek und erfordert für ihre Funktion keine Installation von Microsoft Project.
### Ist technischer Support für Aspose.Tasks-Benutzer verfügbar?
 Ja, Aspose.Tasks-Benutzer können technischen Support über das in Anspruch nehmen[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15).