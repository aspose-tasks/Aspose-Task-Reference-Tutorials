---
title: Erweiterte UND-Verknüpfung in Aspose.Tasks
linktitle: Erweiterte UND-Verknüpfung in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie in Aspose.Tasks für .NET erweiterte UND-Operationen durchführen, um Projektaufgaben basierend auf mehreren Kriterien effizient zu filtern.
type: docs
weight: 10
url: /de/net/advanced-features/advanced-and-operation/
---
## Einführung

 In diesem Tutorial befassen wir uns mit der erweiterten UND-Verknüpfung in Aspose.Tasks für .NET, einem leistungsstarken Tool zum Verwalten von Aufgaben und Projekten. Wir werden untersuchen, wie Projektaufgaben anhand mehrerer Bedingungen mithilfe von gefiltert werden können`Util.And` Klasse.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

1. Grundkenntnisse der Programmiersprache C#.
2.  Installierte Aspose.Tasks für .NET. Wenn nicht, können Sie es hier herunterladen[Hier](https://releases.aspose.com/tasks/net/).
3. Integrierte Entwicklungsumgebung (IDE) wie Visual Studio.

## Namespaces importieren

Importieren wir zunächst die erforderlichen Namespaces in unser C#-Projekt:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;

```

## Schritt 1: Projekt initialisieren und Aufgaben sammeln

Beginnen Sie mit der Initialisierung eines neuen Aspose.Tasks-Projekts und der Sammlung aller darin enthaltenen Aufgaben:

```csharp
// Der Pfad zum Dokumentenverzeichnis.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

## Schritt 2: Filterbedingungen definieren

Als nächstes definieren Sie die Filterbedingungen. Für dieses Beispiel erstellen wir zwei Bedingungen: eine zum Filtern von Sammelaufgaben und eine weitere zum Filtern von Nicht-Null-Aufgaben:

```csharp
var condition1 = new SummaryCondition();
var condition2 = new NotNullCondition();
```

## Schritt 3: Bedingungen mit UND-Verknüpfung kombinieren

 Kombinieren Sie nun die Bedingungen mithilfe von`Util.And` Klasse zum Erstellen einer zusammengesetzten Bedingung:

```csharp
var joinedCondition = new And<Task>(condition1, condition2);
```

## Schritt 4: Bedingungs- und Filteraufgaben anwenden

Wenden Sie die kombinierte Bedingung auf die gesammelten Aufgaben an und filtern Sie sie entsprechend:

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

## Schritt 5: Gefilterte Aufgaben ausgeben

Geben Sie abschließend die gefilterten Aufgaben aus:

```csharp
Console.WriteLine("Filtered tasks: ");
foreach (var task in collection)
{
    Console.WriteLine(" Name: " + task.Get(Tsk.Name));
    // Hier können weitere Bearbeitungen vorgenommen werden
}
```

## Abschluss

 In diesem Tutorial haben wir gelernt, wie man erweiterte UND-Operationen in Aspose.Tasks für .NET durchführt. Durch das Kombinieren von Bedingungen mithilfe der`Util.And`Klasse können wir Aufgaben anhand mehrerer Kriterien effizient filtern.

## FAQs

### F1: Was ist Aspose.Tasks für .NET?

A: Aspose.Tasks für .NET ist eine robuste API, die es Entwicklern ermöglicht, Microsoft Project-Dateien programmgesteuert in .NET-Anwendungen zu bearbeiten.

### F2: Kann ich mit Util.And mehr als zwei Bedingungen anwenden?

A: Ja, Util.And kann verwendet werden, um eine beliebige Anzahl von Bedingungen zu kombinieren, um komplexe Filterkriterien zu erstellen.

### F3: Gibt es eine kostenlose Testversion für Aspose.Tasks für .NET?

 A: Ja, Sie können eine kostenlose Testversion herunterladen[Hier](https://releases.aspose.com/).

### F4: Wo finde ich Dokumentation für Aspose.Tasks für .NET?

 A: Sie finden die Dokumentation[Hier](https://reference.aspose.com/tasks/net/).

### F5: Wie erhalte ich Unterstützung für Aspose.Tasks für .NET?

A: Sie können Unterstützung vom Aspose.Tasks-Community-Forum erhalten[Hier](https://forum.aspose.com/c/tasks/15).