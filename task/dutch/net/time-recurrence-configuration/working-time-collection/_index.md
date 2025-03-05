---
title: Werktijden beheersen in Aspose.Tasks
linktitle: Verzameling van werktijden in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Ontdek de kracht van Aspose.Tasks voor .NET bij het efficiënt beheren van projecttijdlijnen. Pas kalenders aan, stel werktijden in en stroomlijn uw projecten met gemak.
type: docs
weight: 14
url: /nl/net/time-recurrence-configuration/working-time-collection/
---
## Invoering
Wilt u de kunst van het beheren van werktijden onder de knie krijgen in Aspose.Tasks voor .NET? Zoek niet verder! In deze stapsgewijze handleiding verdiepen we ons in de fijne kneepjes van het verzamelen van werktijden met behulp van Aspose.Tasks, waardoor u efficiënt met aangepaste kalenders kunt omgaan en de tijdlijnen van uw projecten kunt stroomlijnen.
## Vereisten
Voordat we aan deze reis beginnen, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
-  Aspose.Tasks voor .NET-bibliotheek: Download en installeer de Aspose.Tasks voor .NET-bibliotheek vanaf de[Aspose.Tasks-releasepagina](https://releases.aspose.com/tasks/net/).
- Werkomgeving: Zet een geschikte ontwikkelomgeving op, bij voorkeur met behulp van een .NET-compatibele IDE.
## Naamruimten importeren
Importeer in uw project de benodigde naamruimten om toegang te krijgen tot de Aspose.Tasks-functionaliteiten:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Laten we de tutorial nu in meerdere stappen opsplitsen, zodat u een soepele leerervaring kunt garanderen.
## Stap 1: Maak een aangepaste kalender
Begin met het maken van een nieuw project en het toevoegen van een aangepaste kalender:
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Custom Calendar");
```
## Stap 2: Werkdagen definiëren
Standaardwerkdagen instellen van maandag tot en met vrijdag:
```csharp
foreach (var dayType in Enum.GetValues(typeof(DayType)).Cast<DayType>())
{
    if (dayType != DayType.Saturday && dayType != DayType.Sunday)
    {
        calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(dayType));
    }
}
```
## Stap 3: Configureer de zaterdagwerktijden
Geef werktijden op voor zaterdag:
```csharp
var saturdayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(8, 12),
    new WorkingTime(13, 15)
};
var saturday = new WeekDay(DayType.Saturday, saturdayWorkingTimes);
```
## Stap 4: Werkperioden op zaterdag afdrukken
Print de geconfigureerde werktijden voor zaterdag:
```csharp
Console.WriteLine("Saturday working period number: " + saturday.WorkingTimes.Count);
foreach (var time in saturday.WorkingTimes)
{
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## Stap 5: Configureer de werktijden op zondag
Werktijden voor zondag definiëren:
```csharp
var sundayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(10, 15)
};
var sunday = new WeekDay(DayType.Sunday, sundayWorkingTimes);
```
## Stap 6: Zondagwerkperioden afdrukken
Print de geconfigureerde werktijden voor zondag:
```csharp
List<WorkingTime> workingTimes = sunday.WorkingTimes.ToList();
Console.WriteLine("Sunday working period number: " + workingTimes.Count);
for (var index = 0; index < workingTimes.Count; index++)
{
    var time = workingTimes[index];
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## Stap 7: aangepaste dagen toevoegen aan de agenda
Neem de geconfigureerde zaterdag en zondag op in de kalender:
```csharp
calendar.WeekDays.Add(saturday);
calendar.WeekDays.Add(sunday);
```
## Stap 8: Doorloop de werktijden
Doorloop de werktijden en geef ze voor elke dag weer in de kalender:
```csharp
foreach (var day in calendar.WeekDays)
{
    Console.WriteLine(day.DayType + ": ");
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
    Console.WriteLine();
}
```
Nu u met succes door de stappen heeft genavigeerd, bent u uitgerust om de kracht van Aspose.Tasks voor .NET te benutten bij het effectief beheren van werktijden.
## Conclusie
Door het verzamelen van werktijden in Aspose.Tasks onder de knie te krijgen, kunt u projectkalenders aanpassen, waardoor een nauwkeurige planning en efficiënt gebruik van middelen wordt gegarandeerd. Duik met vertrouwen in uw projecten, gewapend met de kennis uit deze uitgebreide gids.
## Veel Gestelde Vragen
### Is Aspose.Tasks geschikt voor grootschalig projectmanagement?
Ja, Aspose.Tasks is ontworpen voor projecten van verschillende omvang en biedt robuuste functies voor efficiënt projectbeheer.
### Kan ik Aspose.Tasks integreren met andere .NET-bibliotheken?
Zeker! Aspose.Tasks kan naadloos worden geïntegreerd met andere .NET-bibliotheken, waardoor de veelzijdigheid en compatibiliteit worden vergroot.
### Hoe vaak wordt Aspose.Tasks bijgewerkt?
 Aspose.Tasks wordt regelmatig bijgewerkt met nieuwe functies, verbeteringen en compatibiliteitsverbeteringen. Controleer de[pagina vrijgeven](https://releases.aspose.com/tasks/net/) voor de laatste updates.
### Is er een gratis proefversie beschikbaar voor Aspose.Tasks?
 Ja, u kunt Aspose.Tasks verkennen met een gratis proefperiode door te bezoeken[deze link](https://releases.aspose.com/).
### Waar kan ik ondersteuning zoeken voor Aspose.Tasks?
 Voor vragen of hulp kunt u terecht op de[Ondersteuningsforum van Aspose.Tasks](https://forum.aspose.com/c/tasks/15).