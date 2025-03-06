---
title: Berekeningstype Aspose.Tasks
linktitle: Berekeningstype Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u waardeberekeningen in .NET-projecten kunt aanpassen met het berekeningstype in de Aspose.Tasks-bibliotheek.
weight: 30
url: /nl/net/advanced-features/calculation-type/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Berekeningstype Aspose.Tasks

## Invoering

In deze zelfstudie verkennen we de functie Berekeningstype in Aspose.Tasks voor .NET. Aspose.Tasks is een krachtige bibliotheek waarmee .NET-ontwikkelaars met Microsoft Project-bestanden kunnen werken zonder dat Microsoft Project op hun systemen hoeft te zijn geïnstalleerd. Met Berekeningstype kunnen we definiëren hoe waarden worden berekend voor taken en samenvattingstaken binnen een project.

## Vereisten

Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:

1. Basiskennis van C# en .NET framework.
2. Visual Studio is op uw systeem geïnstalleerd.
3.  Aspose.Tasks voor .NET-bibliotheek geïnstalleerd. Je kunt het downloaden van[hier](https://releases.aspose.com/tasks/net/).
4.  Toegang tot Aspose.Tasks voor .NET-documentatie ter referentie, beschikbaar[hier](https://reference.aspose.com/tasks/net/).

## Naamruimten importeren

Zorg ervoor dat u de benodigde naamruimten importeert voordat u in het voorbeeld duikt:

```csharp
using Aspose.Tasks;
using System;


```

## Stap 1: Maak een nieuw project

Laten we eerst een nieuw projectobject maken:

```csharp
var project = new Project();
```

## Stap 2: Voeg een taak toe

Laten we nu een taak aan ons project toevoegen:

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## Stap 3: Definieer het berekeningstype voor een uitgebreid attribuut

We zullen een uitgebreide attribuutdefinitie maken waarbij het Berekeningstype is ingesteld op Formule:

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## Stap 4: Definieer het berekeningstype voor samenvattingsrijen

Vervolgens maken we nog een uitgebreide attribuutdefinitie waarbij waarden voor samenvattingstaken worden berekend met behulp van het gemiddelde samenvoegingstype:

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## Conclusie

In deze zelfstudie hebben we onderzocht hoe u met het berekeningstype in Aspose.Tasks voor .NET kunt werken. Door berekeningstypen voor uitgebreide attributen te definiëren, kunnen we aanpassen hoe waarden worden berekend voor taken en samenvattingstaken binnen een project, waardoor we meer flexibiliteit en controle krijgen.

## Veelgestelde vragen

### V1: Wat is het berekeningstype in Aspose.Tasks?

A1: Berekeningstype in Aspose.Tasks bepaalt hoe waarden worden berekend voor taken en samenvattingstaken binnen een project, en biedt opties zoals Formule en Samentelling.

### V2: Hoe stel ik het berekeningstype in voor een uitgebreid attribuut?

A2: U kunt het berekeningstype voor een uitgebreid attribuut instellen door de eigenschap CalculationType dienovereenkomstig te definiëren.

### V3: Kan ik het berekeningstype voor samenvattingsrijen in een project aanpassen?

A3: Ja, met Aspose.Tasks kunt u het berekeningstype opgeven voor samenvattingsrijen, zodat u waardeberekeningen kunt aanpassen op basis van uw vereisten.

### V4: Zijn er verschillende samenvoegingstypen beschikbaar voor berekeningen van samenvattingstaken?

A4: Ja, Aspose.Tasks biedt verschillende samenvoegingstypen, zoals Gemiddelde, Som en Aantal, voor het berekenen van waarden van samenvattingstaken.

### V5: Waar kan ik meer bronnen vinden over Aspose.Tasks voor .NET?

 A5: U kunt de documentatie en community-ondersteuningsforums verkennen die beschikbaar zijn op de[Aspose.Tasks voor .NET](https://reference.aspose.com/tasks/net/) voor uitgebreide begeleiding en hulp.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
