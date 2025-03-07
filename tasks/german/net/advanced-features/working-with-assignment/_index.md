---
title: Arbeiten mit Zuweisungen in Aspose.Tasks
linktitle: Arbeiten mit Zuweisungen in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie Projektzuweisungen in .NET mit Aspose.Tasks verwalten. Entdecken Sie verschiedene Konturen für die Ressourcenplanung.
weight: 13
url: /de/net/advanced-features/working-with-assignment/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Arbeiten mit Zuweisungen in Aspose.Tasks

## Einführung

In diesem Tutorial erfahren Sie, wie Sie mit Aufgaben in Aspose.Tasks für .NET arbeiten. Aufgaben sind im Projektmanagement von entscheidender Bedeutung, da sie Ressourcen den Aufgaben zuweisen und so bei der Planung und Verfolgung des Fortschritts helfen. Wir konzentrieren uns auf die Generierung zeitphasenbezogener Ressourcenzuweisungsdaten mit verschiedenen Konturen mithilfe von Aspose.Tasks.

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

1.  Installation von Aspose.Tasks für .NET: Laden Sie die Aspose.Tasks für .NET-Bibliothek von herunter und installieren Sie sie[Download-Link](https://releases.aspose.com/tasks/net/).
2. Grundkenntnisse von C# und .NET Framework: Um mitzumachen, sind Kenntnisse der Programmiersprache C# und der .NET Framework-Konzepte erforderlich.

## Namespaces importieren

Stellen Sie sicher, dass Sie die erforderlichen Namespaces in Ihr C#-Projekt importieren:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;

```

## Schritt 1: Erstellen Sie ein Projekt und eine Aufgabe

Beginnen wir damit, ein neues Projekt zu erstellen und ihm eine Aufgabe hinzuzufügen. Legen Sie das Startdatum, die Dauer und das Enddatum für die Aufgabe fest:

```csharp
var project = new Project();
project.Set(Prj.StartDate, new DateTime(2000, 1, 3, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 1, 7, 17, 0, 0));

var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2000, 1, 3, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task.Set(Tsk.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## Schritt 2: Fügen Sie eine Ressource hinzu und weisen Sie sie einer Aufgabe zu

Fügen Sie als Nächstes eine Ressource zum Projekt hinzu und weisen Sie sie der zuvor erstellten Aufgabe zu:

```csharp
var resource = project.Resources.Add("Resource");

var resourceAssignment = project.ResourceAssignments.Add(task, resource);
resourceAssignment.Set(Asn.Start, new DateTime(2000, 1, 3, 8, 0, 0));
resourceAssignment.Set(Asn.Work, project.GetWork(8));
resourceAssignment.Set(Asn.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## Schritt 3: Zeitphasendaten mit unterschiedlichen Konturen generieren

Lassen Sie uns nun Zeitphasendaten mit unterschiedlichen Konturen für die Ressourcenzuweisung generieren:

```csharp
Console.WriteLine("Flat contour");

var collection = task.GetTimephasedData(project.Get(Prj.StartDate), project.Get(Prj.FinishDate));
foreach (var td in collection)
{
	Console.WriteLine(td.Start.ToShortDateString() + " " + td.Value);
}
```

## Schritt 4: Konturen ändern und Daten generieren

Wir können den Konturtyp ändern und entsprechend Zeitphasendaten generieren. Hier sind einige Beispiele:

```csharp
// Kontur ändern
resourceAssignment.Set(Asn.WorkContour, WorkContourType.Turtle);
// Generieren Sie Zeitphasendaten und drucken Sie sie aus
// Wiederholen Sie diesen Schritt für andere Konturtypen
```

## Abschluss

In diesem Tutorial haben wir gelernt, wie man mit Aufgaben in Aspose.Tasks für .NET arbeitet. Wir haben die Generierung zeitphasenbezogener Ressourcenzuweisungsdaten mit verschiedenen Konturen untersucht. Dieses Wissen kann in Projektmanagement-Szenarien von großem Nutzen sein.

## FAQs

### F1: Kann ich Aspose.Tasks zum Planen von Aufgaben in meiner .NET-Anwendung verwenden?

A1: Ja, Aspose.Tasks bietet umfassende APIs für die Aufgabenplanung und -verwaltung in .NET-Anwendungen.

### F2: Gibt es eine kostenlose Testversion für Aspose.Tasks?

 A2: Ja, Sie können eine kostenlose Testversion von nutzen[Hier](https://releases.aspose.com/).

### F3: Gibt es Einschränkungen hinsichtlich der Anzahl der Aufgaben oder Ressourcen in Aspose.Tasks?

A3: Aspose.Tasks legt keine Beschränkungen hinsichtlich der Anzahl der Aufgaben oder Ressourcen fest, die Sie in Ihren Projekten verwalten können.

### F4: Kann ich die Konturen für Ressourcenzuweisungen in Aspose.Tasks anpassen?

A4: Ja, wie in diesem Tutorial gezeigt, können Sie je nach Projektanforderungen verschiedene Konturen wie Schildkröte, Glocke, Spitze usw. festlegen.

### F5: Wo finde ich Unterstützung für Aspose.Tasks-bezogene Abfragen?

A5: Unterstützung finden Sie auf der[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) wo Experten und Community-Mitglieder aktiv an Diskussionen teilnehmen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
