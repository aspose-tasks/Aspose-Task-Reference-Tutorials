---
title: Passen Sie Gantt-Diagrammspalten mit Aspose.Tasks an
linktitle: Gantt-Diagrammspalten in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie Gantt-Diagrammspalten in Aspose.Tasks für .NET anpassen, um bestimmte Aufgabeninformationen effizient anzuzeigen.
type: docs
weight: 21
url: /de/net/tasks-project-management/gantt-chart-columns/
---
## Einführung
Gantt-Diagramme sind ein grundlegendes Werkzeug im Projektmanagement und bieten eine visuelle Darstellung von Aufgaben, Zeitplänen und Ressourcen. Aspose.Tasks für .NET bietet leistungsstarke Funktionen zur Bearbeitung von Gantt-Diagrammen, einschließlich der Anpassung von Spalten zur Anzeige spezifischer Aufgabeninformationen. In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Tasks für .NET mit Gantt-Diagrammspalten arbeiten.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
1.  Installation: Aspose.Tasks für .NET auf Ihrem System installiert. Wenn nicht, laden Sie es herunter und installieren Sie es von[Hier](https://releases.aspose.com/tasks/net/).
2. .NET-Entwicklungsumgebung: Grundkenntnisse in C# und dem .NET-Framework.
3. Beispielprojektdatei: Halten Sie eine Beispiel-Microsoft-Projektdatei bereit (`.mpp`) praktisch zum Experimentieren. Wenn Sie noch keins haben, können Sie ein einfaches Projekt in MS Project erstellen und speichern.

## Namespaces importieren
Zunächst müssen Sie die erforderlichen Namespaces importieren, um mit Aspose.Tasks für .NET arbeiten zu können:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Globalization;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Schritt 1: Laden Sie die Projektdatei
 Laden Sie die Projektdatei mit`Project` Von Aspose.Tasks bereitgestellte Klasse:
```csharp
// Der Pfad zum Dokumentenverzeichnis.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var task = project.RootTask.Children.GetById(1);
```
## Schritt 2: Gantt-Diagrammspalten definieren
Definieren Sie die Spalten, die Sie im Gantt-Diagramm anzeigen möchten. Sie können integrierte Felder angeben oder benutzerdefinierte Felder erstellen:
```csharp
var columns = new List<ViewColumn>
{
    new GanttChartColumn(20, Field.TaskUniqueID),
    new GanttChartColumn("Name", 150, Field.TaskName),
    new GanttChartColumn("Start", 100, Field.TaskStart),
    new GanttChartColumn("End", 100, Field.TaskFinish),
    new GanttChartColumn("R-Initials", 100, Field.TaskResourceInitials),
    new GanttChartColumn("R-Names", 100, Field.TaskResourceNames),
    new GanttChartColumn("Work", 50, Field.TaskWork),
    new GanttChartColumn(
        "Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new GanttChartColumn(
        "Actual Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.ActualCost).ToString(CultureInfo.InvariantCulture);
        },
        Field.TaskActualCost)
};
```
## Schritt 3: Über Spalten iterieren
Durchlaufen Sie die definierten Spalten, um auf deren Eigenschaften zuzugreifen und Informationen anzuzeigen:
```csharp
foreach (var column in columns)
{
    var col = (GanttChartColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(task));
    Console.WriteLine();
}
```
## Schritt 4: Gantt-Diagramm im CSV-Format speichern
Speichern Sie das Gantt-Diagramm mit definierten Spalten in einer CSV-Datei:
```csharp
var options = new CsvOptions
{
    View = new ProjectView(columns)
};
project.Save(DataDir + "WorkWithGanttChartColumn_out.csv", options);
```
Wenn Sie diese Schritte befolgen, können Sie effektiv mit Gantt-Diagrammspalten in Aspose.Tasks für .NET arbeiten und Aufgabeninformationen nach Bedarf anpassen und anzeigen.

## Abschluss
Die Beherrschung der Manipulation von Gantt-Diagrammspalten in Aspose.Tasks für .NET eröffnet endlose Möglichkeiten, die Visuals des Projektmanagements an Ihre spezifischen Bedürfnisse anzupassen. Indem Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie Aufgabeninformationen effizient verwalten und die Projektklarheit und -organisation verbessern.
## FAQs
### F: Kann ich in Aspose.Tasks für .NET benutzerdefinierte Spalten erstellen?
A: Ja, Sie können benutzerdefinierte Spalten definieren, um bestimmte Aufgabenattribute entsprechend Ihren Projektanforderungen anzuzeigen.
### F: Ist Aspose.Tasks für .NET mit allen Versionen von Microsoft Project-Dateien kompatibel?
A: Aspose.Tasks für .NET unterstützt verschiedene Versionen von Microsoft Project-Dateien und gewährleistet so die Kompatibilität zwischen verschiedenen Projektumgebungen.
### F: Wie kann ich mit Aspose.Tasks für .NET mit komplexen Projektstrukturen umgehen?
A: Aspose.Tasks für .NET bietet umfassende APIs und Funktionen zur Verwaltung komplexer Projektstrukturen und bietet Flexibilität und Skalierbarkeit.
### F: Gibt es Einschränkungen hinsichtlich der Anzahl der Spalten, die ich einem Gantt-Diagramm hinzufügen kann?
A: Aspose.Tasks für .NET bietet umfangreiche Anpassungsoptionen, sodass Sie ohne Einschränkungen eine beträchtliche Anzahl von Spalten zu Gantt-Diagrammen hinzufügen können.
### F: Wo finde ich zusätzlichen Support und Ressourcen für Aspose.Tasks für .NET?
A: Sie können die von Aspose.Tasks für .NET bereitgestellte Dokumentation, Community-Foren und Support-Kanäle durchsuchen, um auf umfassende Ressourcen und Unterstützung zuzugreifen.