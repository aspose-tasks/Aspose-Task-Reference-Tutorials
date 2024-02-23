---
title: Verwalten von Aufgaben in Aspose.Tasks
linktitle: Verwalten von Aufgaben in Aspose.Tasks
second_title: Aspose.Tasks .NET-API
description: Entdecken Sie den umfassenden Leitfaden zum Verwalten von Aufgaben mit Aspose.Tasks für .NET. Erfahren Sie, wie Sie geteilte Teile hinzufügen, anzeigen, verschieben, Eigenschaften abrufen/festlegen und vieles mehr.
type: docs
weight: 15
url: /de/net/task-table-management/managing-tasks/
---
## Einführung
Wenn Sie ein .NET-Entwickler sind und Aufgaben in Ihren Projekten effizient verwalten möchten, bietet Aspose.Tasks für .NET eine robuste Lösung. Dieses Tutorial führt Sie durch verschiedene Aspekte der Aufgabenverwaltung mit Aspose.Tasks und bietet Schritt-für-Schritt-Anleitungen und Codebeispiele. Ganz gleich, ob Sie Aufgaben hinzufügen, geteilte Teile anzeigen, Aufgaben unter dasselbe übergeordnete Element verschieben, Aufgabeneigenschaften abrufen/festlegen, Aufgabenzuweisungen iterieren, Aufgabenbasislinien lesen oder Aufgaben löschen – in diesem Leitfaden sind Sie bestens aufgehoben.
## Voraussetzungen
Bevor Sie mit dem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1.  Aspose.Tasks for .NET-Bibliothek: Stellen Sie sicher, dass Sie die Aspose.Tasks for .NET-Bibliothek installiert haben. Sie können es herunterladen[Hier](https://releases.aspose.com/tasks/net/).
2. Dokumentenverzeichnis: Richten Sie ein Verzeichnis ein, in dem Ihre Projektdokumente gespeichert werden.
## Namespaces importieren
Fügen Sie in Ihr .NET-Projekt die erforderlichen Namespaces ein, um mit Aspose.Tasks zu arbeiten:
```csharp

    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
```
## 1. Eine Aufgabe zu einem Projekt hinzufügen
```csharp
// Erstellen Sie ein neues Projekt
var project = new Project();
// Fügen Sie eine Aufgabe hinzu
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Start, new DateTime(2012, 8, 23, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(24, TimeUnitType.Hour));
task.Set(Tsk.ActualStart, new DateTime(2012, 8, 23, 8, 0, 0));
// Speichern Sie das Projekt
project.Save(DataDir + "CreateNewTask_out.xml", SaveFileFormat.Xml);
```
## 2. Anzeigen der geteilten Teile der Aufgabe
```csharp
// Laden Sie ein Projekt mit aufgeteilten Aufgaben
var project = new Project(DataDir + "ViewSplitTasks.mpp");
//Auf eine Aufgabe zugreifen
var task = project.RootTask.Children.GetById(4);
// Geteilte Teile anzeigen
var collection = task.SplitParts;
foreach (var splitPart in collection)
{
    Console.WriteLine("Start: " + splitPart.Start + "\nFinish: " + splitPart.Finish + "\n");
}
```
## 3. Verschieben einer Aufgabe unter dasselbe übergeordnete Element
```csharp
try
{
    // Laden Sie ein Projekt
    var project = new Project(DataDir + "MoveTask.mpp");
    // Verschieben Sie Aufgaben mit der ID 5 vor die Aufgabe mit der ID 3
    var task = project.RootTask.Children.GetById(5);
    task.MoveToSibling(3);
    // Speichern Sie das geänderte Projekt
    project.Save(DataDir + "MoveTaskUnderSameParent_out.mpp", SaveFileFormat.Mpp);
}
catch (NotSupportedException ex)
{
    Console.WriteLine(ex.Message + "\nPlease apply a valid Aspose.Tasks License.");
}
```
## 4. Aufgabeneigenschaften abrufen/festlegen
```csharp
// Erstellen Sie ein neues Projekt
var project = new Project();
// Fügen Sie eine Aufgabe hinzu und legen Sie Eigenschaften fest
var task = project.RootTask.Children.Add();
task.Set(Tsk.Name, "Task1");
task.Set(Tsk.Start, new DateTime(2020, 3, 31, 8, 0, 0));
task.Set(Tsk.Finish, new DateTime(2020, 3, 31, 17, 0, 0));
// Aufgabeneigenschaften sammeln und anzeigen
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var tsk in collector.Tasks)
{
    Console.WriteLine("Task Id: {0}", tsk.Get(Tsk.Id));
    Console.WriteLine("Task Uid: {0}", tsk.Get(Tsk.Uid));
    Console.WriteLine("Task Name: {0}", tsk.Get(Tsk.Name));
    Console.WriteLine("Task Start: {0}", tsk.Get(Tsk.Start));
    Console.WriteLine("Task Finish: {0}", tsk.Get(Tsk.Finish));
}
```
## 5. Durchlaufen der Aufgabenzuweisungen
```csharp
// Laden Sie ein Projekt mit Aufgaben
var project = new Project(DataDir + "BudgetWorkAndCost.mpp");
// Aufgabenzuweisungen sammeln und anzeigen
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var task in collector.Tasks)
{
    foreach (var assignment in task.Assignments)
    {
        Console.WriteLine(assignment.ToString());
    }
}
```
## 6. Grundlinien der Leseaufgabe
```csharp
// Erstellen Sie ein neues Projekt
var project = new Project();
// Fügen Sie eine Aufgabe hinzu und legen Sie eine Basislinie fest
var task = project.RootTask.Children.Add("Task");
project.SetBaseline(BaselineType.Baseline);
// Zeigt die Basisdauer der Aufgabe an
foreach (var baseline in task.Baselines)
{
    Console.WriteLine("Baseline duration is 1 day: {0}", baseline.Duration.ToString().Equals("1 day"));
    Console.WriteLine("BaselineStart is same as Task Start: {0}", baseline.Start.Equals(task.Get(Tsk.Start)));
    Console.WriteLine("BaselineFinish is same as Task Finish: {0}", baseline.Finish.Equals(task.Get(Tsk.Finish)));
}
```
## 7. Eine Aufgabe löschen
```csharp
// Erstellen Sie ein neues Projekt
var project = new Project();
// Fügen Sie eine Aufgabe hinzu
var task = project.RootTask.Children.Add("Task");
// Zeigen Sie die Anzahl der Aufgaben vor und nach dem Löschen an
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
// Löschen Sie die Aufgabe
task.Delete();
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
```
## Abschluss
Das Verwalten von Aufgaben in Aspose.Tasks für .NET ist mit den bereitgestellten Beispielen ein nahtloser Prozess. Unabhängig davon, ob Sie ein erfahrener Entwickler sind oder gerade erst anfangen, wird die Integration dieser Techniken Ihre Projektmanagementfähigkeiten verbessern.
## Häufig gestellte Fragen
### F: Ist Aspose.Tasks mit allen .NET-Frameworks kompatibel?
A: Ja, Aspose.Tasks unterstützt verschiedene .NET Frameworks und gewährleistet so die Kompatibilität mit Ihrer Entwicklungsumgebung.
### F: Wie kann ich eine temporäre Lizenz für Aspose.Tasks erhalten?
 A: Sie können eine 30-tägige temporäre Lizenz erhalten von[Hier](https://purchase.aspose.com/temporary-license/).
### F: Gibt es Einschränkungen bei der Arbeit mit geteilten Aufgaben in Aspose.Tasks?
 A: Aufgeteilte Aufgaben sind eine leistungsstarke Funktion und eine ausführliche Dokumentation finden Sie hier[Hier](https://reference.aspose.com/tasks/net/).
### F: Kann ich die Aufgabeneigenschaften über die in den Beispielen gezeigten hinaus anpassen?
A: Auf jeden Fall! Aspose.Tasks bietet umfangreiche Anpassungsoptionen für Aufgabeneigenschaften. Weitere Einzelheiten finden Sie in der Dokumentation.
### F: Wie erhalte ich Unterstützung für Aspose.Tasks?
 A: Besuchen Sie die[Aspose.Tasks-Forum](https://forum.aspose.com/c/tasks/15) für Community-Unterstützung und Diskussionen.