---
title: Beherrschen der MS Project-Speicheroptionen für Aspose.Tasks
linktitle: Allgemeine Speicheroptionen für Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie MS Project-Dateien mit Aspose.Tasks für .NET effizient speichern. Passen Sie die Ausgabeoptionen mühelos an Ihre Projekte an.
weight: 17
url: /de/net/saving-options/general-save-options/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Beherrschen der MS Project-Speicheroptionen für Aspose.Tasks

## Einführung
Aspose.Tasks für .NET bietet leistungsstarke Funktionen zum programmgesteuerten Bearbeiten von Microsoft Project-Dateien. In diesem Tutorial befassen wir uns mit den Feinheiten des Speicherns von MS Project-Dateien mithilfe verschiedener Optionen von Aspose.Tasks. Konkret konzentrieren wir uns auf die allgemeinen Speicheroptionen, die für Aspose.Tasks verfügbar sind, sodass Sie die Ausgabe an Ihre spezifischen Anforderungen anpassen können.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1.  Installation von Aspose.Tasks für .NET: Laden Sie Aspose.Tasks für .NET von herunter und installieren Sie es[Download-Link](https://releases.aspose.com/tasks/net/).
2. Grundlegendes Verständnis von .NET Framework: Vertrautheit mit .NET-Programmierkonzepten ist von Vorteil.

## Namensräume importieren
Stellen Sie vor dem Eintauchen in den Code sicher, dass Sie die erforderlichen Namespaces importieren:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Drawing;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
    using Aspose.Tasks.Visualization;
```

## Schritt 1: Laden Sie die Projektdatei
Zunächst müssen Sie die MS Project-Datei mit Aspose.Tasks laden:
```csharp
var project = new Project("Your Document Directory/CreateProject2.mpp");
```
## Schritt 2: Speicheroptionen definieren
 Definieren Sie die Speicheroptionen entsprechend Ihren Anforderungen. In diesem Beispiel verwenden wir`Spreadsheet2003SaveOptions`:
```csharp
var options = new Spreadsheet2003SaveOptions();
```
## Schritt 3: Ansichtsspalten anpassen
Sie können Ansichtsspalten wie Gantt-Diagramm, Ressourcenansicht und Aufgabenansicht anpassen. So fügen Sie jeweils Spalten hinzu:
```csharp
var ganttChartColumn = new GanttChartColumn("WBS", 100, delegate(Task task) { return task.Get(Tsk.WBS); });
options.View.Columns.Add(ganttChartColumn);
var resourceViewColumn = new ResourceViewColumn("Cost center", 100, delegate(Resource resource) { return resource.Get(Rsc.CostCenter); });
options.ResourceView.Columns.Add(resourceViewColumn);
var assignmentViewColumn = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
options.AssignmentView.Columns.Add(assignmentViewColumn);
```
## Schritt 4: Speichern Sie das Projekt mit Optionen
Speichern Sie abschließend das Projekt mit den angegebenen Optionen:
```csharp
project.Save("Your Document Directory/UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Abschluss
Wenn Sie die allgemeinen MS Project-Speicheroptionen mit Aspose.Tasks für .NET beherrschen, können Sie das Ausgabeformat effizient an die Anforderungen Ihres Projekts anpassen.
## FAQs
### F: Ist Aspose.Tasks mit verschiedenen Versionen von MS Project-Dateien kompatibel?
A: Ja, Aspose.Tasks unterstützt verschiedene Versionen von MS Project-Dateien und gewährleistet so die Kompatibilität in verschiedenen Umgebungen.
### F: Kann ich Aspose.Tasks vor dem Kauf testen?
 A: Ja, Sie können Aspose.Tasks mit einer kostenlosen Testversion erkunden[Hier](https://releases.aspose.com/).
### F: Wo finde ich Dokumentation für Aspose.Tasks?
 A: Eine ausführliche Dokumentation finden Sie hier[Hier](https://reference.aspose.com/tasks/net/), mit umfassenden Anleitungen zur Verwendung der Aspose.Tasks-Funktionen.
### F: Wie kann ich temporäre Lizenzen für Aspose.Tasks erhalten?
 A: Für Evaluierungszwecke stehen temporäre Lizenzen zur Verfügung[Hier](https://purchase.aspose.com/temporary-license/).
### F: Wo kann ich Unterstützung für Fragen zu Aspose.Tasks erhalten?
 A: Sie können dem Aspose.Tasks-Community-Forum beitreten[Hier](https://forum.aspose.com/c/tasks/15)um Unterstützung von Experten und anderen Entwicklern zu erhalten.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
