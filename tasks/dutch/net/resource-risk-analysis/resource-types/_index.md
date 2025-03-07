---
title: Soorten bronnen in Aspose.Tasks
linktitle: Soorten bronnen in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u met verschillende soorten bronnen kunt werken in Aspose.Tasks voor .NET, inclusief werk-, materiaal- en kostenbronnen, via een stapsgewijze zelfstudie.
weight: 14
url: /nl/net/resource-risk-analysis/resource-types/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Soorten bronnen in Aspose.Tasks

## Invoering
Aspose.Tasks voor .NET is een krachtige bibliotheek waarmee ontwikkelaars programmatisch met Microsoft Project-bestanden kunnen werken. Of u nu taken, bronnen of planningen beheert, Aspose.Tasks vereenvoudigt het proces door een uitgebreide set API's te bieden. In deze zelfstudie gaan we dieper in op de verschillende soorten bronnen die u binnen uw projecten kunt gebruiken met Aspose.Tasks voor .NET.
## Vereisten
Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:
1. Visual Studio: Installeer Visual Studio, een krachtige geïntegreerde ontwikkelomgeving (IDE) voor .NET-ontwikkeling.
2.  Aspose.Tasks voor .NET: Download en installeer de Aspose.Tasks voor .NET-bibliotheek van[hier](https://releases.aspose.com/tasks/net/).
3. Basiskennis van C#: maak uzelf vertrouwd met C#, de programmeertaal die wordt gebruikt voor .NET-ontwikkeling.

## Naamruimten importeren
Laten we eerst de benodigde naamruimten importeren om toegang te krijgen tot de functionaliteiten van Aspose.Tasks voor .NET:
```csharp
    
```

## Stap 1: Maak een nieuw Project-exemplaar
```csharp
var project = new Project();
```
Deze regel initialiseert een nieuw Project-object, dat dient als container voor alle projectgerelateerde gegevens en bewerkingen.
## Stap 2: Voeg een werkresource toe
```csharp
var work = project.Resources.Add("Work resource");
work.Set(Rsc.Type, ResourceType.Work);
```
Hier maken we een nieuwe werkresource met de naam 'Werkresource' en specificeren we het type als ResourceType.Work.
## Stap 3: Voeg een materiaalbron toe
```csharp
var material = project.Resources.Add("Material resource");
material.Set(Rsc.Type, ResourceType.Material);
material.Set(Rsc.MaterialLabel, "kg");
```
Met deze stap wordt een materiaalresource met de naam "Material resource" toegevoegd, waarbij het type is ingesteld op ResourceType.Material. Bovendien specificeren we het materiaallabel als "kg" om de meeteenheid aan te geven.
## Stap 4: Voeg een kostenresource toe
```csharp
var cost = project.Resources.Add("Cost resource");
cost.Set(Rsc.Type, ResourceType.Cost);
cost.Set(Rsc.Cost, 59.99m);
```
Ten slotte voegen we een kostenbron toe met de naam 'Kostenbron' en stellen we het type ervan in als ResourceType.Cost. Daarnaast hebben we de kostenwaarde ingesteld op 59,99, wat de geldwaarde vertegenwoordigt die aan deze resource is gekoppeld.

## Conclusie
In deze zelfstudie hebben we onderzocht hoe u met verschillende soorten bronnen kunt werken in Aspose.Tasks voor .NET, inclusief werk-, materiaal- en kostenresources. Door de stapsgewijze handleiding te volgen, kunt u de resources binnen uw projecten effectief programmatisch beheren.
## Veelgestelde vragen
### Vraag: Kan ik Aspose.Tasks voor .NET gebruiken met andere softwareformaten voor projectbeheer?
A: Ja, Aspose.Tasks ondersteunt verschillende formaten, waaronder Microsoft Project (MPP), Primavera P6 en meer.
### Vraag: Is er een gratis proefversie beschikbaar voor Aspose.Tasks voor .NET?
 A: Ja, u heeft toegang tot de gratis proefperiode[hier](https://releases.aspose.com/).
### Vraag: Hoe kan ik technische ondersteuning krijgen voor Aspose.Tasks voor .NET?
 A: U kunt het Aspose.Tasks-forum bezoeken[hier](https://forum.aspose.com/c/tasks/15) voor technische assistentie.
### Vraag: Kan ik een tijdelijke licentie kopen voor Aspose.Tasks voor .NET?
 A: Ja, u kunt een tijdelijke licentie aanschaffen[hier](https://purchase.aspose.com/temporary-license/).
### Vraag: Biedt Aspose.Tasks voor .NET documentatie ter referentie?
 A: Ja, u kunt de documentatie vinden[hier](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
