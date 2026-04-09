---
date: 2026-04-09
description: Leer hoe u een standaardkalender instelt en projectvakanties beheert
  in uw .NET‑projecten met Aspose.Tasks voor nauwkeurige planning.
keywords:
- set standard calendar
- manage project holidays
- load project calendar
linktitle: Standaardkalender instellen en uitzonderingen verwerken in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Standaardkalender instellen en uitzonderingen afhandelen in Aspose.Tasks
url: /nl/net/calendar-scheduling/calendar-exception-collection/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Standaardkalender instellen en uitzonderingen afhandelen in Aspose.Tasks

## Introductie

Nauwkeurige planning is de ruggengraat van elk succesvol project, en real‑world plannen moeten vaak afwijken van de standaard werkagenda vanwege feestdagen, speciale evenementen of onverwachte stilleggingen. Aspose.Tasks voor .NET maakt het eenvoudig om **set standard calendar** instellingen te configureren en vervolgens aangepaste uitzonderingen toe te voegen. In deze tutorial leer je hoe je een projectkalender laadt, een standaardkalender instelt en projectvakanties beheert via de Calendar Exception Collection‑functie.

## Snelle antwoorden
- **Wat doet “set standard calendar”?** Het reset een kalender naar de standaard werktijd (9 uur‑17 uur, maandag‑vrijdag) voordat je aangepaste uitzonderingen toevoegt.  
- **Welke methode wist bestaande uitzonderingen?** `Calendar.Exceptions.Clear()` verwijdert alle eerder gedefinieerde uitzonderingen.  
- **Hoe kan ik een vakantie toevoegen?** Maak een `CalendarException` met `DayWorking = false` en voeg deze toe aan de collectie.  
- **Moet ik het project opnieuw laden na wijzigingen?** Nee, wijzigingen worden direct toegepast op het in‑memory `Project`‑object.  
- **Welke bibliotheken zijn vereist?** Aspose.Tasks voor .NET (elke ondersteunde .NET‑versie) en `System`‑namespaces.

## Voorvereisten

