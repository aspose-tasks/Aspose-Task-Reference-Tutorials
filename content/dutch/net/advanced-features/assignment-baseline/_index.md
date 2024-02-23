---
title: Toewijzingsbasislijn beheren in Aspose.Tasks
linktitle: Toewijzingsbasislijn beheren in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u de basislijnen van opdrachten efficiënt kunt beheren met Aspose.Tasks voor .NET, zodat u de voortgang en prestaties van projecten nauwkeurig kunt volgen.
type: docs
weight: 14
url: /nl/net/advanced-features/assignment-baseline/
---
## Invoering

Bij het werken aan projectmanagementtaken is het beheren van de basislijnen van opdrachten cruciaal voor het nauwkeurig volgen van de voortgang. Aspose.Tasks voor .NET biedt een uitgebreide set tools om toewijzingsbasislijnen efficiënt af te handelen. In deze zelfstudie gaan we stap voor stap dieper in op het proces van het beheren van toewijzingsbasislijnen.

## Vereisten

Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:

- Basiskennis van de programmeertaal C#.
- Visual Studio is op uw systeem geïnstalleerd.
- Aspose.Tasks voor .NET-bibliotheek toegevoegd aan uw project. Je kunt het downloaden van[hier](https://releases.aspose.com/tasks/net/).
- Toegang tot een projectbestand in MPP-formaat.

## Naamruimten importeren

Om met Aspose.Tasks te gaan werken, moet u de benodigde naamruimten in uw C#-project importeren. Voeg de volgende naamruimten toe aan het begin van uw C#-bestand:

```csharp
using Aspose.Tasks;
using System;


```

## Stap 1: Project laden en basislijn instellen

 Laad eerst het projectbestand met behulp van de`Project` klasse van Aspose.Tasks. Stel vervolgens het basislijntype voor het project in met behulp van de`SetBaseline` methode.

```csharp
// Het pad naar de documentenmap.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## Stap 2: Lees de basislijninformatie van de opdracht

Doorloop elke resourcetoewijzing in het project en haal basisinformatie op voor elke toewijzing.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var baseline in assignment.Baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
        Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
        Console.WriteLine("Bcwp: " + baseline.Bcwp);
        Console.WriteLine("Bcws: " + baseline.Bcws);
        Console.WriteLine("Cost: " + baseline.Cost);
        Console.WriteLine("Work: " + baseline.Work);
        if (baseline.TimephasedData != null)
        {
            foreach (var td in baseline.TimephasedData)
            {
                Console.WriteLine("TD Start: " + td.Start);
                Console.WriteLine("TD Finish: " + td.Finish);
                Console.WriteLine("TD Timephased Data Type: " + td.TimephasedDataType);
                Console.WriteLine();
            }
        }

        Console.WriteLine();
    }

    Console.WriteLine();
}
```

## Stap 3: Controleer de uitgangsgelijkheid

Vergelijk basisinformatie voor verschillende opdrachten met behulp van verschillende vergelijkingsmethoden van Aspose.Tasks.

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Controleer de basisgelijkheid
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Controleer de basislijnvergelijking
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Basislijn-hashcodes weergeven
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## Conclusie

Het beheren van opdrachtbasislijnen is een integraal onderdeel van projectmanagement, waardoor de voortgang en prestaties nauwkeurig kunnen worden gevolgd. Met Aspose.Tasks voor .NET wordt de afhandeling van toewijzingsbasislijnen gestroomlijnd en efficiënt, waardoor ontwikkelaars krachtige tools krijgen om de workflows voor projectbeheer te verbeteren.

## Veelgestelde vragen

### Vraag 1: Kan Aspose.Tasks meerdere basislijnen verwerken voor één enkele opdracht?

A1: Ja, Aspose.Tasks ondersteunt meerdere basislijnen voor elke opdracht, waardoor de projectvoortgang in de loop van de tijd uitgebreid kan worden gevolgd.

### V2: Is Aspose.Tasks compatibel met verschillende andere projectbestandsformaten dan MPP?

A2: Ja, Aspose.Tasks ondersteunt een breed scala aan projectbestandsformaten, waaronder XML, MPX en MPP, waardoor compatibiliteit met verschillende projectmanagementtools wordt gegarandeerd.

### V3: Kan ik basislijninformatie programmatisch wijzigen met Aspose.Tasks?

A3: Absoluut, Aspose.Tasks biedt uitgebreide API's om basisinformatie dynamisch aan te passen aan de projectvereisten, waardoor flexibiliteit en controle over projectmanagementprocessen wordt geboden.

### V4: Biedt Aspose.Tasks documentatie en ondersteuningsbronnen voor ontwikkelaars?

A4: Ja, ontwikkelaars hebben toegang tot uitgebreide documentatie, tutorials en forums op de Aspose.Tasks-website, wat een soepele integratie en probleemoplossing mogelijk maakt.

### V5: Is er een proefversie beschikbaar voor Aspose.Tasks voor .NET?

 A5: Ja, ontwikkelaars kunnen een gratis proefversie van Aspose.Tasks voor .NET verkrijgen van[hier](https://releases.aspose.com/), waardoor ze de functies en mogelijkheden ervan kunnen evalueren voordat ze een aankoopbeslissing nemen.