---
title: Taakkoppelingen verwerken in Aspose.Tasks
linktitle: Taakkoppelingen verwerken in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Ontdek de kracht van Aspose.Tasks voor .NET bij het efficiënt beheren van projecttaakkoppelingen. Volg onze stapsgewijze handleiding om uw projectmanagementervaring te verbeteren.
type: docs
weight: 19
url: /nl/net/task-table-management/task-link-collection/
---
## Invoering
Welkom bij de stapsgewijze handleiding voor het omgaan met taakkoppelingen in Aspose.Tasks voor .NET! Taakkoppelingen spelen een cruciale rol bij projectmanagement, waardoor u relaties tussen taken kunt leggen en afhankelijkheden kunt creëren. In deze zelfstudie leiden we u door het proces van het werken met taaklinkverzamelingen met behulp van Aspose.Tasks.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1.  Aspose.Tasks voor .NET-bibliotheek: Download en installeer de Aspose.Tasks-bibliotheek. Je kunt de bibliotheek vinden[hier](https://releases.aspose.com/tasks/net/).
2. Voorbeeldprojectbestand: Bereid een voorbeeldprojectbestand voor (bijvoorbeeld "SampleProject.mpp") om samen met de voorbeelden te volgen.
Laten we nu beginnen!
## Naamruimten importeren
Zorg ervoor dat u in uw .NET-project de benodigde naamruimten importeert om met Aspose.Tasks te werken:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Stap 1: Laad de project- en toegangstaken
```csharp
// Het pad naar de documentenmap.
String DataDir = "Your Document Directory";
// Laad het project
var project = new Project(DataDir + "SampleProject.mpp");
// Toegang tot taken op ID
var task1 = project.RootTask.Children.GetById(1);
var task2 = project.RootTask.Children.GetById(2);
var task3 = project.RootTask.Children.GetById(3);
var task4 = project.RootTask.Children.GetById(4);
var task5 = project.RootTask.Children.GetById(5);
```
## Stap 2: Taakkoppelingen maken
Koppel de taken aan elkaar om afhankelijkheden vast te stellen:
```csharp
// Koppel taken met behulp van de FinishToStart-afhankelijkheid
project.TaskLinks.Add(task1, task2);
project.TaskLinks.Add(task2, task3, TaskLinkType.FinishToStart);
project.TaskLinks.Add(task3, task4, TaskLinkType.FinishToStart);
project.TaskLinks.Add(task4, task5, TaskLinkType.FinishToStart, project.GetDuration(1, TimeUnitType.Day));
project.TaskLinks.Add(task2, task5, TaskLinkType.FinishToStart, project.GetDuration(2, TimeUnitType.Day));
```
## Stap 3: Taaklinks afdrukken
Druk de taaklinks voor het project af:
```csharp
Console.WriteLine("Print task links of " + project.TaskLinks.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Task links count: " + project.TaskLinks.Count);
//Herhaal de taakkoppelingen
foreach (var link in project.TaskLinks)
{
    Console.WriteLine("From ID = " + link.PredTask.Get(Tsk.Id) + " => To ID = " + link.SuccTask.Get(Tsk.Id));
    Console.WriteLine();
}
```
## Stap 4: Taaklink bewerken
Bewerk een taakkoppeling via indextoegang:
```csharp
project.TaskLinks[0].LagFormat = TimeUnitType.Hour;
```
## Stap 5: Taaklinks verwijderen
Verwijder alle taaklinks uit het project:
```csharp
List<TaskLink> taskLinks = project.TaskLinks.ToList();
foreach (var link in taskLinks)
{
    project.TaskLinks.Remove(link);
}
```
## Conclusie
Gefeliciteerd! U hebt met succes geleerd hoe u met taakkoppelingen omgaat in Aspose.Tasks voor .NET. Deze uitgebreide handleiding behandelde het laden van een project, het maken van taakkoppelingen, het afdrukken van koppelingen, het bewerken van koppelingen en het verwijderen van taakkoppelingen.
Ontdek gerust meer functies en functionaliteiten die door Aspose.Tasks worden aangeboden om uw projectmanagementervaring te verbeteren.
## Veelgestelde vragen
### Is Aspose.Tasks compatibel met alle versies van .NET?
Ja, Aspose.Tasks is ontworpen om naadloos samen te werken met alle versies van .NET.
### Kan ik aangepaste taakkoppelingstypen maken met Aspose.Tasks?
Momenteel ondersteunt Aspose.Tasks standaard taakkoppelingstypen, en aangepaste koppelingstypen zijn niet beschikbaar.
### Hoe kan ik beperkingen toepassen op taken in Aspose.Tasks?
 U kunt beperkingen toepassen met behulp van de`ConstraintType` eigendom van de`Task` klasse in Aspose.Tasks.
### Zijn er beperkingen aan de grootte van de projectbestanden die Aspose.Tasks kan verwerken?
Aspose.Tasks kan grote projectbestanden efficiënt verwerken met minimale impact op de prestaties.
### Is er een communityforum voor Aspose.Tasks-ondersteuning?
 Ja, je kunt ondersteuning vinden en in contact komen met de gemeenschap op de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15).