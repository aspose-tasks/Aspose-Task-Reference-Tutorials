---
title: Umgang mit Aufgabenlinks in Aspose.Tasks
linktitle: Umgang mit Aufgabenlinks in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Entdecken Sie die Leistungsfähigkeit von Aspose.Tasks für .NET bei der effizienten Verwaltung von Projektaufgabenverknüpfungen. Befolgen Sie unsere Schritt-für-Schritt-Anleitung, um Ihr Projektmanagement-Erlebnis zu verbessern.
weight: 19
url: /de/net/task-table-management/task-link-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Umgang mit Aufgabenlinks in Aspose.Tasks

## Einführung
Willkommen bei der Schritt-für-Schritt-Anleitung zum Umgang mit Aufgabenlinks in Aspose.Tasks für .NET! Aufgabenverknüpfungen spielen im Projektmanagement eine entscheidende Rolle, da sie es Ihnen ermöglichen, Beziehungen zwischen Aufgaben herzustellen und Abhängigkeiten zu schaffen. In diesem Tutorial führen wir Sie durch den Prozess der Arbeit mit Aufgaben-Link-Sammlungen mithilfe von Aspose.Tasks.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1.  Aspose.Tasks für .NET-Bibliothek: Laden Sie die Aspose.Tasks-Bibliothek herunter und installieren Sie sie. Sie finden die Bibliothek[Hier](https://releases.aspose.com/tasks/net/).
2. Beispielprojektdatei: Bereiten Sie eine Beispielprojektdatei (z. B. „SampleProject.mpp“) vor, um sie zusammen mit den Beispielen zu verfolgen.
Jetzt fangen wir an!
## Namespaces importieren
Stellen Sie in Ihrem .NET-Projekt sicher, dass Sie die erforderlichen Namespaces für die Arbeit mit Aspose.Tasks importieren:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Schritt 1: Laden Sie das Projekt und greifen Sie auf Aufgaben zu
```csharp
// Der Pfad zum Dokumentenverzeichnis.
String DataDir = "Your Document Directory";
// Laden Sie das Projekt
var project = new Project(DataDir + "SampleProject.mpp");
// Greifen Sie nach ID auf Aufgaben zu
var task1 = project.RootTask.Children.GetById(1);
var task2 = project.RootTask.Children.GetById(2);
var task3 = project.RootTask.Children.GetById(3);
var task4 = project.RootTask.Children.GetById(4);
var task5 = project.RootTask.Children.GetById(5);
```
## Schritt 2: Erstellen Sie Aufgabenlinks
Verknüpfen Sie die Aufgaben miteinander, um Abhängigkeiten herzustellen:
```csharp
// Verknüpfen Sie Aufgaben mithilfe der FinishToStart-Abhängigkeit
project.TaskLinks.Add(task1, task2);
project.TaskLinks.Add(task2, task3, TaskLinkType.FinishToStart);
project.TaskLinks.Add(task3, task4, TaskLinkType.FinishToStart);
project.TaskLinks.Add(task4, task5, TaskLinkType.FinishToStart, project.GetDuration(1, TimeUnitType.Day));
project.TaskLinks.Add(task2, task5, TaskLinkType.FinishToStart, project.GetDuration(2, TimeUnitType.Day));
```
## Schritt 3: Aufgabenlinks drucken
Drucken Sie die Aufgabenlinks für das Projekt aus:
```csharp
Console.WriteLine("Print task links of " + project.TaskLinks.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Task links count: " + project.TaskLinks.Count);
//Durchlaufen Sie Aufgabenverknüpfungen
foreach (var link in project.TaskLinks)
{
    Console.WriteLine("From ID = " + link.PredTask.Get(Tsk.Id) + " => To ID = " + link.SuccTask.Get(Tsk.Id));
    Console.WriteLine();
}
```
## Schritt 4: Aufgabenlink bearbeiten
Bearbeiten Sie einen Aufgabenlink nach Indexzugriff:
```csharp
project.TaskLinks[0].LagFormat = TimeUnitType.Hour;
```
## Schritt 5: Aufgabenlinks entfernen
Entfernen Sie alle Aufgabenverknüpfungen aus dem Projekt:
```csharp
List<TaskLink> taskLinks = project.TaskLinks.ToList();
foreach (var link in taskLinks)
{
    project.TaskLinks.Remove(link);
}
```
## Abschluss
Glückwunsch! Sie haben erfolgreich gelernt, wie Sie mit Aufgabenverknüpfungen in Aspose.Tasks für .NET umgehen. In dieser umfassenden Anleitung wurde das Laden eines Projekts, das Erstellen von Aufgabenlinks, das Drucken von Links, das Bearbeiten von Links und das Entfernen von Aufgabenlinks behandelt.
Entdecken Sie gerne weitere Features und Funktionalitäten von Aspose.Tasks, um Ihr Projektmanagement-Erlebnis zu verbessern.
## FAQs
### Ist Aspose.Tasks mit allen Versionen von .NET kompatibel?
Ja, Aspose.Tasks ist so konzipiert, dass es nahtlos mit allen Versionen von .NET zusammenarbeitet.
### Kann ich mit Aspose.Tasks benutzerdefinierte Aufgabenverknüpfungstypen erstellen?
Derzeit unterstützt Aspose.Tasks Standard-Aufgabenlinktypen und benutzerdefinierte Linktypen sind nicht verfügbar.
### Wie kann ich Einschränkungen auf Aufgaben in Aspose.Tasks anwenden?
 Sie können Einschränkungen mithilfe von anwenden`ConstraintType` Eigentum der`Task` Klasse in Aspose.Tasks.
### Gibt es Einschränkungen hinsichtlich der Größe der Projektdateien, die Aspose.Tasks verarbeiten kann?
Aspose.Tasks kann große Projektdateien effizient und mit minimalen Auswirkungen auf die Leistung verarbeiten.
### Gibt es ein Community-Forum für den Aspose.Tasks-Support?
 Ja, Sie können auf der Website Unterstützung finden und mit der Community in Kontakt treten[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
