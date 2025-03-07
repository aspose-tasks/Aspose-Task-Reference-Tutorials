---
title: Weekdagen beheersen in Aspose.Tasks
linktitle: Verzameling van weekdagen in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Ontdek de kracht van Aspose.Tasks voor .NET bij het moeiteloos beheren van weekdagen. Pas werkdagen aan, verwijder weekenden en maak eenvoudig gespecialiseerde kalenders.
weight: 11
url: /nl/net/time-recurrence-configuration/weekday-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Weekdagen beheersen in Aspose.Tasks

## Invoering
Aspose.Tasks voor .NET is een krachtige bibliotheek die efficiënte manipulatie van projectmanagementgegevens mogelijk maakt. In deze zelfstudie verkennen we de verzameling weekdagen in Aspose.Tasks, zodat u werkdagen kunt aanpassen, weekends kunt verwijderen en gespecialiseerde kalenders kunt maken om aan uw projectvereisten te voldoen. Of u nu een doorgewinterde ontwikkelaar of een nieuwkomer bent, deze stapsgewijze handleiding leidt u door het proces van het werken met weekdagen in Aspose.Tasks voor .NET.
## Vereisten
Voordat we ingaan op de tutorial, zorg ervoor dat je aan de volgende vereisten voldoet:
-  Installeer de Aspose.Tasks voor .NET-bibliotheek. Je kunt het downloaden van de[Aspose.Tasks voor .NET-downloadpagina](https://releases.aspose.com/tasks/net/).
- Kennis van de programmeertaal C#.
- Geïntegreerde ontwikkelomgeving (IDE) zoals Visual Studio.
## Naamruimten importeren
Begin met het importeren van de benodigde naamruimten in uw C#-project:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Stap 1: Maak een projectinstantie
Initialiseer een nieuw Aspose.Tasks-project:
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## Stap 2: Open de kalender
Haal de projectkalender op:
```csharp
var calendar = project.Calendars.GetByName("Standard");
```
## Stap 3: Pas weekdagen aan
Bestaande weekdagen wissen en standaardwerkdagen instellen:
```csharp
calendar.WeekDays.Clear();
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
// Voeg andere weekdagen op dezelfde manier toe...
```
## Stap 4: Werktijden toevoegen
Werktijden toevoegen voor specifieke weekdagen:
```csharp
var fridayWorkingTimes = new List<WorkingTime> { new WorkingTime(new DateTime(2020, 4, 13, 8, 0, 0), new DateTime(2020, 4, 13, 12, 0, 0)) };
var friday = new WeekDay(DayType.Friday, fridayWorkingTimes);
calendar.WeekDays.Insert(4, friday);
```
## Stap 5: Agenda-informatie weergeven
Agendagegevens naar de console uitvoeren:
```csharp
Console.WriteLine("Calendar: " + calendar.Name);
Console.WriteLine("Week days count: " + calendar.WeekDays.Count);
// Geef elke weekdag en werktijden weer...
```
## Stap 6: Weekends verwijderen
Verwijder zaterdag en zondag uit de weekdagen:
```csharp
calendar.WeekDays.RemoveAt(5);
if (calendar.WeekDays.Contains(saturday))
{
    calendar.WeekDays.Remove(sunday);
}
```
## Stap 7: Geef bijgewerkte werktijden weer
Voer bijgewerkte werktijden uit na het verwijderen van weekenden:
```csharp
Console.WriteLine("Working times after weekend was removed: ");
List<WeekDay> weekDays = calendar.WeekDays.ToList();
// Geef elke bijgewerkte weekdag en werktijden weer...
```
## Stap 8: Maak een 24-uurskalender
Maak een 24-uurskalender en kopieer weekdagen:
```csharp
var hour24Calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(hour24Calendar);
var weekDaysArray = new WeekDay[calendar.WeekDays.Count];
calendar.WeekDays.CopyTo(weekDaysArray, 0);
foreach (var weekDay in weekDaysArray)
{
    hour24Calendar.WeekDays.Add(weekDay);
}
```
## Conclusie
In deze tutorial hebben we de krachtige mogelijkheden van Aspose.Tasks voor .NET onderzocht bij het beheren van weekdagen binnen projectkalenders. Van het aanpassen van werkdagen tot het maken van gespecialiseerde 24-uurskalenders, Aspose.Tasks vereenvoudigt het proces en biedt flexibiliteit en controle bij projectbeheer.
## Veel Gestelde Vragen
### Vraag: Kan ik Aspose.Tasks voor .NET gebruiken met andere programmeertalen?
A: Aspose.Tasks ondersteunt voornamelijk .NET-talen, maar biedt ook versies voor Java.
### Vraag: Is er een gratis proefversie beschikbaar voor Aspose.Tasks voor .NET?
 A: Ja, u kunt een gratis proefversie downloaden van de[Aspose.Tasks-releasepagina](https://releases.aspose.com/).
### Vraag: Hoe kan ik ondersteuning krijgen voor Aspose.Tasks voor .NET?
 A: Bezoek de[Aspose.Tasks-forum](https://forum.aspose.com/c/tasks/15) voor gemeenschapsondersteuning of overweeg een ondersteuningsplan aan te schaffen.
### Vraag: Waar kan ik uitgebreide documentatie vinden voor Aspose.Tasks voor .NET?
 A: Raadpleeg de[Aspose.Tasks voor .NET-documentatie](https://reference.aspose.com/tasks/net/) voor gedetailleerde informatie.
### Vraag: Hoe verkrijg ik een tijdelijke licentie voor Aspose.Tasks voor .NET?
 A: U kunt een tijdelijke licentie verkrijgen bij de[tijdelijke licentiepagina](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
