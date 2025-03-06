---
title: Beheer uitgebreide attribuutdefinities MS Project in Aspose.Tasks
linktitle: Verzameling van uitgebreide attribuutdefinities in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u uitgebreide attribuutdefinities in Microsoft Project kunt beheren met Aspose.Tasks voor .NET. Pas uw projectgegevens moeiteloos aan en verbeter ze.
type: docs
weight: 14
url: /nl/net/tasks-project-management/extended-attribute-definition-collection/
---
## Invoering
In deze zelfstudie onderzoeken we hoe u met uitgebreide attribuutdefinities in Microsoft Project kunt werken met behulp van Aspose.Tasks voor .NET. Uitgebreide attributen bieden een flexibele manier om projectgegevens aan te passen en te verbeteren, waardoor gebruikers extra velden kunnen toevoegen naast de standaardvelden die standaard worden geleverd. Met Aspose.Tasks kunt u deze uitgebreide kenmerken moeiteloos beheren om aan uw projectbeheerbehoeften te voldoen.
## Vereisten
Voordat u doorgaat, moet u ervoor zorgen dat de volgende vereisten zijn geïnstalleerd:
- [.NET-framework](https://dotnet.microsoft.com/download)
-  Aspose.Tasks voor .NET-bibliotheek. Je kunt het downloaden van[hier](https://releases.aspose.com/tasks/net/).

## Naamruimten importeren
Eerst moet u de benodigde naamruimten importeren om toegang te krijgen tot de Aspose.Tasks-klassen en -methoden in uw .NET-project. Volg deze stappen:
## Stap 1: Open uw .NET-project
Open uw .NET-project in de IDE van uw voorkeur, zoals Visual Studio.
## Stap 2: Voeg de Aspose.Tasks-naamruimte toe
Voeg de volgende regel toe aan het begin van uw codebestand om de naamruimte Aspose.Tasks te importeren:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```

Laten we nu de gegeven codevoorbeelden opsplitsen in meerdere stappen voor een uitgebreid begrip:
## Stap 1: Laad het projectbestand
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## Stap 2: Bestaande uitgebreide attribuutdefinities wissen (optioneel)
```csharp
if (!project.ExtendedAttributes.IsReadOnly)
{
    if (project.ExtendedAttributes.Count > 0)
    {
        project.ExtendedAttributes.Clear();
    }
}
```
## Stap 3: Maak en voeg een uitgebreide attribuutdefinitie voor een taak toe
```csharp
var taskDefinition = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
project.ExtendedAttributes.Add(taskDefinition);
```
## Stap 4: Herhaal de taakuitgebreide attributen
```csharp
Console.WriteLine("Iterate over extended attributes of " + project.ExtendedAttributes.ParentProject.Get(Prj.Name) + " project: ");
foreach (var attribute in project.ExtendedAttributes)
{
    Console.WriteLine("Attribute Alias: " + attribute.Alias);
    Console.WriteLine("Attribute CfType: " + attribute.CfType);
    Console.WriteLine();
}
```
## Stap 5: Maak en voeg een uitgebreide attribuutdefinitie voor een resource toe
```csharp
var resourceDefinition = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Cost, ExtendedAttributeResource.Cost5, "My cost");
if (!project.ExtendedAttributes.Contains(resourceDefinition))
{
    project.ExtendedAttributes.Add(resourceDefinition);
}
```
## Stap 6: Voeg een uitgebreide resource-attribuutdefinitie in
```csharp
var resourceDefinition2 = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Number, ExtendedAttributeResource.Cost1, "My Cost 2");
if (project.ExtendedAttributes.IndexOf(resourceDefinition2) < 0)
{
    project.ExtendedAttributes.Insert(0, resourceDefinition2);
}
```
## Stap 7: Verwijder een uitgebreid attribuut per index
```csharp
project.ExtendedAttributes.RemoveAt(0);
```

## Conclusie
In deze zelfstudie hebben we de basisbeginselen besproken van het werken met uitgebreide attribuutdefinities in Microsoft Project met behulp van Aspose.Tasks voor .NET. Door deze stappen te volgen, kunt u uitgebreide kenmerken efficiënt beheren en aanpassen aan uw projectbeheervereisten.
## Veelgestelde vragen
### Vraag: Kan ik bestaande uitgebreide attribuutdefinities wijzigen?
A: Ja, u kunt bestaande uitgebreide attribuutdefinities wijzigen of nieuwe creëren, afhankelijk van uw behoeften.
### Vraag: Worden uitgebreide kenmerken ondersteund in alle versies van Microsoft Project?
A: Ja, uitgebreide kenmerken worden ondersteund in de meeste versies van Microsoft Project, inclusief recente versies.
### Vraag: Kan ik uitgebreide attributen gebruiken om aangepaste velden te berekenen?
A: Absoluut, uitgebreide attributen kunnen worden gebruikt om aangepaste velden te berekenen op basis van specifieke criteria die u definieert.
### Vraag: Is Aspose.Tasks compatibel met andere .NET-frameworks?
A: Aspose.Tasks is compatibel met verschillende .NET-frameworks, wat flexibiliteit en integratiegemak garandeert.
### Vraag: Waar kan ik meer bronnen en ondersteuning vinden voor Aspose.Tasks?
 A: U kunt een bezoek brengen aan de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15) voor ondersteuning en verken de documentatie[hier](https://reference.aspose.com/tasks/net/).