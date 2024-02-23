---
title: Configureer werktijden in Aspose.Tasks
linktitle: Configureer werktijden in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Verbeter de projectplanning in .NET met Aspose.Tasks. Configureer moeiteloos werktijden voor nauwkeurig resourcebeheer. Download de bibliotheek nu!
type: docs
weight: 13
url: /nl/net/time-recurrence-configuration/working-times/
---
## Invoering
Bij projectmanagement is nauwkeurige controle over de werktijden cruciaal voor een nauwkeurige planning en toewijzing van middelen. Aspose.Tasks voor .NET biedt een krachtige oplossing voor het verwerken van werktijdinformatie binnen uw projecten. Deze tutorial begeleidt u bij het configureren van werktijden met Aspose.Tasks in een .NET-omgeving.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u over het volgende beschikt:
- Basiskennis van de programmeertaal C#.
- Aspose.Tasks voor .NET-bibliotheek geïnstalleerd. Je kunt het downloaden[hier](https://releases.aspose.com/tasks/net/).
- Stel Visual Studio of een andere C#-ontwikkelomgeving van uw voorkeur in.
## Naamruimten importeren
Begin met het importeren van de benodigde naamruimten om toegang te krijgen tot de Aspose.Tasks-functionaliteiten:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    
```
## Stap 1: Agenda maken
```csharp
var project = new Project();
var calendar = CreateCalendar(project);
project.Set(Prj.Calendar, calendar);
```
Hier starten we een nieuw project en maken we een kalender met de naam "MyCalendar" op basis van de standaardkalender. Deze kalender wordt gebruikt om specifieke werktijden te definiëren.

```csharp
        public static Calendar CreateCalendar(Project project)
        {
            var calendar = project.Calendars.Add("MyCalendar", project.Calendars.GetByName("Standard"));
            var workingTimes = new List<WorkingTime>
                                   {
                                       new WorkingTime(new DateTime(1, 1, 1, 9, 0, 0), new DateTime(1, 1, 1, 12, 0, 0)),
                                       new WorkingTime(new DateTime(1, 1, 1, 13, 0, 0), new DateTime(1, 1, 1, 18, 0, 0))
                                   };

            calendar.WeekDays.Add(new WeekDay(DayType.Monday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Tuesday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Wednesday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Thursday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Friday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Saturday));
            calendar.WeekDays.Add(new WeekDay(DayType.Sunday));

            return calendar;
        }	
```
## Stap 2: Geef werkweekinformatie weer
```csharp
Console.WriteLine("Work Week Number: " + calendar.WeekDays.Count);
```
Met deze stap wordt het totale aantal werkdagen in de opgegeven kalender afgedrukt.
## Stap 3: Details van de werktijden
```csharp
List<WeekDay> weekDays = calendar.WeekDays.ToList();
foreach (var day in weekDays)
{
    Console.WriteLine(day.DayType.ToString());
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine(workingTime.From);
        Console.WriteLine(workingTime.To);
    }
}
```
In dit deel doorlopen we elke dag van de week, waarbij we het dagtype en de bijbehorende werktijden afdrukken. U kunt de werktijden voor elke weekdag aanpassen aan uw projectvereisten.
## Conclusie
Het effectief configureren van werktijden in Aspose.Tasks voor .NET zorgt voor een nauwkeurige projectplanning en resourcebeheer. Door deze stapsgewijze handleiding te volgen, kunt u werktijdaanpassingen naadloos integreren in uw projectworkflows.
## Veel Gestelde Vragen
### Is Aspose.Tasks geschikt voor grootschalig projectmanagement?
Ja, Aspose.Tasks is ontworpen voor projecten van verschillende omvang en biedt robuuste functies voor efficiënt projectbeheer.
### Kan ik verschillende werktijden instellen voor verschillende teamleden?
Absoluut. U kunt de werktijden per resource aanpassen, waardoor geïndividualiseerde schema's mogelijk zijn.
### Ondersteunt Aspose.Tasks integratie met andere projectmanagementtools?
Ja, Aspose.Tasks vergemakkelijkt de integratie met verschillende projectmanagementtools, waardoor de interoperabiliteit wordt verbeterd.
### Is het mogelijk om projectgegevens in verschillende formaten te importeren/exporteren?
Aspose.Tasks ondersteunt meerdere bestandsformaten, waardoor naadloze import-/exportbewerkingen voor projectgegevens mogelijk zijn.
### Hoe vaak worden Aspose.Tasks-updates uitgebracht?
Er worden regelmatig updates uitgebracht om compatibiliteit met de nieuwste technologieën te garanderen en om feedback van gebruikers te verwerken.