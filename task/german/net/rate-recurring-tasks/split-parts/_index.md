---
title: Umgang mit geteilten MS Project-Teilen in Aspose.Tasks
linktitle: Umgang mit geteilten Teilen in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Erfahren Sie, wie Sie mit Aspose.Tasks für .NET effizient mit geteilten MS Project-Teilen umgehen. Verbessern Sie Ihren Projektmanagement-Workflow.
type: docs
weight: 18
url: /de/net/rate-recurring-tasks/split-parts/
---

## Einführung
Die Verwaltung geteilter MS Project-Teile kann ein entscheidender Aspekt des Projektmanagements sein, wenn Sie Aspose.Tasks für .NET verwenden. In diesem Tutorial erfahren Sie anhand einer Schritt-für-Schritt-Anleitung, wie Sie mit geteilten Teilen effektiv umgehen.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
1.  Installation von Aspose.Tasks für .NET: Laden Sie Aspose.Tasks für .NET von herunter und installieren Sie es[Webseite](https://releases.aspose.com/tasks/net/).
   
2. Grundkenntnisse von C#: Vertrautheit mit der Programmiersprache C# ist von Vorteil.

## Namespaces importieren
Stellen Sie sicher, dass Sie in Ihrem C#-Code die erforderlichen Namespaces importieren:
```csharp
    using Aspose.Tasks;
    using System;
    
```

## Schritt 1: Erstellen einer Projektinstanz
```csharp
var project = new Project();
```
 Erstellen Sie eine neue Instanz von`Project` Klasse.
## Schritt 2: Festlegen der Start- und Enddaten des Projekts
```csharp
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 3, 21, 17, 0, 0));
```
Legen Sie die Start- und Endtermine für das Projekt fest.
## Schritt 3: Eine Aufgabe hinzufügen
```csharp
var task = project.RootTask.Children.Add("Task1");
```
Fügen Sie dem Projekt eine neue Aufgabe hinzu.
## Schritt 4: Aufgabeneigenschaften festlegen
```csharp
task.Set(Tsk.IsManual, false);
task.Set(Tsk.Start, new DateTime(2000, 3, 15, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(3));
```
Legen Sie Eigenschaften wie manuellen Status, Startdatum und Dauer für die Aufgabe fest.
## Schritt 5: Ressourcenzuweisungen hinzufügen
```csharp
var assignment = project.ResourceAssignments.Add(task, project.Resources.Add("r1"));
```
Fügen Sie der Aufgabe Ressourcenzuweisungen hinzu.
## Schritt 6: Zuweisungseigenschaften festlegen
```csharp
assignment.Set(Asn.Start, new DateTime(2000, 3, 15, 8, 0, 0));
assignment.Set(Asn.Work, task.Get(Tsk.Work));
assignment.Set(Asn.Finish, new DateTime(2000, 3, 19, 17, 0, 0));
```
Legen Sie Eigenschaften wie Startdatum, Arbeit und Enddatum für die Aufgabe fest.
## Schritt 7: Zeitphasendaten generieren
```csharp
assignment.TimephasedDataFromTaskDuration(project.Get(Prj.Calendar));
```
Generieren Sie Zeitphasendaten für den Auftrag basierend auf dem Projektkalender.
## Schritt 8: Aufteilen der Aufgabe
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 17, 17, 0, 0), project.Get(Prj.Calendar));
```
Teilen Sie die Aufgabe innerhalb des angegebenen Zeitrahmens in mehrere Teile auf.
## Schritt 9: Iterieren über geteilte Teile
```csharp
Console.WriteLine("Number of split parts: " + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("  Split Part Start: " + splitPart.Start);
    Console.WriteLine("  Split Part Finish: " + splitPart.Finish);
    Console.WriteLine();
}
```
Durchlaufen Sie die aufgeteilten Teile der Aufgabe und drucken Sie deren Start- und Enddatum aus.

## Abschluss
Die effektive Handhabung geteilter MS Project-Teile in Aspose.Tasks für .NET ist für die Effizienz des Projektmanagements von entscheidender Bedeutung. Indem Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie aufgeteilte Aufgaben nahtlos verwalten und Ihren Projektmanagement-Workflow verbessern.
## FAQs
### F: Kann ich Aspose.Tasks für .NET mit anderen .NET-Frameworks verwenden?
A: Ja, Aspose.Tasks für .NET ist mit verschiedenen .NET-Frameworks kompatibel, einschließlich .NET Core und .NET Standard.
### F: Gibt es eine kostenlose Testversion für Aspose.Tasks für .NET?
 A: Ja, Sie können eine kostenlose Testversion von erhalten[Hier](https://releases.aspose.com/).
### F: Unterstützt Aspose.Tasks für .NET die Ressourcenverwaltung?
A: Ja, mit Aspose.Tasks für .NET können Sie Projektressourcen effizient verwalten.
### F: Kann ich Projektkalender mit Aspose.Tasks für .NET anpassen?
A: Auf jeden Fall können Sie Projektkalender an Ihre Projektanforderungen anpassen.
### F: Wo finde ich Unterstützung für Aspose.Tasks für .NET?
 A: Unterstützung und Hilfe finden Sie auf der[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15).