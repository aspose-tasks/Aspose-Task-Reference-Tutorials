---
date: 2026-04-01
description: Leer hoe u herhaling in Aspose.Tasks voor .NET kunt instellen, een terugkerende
  taak kunt toevoegen en terugkerende taken per maand, week en dag kunt automatiseren.
keywords:
- how to set recurrence
- add recurring task
- automate recurring tasks
linktitle: Herhaling per maand, week, dag in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Hoe stel je herhaling in Aspose.Tasks in (maand, week, dag)
url: /nl/net/advanced-features/repetition-by-month-week-day/
weight: 26
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe herhaling instellen in Aspose.Tasks (Maand, Week, Dag)

## Inleiding

Als je **hoe herhaling in te stellen** voor taken in een project nodig hebt, biedt Aspose.Tasks voor .NET een nette, programmeerbare manier om terugkerende taakdefinities toe te voegen die maandelijks, wekelijks of dagelijks worden uitgevoerd. In deze tutorial lopen we een praktijkvoorbeeld door dat laat zien hoe je **voeg terugkerende taak toe** items kunt **automatiseren**, en ze rechtstreeks vanuit C#‑code kunt beheren. Aan het einde ben je klaar om deze functionaliteit in elke planning‑ of project‑managementoplossing te integreren.

## Snelle antwoorden
- **Wat betekent “herhaling” in Aspose.Tasks?** Het definieert een patroon (dagelijks, wekelijks, maandelijks) dat automatisch taakinstanties maakt over een datumbereik.  
- **Welke primaire methode maakt de herhaling?** `RecurringTaskParameters` gecombineerd met een specifieke `RecurrencePattern`.  
- **Heb ik een licentie nodig om deze code uit te voeren?** Een proefversie werkt voor evaluatie; een commerciële licentie is vereist voor productie.  
- **Kan ik wekelijkse taken plannen in plaats van maandelijkse?** Ja – vervang `MonthlyRecurrencePattern` door `WeeklyRecurrencePattern`.  
- **Welke .NET‑versies worden ondersteund?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6 en later.

## Wat is herhaling in Aspose.Tasks?

Herhaling is een reeks regels die Aspose.Tasks vertelt om taakinstanties te genereren op regelmatige intervallen—dagelijks, wekelijks of maandelijks—zonder ze handmatig te dupliceren. Deze functie is essentieel voor projecten die routinematige activiteiten bevatten, zoals statusvergaderingen, inspecties of onderhoudswerk.

## Waarom herhalingsfuncties gebruiken?

- **Tijd besparen:** Geen handmatig kopiëren‑plakken van taken.  
- **Fouten verminderen:** De bibliotheek garandeert consistente datums en duur.  
- **Flexibiliteit:** Combineer patronen (bijv. “eerste zondag van elke 2 maanden”).  
- **Automatisering:** Perfect voor het genereren van planningen in CI‑pipelines of rapportagetools.

## Vereisten

Voordat we beginnen, zorg dat je het volgende hebt:

1. **Basiskennis van C#** – je zult een paar regels C#‑code schrijven.  
2. **Aspose.Tasks voor .NET geïnstalleerd** – haal het op van de [download page](https://releases.aspose.com/tasks/net/).  
3. **Een .mpp‑projectbestand** – we gebruiken `Project1.mpp` als bronbestand.

## Namespaces importeren

Om te beginnen, importeer de benodigde Aspose.Tasks‑namespaces:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### Stap 1: Laad het projectbestand

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

We maken een `Project`‑instantie die verwijst naar een bestaand Microsoft Project‑bestand.

### Stap 2: Definieer terugkerende taakparameters

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthWeekDayRepetition
        {
            Position = OrdinalNumber.First,
            WeekDay = DayOfWeek.Sunday,
            RepetitionInterval = 2
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 2, 17, 0, 0)
        }
    }
};
```

Hier **creëren we terugkerende taak**‑parameters:

- **TaskName** – de naam van de gegenereerde taak.  
- **Duration** – hoe lang elke gebeurtenis duurt.  
- **RecurrencePattern** – een maandelijks patroon dat elke 2 maand op de eerste zondag herhaalt.  
- **RecurrenceRange** – de start‑ en einddatums die de planning begrenzen.

### Stap 3: Voeg de terugkerende taak toe aan het project

```csharp
project.RootTask.Children.Add(parameters);
```

Deze regel **voegt de terugkerende taak toe** aan de root van de projecthiërarchie.

### Stap 4: Sla het bijgewerkte project op

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Het project wordt opgeslagen als een nieuw `.mpp`‑bestand dat nu de geautomatiseerde planning bevat.

## Veelvoorkomende problemen en oplossingen

| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| **Taak verschijnt niet** | Herhalingsbereik ligt buiten de projectdatums. | Controleer of `Start`‑ en `Finish`‑waarden binnen de projectkalender vallen. |
| **Verkeerde weekdag** | `WeekDay` enum komt niet overeen. | Gebruik `DayOfWeek.Monday` … `DayOfWeek.Sunday` indien nodig. |
| **Licentie‑uitzondering** | Uitvoeren zonder een geldige licentie in productie. | Pas een tijdelijke of volledige licentie toe vóór het opslaan. |

## Veelgestelde vragen

### Q1: Kan ik het herhalingspatroon aanpassen buiten de gegeven voorbeelden?

A1: Ja, Aspose.Tasks voor .NET biedt uitgebreide aanpassingsopties voor herhalingspatronen, zodat je ze kunt afstemmen op je specifieke eisen.

### Q2: Is er een proefversie beschikbaar voor Aspose.Tasks voor .NET?

A2: Ja, je kunt een gratis proefversie van Aspose.Tasks voor .NET verkrijgen via de [releases page](https://releases.aspose.com/).

### Q3: Hoe kan ik ondersteuning krijgen voor Aspose.Tasks voor .NET?

A3: Je kunt hulp zoeken en deelnemen aan de community op het [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### Q4: Zijn tijdelijke licenties beschikbaar voor Aspose.Tasks voor .NET?

A4: Ja, je kunt tijdelijke licenties aanschaffen via de [purchase page](https://purchase.aspose.com/temporary-license/) voor test‑ en evaluatiedoeleinden.

### Q5: Waar vind ik uitgebreide documentatie voor Aspose.Tasks voor .NET?

A5: Je kunt de gedetailleerde [documentation](https://reference.aspose.com/tasks/net/) raadplegen op de Aspose‑website voor diepgaande begeleiding bij het gebruik van de bibliotheek.

---

**Laatste update:** 2026-04-01  
**Getest met:** Aspose.Tasks 24.11 voor .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}