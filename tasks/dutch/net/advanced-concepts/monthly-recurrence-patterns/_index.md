---
date: 2026-03-08
description: Leer hoe u een maandelijks terugkerende taak in Aspose.Tasks voor .NET
  maakt met deze stapsgewijze tutorial.
linktitle: How to Create Monthly Recurring Task in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Hoe maak je een maandelijks terugkerende taak in Aspose.Tasks
url: /nl/net/advanced-concepts/monthly-recurrence-patterns/
weight: 18
---

.

Also "## Frequently Asked Questions" we also translate to "## Veelgestelde Vragen". Could differentiate but okay.

Make sure to keep markdown formatting.

Now produce final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maak Maandelijkse Terugkerende Taak Met Aspose.Tasks

## Inleiding

Aspose.Tasks for .NET stelt je in staat om programmatically Microsoft Project‑bestanden te manipuleren, en een van de meest voorkomende praktijkbehoeften is om **maandelijkse terugkerende taak** schema's te maken. Of je nu een project‑volgtool bouwt, resource‑toewijzing automatiseert, of terugkerende onderhoudswerkitems genereert, deze tutorial leidt je stap voor stap door het toevoegen van een maandelijks herhalingspatroon aan een taak.

## Snelle Antwoorden
- **Wat betekent “monthly recurring task”?** Een taak die elke maand herhaalt volgens een gedefinieerd dag‑of‑weekpatroon.  
- **Welke API‑klasse behandelt herhaling?** `RecurringTaskParameters` samen met `MonthlyRecurrencePattern`.  
- **Heb ik een licentie nodig om het voorbeeld uit te voeren?** Een gratis proefversie werkt voor evaluatie; een licentie is vereist voor productie.  
- **Kan ik het interval wijzigen?** Ja – stel `RepetitionInterval` in op het aantal maanden tussen de gebeurtenissen.  
- **Welke bestandsformaten worden ondersteund?** Zowel `.mpp` als `.xml` Project‑bestanden kunnen worden geladen en opgeslagen.

## Wat is een Maandelijks Herhalingspatroon?

Een maandelijks herhalingspatroon vertelt Microsoft Project (en Aspose.Tasks) hoe vaak een taak elke maand moet worden herhaald. Je kunt een vaste dag van de maand opgeven (bijv. de 1e) of een relatieve positie (bijv. de laatste vrijdag). De API vertaalt deze regels naar de onderliggende Project‑bestandstructuur.

## Waarom Aspose.Tasks hiervoor gebruiken?

- **Volledige controle** – Geen UI‑beperkingen; je definieert elk aspect van het patroon in code.  
- **Cross‑platform** – Werkt op .NET Framework, .NET Core en .NET 5/6+.  
- **Geen Microsoft Project vereist** – Genereer of wijzig bestanden op een server of CI‑pipeline.  

## Voorvereisten

- .NET 6 (of .NET 5/Framework 4.7+) geïnstalleerd.  
- Aspose.Tasks for .NET NuGet‑pakket toegevoegd aan je project.  
- Een voorbeeld Project‑bestand (`Project1.mpp`) geplaatst in een bekende map (`DataDir`).  

## Importer Namespaces

Importeer eerst de namespaces die nodig zijn voor het werken met taken en het opslaan van projecten:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

## Stap 1: Initialiseer het Project

Maak een `Project`‑instantie die naar je bestaande `.mpp`‑bestand wijst. Dit laadt het bestand in het geheugen zodat je het kunt wijzigen.

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

> **Pro tip:** Als het bestand niet bestaat, maakt Aspose.Tasks automatisch een nieuw leeg project aan.

## Stap 2: Stel Recurring Task‑parameters in

