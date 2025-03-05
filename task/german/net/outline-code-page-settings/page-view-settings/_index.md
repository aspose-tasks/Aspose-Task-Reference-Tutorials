---
title: Passen Sie die Einstellungen für die Seitenansicht von MS Project in Aspose.Tasks an
linktitle: Konfigurieren der Seitenansichtseinstellungen in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie die Seitenansichtseinstellungen in Aspose.Tasks für .NET konfigurieren, um das Druckformat Ihrer Microsoft Project-Dokumente anzupassen.
type: docs
weight: 21
url: /de/net/outline-code-page-settings/page-view-settings/
---
## Einführung
Microsoft Project ist ein leistungsstarkes Tool für das Projektmanagement. Manchmal müssen Sie jedoch die Art und Weise anpassen, wie Ihr Projekt angezeigt und gedruckt wird. Mit Aspose.Tasks für .NET können Sie die Einstellungen für die Seitenansicht ganz einfach so konfigurieren, dass sie Ihren spezifischen Anforderungen entsprechen. In diesem Tutorial führen wir Sie Schritt für Schritt durch den Prozess.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1.  Aspose.Tasks für .NET: Stellen Sie sicher, dass Sie die Aspose.Tasks für .NET-Bibliothek heruntergeladen und installiert haben. Sie können es herunterladen unter[Hier](https://releases.aspose.com/tasks/net/).
2. Microsoft Project-Datei: Halten Sie eine Microsoft Project-Datei bereit, für die Sie die Seitenansichtseinstellungen konfigurieren möchten.

## Namespaces importieren
Zunächst müssen Sie die erforderlichen Namespaces importieren, um mit Aspose.Tasks in Ihrem .NET-Projekt arbeiten zu können.
```csharp
    
    using Aspose.Tasks.Saving;
```
## Schritt 1: Laden Sie die Projektdatei
 Laden Sie zunächst Ihre Microsoft Project-Datei in eine Instanz von`Project` Klasse.
```csharp
// Der Pfad zum Dokumentenverzeichnis.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Input.mpp");
```
## Schritt 2: Legen Sie die Anzahl der ersten Spalten fest
Geben Sie die Anzahl der ersten Spalten an, die auf allen Seiten gedruckt werden sollen.
```csharp
project.DefaultView.PageInfo.PageViewSettings.FirstColumnsCount = 2;
```
## Schritt 3: Notizen drucken
Wählen Sie aus, ob Notizen zusammen mit dem Projekt gedruckt werden sollen.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintNotes = true;
```
## Schritt 4: Passen Sie die Zeitskala an das Ende der Seite an
Entscheiden Sie, ob die Zeitskala beim Drucken an das Ende einer Seite angepasst werden soll.
```csharp
project.DefaultView.PageInfo.PageViewSettings.FitTimescaleToEndOfPage = true;
```
## Schritt 5: Alle Blattspalten drucken
Geben Sie an, ob alle Blattspalten einer Ansicht gedruckt werden sollen.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintAllSheetColumns = true;
```
## Schritt 6: Leere Seiten drucken
Wählen Sie aus, ob leere Seiten einer Ansicht gedruckt werden sollen.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintBlankPages = false;
```
## Schritt 7: Drucken Sie die ersten Spalten auf allen Seiten
Legen Sie fest, ob eine bestimmte Anzahl erster Spalten auf allen Seiten gedruckt werden soll.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintFirstColumnsCountOnAllPages = true;
```
## Schritt 8: Speichern Sie das Projekt mit den konfigurierten Einstellungen
Speichern Sie abschließend das Projekt mit den konfigurierten Seitenansichtseinstellungen und geben Sie das Ausgabeformat an, z. B. PDF.
```csharp
project.Save(DataDir + "ProjectWithComments_out.pdf", SaveFileFormat.Pdf);
```

## Abschluss
Das Konfigurieren der Microsoft Project-Seitenansichtseinstellungen in Aspose.Tasks für .NET ist unkompliziert und ermöglicht Ihnen, das Druckformat genau an Ihre Bedürfnisse anzupassen. Indem Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie sicherstellen, dass Ihre Projektdokumente genau wie erforderlich präsentiert werden.
## FAQs
### F: Kann ich die Seitenansichtseinstellungen für andere Dateiformate als PDF konfigurieren?
A: Ja, Aspose.Tasks unterstützt verschiedene Dateiformate zum Speichern von Projekten, darunter XLSX, MPP und HTML.
### F: Gibt es Einschränkungen hinsichtlich der Anzahl der Spalten, die ich drucken kann?
A: Mit Aspose.Tasks können Sie die Anzahl der zu druckenden Spalten entsprechend Ihren Anforderungen anpassen.
### F: Kann ich für verschiedene Projekte unterschiedliche Einstellungen für die Seitenansicht anwenden?
A: Ja, Sie können die Seitenansichtseinstellungen für jede Projektdatei, mit der Sie arbeiten, unabhängig anpassen.
### F: Ist Aspose.Tasks mit allen Versionen von Microsoft Project kompatibel?
A: Aspose.Tasks bietet Kompatibilität mit Microsoft Project 2003 und späteren Versionen.
### F: Wo finde ich weitere Hilfe oder Unterstützung für Aspose.Tasks?
 A: Sie können die besuchen[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) für alle Fragen oder Probleme, die während der Nutzung auftreten.