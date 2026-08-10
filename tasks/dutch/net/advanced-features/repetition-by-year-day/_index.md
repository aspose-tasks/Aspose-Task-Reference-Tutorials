---
date: 2026-04-03
description: Leer taakplanning in projectmanagement en hoe je terugkerende taken toevoegt
  met Aspose.Tasks voor .NET, inclusief het opslaan van het project als MPP.
keywords:
- project management task scheduling
- how to add recurring task
- save project as mpp
linktitle: Herhaling per jaardag in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Projectmanagementtaakplanning met jaarlijkse dagherhaling in Aspose.Tasks
url: /nl/net/advanced-features/repetition-by-year-day/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Projectmanagementtaakplanning met jaardagherhaling in Aspose.Tasks

## Introductie

Effectieve **project management task scheduling** is de ruggengraat van elk succesvol project. Wanneer taken jaarlijks terugkeren — zoals jaarlijkse audits, onderhoudsvensters of seizoensgebonden beoordelingen — kan het handmatig afhandelen van die herhalingen foutgevoelig en tijdrovend zijn. Aspose.Tasks for .NET vereenvoudigt dit door je programmatisch jaar‑dagpatronen te laten definiëren, zodat je je kunt concentreren op wat het belangrijkst is: waarde leveren. In deze tutorial leer je **hoe je terugkerende taak** logica toevoegt op basis van een specifieke dag van het jaar en zie je precies **hoe je het project opslaat als MPP** voor naadloze integratie met Microsoft Project.

## Snelle antwoorden
- **Wat betekent “year day repetition”?** Het plant een taak op een specifieke dag van een specifieke maand elk jaar.  
- **Welke API‑klasse maakt de herhaling?** `YearlyRecurrencePattern` gecombineerd met `ByYearDayRepetition`.  
- **Kan ik een start‑ en einddatum instellen?** Ja, met `EndByRecurrenceRange`.  
- **Welk bestandsformaat wordt geproduceerd?** Het project wordt opgeslagen als een MPP‑bestand (`SaveFileFormat.Mpp`).  
- **Heb ik een licentie nodig voor productie?** Een commerciële licentie is vereist voor niet‑evaluatiegebruik.

## Vereisten

Voordat je aan de tutorial begint, zorg ervoor dat je de volgende vereisten hebt:

1. Aspose.Tasks for .NET Library: Download en installeer de Aspose.Tasks for .NET‑bibliotheek vanaf de [website](https://releases.aspose.com/tasks/net/).  
2. Ontwikkelomgeving: Richt een geschikte ontwikkelomgeving in met Visual Studio of een andere favoriete IDE voor .NET‑ontwikkeling.  
3. Basiskennis van C#: Maak jezelf vertrouwd met de basisprincipes van de programmeertaal C# om de codevoorbeelden te kunnen volgen.  
4. Concepten van projectmanagement: Inzicht in projectmanagementconcepten en taakplanning helpt bij het effectief begrijpen van de tutorial.

## Namespaces importeren

Voordat we beginnen met coderen, importeren we de benodigde namespaces om onze taakmanipulatie met Aspose.Tasks for .NET te vergemakkelijken.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

Laten we nu het gegeven voorbeeld opsplitsen in meerdere stappen en elke stap in detail toelichten.

## Hoe een terugkerende taak toe te voegen met jaardagpatroon

### Stap 1: Projectbestand laden

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

Hier initialiseren we een nieuw `Project`‑object en laden we een bestaand projectbestand met de naam **Project1.mpp**.

### Stap 2: Recurrerende taakparameters definiëren

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearDayRepetition { DayPosition = 1, Month = Month.July },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 1, 17, 0, 0)
        }
    }
};
```

In deze stap definiëren we de parameters voor onze terugkerende taak. We geven de taaknaam, duur en het herhalingspatroon op. Voor jaarlijkse herhaling gebruiken we de `YearlyRecurrencePattern` en stellen we de herhaling in op de **1e dag van juli** met `ByYearDayRepetition`. Daarnaast definiëren we het herhalingsbereik van 1 juli 2018 tot 1 juli 2019.

### Stap 3: Taak aan project toevoegen

```csharp
project.RootTask.Children.Add(parameters);
```

Hier voegen we de gedefinieerde terugkerende taakparameters toe aan de root‑taak van het project.

### Stap 4: Project opslaan als MPP

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

Tot slot **slaan we het project op als een MPP‑bestand** op, zodat het klaar is om te openen in Microsoft Project of een compatibele viewer.

## Waarom dit belangrijk is

- **Automatisering** – Elimineert handmatige invoer van jaarlijkse taken, waardoor menselijke fouten worden verminderd.  
- **Consistentie** – Garandeert dat hetzelfde dag‑maand‑patroon wordt toegepast over meerdere jaren.  
- **Integratie** – Het resulterende MPP‑bestand kan worden gedeeld met belanghebbenden die afhankelijk zijn van Microsoft Project.  

## Veelvoorkomende valkuilen & tips

- **DateTime‑precisie** – Zorg ervoor dat de starttijd overeenkomt met je projectkalender; anders kan de taak verschoven verschijnen.  
- **Tijdzones** – De API werkt met `DateTime`‑objecten; overweeg UTC‑conversie als je applicatie zich over meerdere regio's uitstrekt.  
- **Licentie‑handhaving** – In evaluatiemodus kan het opgeslagen MPP een watermerk bevatten; gebruik een geldige licentie voor productie.

## Veelgestelde vragen

**Q: Kan Aspose.Tasks complexe herhalingspatronen aan?**  
A: Ja, Aspose.Tasks biedt uitgebreide ondersteuning voor verschillende herhalingspatronen, inclusief jaarlijkse, maandelijkse, wekelijkse en dagelijkse herhalingen.

**Q: Is Aspose.Tasks compatibel met verschillende projectbestandsformaten?**  
A: Absoluut, Aspose.Tasks ondersteunt populaire projectbestandsformaten zoals MPP, XML en CSV, waardoor compatibiliteit met verschillende projectmanagementtools wordt gegarandeerd.

**Q: Biedt Aspose.Tasks documentatie en ondersteuning voor ontwikkelaars?**  
A: Ja, ontwikkelaars hebben toegang tot uitgebreide documentatie en kunnen hulp zoeken op de Aspose.Tasks community‑forums voor eventuele vragen of problemen.

**Q: Kan ik taak‑eigenschappen zoals duur en startdatum aanpassen met Aspose.Tasks?**  
A: Zeker, Aspose.Tasks biedt robuuste API’s om taak‑eigenschappen dynamisch te manipuleren, waardoor ontwikkelaars duur, startdatums, afhankelijkheden en meer kunnen aanpassen.

**Q: Is Aspose.Tasks geschikt voor zowel kleinschalige als grootschalige (enterprise) projecten?**  
A: Inderdaad, Aspose.Tasks is ontworpen om te voldoen aan de behoeften van ontwikkelaars die werken aan projecten van elke omvang, van individuele taken tot grootschalige enterprise‑projecten.

---

**Laatst bijgewerkt:** 2026-04-03  
**Getest met:** Aspose.Tasks 24.12 for .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}