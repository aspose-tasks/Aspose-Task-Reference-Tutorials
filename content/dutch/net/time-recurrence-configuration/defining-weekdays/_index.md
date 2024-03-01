---
title: Weekdagen beheersen in Aspose.Tasks voor .NET
linktitle: Weekdagen definiëren in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Ontdek de kracht van het definiëren van weekdagen in Aspose.Tasks .NET. Volg onze gedetailleerde tutorial om projectkalenders efficiënt te beheren, werktijden aan te passen en meer.
type: docs
weight: 10
url: /nl/net/time-recurrence-configuration/defining-weekdays/
---
## Invoering
Als je in de wereld van projectmanagement duikt met Aspose.Tasks voor .NET, is het begrijpen en manipuleren van weekdagen een cruciaal aspect. Het efficiënt beheren en aanpassen van weekdagen binnen uw projectkalender kan een aanzienlijke impact hebben op de projecttijdlijnen. In deze zelfstudie begeleiden we u bij het definiëren van weekdagen met Aspose.Tasks, waarbij we stapsgewijze instructies en voorbeelden geven voor meer duidelijkheid.
## Vereisten
Voordat we aan deze reis beginnen, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Basiskennis van de programmeertaal C#.
-  Aspose.Tasks voor .NET-bibliotheek geïnstalleerd. Zo niet, download het dan van[hier](https://releases.aspose.com/tasks/net/).
## Naamruimten importeren
Begin met het importeren van de benodigde naamruimten in uw project:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. Controleer de gelijkheid van weekdagen
```csharp
// Uw documentmap
String DataDir = "Your Document Directory";
// Projectbestand laden
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
// Toegang weekdagen
var weekDay1 = calendar.WeekDays[0];
var weekDay2 = calendar.WeekDays[1];
// Controleer de gelijkheid op basis van verschillende eigenschappen
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
// Voeg vergelijkbare uitvoerinstructies toe voor DayWorking, FromDate, ToDate en WorkingTimes
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
```
## 2. Kloon een weekdag
```csharp
// Projectbestand laden
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[0];
// Maak een diepe kopie van de weekdag
var weekDay2 = weekDay1.Clone();
// Uitvoereigenschappen van beide weekdagen
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
// Voeg vergelijkbare uitvoerinstructies toe voor DayWorking, FromDate, ToDate en WorkingTimes
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
Console.WriteLine("Are weekdays equal (by reference): " + ReferenceEquals(weekDay1, weekDay2));
```
## 3. Ontvang de hashcode van een weekdag
```csharp
// Projectbestand laden
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[1];
var weekDay2 = calendar.WeekDays[2];
// Uitvoereigenschappen van beide weekdagen
// Voeg vergelijkbare uitvoerinstructies toe voor DayWorking, FromDate, ToDate en WorkingTimes
Console.WriteLine("Week Day 1 Hash Code: {0}", weekDay1.GetHashCode());
Console.WriteLine("Week Day 2 Hash Code: {0}", weekDay2.GetHashCode());
```
## 4. Maak een nieuwe kalender met gedefinieerde weekdagen
```csharp
// Maak een nieuw project
var project = new Project();
// Definieer een kalender
var calendar = project.Calendars.Add("Calendar1");
// Voeg werkdagen en uitzonderingsdag toe
// Voeg vergelijkbare uitvoerinstructies toe voor FromDate en ToDate
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
// Stel werktijden in voor vrijdag
// Voeg vergelijkbare uitvoerinstructies toe voor DayWorking, FromDate, ToDate en WorkingTimes
var workingTimes = new List<WorkingTime> { new WorkingTime(9, 12), new WorkingTime(13, 16) };
var dayType = WeekDay.CastToDayType(DayOfWeek.Friday);
var weekDay = new WeekDay(dayType, workingTimes);
weekDay.DayWorking = true;
calendar.WeekDays.Add(weekDay);
```
## 5. Stel de standaardwerktijd voor een dag in
```csharp
// Maak een nieuw project
var project = new Project();
var calendar = project.Calendars.Add("Calendar1");
calendar.WeekDays.Clear();
// Voeg standaardwerktijden toe voor maandag tot en met vrijdag
// Voeg vergelijkbare uitvoerinstructies toe voor DayWorking, FromDate, ToDate en WorkingTimes
var monday = new WeekDay(DayType.Monday);
WeekDay.SetDefaultWorkingTime(monday);
calendar.WeekDays.Add(monday);
// Herhaal dit voor dinsdag, woensdag, donderdag en vrijdag
// Stel niet-werkdagen in voor zaterdag en zondag
// Voeg vergelijkbare uitvoerinstructies toe voor DayWorking, FromDate, ToDate en WorkingTimes
var saturday = new WeekDay(DayType.Saturday);
saturday.DayWorking = false;
calendar.WeekDays.Add(saturday);
var sunday = new WeekDay(DayType.Sunday);
sunday.DayWorking = false;
calendar.WeekDays.Add(sunday);
```
## Conclusie
In deze zelfstudie hebben we essentiële aspecten van het definiëren van weekdagen in Aspose.Tasks voor .NET besproken. Het manipuleren van weekdagen is een sleutelvaardigheid voor effectief projectmanagement. Experimenteer met de gegeven voorbeelden, pas ze aan de behoeften van uw project aan en ontgrendel het volledige potentieel van Aspose.Tasks.
## Veelgestelde vragen
### Kan ik voor elke dag aangepaste werktijden definiëren?
Ja, u kunt aangepaste werktijden instellen voor specifieke weekdagen aan de hand van de meegeleverde voorbeelden.
### Is het mogelijk om meerdere uitzonderingsdagen aan de kalender toe te voegen?
Absoluut. Wijzig de code in het vierde voorbeeld om extra uitzonderingsdagen op te nemen.
### Hoe kan ik een specifieke weekdag uit de kalender verwijderen?
Gebruik de juiste methoden van de Aspose.Tasks-bibliotheek om indien nodig weekdagen te verwijderen.
### Zijn de wijzigingen in de weekdagen persistent in het projectbestand?
Ja, alle wijzigingen aan weekdagen worden bij het opslaan weergegeven in het projectbestand.
### Kan ik Aspose.Tasks met andere programmeertalen gebruiken?
Aspose.Tasks ondersteunt verschillende programmeertalen, maar de voorbeelden hier zijn specifiek voor .NET.