1. **Aspose.Tasks for .NET** – download het [hier](https://releases.aspose.com/tasks/net/).  
2. Basiskennis van **C#** – je zult een paar korte fragmenten schrijven.  
3. Een ontwikkelomgeving zoals **Visual Studio** of **JetBrains Rider**.

## Namespaces importeren

Deze `using`‑directieven geven je toegang tot de klassen die nodig zijn voor het manipuleren van kalenders.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Wat is een kalenderuitzondering?

Een *kalenderuitzondering* vertegenwoordigt een periode waarin het normale werkschema wordt aangepast – bijvoorbeeld een bedrijfsbrede feestdag of een tijdelijk overurenschema. Door uitzonderingen aan een kalender toe te voegen kun je real‑world beperkingen modelleren zonder de basisagenda te wijzigen.

## Hoe een standaardkalender instellen in Aspose.Tasks

De eerste stap is het laden van je projectbestand en het ophalen van de kalender waarmee je wilt werken.

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

### Stap 1: Bestaande uitzonderingen wissen en resetten naar een standaardkalender

Voordat je nieuwe regels toevoegt, is het een goede gewoonte om eventuele oude uitzonderingen te wissen en **set standard calendar** instellingen te gebruiken. Dit zorgt voor een schone basis.

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

### Stap 2: Een werktijd‑uitzondering definiëren

Soms moet je een tijdelijk schema maken (bijv. verlengde uren voor een productlancering). Het volgende fragment definieert een werktijd‑uitzondering die zich over meerdere dagen uitstrekt en twee dagelijkse werkperioden bevat.

```csharp
var exception = new CalendarException();
exception.FromDate = new DateTime(2020, 3, 30, 8, 0, 0);
exception.ToDate = new DateTime(2020, 4, 3, 17, 0, 0);
exception.DayWorking = true;
exception.Name = "Exception 1";

var wt1 = new WorkingTime(9, 13);
var wt2 = new WorkingTime(14, 19);

exception.WorkingTimes.Add(wt1);
exception.WorkingTimes.Add(wt2);
calendar.Exceptions.Add(exception);
```

### Stap 3: Niet‑werkende tijd‑uitzonderingen toevoegen (vakanties)

Om **projectvakanties** te beheren, maak je uitzonderingen waarbij `DayWorking` `false` is. Het voorbeeld hieronder voegt een twee‑daagse vakantieblok toe.

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// Add more exceptions if needed

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

### Stap 4: Kalenderuitzonderingen weergeven (verificatie)

Na het toevoegen van uitzonderingen wil je vaak verifiëren dat ze correct zijn vastgelegd. De volgende lus print de details van elke uitzondering naar de console.

```csharp
Console.WriteLine("Exceptions of calendar {0}: ", calendar.Exceptions.ParentCalendar.Name);
Console.WriteLine("Exceptions count: {0}", calendar.Exceptions.Count);
Console.WriteLine();
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Name: " + calendarException.Name);
    Console.WriteLine("From Date: " + calendarException.FromDate);
    Console.WriteLine("To Date: " + calendarException.ToDate);
    Console.WriteLine("Is day working: " + calendarException.DayWorking);
    Console.WriteLine();
}
```

### Stap 5: Alle uitzonderingen verwijderen (opschonen)

Als je de kalender wilt terugzetten naar de oorspronkelijke staat, kun je elke uitzondering programmatisch verwijderen.

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

## Veelvoorkomende problemen en oplossingen

| Probleem | Reden | Oplossing |
|----------|-------|-----------|
| Uitzonderingen verschijnen niet na opslaan | Project niet opgeslagen na wijzigingen | Roep `project.Save("output.mpp")` aan na het aanbrengen van wijzigingen. |
| Overlapende uitzonderingen veroorzaken onverwachte werktijden | Aspose.Tasks gebruikt de laatst toegevoegde uitzondering voor overlappende periodes | Orden je `Add`‑aanroepen zorgvuldig of pas handmatig prioriteiten aan. |
| `MakeStandardCalendar` reset aangepaste werktijden | Het wist opzettelijk aangepaste tijden; voeg ze opnieuw toe na de aanroep indien nodig. | Voeg je aangepaste `WorkingTime`‑objecten toe na het aanroepen van `MakeStandardCalendar`. |

## Veelgestelde vragen

**Q: Kan ik meerdere uitzonderingen aan één kalender toevoegen?**  
A: Ja, je kunt meerdere uitzonderingen aan een kalender toevoegen met de `AddRange`‑methode.

**Q: Hoe ga ik om met terugkerende uitzonderingen, zoals wekelijkse vakanties?**  
A: Je kunt programmatisch terugkerende uitzonderingen berekenen en ze aan de kalender toevoegen met aangepaste logica.

**Q: Is het mogelijk om kalenderuitzonderingen te importeren vanuit externe bronnen?**  
A: Ja, je kunt kalenderuitzonderingen lezen uit externe bronnen zoals databases of CSV‑bestanden en ze in je project integreren.

**Q: Wat gebeurt er als er overlappende uitzonderingen in de kalender zijn?**  
A: Aspose.Tasks voor .NET stelt je in staat overlappende uitzonderingen af te handelen door prioriteiten te definiëren of conflicten op te lossen op basis van je projectvereisten.

**Q: Kan ik de werktijden voor elke dag binnen een uitzondering aanpassen?**  
A: Ja, je kunt aangepaste werktijden specificeren voor individuele dagen binnen een uitzondering om te voldoen aan specifieke planningsbehoeften.

## Conclusie

Door eerst **set standard calendar** in te stellen en vervolgens aangepaste uitzonderingen toe te voegen, krijg je volledige controle over projectplanning, waardoor het eenvoudig wordt om **projectvakanties** te beheren en andere speciale tijdlijnen. De Calendar Exception Collection in Aspose.Tasks biedt een nette, programmatic manier om real‑world kalenders direct binnen je .NET‑applicaties te modelleren.

---

**Laatst bijgewerkt:** 2026-04-09  
**Getest met:** Aspose.Tasks 24.12 for .NET  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}