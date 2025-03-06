---
title: Beheer de verzameling MS-projectkenmerken in Aspose.Tasks
linktitle: Uitgebreide attribuutverzameling beheren in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u de uitgebreide kenmerken van MS Project efficiënt kunt beheren met Aspose.Tasks voor .NET. Bewerk taakkenmerken naadloos met stapsgewijze begeleiding.
weight: 12
url: /nl/net/tasks-project-management/extended-attribute-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Beheer de verzameling MS-projectkenmerken in Aspose.Tasks

## Invoering
Wilt u de uitgebreide kenmerken van MS Project efficiënt beheren met Aspose.Tasks voor .NET? In deze tutorial begeleiden we u stap voor stap door het proces. Laten we erin duiken!
## Vereisten
Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:
1. Visual Studio: Installeer Visual Studio op uw systeem.
2.  Aspose.Tasks voor .NET: Download en installeer Aspose.Tasks voor .NET van[hier](https://releases.aspose.com/tasks/net/).
3. Basiskennis van C#: maak uzelf vertrouwd met de basisprincipes van de programmeertaal C#.

## Naamruimten importeren
Begin met het importeren van de benodigde naamruimten in uw project:
```csharp
    using Aspose.Tasks;
    using System;
    
```
## Stap 1: Projectbestand laden
Laad eerst het MS Project-bestand met behulp van het volgende codefragment:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## Stap 2: Toegang tot taak en uitgebreide attributen
Toegang tot een specifieke taak en de uitgebreide kenmerken ervan:
```csharp
var task = project.RootTask.Children.GetById(1);
```
## Stap 3: Wis uitgebreide kenmerken
Wis indien nodig bestaande uitgebreide kenmerken:
```csharp
if (!task.ExtendedAttributes.IsReadOnly && task.ExtendedAttributes.Count > 0)
{
    task.ExtendedAttributes.Clear();
}
```
## Stap 4: Maak uitgebreide attribuutdefinities
Maak definities voor nieuwe uitgebreide attributen:
```csharp
var taskDefinition1 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
var taskDefinition2 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Finish, ExtendedAttributeTask.Finish7, "Finish 7");
project.ExtendedAttributes.Add(taskDefinition1);
project.ExtendedAttributes.Add(taskDefinition2);
```
## Stap 5: Herhaal de uitgebreide taakkenmerken
Herhaal de taakuitgebreide attributen:
```csharp
Console.WriteLine("Iterate over task extended attributes of " + task.Get(Tsk.Name) + " task: ");
foreach (var attribute in task.ExtendedAttributes)
{
    Console.WriteLine("Attribute FieldId: " + attribute.FieldId);
    Console.WriteLine("Attribute Value: " + attribute.DateValue);
    Console.WriteLine();
}
```
## Stap 6: Voeg uitgebreide attributen toe
Voeg nieuwe uitgebreide attributen toe aan de taak:
```csharp
var extendedAttribute1 = taskDefinition1.CreateExtendedAttribute();
extendedAttribute1.DateValue = new DateTime(2020, 4, 14, 8, 0, 0);
if (task.ExtendedAttributes.IndexOf(extendedAttribute1) < 0)
{
    task.ExtendedAttributes.Insert(0, extendedAttribute1);
}
var extendedAttribute2 = taskDefinition2.CreateExtendedAttribute();
extendedAttribute2.DateValue = new DateTime(2020, 4, 14, 17, 0, 0);
task.ExtendedAttributes.Add(extendedAttribute2);
```
## Stap 7: Werk met uitgebreide attributen
Voer indien nodig bewerkingen uit op uitgebreide attributen.
## Stap 8: Uitgebreide attributen verwijderen
Uitgebreide attributen verwijderen per index of voorwaardelijk:
```csharp
task.ExtendedAttributes.RemoveAt(0);
task.ExtendedAttributes.Remove(extendedAttribute2);
```
## Stap 9: Kopieer attributen naar een andere taak
Kopieer attributen naar een andere taak binnen hetzelfde of een ander project:
```csharp
var otherProject = new Project();
var otherTask = otherProject.RootTask.Children.Add("Other task");
foreach (var attribute in attributes)
{
    otherTask.ExtendedAttributes.Add(attribute);
}
```

## Conclusie
Het beheren van uitgebreide MS Project-attribuutcollecties wordt naadloos met Aspose.Tasks voor .NET. Door de stappen te volgen die in deze zelfstudie worden beschreven, kunt u op efficiënte wijze omgaan met uitgebreide kenmerken, waardoor uw mogelijkheden voor projectbeheer worden uitgebreid.
## Veelgestelde vragen
### Vraag: Kan ik uitgebreide attributen voor meerdere projecten manipuleren?
A: Ja, u kunt uitgebreide kenmerken kopiëren tussen taken in verschillende projecten met behulp van Aspose.Tasks voor .NET.
### Vraag: Zijn er beperkingen op het aantal uitgebreide attributen per taak?
A: Aspose.Tasks voor .NET legt geen inherente beperkingen op aan het aantal uitgebreide attributen per taak.
### Vraag: Kan ik aangepaste uitgebreide attribuutvelden maken?
EEN: Absoluut! Met Aspose.Tasks voor .NET kunt u aangepaste uitgebreide attribuutvelden definiëren die zijn afgestemd op uw projectvereisten.
### Vraag: Ondersteunt Aspose.Tasks voor .NET het lezen van en schrijven naar MS Project-bestanden van verschillende versies?
A: Ja, Aspose.Tasks voor .NET ondersteunt MS Project-bestandsformaten in verschillende versies.
### Vraag: Is er een proefversie beschikbaar voor Aspose.Tasks voor .NET?
 A: Ja, u kunt een gratis proefversie downloaden van[hier](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
