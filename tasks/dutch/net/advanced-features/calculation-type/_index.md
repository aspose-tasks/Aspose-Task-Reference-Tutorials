---
date: 2026-03-24
description: Leer hoe u berekeningen instelt in Aspose.Tasks voor .NET, met voorbeelden
  om samenvattingswaarden te berekenen, een berekeningsformule te definiëren en een
  roll‑up‑samenvatting te configureren.
linktitle: Calculation Type in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Hoe het berekeningstype in Aspose.Tasks instellen
url: /nl/net/advanced-features/calculation-type/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe berekeningstype in te stellen in Aspose.Tasks

## Inleiding

Als je **hoe berekening** regels voor taken en samenvattingsrijen in een Microsoft Project‑bestand moet instellen, laat deze tutorial je precies dat zien met Aspose.Tasks voor .NET. We lopen een volledig **berekeningstype‑voorbeeld** door, demonstreren hoe je **samenvattingswaarden berekent**, en leggen uit hoe je **berekeningsformule** definieert en **samenvatting‑roll‑up** configureert voor uitgebreide attributen. Aan het einde kun je een taak aan een project toevoegen, aangepaste berekeningslogica instellen en het roll‑up‑gedrag met vertrouwen beheren.

## Snelle antwoorden
- **Wat is het primaire doel?** Het controleren hoe taak‑ en samenvattingswaarden worden berekend in een Project‑bestand.  
- **Welke API‑klasse wordt gebruikt?** `ExtendedAttributeDefinition` samen met `CalculationType` en `SummaryRowsCalculationType`.  
- **Kan ik een formule gebruiken?** Ja – stel `CalculationType = CalculationType.Formula` in en geef een formule‑string op.  
- **Hoe rol ik samenvattingswaarden op?** Gebruik `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` en specificeer een `RollupType` zoals `Average`.  
- **Heb ik een licentie nodig?** Een geldige Aspose.Tasks‑licentie is vereist voor productiegebruik.

## Wat is Berekeningstype en hoe stel je berekening in?

`CalculationType` vertelt Aspose.Tasks hoe de waarde van een uitgebreid attribuut moet worden berekend. Je kunt kiezen voor een statische waarde, een formule, of de bibliotheek laten roll‑up‑waarden van onderliggende taken. Het correct instellen van de berekening is essentieel wanneer je wilt dat het project aangepaste bedrijfsregels weerspiegelt zonder handmatige updates.

## Waarom berekeningstype gebruiken om samenvattingswaarden te berekenen?

Wanneer een project samenvattende taken bevat, moet je vaak dat de samenvattingsrijen geaggregeerde gegevens tonen (bijv. totale kosten, gemiddelde duur). Door **samenvattingswaarden berekenen** te configureren via `SummaryRowsCalculationType` en `RollupType`, kan Aspose.Tasks die aggregaten automatisch synchroon houden terwijl je individuele taken wijzigt.

## Voorvereisten

Voordat we beginnen, zorg dat je het volgende hebt:

1. Basiskennis van C# en het .NET‑framework.  
2. Visual Studio (een recente versie) geïnstalleerd op je machine.  
3. Aspose.Tasks voor .NET‑bibliotheek geïnstalleerd – je kunt deze downloaden van [hier](https://releases.aspose.com/tasks/net/).  
4. Toegang tot de officiële Aspose.Tasks voor .NET‑documentatie voor referentie, beschikbaar [hier](https://reference.aspose.com/tasks/net/).

## Namespaces importeren

Voordat je in het voorbeeld duikt, importeer je de benodigde namespaces:

```csharp
using Aspose.Tasks;
using System;
```

## Stap 1: Een nieuw Project maken

Eerst maken we een leeg `Project`‑object dat onze taken en aangepaste attributen zal bevatten.

```csharp
var project = new Project();
```

## Stap 2: Een taak aan het project toevoegen

Nu **voegen we taak‑project**‑gegevens toe door een eenvoudige taak te maken, de startdatum in te stellen en een duur van één dag toe te kennen.

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## Stap 3: Berekeningstype definiëren voor een uitgebreid attribuut (Formule‑voorbeeld)

Hier maken we een definitie van een uitgebreid attribuut waarvan de waarde wordt berekend uit een formule. Dit demonstreert een **berekeningstype‑voorbeeld** en laat zien hoe je een **berekeningsformule** definieert.

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## Stap 4: Berekeningstype definiëren voor samenvattingsrijen (Roll‑up‑samenvatting configureren)

Vervolgens maken we een andere definitie van een uitgebreid attribuut die Aspose.Tasks vertelt **roll‑up‑samenvatting te configureren** met het *Average* roll‑up‑type. Dit is de gebruikelijke manier om **samenvattingswaarden te berekenen** voor kosten, werk of aangepaste velden.

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## Veelvoorkomende problemen & probleemoplossing

| Symptoom | Waarschijnlijke oorzaak | Oplossing |
|----------|--------------------------|-----------|
| Formule geeft `null` terug | Onjuiste veldreferentie in de formule | Controleer de veldnaam tussen haakjes (bijv. `[Start]` niet `[stARt]`). |
| Samenvattingsrijen tonen 0 | `SummaryRowsCalculationType` niet ingesteld of verkeerde `RollupType` | Zorg dat `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` en kies een passend `RollupType`. |
| Project laadt niet na het toevoegen van attributen | Mismatch tussen attribuutdefinitie en taakgebruik | Voeg de attribuutdefinitie **toe vóór** je deze aan een taak toewijst. |

## Conclusie

In deze tutorial hebben we behandeld **hoe berekening** regels in te stellen in Aspose.Tasks voor .NET, van het maken van een eenvoudige taak tot het definiëren van zowel formule‑gebaseerde als roll‑up‑gebaseerde berekeningstypen. Door deze instellingen te beheersen krijg je fijnmazige controle over **samenvattingswaarden berekenen**, waardoor je rijkere projectanalyses krijgt zonder handmatig spreadsheet‑werk.

## Veelgestelde vragen

### Q1: Wat is Berekeningstype in Aspose.Tasks?

A1: Berekeningstype in Aspose.Tasks bepaalt hoe waarden worden berekend voor taken en samenvattende taken binnen een project, met opties zoals Formule en Rollup.

### Q2: Hoe stel ik Berekeningstype in voor een uitgebreid attribuut?

A2: Je kunt Berekeningstype voor een uitgebreid attribuut instellen door de eigenschap `CalculationType` overeenkomstig te definiëren.

### Q3: Kan ik Berekeningstype aanpassen voor samenvattingsrijen in een project?

A3: Ja, Aspose.Tasks stelt je in staat om Berekeningstype voor samenvattingsrijen op te geven, zodat je de waardeberekeningen kunt afstemmen op je specifieke eisen.

### Q4: Zijn er verschillende Rollup‑typen beschikbaar voor berekeningen van samenvattende taken?

A4: Ja, Aspose.Tasks biedt diverse Rollup‑typen zoals Average, Sum en Count voor het berekenen van waarden van samenvattende taken.

### Q5: Waar vind ik meer bronnen over Aspose.Tasks voor .NET?

A5: Je kunt de documentatie en community‑ondersteuningsforums raadplegen die beschikbaar zijn op de [Aspose.Tasks for .NET](https://reference.aspose.com/tasks/net/) voor uitgebreide begeleiding en hulp.

---

**Laatst bijgewerkt:** 2026-03-24  
**Getest met:** Aspose.Tasks voor .NET (nieuwste release)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}