Definieer de details van de terugkerende taak, inclusief de naam, duur en het maandelijkse patroon dat je wilt toepassen.

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthDayRepetition { DayPosition = 1, RepetitionInterval = 2 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 30, 17, 0, 0)
        }
    }
};
```

- `DayPosition = 1` betekent dat de taak plaatsvindt op de **eerste dag** van de maand.  
- `RepetitionInterval = 2` zorgt ervoor dat de taak **elke twee maanden** wordt herhaald.  
- `Start` en `Finish` definiëren het totale venster waarin de herhaling actief is.

## Stap 3: Voeg Parameters toe aan het Project

Koppel het `RecurringTaskParameters`‑object aan de children‑collectie van de root‑taak. Dit creëert effectief de terugkerende taak in de project‑hiërarchie.

```csharp
project.RootTask.Children.Add(parameters);
```

## Stap 4: Sla het Project op

Bewaar de wijzigingen door het project op te slaan naar een nieuw bestand. Je kunt elk ondersteund formaat kiezen; hier gebruiken we het native `.mpp`‑formaat.

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Na het uitvoeren van de code, open je het resulterende bestand in Microsoft Project om de maandelijkse terugkerende taak die je zojuist hebt gemaakt te zien.

## Veelvoorkomende Problemen en Oplossingen

| Probleem | Oorzaak | Oplossing |
|----------|---------|-----------|
| Taak verschijnt niet na opslaan | Project niet ververst in UI | Open het bestand opnieuw of roep `project.UpdateTaskLinks()` aan vóór het opslaan. |
| Verkeerde startdatum | `Start` ingesteld op een weekend | Gebruik een `DateTime` die op een werkdag valt of pas de kalender aan. |
| Herhalingsinterval genegeerd | Gebruik van `ByMonthDayRepetition` met `DayPosition` = 0 | Zorg ervoor dat `DayPosition` tussen 1‑31 ligt. |

## Conclusie

Door deze stappen te volgen, weet je nu hoe je **maandelijkse terugkerende taak** schema's kunt maken met Aspose.Tasks voor .NET. De API biedt je gedetailleerde controle over herhalingsintervallen, start-/eindbereiken en het specifieke dagpatroon, waardoor je complexe project‑planningsscenario's kunt automatiseren.

## FAQ's

### Q1: Is Aspose.Tasks compatibel met alle versies van Microsoft Project‑bestanden?

A1: Aspose.Tasks ondersteunt verschillende versies van Microsoft Project‑bestanden, waaronder MPP, MPT, XML en MPX.

### Q2: Kan ik het herhalingspatroon verder aanpassen?

A2: Ja, Aspose.Tasks biedt uitgebreide opties voor het aanpassen van herhalingspatronen, inclusief dagelijks, wekelijks, maandelijks en jaarlijks.

### Q3: Is er een gratis proefversie beschikbaar voor Aspose.Tasks?

A3: Ja, je kunt een gratis proefversie van Aspose.Tasks verkrijgen via de website [hier](https://releases.aspose.com/).

### Q4: Hoe kan ik ondersteuning krijgen voor Aspose.Tasks?

A4: Je kunt hulp zoeken en deelnemen aan discussies op het [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### Q5: Waar kan ik een licentie voor Aspose.Tasks kopen?

A5: Je kunt een licentie voor Aspose.Tasks kopen via de website [hier](https://purchase.aspose.com/buy)

## Veelgestelde Vragen

**V: Kan ik deze code gebruiken in een .NET Core‑applicatie?**  
A: Absoluut. Aspose.Tasks for .NET ondersteunt volledig .NET Core 3.1 en latere versies.

**V: Hoe wijzig ik de herhaling naar “laatste weekdag van de maand”?**  
A: Gebruik `ByMonthDayRepetition` met `DayPosition = -1` (negatieve waarden tellen vanaf het einde van de maand) en stel `WeekDay` dienovereenkomstig in.

**V: Wat gebeurt er als het herhalingsbereik de projectkalender overschrijdt?**  
A: De API respecteert de projectkalender; gebeurtenissen die op niet‑werkdagen vallen, worden ofwel overgeslagen of verplaatst volgens de instellingen van de kalender.

**V: Is het mogelijk om een specifieke gebeurtenis van een terugkerende taak te verwijderen?**  
A: Ja. Na het toevoegen van de terugkerende taak kun je individuele gebeurtenissen ophalen via `Task.GetOccurrences()` en de ongewenste verwijderen.

**V: Handelt Aspose.Tasks tijdzoneverschillen automatisch af?**  
A: De bibliotheek slaat datums op in UTC; je kunt ze indien nodig omzetten naar lokale tijd met standaard .NET `DateTime`‑methoden.

---

**Laatst bijgewerkt:** 2026-03-08  
**Getest met:** Aspose.Tasks 24.11 for .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}