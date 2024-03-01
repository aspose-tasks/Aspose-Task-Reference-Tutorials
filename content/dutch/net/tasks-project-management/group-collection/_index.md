---
title: Projectverzamelingen beheren in Aspose.Tasks
linktitle: Groepsverzameling beheren in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u MS Project-collecties efficiënt kunt beheren met Aspose.Tasks voor .NET. Volg onze stapsgewijze handleiding.
type: docs
weight: 26
url: /nl/net/tasks-project-management/group-collection/
---
## Invoering
In deze zelfstudie onderzoeken we hoe u MS Project-groepscollecties kunt beheren met Aspose.Tasks voor .NET. Het beheren van groepscollecties is cruciaal voor het efficiënt organiseren en manipuleren van taken en bronnen binnen uw project.
## Vereisten
Voordat u doorgaat met deze zelfstudie, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1.  Aspose.Tasks voor .NET-bibliotheek: Download en installeer de Aspose.Tasks voor .NET-bibliotheek vanaf de[download link](https://releases.aspose.com/tasks/net/).
2. Basiskennis van C#: Maak uzelf vertrouwd met de basisprincipes van de programmeertaal C#, aangezien deze tutorial betrekking heeft op coderen in C#.
3. Ontwikkelomgeving: Zet een ontwikkelomgeving op, zoals Visual Studio of een andere IDE die .NET-ontwikkeling ondersteunt.

## Naamruimten importeren
Laten we eerst de benodigde naamruimten importeren om met Aspose.Tasks-functionaliteiten in onze C#-code te werken.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## Stap 1: Laad het project
```csharp
// Het pad naar de documentenmap.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
Deze stap omvat het laden van het MS Project-bestand in het Aspose.Tasks-projectobject, zodat we er bewerkingen op kunnen uitvoeren.
## Stap 2: Herhaal taakgroepen
```csharp
Console.WriteLine("Print task groups of {0} project: ", project.Get(Prj.Name));
Console.WriteLine("Task Group Count: " + project.TaskGroups.Count);
foreach (var group in project.TaskGroups)
{
    Console.WriteLine("Index: " + group.Index);
    Console.WriteLine("Name: " + group.Name);
    Console.WriteLine("Show In Menu: " + group.ShowInMenu);
    Console.WriteLine();
}
```
Hier herhalen we taakgroepen binnen het project, waarbij details zoals index, naam en zichtbaarheid in het menu voor elke groep worden afgedrukt.
## Stap 3: Herhaal de resourcegroepen
```csharp
Console.WriteLine("Project resource group count: " + project.ResourceGroups.Count);
foreach (var group in project.ResourceGroups)
{
    Console.WriteLine("Resource group Index: " + group.Index);
    Console.WriteLine("Resource group Name: " + group.Name);
    Console.WriteLine("Resource group ShowInMenu" + group.ShowInMenu);
}
```
Op dezelfde manier herhaalt deze stap de resourcegroepen, waarbij hun index, naam en zichtbaarheid in het menu worden weergegeven.
## Stap 4: Groepen wissen en kopiëren naar een ander project
```csharp
var otherProject = new Project(DataDir + "Blank2010.mpp");
// Wis de groepen van andere projecten
otherProject.TaskGroups.Clear();
// Kopieer groepen naar een ander project
var groups = new Group[project.TaskGroups.Count];
project.TaskGroups.CopyTo(groups, 0);
foreach (var group in groups)
{
    otherProject.TaskGroups.Add(group);
}
```
Hier wissen we de groepen van een ander project en kopiëren vervolgens groepen van het oorspronkelijke project ernaartoe.
## Stap 5: Voeg een aangepaste taakgroep toe
```csharp
var customGroup = new Group
{
    Name = "Custom Group",
    ShowInMenu = true
};
if (!otherProject.TaskGroups.Contains(customGroup))
{
    if (!otherProject.TaskGroups.IsReadOnly)
    {
        otherProject.TaskGroups.Add(customGroup);
    }
}
```
In deze stap maken we een aangepaste taakgroep en voegen deze toe aan het andere project als deze nog niet aanwezig is.
## Stap 6: Verwijder alle groepen
```csharp
List<Group> groupsToDelete = otherProject.TaskGroups.ToList();
foreach (var group in groupsToDelete)
{
    otherProject.TaskGroups.Remove(group);
}
```
Ten slotte verwijderen we alle groepen uit het andere project.

## Conclusie
Het beheren van MS Project-groepscollecties in Aspose.Tasks voor .NET is essentieel voor het efficiënt organiseren en manipuleren van projectgegevens. Door de stappen in deze zelfstudie te volgen, kunt u taak- en resourcegroepen binnen uw projecten effectief afhandelen, waardoor het algehele projectbeheer wordt verbeterd.
## Veelgestelde vragen
### Is Aspose.Tasks voor .NET compatibel met alle versies van MS Project?
Aspose.Tasks voor .NET ondersteunt verschillende versies van Microsoft Project, waaronder 2003, 2007, 2010, 2013, 2016 en 2019.
### Kan ik groepseigenschappen aanpassen met Aspose.Tasks voor .NET?
Ja, u kunt groepseigenschappen zoals naam en zichtbaarheid aanpassen met Aspose.Tasks voor .NET.
### Biedt Aspose.Tasks voor .NET platformonafhankelijke compatibiliteit?
Aspose.Tasks voor .NET richt zich primair op het .NET-framework, maar kan worden gebruikt in platformonafhankelijke scenario's met .NET Core en .NET Standard.
### Hoe kan ik ondersteuning krijgen voor Aspose.Tasks voor .NET?
 U kunt ondersteuning krijgen voor Aspose.Tasks voor .NET via de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15).
### Is er een proefversie beschikbaar voor Aspose.Tasks voor .NET?
 Ja, u kunt een gratis proefversie van Aspose.Tasks voor .NET downloaden van de[website](https://releases.aspose.com/).