---
title: Omgaan met gesplitste MS Project-onderdelen in Aspose.Tasks
linktitle: Gesplitste onderdelen afhandelen in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u efficiënt met MS Project-gesplitste onderdelen kunt omgaan met Aspose.Tasks voor .NET. Verbeter uw projectmanagementworkflow.
type: docs
weight: 18
url: /nl/net/rate-recurring-tasks/split-parts/
---

## Invoering
Het beheren van gesplitste MS Project-onderdelen kan een cruciaal aspect zijn van projectbeheer bij het gebruik van Aspose.Tasks voor .NET. In deze zelfstudie onderzoeken we hoe u effectief met gesplitste onderdelen kunt omgaan met behulp van stapsgewijze begeleiding.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1.  Installatie van Aspose.Tasks voor .NET: Download en installeer Aspose.Tasks voor .NET vanaf de[website](https://releases.aspose.com/tasks/net/).
   
2. Basiskennis van C#: Bekendheid met de programmeertaal C# is een voordeel.

## Naamruimten importeren
Zorg ervoor dat u in uw C#-code de benodigde naamruimten importeert:
```csharp
    using Aspose.Tasks;
    using System;
    
```

## Stap 1: Een projectinstantie maken
```csharp
var project = new Project();
```
 Maak een nieuw exemplaar van de`Project` klas.
## Stap 2: Begin- en einddatum van het project instellen
```csharp
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 3, 21, 17, 0, 0));
```
Stel de start- en einddatum voor het project in.
## Stap 3: Een taak toevoegen
```csharp
var task = project.RootTask.Children.Add("Task1");
```
Voeg een nieuwe taak toe aan het project.
## Stap 4: Taakeigenschappen instellen
```csharp
task.Set(Tsk.IsManual, false);
task.Set(Tsk.Start, new DateTime(2000, 3, 15, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(3));
```
Stel eigenschappen in, zoals handmatige status, startdatum en duur voor de taak.
## Stap 5: Resourcetoewijzingen toevoegen
```csharp
var assignment = project.ResourceAssignments.Add(task, project.Resources.Add("r1"));
```
Voeg resourcetoewijzingen toe aan de taak.
## Stap 6: Toewijzingseigenschappen instellen
```csharp
assignment.Set(Asn.Start, new DateTime(2000, 3, 15, 8, 0, 0));
assignment.Set(Asn.Work, task.Get(Tsk.Work));
assignment.Set(Asn.Finish, new DateTime(2000, 3, 19, 17, 0, 0));
```
Stel eigenschappen zoals startdatum, werk en einddatum voor de opdracht in.
## Stap 7: Tijdgebonden gegevens genereren
```csharp
assignment.TimephasedDataFromTaskDuration(project.Get(Prj.Calendar));
```
Genereer tijdgebonden gegevens voor de opdracht op basis van de projectkalender.
## Stap 8: De taak splitsen
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 17, 17, 0, 0), project.Get(Prj.Calendar));
```
Splits de taak op in meerdere delen binnen het opgegeven tijdsbestek.
## Stap 9: Itereren over gesplitste delen
```csharp
Console.WriteLine("Number of split parts: " + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("  Split Part Start: " + splitPart.Start);
    Console.WriteLine("  Split Part Finish: " + splitPart.Finish);
    Console.WriteLine();
}
```
Herhaal de gesplitste delen van de taak en druk hun start- en einddatum af.

## Conclusie
Het effectief verwerken van gesplitste MS Project-onderdelen in Aspose.Tasks voor .NET is cruciaal voor de efficiëntie van projectbeheer. Door de stappen in deze zelfstudie te volgen, kunt u gesplitste taken naadloos beheren en uw projectbeheerworkflow verbeteren.
## Veelgestelde vragen
### Vraag: Kan ik Aspose.Tasks voor .NET gebruiken met andere .NET-frameworks?
A: Ja, Aspose.Tasks voor .NET is compatibel met verschillende .NET-frameworks, waaronder .NET Core en .NET Standard.
### Vraag: Is er een gratis proefversie beschikbaar voor Aspose.Tasks voor .NET?
 A: Ja, u kunt een gratis proefversie verkrijgen van[hier](https://releases.aspose.com/).
### Vraag: Ondersteunt Aspose.Tasks voor .NET resourcebeheer?
A: Ja, met Aspose.Tasks voor .NET kunt u projectbronnen efficiënt beheren.
### Vraag: Kan ik projectkalenders aanpassen met Aspose.Tasks voor .NET?
A: Absoluut, u kunt projectkalenders aanpassen aan uw projectvereisten.
### Vraag: Waar kan ik ondersteuning vinden voor Aspose.Tasks voor .NET?
 A: U kunt ondersteuning en hulp vinden op de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15).