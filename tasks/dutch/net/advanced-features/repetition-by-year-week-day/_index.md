---
date: 2026-04-03
description: Leer hoe u Aspose.Tasks kunt gebruiken om een terugkerende taak aan een
  project toe te voegen en het project op te slaan als MPP. Deze gids toont stap voor
  stap de functie Herhaling per jaar, week, dag.
keywords:
- how to use aspose.tasks
- add recurring task project
- save project as mpp
linktitle: Herhaling per jaar, week, dag in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Hoe Aspose.Tasks te gebruiken – Herhaling per jaar, week, dag
url: /nl/net/advanced-features/repetition-by-year-week-day/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Herhaling per Jaar Weekdag in Aspose.Tasks

## Introductie

Wanneer je **how to use Aspose.Tasks** nodig hebt voor het afhandelen van complexe terugkerende schema's, biedt de bibliotheek je fijnmazige controle over jaarlijkse patronen. In deze tutorial lopen we stap voor stap door het maken van een taak die zich herhaalt op een specifieke weekdag van een bepaalde maand, over meerdere jaren. Aan het einde kun je **add recurring task project** items toevoegen en **save project as MPP** met slechts een paar regels C#.

## Snelle antwoorden
- **Wat betekent “Repetition by Year Week Day”?** Het herhaalt een taak op een gekozen weekdag (bijv. eerste zondag) van een bepaalde maand elk jaar.  
- **Welke .NET‑versies worden ondersteund?** Alle moderne .NET Framework- en .NET Core/5/6‑versies.  
- **Heb ik een licentie nodig om de code uit te voeren?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Kan ik het herhalingsbereik wijzigen?** Ja – je kunt een startdatum, einddatum of een vast aantal herhalingen instellen.  
- **Is de output een MPP‑bestand?** Absoluut – het project wordt opgeslagen als een MPP‑bestand klaar voor Microsoft Project.

## Wat is de “Repetition by Year Week Day” functie?

De functie stelt je in staat om een jaarlijkse herhaling te definiëren die zich richt op een specifieke **day of the week** (bijv. Sunday) en een **position** binnen de maand (eerste, tweede, laatste, enz.). Dit is ideaal voor taken zoals kwartaalreviews, jaarlijkse audits, of elk evenement dat een op de kalender gebaseerd ritme volgt.

## Waarom Aspose.Tasks gebruiken voor terugkerende taken?

- **Precisie** – Volledige controle over maanden, weekdagen en ordinale posities.  
- **Compatibiliteit** – Genereert native MPP‑bestanden die foutloos openen in Microsoft Project.  
- **Geen COM‑interoperabiliteit** – Pure .NET API, geen Office‑installaties nodig.  
- **Schaalbaarheid** – Werkt zowel voor kleine projecten als voor enterprise‑niveau schema's.

## Voorvereisten

Voordat je in de code duikt, zorg ervoor dat je het volgende hebt:

