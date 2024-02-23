---
title: Pas werkweken aan in Aspose.Tasks
linktitle: Verzameling van werkweken in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Leer hoe u werkweken kunt aanpassen in Aspose.Tasks voor .NET. Stapsgewijze handleiding voor het maken van gepersonaliseerde projectkalenders. Download nu!
type: docs
weight: 17
url: /nl/net/time-recurrence-configuration/workweek-collection/
---
## Invoering
Welkom bij onze tutorial over het maken van een aangepaste werkweek met Aspose.Tasks voor .NET! In deze stapsgewijze handleiding leiden we u door het proces van het definiëren van een gepersonaliseerde werkweek voor een kalender in uw project. Aspose.Tasks is een krachtige bibliotheek waarmee ontwikkelaars efficiënt kunnen werken met Microsoft Project-documenten in hun .NET-toepassingen.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1. Visual Studio: Zorg ervoor dat Visual Studio op uw computer is geïnstalleerd.
2.  Aspose.Tasks voor .NET: Download en installeer de Aspose.Tasks-bibliotheek. Je kunt de downloadlink vinden[hier](https://releases.aspose.com/tasks/net/).
3. Basiskennis van C#: maak uzelf vertrouwd met de basisprincipes van de programmeertaal C#.
## Naamruimten importeren
Zorg ervoor dat u in uw C#-project de benodigde naamruimten importeert:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Stap 1: Maak een project en kalender
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Standard");
Calendar.MakeStandardCalendar(calendar);
```
## Stap 2: Definieer een aangepaste werkweek
```csharp
var customWorkWeek = new WorkWeek();
customWorkWeek.Name = "My Work Week";
customWorkWeek.FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
customWorkWeek.ToDate = new DateTime(2020, 4, 17, 17, 0, 0);
```
## Stap 3: Stel werkdagen in
```csharp
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Friday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Saturday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Sunday));
calendar.WorkWeeks.Add(customWorkWeek);
```
## Stap 4: Geef informatie over werkweken weer
```csharp
Console.WriteLine("Work Weeks Count: " + calendar.WorkWeeks.Count);
foreach (var workWeek in calendar.WorkWeeks)
{
    Console.WriteLine("Name: " + workWeek.Name);
    Console.WriteLine("Parent calendar name: " + calendar.Name);
    Console.WriteLine("From Date: " + workWeek.FromDate);
    Console.WriteLine("To Date: " + workWeek.ToDate);
    List<WeekDay> weekDays = workWeek.WeekDays.ToList();
    foreach (var day in weekDays)
    {
        Console.WriteLine(day.DayType.ToString());
        foreach (var workingTime in day.WorkingTimes)
        {
            Console.WriteLine(workingTime.From);
            Console.WriteLine(workingTime.To);
        }
    }
    Console.WriteLine();
}
```
Met deze uitgebreide handleiding kunt u op efficiënte wijze aangepaste werkweken maken en beheren met Aspose.Tasks voor .NET.
## Conclusie
Concluderend biedt Aspose.Tasks voor .NET een robuuste oplossing voor het verwerken van projectkalenders met aangepaste werkweken. Door deze tutorial te volgen, heeft u geleerd hoe u informatie over aangepaste werkweken in uw project kunt maken en weergeven.
## Veelgestelde vragen
### Kan ik meerdere maatwerkweken in één project hebben?
Ja, u kunt meerdere maatwerkwerkweken toevoegen aan een projectkalender.
### Hoe kan ik bestaande werkweken wijzigen?
 Gebruik de meegeleverde`WorkWeek` eigenschappen en methoden om bestaande werkweken aan te passen.
### Is Aspose.Tasks compatibel met .NET Core?
Ja, Aspose.Tasks ondersteunt .NET Core.
### Kan ik het project met aangepaste werkweken exporteren naar het Microsoft Project-bestandsformaat?
Absoluut, met Aspose.Tasks kunt u uw project in verschillende formaten opslaan, waaronder Microsoft Project.
### Waar kan ik ondersteuning zoeken voor Aspose.Tasks-gerelateerde vragen?
 bezoek de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15) voor elke steun of hulp.