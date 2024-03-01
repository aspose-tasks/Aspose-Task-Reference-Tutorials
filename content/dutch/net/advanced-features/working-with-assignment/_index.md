---
title: Werken met toewijzingen in Aspose.Tasks
linktitle: Werken met toewijzingen in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u projecttoewijzingen in .NET beheert met Aspose.Tasks. Ontdek verschillende contouren voor resourceplanning.
type: docs
weight: 13
url: /nl/net/advanced-features/working-with-assignment/
---
## Invoering

In deze zelfstudie onderzoeken we hoe u met opdrachten in Aspose.Tasks voor .NET kunt werken. Toewijzingen zijn cruciaal in projectmanagement, omdat ze middelen toewijzen aan taken, wat helpt bij het plannen en volgen van de voortgang. We zullen ons concentreren op het genereren van tijdgebonden gegevens voor resourcetoewijzing met verschillende contouren met behulp van Aspose.Tasks.

## Vereisten

Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:

1.  Installatie van Aspose.Tasks voor .NET: Download en installeer de Aspose.Tasks voor .NET-bibliotheek van de[download link](https://releases.aspose.com/tasks/net/).
2. Basiskennis van C# en .NET Framework: Bekendheid met de programmeertaal C# en .NET Framework-concepten is noodzakelijk om mee te kunnen doen.

## Naamruimten importeren

Zorg ervoor dat u de benodigde naamruimten in uw C#-project importeert:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;

```

## Stap 1: Maak een project en een taak

Laten we beginnen met het maken van een nieuw project en het toevoegen van een taak eraan. Stel de startdatum, duur en einddatum voor de taak in:

```csharp
var project = new Project();
project.Set(Prj.StartDate, new DateTime(2000, 1, 3, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 1, 7, 17, 0, 0));

var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2000, 1, 3, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task.Set(Tsk.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## Stap 2: Voeg een resource toe en wijs deze toe aan een taak

Voeg vervolgens een resource toe aan het project en wijs deze toe aan de eerder gemaakte taak:

```csharp
var resource = project.Resources.Add("Resource");

var resourceAssignment = project.ResourceAssignments.Add(task, resource);
resourceAssignment.Set(Asn.Start, new DateTime(2000, 1, 3, 8, 0, 0));
resourceAssignment.Set(Asn.Work, project.GetWork(8));
resourceAssignment.Set(Asn.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## Stap 3: Genereer tijdgebonden gegevens met verschillende contouren

Laten we nu tijdgebonden gegevens genereren met verschillende contouren voor de resourcetoewijzing:

```csharp
Console.WriteLine("Flat contour");

var collection = task.GetTimephasedData(project.Get(Prj.StartDate), project.Get(Prj.FinishDate));
foreach (var td in collection)
{
	Console.WriteLine(td.Start.ToShortDateString() + " " + td.Value);
}
```

## Stap 4: Verander contouren en genereer gegevens

We kunnen het contourtype wijzigen en dienovereenkomstig tijdgebonden gegevens genereren. Hier zijn enkele voorbeelden:

```csharp
// Wijzig contour
resourceAssignment.Set(Asn.WorkContour, WorkContourType.Turtle);
// Genereer tijdgebonden gegevens en druk af
// Herhaal deze stap voor andere contourtypen
```

## Conclusie

In deze tutorial hebben we geleerd hoe we met opdrachten kunnen werken in Aspose.Tasks voor .NET. We hebben onderzoek gedaan naar het genereren van tijdgebonden gegevens over toewijzing van resources met verschillende contouren. Deze kennis kan enorm nuttig zijn in projectmanagementscenario's.

## Veelgestelde vragen

### V1: Kan ik Aspose.Tasks gebruiken voor het plannen van taken in mijn .NET-toepassing?

A1: Ja, Aspose.Tasks biedt uitgebreide API's voor taakplanning en -beheer in .NET-applicaties.

### V2: Is er een gratis proefversie beschikbaar voor Aspose.Tasks?

 A2: Ja, u kunt profiteren van een gratis proefperiode van[hier](https://releases.aspose.com/).

### V3: Zijn er beperkingen op het aantal taken of bronnen in Aspose.Tasks?

A3: Aspose.Tasks legt geen beperkingen op aan het aantal taken of bronnen die u in uw projecten kunt beheren.

### V4: Kan ik de contouren voor resourcetoewijzingen in Aspose.Tasks aanpassen?

A4: Ja, zoals gedemonstreerd in deze tutorial, kunt u verschillende contouren instellen, zoals schildpad, bel, piek, enz., afhankelijk van uw projectvereisten.

### V5: Waar kan ik ondersteuning vinden voor Aspose.Tasks-gerelateerde vragen?

A5: U kunt ondersteuning vinden op de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15) waar experts en leden van de gemeenschap actief deelnemen aan discussies.