1. **Basis .NET‑kennis** – Vertrouwd met C# en objectgeoriënteerde concepten.  
2. **Aspose.Tasks for .NET** – Download het van de [download link](https://releases.aspose.com/tasks/net/) en voeg de DLL toe aan je project.  
3. **Toegang tot de officiële documentatie** – De [documentation](https://reference.aspose.com/tasks/net/) bevat uitgebreide details over alle klassen.  
4. **Een ontwikkel‑IDE** – Visual Studio, Rider, of een andere compatibele .NET‑editor.

Nu je klaar bent, laten we de implementatie bekijken.

## Hoe Aspose.Tasks te gebruiken voor terugkerende taken

### Importeren van benodigde namespaces

Eerst, breng de benodigde namespaces in scope zodat je kunt werken met projecten, taken en opslaan‑opties.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### Stap 1: Initialiseer Project- en Taakparameters

Maak een nieuwe `Project`‑instantie aan en definieer vervolgens een `RecurringTaskParameters`‑object dat het herhalingspatroon beschrijft.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearWeekDayRepetition
        {
            Month = Month.July, WeekDay = DayOfWeek.Sunday, Position = OrdinalNumber.First
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 31, 17, 0, 0)
        }
    }
};
```

> **Pro tip:** Pas `Month`, `WeekDay` en `Position` aan om overeen te komen met je werkschema.

### Stap 2: Voeg parameters toe aan project

Voeg de terugkerende taakdefinitie in de root van het project in.

```csharp
project.RootTask.Children.Add(parameters);
```

### Stap 3: Sla project op als MPP

Sla tenslotte het project op in een MPP‑bestand zodat het geopend kan worden in Microsoft Project of een andere compatibele viewer.

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearWeekDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

> Dit demonstreert **save project as mpp** in één regel code.

## Veelvoorkomende problemen en oplossingen

| Symptoom | Waarschijnlijke oorzaak | Oplossing |
|----------|--------------------------|-----------|
| Geen taken zichtbaar na het openen van het MPP‑bestand | Datums van het herhalingsbereik vallen buiten de projectkalender | Controleer of `Start`‑ en `Finish`‑datums binnen de werktijd van het project vallen |
| Uitzondering `ArgumentNullException` bij `Add` | `parameters` is null of niet volledig geïnitialiseerd | Zorg ervoor dat alle vereiste eigenschappen (TaskName, Duration, RecurrencePattern) zijn ingesteld |
| Verkeerde weekdag geselecteerd | `WeekDay` enum‑waarde komt niet overeen | Gebruik `DayOfWeek.Monday` … `DayOfWeek.Sunday` indien nodig |

## Veelgestelde vragen

**Q: Kan ik het herhalingspatroon aanpassen buiten het gegeven voorbeeld?**  
A: Ja, Aspose.Tasks laat je `MonthlyRecurrencePattern`, `WeeklyRecurrencePattern` of zelfs aangepaste `RecurrenceRange`‑objecten combineren om elk schema te passen.

**Q: Is Aspose.Tasks for .NET compatibel met andere projectmanagementsoftware?**  
A: Absoluut – de bibliotheek leest en schrijft MPP, XML en Primavera‑formaten, waardoor soepele gegevensuitwisseling mogelijk is.

**Q: Hoe kan ik uitzonderingen of wijzigingen in terugkerende taken afhandelen?**  
A: Gebruik de `ExceptionTask`‑klasse om overrides voor specifieke voorkomens te maken, of bewerk de `RecurringTaskParameters` en sla het project opnieuw op.

**Q: Ondersteunt Aspose.Tasks cloud‑gebaseerde oplossingen?**  
A: Ja, je kunt de API uitvoeren in Azure Functions, AWS Lambda of elke .NET‑compatibele cloudservice.

**Q: Is er een proefversie beschikbaar voor Aspose.Tasks for .NET?**  
A: Ja, je kunt een gratis proefversie van Aspose.Tasks for .NET verkrijgen via de [website](https://releases.aspose.com/), zodat je de functies kunt verkennen voordat je een aankoopbeslissing neemt.

**Q: Hoe voeg ik een terugkerende taak toe aan een bestaand project zonder andere gegevens te overschrijven?**  
A: Laad het bestaande project met `new Project("Existing.mpp")`, voeg de `RecurringTaskParameters` toe aan `RootTask.Children` en sla vervolgens het bestand op met `Save`.

## Conclusie

Door **how to use Aspose.Tasks** voor het **Repetition by Year Week Day** scenario onder de knie te krijgen, krijg je de mogelijkheid om **add recurring task project** items toe te voegen die perfect aansluiten op echte kalenders en **save project as MPP** voor naadloze samenwerking. Integreer deze fragmenten in je eigen oplossingen om de planningsnauwkeurigheid te verhogen en handmatig werk te verminderen.

---

**Last Updated:** 2026-04-03  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}