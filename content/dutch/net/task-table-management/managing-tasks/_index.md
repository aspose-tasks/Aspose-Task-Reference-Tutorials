---
title: Taken beheren in Aspose.Tasks
linktitle: Taken beheren in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Ontdek de uitgebreide handleiding over het beheren van taken met Aspose.Tasks voor .NET. Leer hoe u onderdelen kunt toevoegen, weergeven, verplaatsen, eigenschappen kunt ophalen/instellen en meer.
type: docs
weight: 15
url: /nl/net/task-table-management/managing-tasks/
---
## Invoering
Als u een .NET-ontwikkelaar bent en taken binnen uw projecten efficiënt wilt beheren, biedt Aspose.Tasks voor .NET een robuuste oplossing. Deze tutorial leidt u door verschillende aspecten van het beheren van taken met Aspose.Tasks, met stapsgewijze instructies en codevoorbeelden. Of u nu taken toevoegt, gesplitste delen weergeeft, taken onder hetzelfde bovenliggende item verplaatst, taakeigenschappen ophaalt/instelt, taaktoewijzingen herhaalt, taakbasislijnen leest of taken verwijdert, deze handleiding heeft de oplossing voor u.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1.  Aspose.Tasks voor .NET-bibliotheek: Zorg ervoor dat de Aspose.Tasks voor .NET-bibliotheek is geïnstalleerd. Je kunt het downloaden[hier](https://releases.aspose.com/tasks/net/).
2. Documentmap: stel een map in waarin uw projectdocumenten worden opgeslagen.
## Naamruimten importeren
Neem in uw .NET-project de benodigde naamruimten op om met Aspose.Tasks te werken:
```csharp

    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
```
## 1. Een taak aan een project toevoegen
```csharp
// Maak een nieuw project
var project = new Project();
// Voeg een taak toe
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Start, new DateTime(2012, 8, 23, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(24, TimeUnitType.Hour));
task.Set(Tsk.ActualStart, new DateTime(2012, 8, 23, 8, 0, 0));
// Sla het project op
project.Save(DataDir + "CreateNewTask_out.xml", SaveFileFormat.Xml);
```
## 2. Gesplitste delen van taak weergeven
```csharp
// Laad een project met gesplitste taken
var project = new Project(DataDir + "ViewSplitTasks.mpp");
//Toegang tot een taak
var task = project.RootTask.Children.GetById(4);
// Gesplitste onderdelen weergeven
var collection = task.SplitParts;
foreach (var splitPart in collection)
{
    Console.WriteLine("Start: " + splitPart.Start + "\nFinish: " + splitPart.Finish + "\n");
}
```
## 3. Een taak onder dezelfde ouder verplaatsen
```csharp
try
{
    // Laad een project
    var project = new Project(DataDir + "MoveTask.mpp");
    // Verplaats taken met id 5 vóór taak met id 3
    var task = project.RootTask.Children.GetById(5);
    task.MoveToSibling(3);
    // Sla het gewijzigde project op
    project.Save(DataDir + "MoveTaskUnderSameParent_out.mpp", SaveFileFormat.Mpp);
}
catch (NotSupportedException ex)
{
    Console.WriteLine(ex.Message + "\nPlease apply a valid Aspose.Tasks License.");
}
```
## 4. Taakeigenschappen verkrijgen/instellen
```csharp
// Maak een nieuw project
var project = new Project();
// Voeg een taak toe en stel eigenschappen in
var task = project.RootTask.Children.Add();
task.Set(Tsk.Name, "Task1");
task.Set(Tsk.Start, new DateTime(2020, 3, 31, 8, 0, 0));
task.Set(Tsk.Finish, new DateTime(2020, 3, 31, 17, 0, 0));
// Taakeigenschappen verzamelen en weergeven
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
## 5. De toewijzingen van taken herhalen
```csharp
// Laad een project met opdrachten
var project = new Project(DataDir + "BudgetWorkAndCost.mpp");
// Taaktoewijzingen verzamelen en weergeven
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
## 6. Basislijnen van de taak lezen
```csharp
// Maak een nieuw project
var project = new Project();
// Voeg een taak toe en stel een basislijn in
var task = project.RootTask.Children.Add("Task");
project.SetBaseline(BaselineType.Baseline);
// Geef de basislijnduur van de taak weer
foreach (var baseline in task.Baselines)
{
    Console.WriteLine("Baseline duration is 1 day: {0}", baseline.Duration.ToString().Equals("1 day"));
    Console.WriteLine("BaselineStart is same as Task Start: {0}", baseline.Start.Equals(task.Get(Tsk.Start)));
    Console.WriteLine("BaselineFinish is same as Task Finish: {0}", baseline.Finish.Equals(task.Get(Tsk.Finish)));
}
```
## 7. Een taak verwijderen
```csharp
// Maak een nieuw project
var project = new Project();
// Voeg een taak toe
var task = project.RootTask.Children.Add("Task");
// Geef het aantal taken weer voor en na het verwijderen
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
// Verwijder de taak
task.Delete();
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
```
## Conclusie
Het beheren van taken in Aspose.Tasks voor .NET is een naadloos proces met de meegeleverde voorbeelden. Of u nu een doorgewinterde ontwikkelaar bent of net begint, het integreren van deze technieken zal uw projectmanagementmogelijkheden vergroten.
## Veel Gestelde Vragen
### Vraag: Is Aspose.Tasks compatibel met alle .NET-frameworks?
A: Ja, Aspose.Tasks ondersteunt verschillende .NET-frameworks, waardoor compatibiliteit met uw ontwikkelomgeving wordt gegarandeerd.
### Vraag: Hoe kan ik een tijdelijke licentie voor Aspose.Tasks verkrijgen?
 A: U kunt een tijdelijke licentie van 30 dagen krijgen van[hier](https://purchase.aspose.com/temporary-license/).
### Vraag: Zijn er beperkingen bij het werken met gesplitste taken in Aspose.Tasks?
 A: Gesplitste taken zijn een krachtige functie en er is gedetailleerde documentatie te vinden[hier](https://reference.aspose.com/tasks/net/).
### Vraag: Kan ik de taakeigenschappen aanpassen buiten wat in de voorbeelden wordt weergegeven?
EEN: Absoluut! Aspose.Tasks biedt uitgebreide aanpassingsmogelijkheden voor taakeigenschappen. Raadpleeg de documentatie voor meer details.
### Vraag: Hoe krijg ik ondersteuning voor Aspose.Tasks?
 A: Bezoek de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15) voor gemeenschapsondersteuning en discussies.