---
title: Beheer MS-projectgroepcriteria met Aspose.Tasks
linktitle: Verzameling van groepscriteria beheren in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u de Group Criterion MS Project-verzameling beheert met Aspose.Tasks voor .NET. Stapsgewijze handleiding voor ontwikkelaars.
type: docs
weight: 28
url: /nl/net/tasks-project-management/group-criterion-collection/
---
## Invoering
Aspose.Tasks voor .NET is een krachtige API waarmee ontwikkelaars programmatisch met Microsoft Project-bestanden kunnen werken. In deze zelfstudie onderzoeken we hoe u de verzameling groepscriteria binnen MS Project kunt beheren met Aspose.Tasks.

## Vereisten

Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:

1.  Aspose.Tasks voor .NET: Zorg ervoor dat de Aspose.Tasks-bibliotheek in uw .NET-project is geïnstalleerd. Je kunt het downloaden van[hier](https://releases.aspose.com/tasks/net/).

2. Microsoft Project-bestand: Zorg ervoor dat u een Microsoft Project-bestand (MPP) gereed heeft om mee te werken.

## Naamruimten importeren

Ten eerste moet u de benodigde naamruimten in uw C#-code importeren. Deze stap is cruciaal voor toegang tot de functionaliteiten van Aspose.Tasks.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## Stap 1: Laad het projectbestand

 Initialiseer een`Project` object door het MPP-bestand te laden. 

```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```

## Stap 2: Toegang tot groepscriteria

Haal de groep op uit het project en open de criteria ervan.

```csharp
var group = project.TaskGroups.ToList()[0];
```

## Stap 3: Herhaal de groepscriteria

Loop door elk criterium in de groep en geef de eigenschappen ervan weer.

```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Index: " + criterion.Index);
    Console.WriteLine("Field: " + criterion.Field);
    Console.WriteLine("Group On: " + criterion.GroupOn);
    Console.WriteLine();
}
```

## Stap 4: Duidelijke groepscriteria

Wis bestaande groepscriteria als deze niet alleen-lezen zijn.

```csharp
group.GroupCriteria.Clear();
```

## Stap 5: Nieuw criterium toevoegen

Maak een nieuw groepscriterium aan en voeg dit toe aan de groep.

```csharp
var criterionToAdd = new GroupCriterion
{
    Ascending = true,
    Field = Field.TaskActive
};

if (!group.GroupCriteria.Contains(criterionToAdd))
{
    group.GroupCriteria.Add(criterionToAdd);
}
```

## Stap 6: Kopieer criteria naar een andere groep

Kopieer de criteria van de ene groep naar de andere.

```csharp
var otherGroup = project.TaskGroups.ToList()[0];

var criteria = new GroupCriterion[group.GroupCriteria.Count];
group.GroupCriteria.CopyTo(criteria, 0);
foreach (var criterion in criteria)
{
    otherGroup.GroupCriteria.Add(criterion);
}
```

### Conclusie

In deze zelfstudie hebben we geleerd hoe u de Group Criterion MS Project-verzameling kunt beheren met Aspose.Tasks voor .NET. Door deze stappen te volgen, kunt u groepscriteria binnen uw Microsoft Project-bestanden programmatisch effectief manipuleren.

## Veelgestelde vragen

### V1: Is Aspose.Tasks compatibel met alle versies van Microsoft Project?

A: Ja, Aspose.Tasks ondersteunt Microsoft Project-bestanden van verschillende versies, waaronder 2003, 2007, 2010, 2013 en 2016.

### Vraag 2: Kan ik meerdere criteria op één groep toepassen?

A: Absoluut, u kunt meerdere criteria aan een groep toevoegen door ze allemaal te doorlopen en ze dienovereenkomstig toe te voegen.

### V3: Is er een proefversie beschikbaar voor Aspose.Tasks?

 A: Ja, u kunt een gratis proefversie van Aspose.Tasks verkrijgen via[hier](https://releases.aspose.com/).

### V4: Waar kan ik documentatie voor Aspose.Tasks vinden?

 A: U kunt de documentatie raadplegen[hier](https://reference.aspose.com/tasks/net/).

### Vraag 5: Hoe kan ik ondersteuning krijgen als ik problemen tegenkom?

 A: Als u vragen heeft of problemen ondervindt, kunt u ondersteuning zoeken op het Aspose.Tasks-forum[hier](https://forum.aspose.com/c/tasks/15).