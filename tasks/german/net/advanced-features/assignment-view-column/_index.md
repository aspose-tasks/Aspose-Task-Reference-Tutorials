---
title: Spalte „Benutzerdefinierte Zuweisungsansicht“ in Aspose.Tasks
linktitle: Spalte „Benutzerdefinierte Zuweisungsansicht“ in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie in Aspose.Tasks für .NET benutzerdefinierte Spalten für die Aufgabenansicht hinzufügen, um die Projektmanagementfunktionen zu verbessern.
weight: 16
url: /de/net/advanced-features/assignment-view-column/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Spalte „Benutzerdefinierte Zuweisungsansicht“ in Aspose.Tasks

## Einführung

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Tasks für .NET benutzerdefinierte Spalten für Aufgabenansichten hinzufügen. Benutzerdefinierte Spalten bieten Flexibilität und ermöglichen Ihnen die Anzeige zusätzlicher Informationen, die für Ihre Projektmanagementanforderungen relevant sind.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

1. Grundkenntnisse der Programmiersprache C#.
2.  Aspose.Tasks für .NET-Bibliothek installiert. Wenn nicht, können Sie es herunterladen[Hier](https://releases.aspose.com/tasks/net/).
3. Eine integrierte Entwicklungsumgebung (IDE) wie Visual Studio.

## Namespaces importieren

Importieren wir zunächst die erforderlichen Namespaces, um auf die Klassen und Methoden zuzugreifen, die zum Erstellen benutzerdefinierter Zuweisungsansichtsspalten erforderlich sind:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Schritt 1: Laden Sie das Projekt

 Laden Sie zunächst Ihre Projektdatei mit`Project` Klasse:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

## Schritt 2: Erstellen Sie Optionen zum Speichern der Tabellenkalkulation

 Erstellen Sie als Nächstes eine Instanz von`Spreadsheet2003SaveOptions` Dadurch können wir die Spalten der Aufgabenansicht anpassen:

```csharp
var options = new Spreadsheet2003SaveOptions();
```

## Schritt 3: Benutzerdefinierte Spalte definieren

 Definieren Sie nun Ihre benutzerdefinierte Spalte, indem Sie eine Instanz von erstellen`AssignmentViewColumn`. Diese Klasse benötigt den Spaltennamen, die Breite und eine Delegate-Funktion, um Zuweisungsdaten in Spaltentext umzuwandeln:

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

## Schritt 4: Benutzerdefinierte Spalte zu den Optionen hinzufügen

Fügen Sie die benutzerdefinierte Spalte zur Sammlung der Zuweisungsansichtsspalten der Speicheroptionen hinzu:

```csharp
options.AssignmentView.Columns.Add(column);
```

## Schritt 5: Durchgehen Sie die Aufgaben

Durchlaufen Sie jede Ressourcenzuweisung im Projekt und zeigen Sie den benutzerdefinierten Spaltentext an:

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var col in options.AssignmentView.Columns)
    {
        var assnCol = (AssignmentViewColumn)col;
        Console.WriteLine("Column Field: " + assnCol.Field);
        Console.WriteLine("Column Text (converted): " + assnCol.GetColumnText(assignment));
        Console.WriteLine();
    }
}
```

## Schritt 6: Speichern Sie das Projekt mit benutzerdefinierten Spalten

Speichern Sie abschließend das Projekt mit den benutzerdefinierten Aufgabenansichtsspalten:

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aspose.Tasks für .NET benutzerdefinierte Spalten für die Aufgabenansicht hinzufügt. Benutzerdefinierte Spalten bieten Flexibilität bei der Anzeige zusätzlicher, auf Ihre Projektanforderungen zugeschnittener Informationen und verbessern so die Projektmanagementfunktionen.

## FAQs

### F1: Kann ich der Aufgabenansicht mehrere benutzerdefinierte Spalten hinzufügen?

 A1: Ja, Sie können mehrere benutzerdefinierte Spalten hinzufügen, indem Sie zusätzliche Instanzen von erstellen`AssignmentViewColumn` und sie dem hinzufügen`Columns` Sammlung.

### F2: Gibt es vordefinierte Konverter für allgemeine Zuweisungsfelder?

A2: Ja, Aspose.Tasks bietet vordefinierte Konverter für allgemeine Zuweisungsfelder und erleichtert so das Extrahieren von Daten für benutzerdefinierte Spalten.

### F3: Kann ich das Erscheinungsbild benutzerdefinierter Spalten anpassen, z. B. durch Formatieren von Text oder Anwenden von Stilen?

A3: Ja, Sie können das Erscheinungsbild benutzerdefinierter Spalten anpassen, indem Sie Eigenschaften wie Breite, Schriftart und Ausrichtung ändern.

### F4: Ist es möglich, Standardspalten aus der Aufgabenansicht zu entfernen?

 A4: Ja, Sie können Standardspalten entfernen, indem Sie sie aus dem ausschließen`Columns` Sammlung oder Setzen ihrer Breite auf Null.

### F5: Unterstützt Aspose.Tasks den Export von Projekten in andere Formate als Tabellenkalkulationen mit benutzerdefinierten Spalten?

A5: Ja, Aspose.Tasks unterstützt den Export von Projekten in verschiedene Formate wie PDF, HTML und XML und ermöglicht so vielseitige Projektberichtsoptionen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
