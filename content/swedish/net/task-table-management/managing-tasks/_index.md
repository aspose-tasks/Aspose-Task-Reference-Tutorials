---
title: Hantera uppgifter i Aspose.Tasks
linktitle: Hantera uppgifter i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Utforska den omfattande guiden om att hantera uppgifter med Aspose.Tasks för .NET. Lär dig att lägga till, visa delade delar, flytta, hämta/ställa in egenskaper och mer.
type: docs
weight: 15
url: /sv/net/task-table-management/managing-tasks/
---
## Introduktion
Om du är en .NET-utvecklare som vill hantera uppgifter inom dina projekt effektivt, erbjuder Aspose.Tasks för .NET en robust lösning. Denna handledning guidar dig genom olika aspekter av att hantera uppgifter med Aspose.Tasks, och erbjuder steg-för-steg-instruktioner och kodexempel. Oavsett om du lägger till uppgifter, visar delade delar, flyttar uppgifter under samma förälder, hämtar/ställer in uppgiftsegenskaper, itererar över uppgiftstilldelningar, läser uppgiftens baslinjer eller tar bort uppgifter, har den här guiden täckt dig.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:
1. Aspose.Tasks for .NET Library: Se till att du har Aspose.Tasks for .NET-biblioteket installerat. Du kan ladda ner den[här](https://releases.aspose.com/tasks/net/).
2. Dokumentkatalog: Skapa en katalog där dina projektdokument kommer att lagras.
## Importera namnområden
I ditt .NET-projekt, inkludera de nödvändiga namnområdena för att arbeta med Aspose.Tasks:
```csharp

    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
```
## 1. Lägga till en uppgift till ett projekt
```csharp
// Skapa ett nytt projekt
var project = new Project();
// Lägg till en uppgift
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Start, new DateTime(2012, 8, 23, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(24, TimeUnitType.Hour));
task.Set(Tsk.ActualStart, new DateTime(2012, 8, 23, 8, 0, 0));
// Spara projektet
project.Save(DataDir + "CreateNewTask_out.xml", SaveFileFormat.Xml);
```
## 2. Visar uppgiftens delade delar
```csharp
// Ladda ett projekt med delade uppgifter
var project = new Project(DataDir + "ViewSplitTasks.mpp");
// Få åtkomst till en uppgift
var task = project.RootTask.Children.GetById(4);
// Visa delade delar
var collection = task.SplitParts;
foreach (var splitPart in collection)
{
    Console.WriteLine("Start: " + splitPart.Start + "\nFinish: " + splitPart.Finish + "\n");
}
```
## 3. Flytta en uppgift under samma förälder
```csharp
try
{
    // Ladda ett projekt
    var project = new Project(DataDir + "MoveTask.mpp");
    // Flytta uppgifter med id 5 före uppgift med id 3
    var task = project.RootTask.Children.GetById(5);
    task.MoveToSibling(3);
    // Spara det ändrade projektet
    project.Save(DataDir + "MoveTaskUnderSameParent_out.mpp", SaveFileFormat.Mpp);
}
catch (NotSupportedException ex)
{
    Console.WriteLine(ex.Message + "\nPlease apply a valid Aspose.Tasks License.");
}
```
## 4. Hämta/ställ in uppgiftsegenskaper
```csharp
// Skapa ett nytt projekt
var project = new Project();
// Lägg till en uppgift och ange egenskaper
var task = project.RootTask.Children.Add();
task.Set(Tsk.Name, "Task1");
task.Set(Tsk.Start, new DateTime(2020, 3, 31, 8, 0, 0));
task.Set(Tsk.Finish, new DateTime(2020, 3, 31, 17, 0, 0));
// Samla och visa uppgiftsegenskaper
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
## 5. Iterera över uppgiftens tilldelningar
```csharp
// Ladda ett projekt med uppdrag
var project = new Project(DataDir + "BudgetWorkAndCost.mpp");
// Samla och visa uppgiftsuppgifter
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
## 6. Läsa Tasks grundlinjer
```csharp
// Skapa ett nytt projekt
var project = new Project();
// Lägg till en uppgift och ställ in en baslinje
var task = project.RootTask.Children.Add("Task");
project.SetBaseline(BaselineType.Baseline);
// Visa uppgiftens baslinjevaraktighet
foreach (var baseline in task.Baselines)
{
    Console.WriteLine("Baseline duration is 1 day: {0}", baseline.Duration.ToString().Equals("1 day"));
    Console.WriteLine("BaselineStart is same as Task Start: {0}", baseline.Start.Equals(task.Get(Tsk.Start)));
    Console.WriteLine("BaselineFinish is same as Task Finish: {0}", baseline.Finish.Equals(task.Get(Tsk.Finish)));
}
```
## 7. Ta bort en uppgift
```csharp
// Skapa ett nytt projekt
var project = new Project();
// Lägg till en uppgift
var task = project.RootTask.Children.Add("Task");
//Visa antalet uppgifter före och efter borttagning
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
// Ta bort uppgiften
task.Delete();
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
```
## Slutsats
Att hantera uppgifter i Aspose.Tasks för .NET är en sömlös process med de medföljande exemplen. Oavsett om du är en erfaren utvecklare eller precis har börjat, kommer att införliva dessa tekniker förbättra dina projektledningsmöjligheter.
## Vanliga frågor
### F: Är Aspose.Tasks kompatibel med alla .NET-ramverk?
S: Ja, Aspose.Tasks stöder olika .NET-ramverk, vilket säkerställer kompatibilitet med din utvecklingsmiljö.
### F: Hur kan jag få en tillfällig licens för Aspose.Tasks?
 S: Du kan få en 30-dagars tillfällig licens från[här](https://purchase.aspose.com/temporary-license/).
### F: Finns det några begränsningar när man arbetar med delade uppgifter i Aspose.Tasks?
 S: Delade uppgifter är en kraftfull funktion och detaljerad dokumentation kan hittas[här](https://reference.aspose.com/tasks/net/).
### F: Kan jag anpassa uppgiftsegenskaperna utöver vad som visas i exemplen?
A: Absolut! Aspose.Tasks tillhandahåller omfattande anpassningsalternativ för uppgiftsegenskaper. Se dokumentationen för mer information.
### F: Hur får jag support för Aspose.Tasks?
 A: Besök[Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) för samhällsstöd och diskussioner.