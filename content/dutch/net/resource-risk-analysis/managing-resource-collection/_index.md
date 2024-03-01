---
title: Het verzamelen van projectbronnen beheren in Aspose.Tasks
linktitle: Resourceverzameling beheren in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u Microsoft Project-resourceverzamelingen in .NET efficiënt kunt beheren met behulp van de Aspose.Tasks API. Verhoog de productiviteit en flexibiliteit.
type: docs
weight: 13
url: /nl/net/resource-risk-analysis/managing-resource-collection/
---
## Invoering
In deze zelfstudie onderzoeken we hoe u Microsoft Project-bronverzamelingen effectief kunt beheren met Aspose.Tasks voor .NET. Aspose.Tasks is een krachtige API waarmee ontwikkelaars programmatisch met Microsoft Project-bestanden kunnen werken, waardoor een naadloze integratie en manipulatie van projectgegevens mogelijk is.
## Vereisten
Voordat u in deze zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1. Kennis van C# en .NET Framework: Deze tutorial veronderstelt bekendheid met de programmeertaal C# en het .NET Framework.
2. Installatie van Aspose.Tasks voor .NET: Zorg ervoor dat u Aspose.Tasks voor .NET hebt geïnstalleerd. Je kunt het downloaden van[hier](https://releases.aspose.com/tasks/net/).
3. Ontwikkelomgeving instellen: Stel uw ontwikkelomgeving in met Visual Studio of een andere gewenste IDE.

## Naamruimten importeren
Voordat we beginnen, importeert u de benodigde naamruimten om toegang te krijgen tot de Aspose.Tasks-functionaliteiten:
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## Stap 1: Laad het projectbestand
Laad eerst het Microsoft Project-bestand in het Aspose.Tasks-projectobject:
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "SampleProject.mpp");
```
## Stap 2: Lege bron toevoegen
Laten we vervolgens een lege bron aan het project toevoegen:
```csharp
var resource = project.Resources.Add();
resource.Set(Rsc.Type, ResourceType.Work);
```
## Stap 3: Voeg een resource met een naam toe
Voeg nu een resource met een opgegeven naam toe aan het project:
```csharp
var developer = project.Resources.Add("Developer");
developer.Set(Rsc.Type, ResourceType.Work);
```
## Stap 4: Voeg een bron toe vóór een andere bron
Voeg een resource met een opgegeven naam toe vóór een andere resource op basis van de ID:
```csharp
var manager = project.Resources.Add("Manager", developer.Get(Rsc.Id));
manager.Set(Rsc.Type, ResourceType.Work);
```
## Stap 5: Toegang tot bronnen via ID of UID
U kunt toegang krijgen tot bronnen via hun ID of UID:
```csharp
var devResource = project.Resources.GetById(4);
devResource.Set(Rsc.Code, "12345");
var manResource = project.Resources.GetByUid(4);
manResource.Set(Rsc.Code, "54321");
```
## Stap 6: Broninformatie afdrukken
Informatie over de projectbronnen afdrukken:
```csharp
Console.WriteLine("Print the resources of " + project.Resources.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Count of resources: " + project.Resources.Count);
foreach (var rsc in project.Resources)
{
    Console.WriteLine("Resource Name: " + rsc.Get(Rsc.Name));
}
```
## Stap 7: Bronnen verwijderen
Resources uit het project verwijderen:
```csharp
List<Resource> list = project.Resources.ToList();
foreach (var rsc in list)
{
    rsc.Delete();
}
```

## Conclusie
Het beheren van Microsoft Project-resourcecollecties met Aspose.Tasks voor .NET biedt ontwikkelaars een robuuste set tools om projectresources programmatisch efficiënt af te handelen. Door de stappen in deze zelfstudie te volgen, kunt u bronnen binnen uw projecten naadloos manipuleren, waardoor de productiviteit en flexibiliteit bij projectbeheertaken wordt verbeterd.
## Veelgestelde vragen
### Vraag: Kan Aspose.Tasks grootschalige projectbestanden verwerken?

A: Ja, Aspose.Tasks is ontworpen om grootschalige projectbestanden efficiënt te verwerken en hoge prestaties en betrouwbaarheid te bieden.

### Vraag: Is Aspose.Tasks compatibel met verschillende versies van Microsoft Project?

A: Aspose.Tasks ondersteunt verschillende versies van Microsoft Project, waardoor compatibiliteit tussen verschillende omgevingen wordt gegarandeerd.

### Vraag: Kan ik resource-eigenschappen aanpassen met Aspose.Tasks?

A: Absoluut, Aspose.Tasks biedt uitgebreide mogelijkheden om resource-eigenschappen aan te passen aan specifieke projectvereisten.

### Vraag: Ondersteunt Aspose.Tasks multi-threading voor gelijktijdige bewerkingen?

A: Ja, Aspose.Tasks ondersteunt multi-threading, waardoor gelijktijdige bewerkingen op projectgegevens mogelijk zijn om de prestaties te verbeteren.

### Vraag: Is er technische ondersteuning beschikbaar voor Aspose.Tasks-gebruikers?

 A: Ja, Aspose.Tasks-gebruikers hebben via het forum toegang tot technische ondersteuning[hier](https://forum.aspose.com/c/tasks/15).