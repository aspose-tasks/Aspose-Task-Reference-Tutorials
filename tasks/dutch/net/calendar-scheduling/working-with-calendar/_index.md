---
title: Werken met Agenda in Aspose.Tasks
linktitle: Werken met Agenda in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Beheer projectkalenders, bereken de duur en handel uitzonderingen eenvoudig af met Aspose.Tasks voor .NET.
weight: 10
url: /nl/net/calendar-scheduling/working-with-calendar/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Werken met Agenda in Aspose.Tasks

## Invoering

Aspose.Tasks voor .NET biedt krachtige functies voor het werken met agenda's, waardoor ontwikkelaars projectplanningen en resourcetoewijzingen efficiënt kunnen beheren. In deze zelfstudie onderzoeken we hoe u Aspose.Tasks kunt gebruiken voor interactie met agenda's, waarbij essentiële handelingen worden behandeld, zoals het ophalen van agenda-informatie, het definiëren van werkweken, het berekenen van werkuren en meer.

## Vereisten

Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:

- Basiskennis van de programmeertaal C#.
-  Installatie van Aspose.Tasks voor .NET. Als het nog niet is geïnstalleerd, download het dan van[hier](https://releases.aspose.com/tasks/net/).
- Bekendheid met Visual Studio of een andere .NET-ontwikkelomgeving die de voorkeur heeft.

## Naamruimten importeren

Zorg ervoor dat u de benodigde naamruimten importeert voordat u begint met coderen:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Laten we nu elk voorbeeld opsplitsen in meerdere stappen in een stapsgewijze handleiding:

## Stap 1: Agenda-informatie ophalen

Volg deze stappen om kalenderinformatie uit een project op te halen:

```csharp
public static void RetrieveCalendarInfo()
{
    var project = new Project(DataDir + "RetrieveCalendarInfo.mpp");

    // Agenda-informatie ophalen
    foreach (var calendar in project.Calendars)
    {
        if (calendar.Name == null)
        {
            continue;
        }

        Console.WriteLine("Calendar UID: " + calendar.Uid);
        Console.WriteLine("Calendar Name: " + calendar.Name);
    }
}
```

Uitleg:
- Laad het projectbestand.
- Herhaal elke kalender in het project.
- Print UID en naam van elke kalender.

## Stap 2: Lees informatie over werkweken

Volg deze stappen om informatie over werkweken uit een kalender te lezen:

```csharp
public static void ReadWorkWeeksInformation()
{
    var project = new Project(DataDir + "WorkWithWorkWeekCollection.mpp");
    var calendar = project.Calendars.GetByUid(1);

    foreach (var workWeek in calendar.WorkWeeks)
    {
        var name = workWeek.Name;
        var fromDate = workWeek.FromDate;
        var toDate = workWeek.ToDate;
        Console.WriteLine("Name: " + name);
        Console.WriteLine("From Date: " + fromDate);
        Console.WriteLine("To Date: " + toDate);

        foreach (var day in workWeek.WeekDays)
        {
            foreach (var workingTime in day.WorkingTimes)
            {
                Console.WriteLine(workingTime.From);
                Console.WriteLine(workingTime.To);
            }
        }
    }
}
```

Uitleg:
- Laad het projectbestand.
- Download de kalender via UID.
- Herhaal elke werkweek in de kalender.
- Druk de naam, startdatum en einddatum van elke werkweek af.
- Doorloop werkdagen en werktijden binnen elke week.

## Stap 3: Lees Agenda-eigenschappen

Volg deze stappen om de eigenschappen van projectkalenders te lezen:

```csharp
public void ReadCalendarProps()
{
    var project = new Project(DataDir + "Project_GeneralCalendarProperties.xml");

    foreach (var calendar in project.Calendars)
    {
        if (calendar.Name == null)
        {
            continue;
        }

        Console.WriteLine("UID : " + calendar.Uid + " Name: " + calendar.Name);

        Console.Write("Base Calendar : ");
        Console.WriteLine(calendar.IsBaseCalendar ? "Self" : calendar.BaseCalendar.Name);

        foreach (var wd in calendar.WeekDays)
        {
            var ts = wd.GetWorkingTime();
            Console.WriteLine("Day Type: " + wd.DayType + " Hours: " + ts);
        }
    }
}
```

Uitleg:
- Laad het projectbestand.
- Herhaal elke kalender in het project.
- Print UID, naam en of het een basiskalender is.
- Werkuren afdrukken voor elk dagtype.

## Stap 4: Bereken werkuren

Volg deze stappen om de werkuren voor een taak te berekenen:

```csharp
public void CalculateWorkHours()
{
    var project = new Project(DataDir + "CalculateWorkHours.mpp");
    var task = project.RootTask.Children.GetById(1);
    var taskCalendar = task.Get(Tsk.Calendar);
    var startDate = task.Get(Tsk.Start);
    var endDate = task.Get(Tsk.Finish);
    var resource = project.Resources.GetByUid(1);
    var resourceCalendar = resource.Get(Rsc.Calendar);
    TimeSpan timeSpan;
    double durationInMins = 0;
    var tempDate = startDate;

    while (tempDate < endDate)
    {
        if (taskCalendar.IsDayWorking(tempDate) && resourceCalendar.IsDayWorking(tempDate))
        {
            timeSpan = taskCalendar.GetWorkingHours(tempDate);
            durationInMins += timeSpan.TotalMinutes;
        }

        tempDate = tempDate.AddDays(1);
    }

    Console.WriteLine("Duration in Minutes = " + durationInMins);
}
```

Uitleg:
- Laad het projectbestand.
- Ontvang taakdetails zoals kalender, startdatum en einddatum.
- Bereken de werkuren door elke dag te herhalen en te controleren of het een werkdag is.
- Tel de totale duur bij elkaar op in minuten.

## Stap 5: Definieer weekdagen voor Agenda

Volg deze stappen om weekdagen voor een kalender te definiëren:

```csharp
public void DefineWeekdaysForCalendar()
{
    var project = new Project();
    var calendar = project.Calendars.Add("Calendar1");

    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
    calendar.WeekDays.Add(new WeekDay(DayType.Saturday));
    calendar.WeekDays.Add(new WeekDay(DayType.Sunday));

    var weekDay = new WeekDay(DayType.Friday);
    var workingTime = new WorkingTime(9, 12);
    var workingTime2 = new WorkingTime(13, 16);
    weekDay.WorkingTimes.Add(workingTime);
    weekDay.WorkingTimes.Add(workingTime2);
    weekDay.DayWorking = true;
    calendar.WeekDays.Add(weekDay);
}
```

Uitleg:
- Maak een nieuw project en een kalender aan.
- Voeg standaardwerkdagen (maandag tot en met donderdag) en aangepaste werktijden voor vrijdag toe.
- Stel zaterdag en zondag in als niet-werkdagen.

## Stap 6: Schrijf bijgewerkte kalendergegevens naar MPP

Volg deze stappen om bijgewerkte agendagegevens naar een MPP-bestand te schrijven:

```csharp
public void WriteUpdatedCalendarDataToMpp()
{
    try
    {
        var project = new Project(DataDir + "project_update_test.mpp");
        var calendar = project.Calendars.GetByName("Standard");

        Calendar.MakeStandardCalendar(calendar);
        calendar.Name = "Test calendar";
        var exception = new CalendarException();
        exception.Name = "Exception 1";
        exception.FromDate = DateTime.Now;
        exception.ToDate = DateTime.Now.AddDays(2);
        exception.DayWorking = true;

        exception.WorkingTimes.Add(new WorkingTime(9, 13));
        exception.WorkingTimes.Add(new WorkingTime(14, 19));
        exception.WorkingTimes.Add(new WorkingTime(20, 21));
        calendar.Exceptions.Add(exception);

        var exception2 = new CalendarException();
        exception.Name = "Exception 2";
        exception2.FromDate = DateTime.Now.AddDays(7);
        exception2.ToDate = exception2.FromDate;
        exception2.DayWorking = false;
        calendar.Exceptions.Add(exception2);

        project.Set(Prj.Calendar, calendar);

        project.Save(OutDir + "WriteUpdatedCalendarDataToMPP_out.mpp", SaveFileFormat.Mpp);
    }
    catch (NotSupportedException ex)
    {
        Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase a full license or get a 30-day temporary license from [here](https://aankoop.aspose.com/temporary-license/).");
    }
}
```

Uitleg:
- Laad het projectbestand en haal de standaardkalender op.
- Wijzig kalendergegevens zoals uitzonderingen en werktijden.
- Sla het bijgewerkte project op met de gewijzigde kalendergegevens.

## Stap 7: Bereken de einddatum van de gesplitste taak

Volg deze stappen om de einddatum van een gesplitste taak te berekenen:

```csharp
public void CalculateSplitTaskFinishDate()
{
    var project = new Project(DataDir + "SplitTaskFinishDate.mpp");
    var task = project.RootTask.Children.GetByUid(4);
    var calendar = project.Get(Prj.Calendar);

    Console.WriteLine(
        "Start Date: " + task.Get(Tsk.Start).ToShortDateString() + "\n+ Duration 8 hours\nFinish Date: "
        + calendar.GetTaskFinishDateFromDuration(task, new TimeSpan(8, 0, 0)));
}
```

Uitleg:
- Laad het projectbestand en haal de gesplitste taak op.
- Download de projectkalender.
- Bereken de einddatum op basis van een aangepaste duur.

## Stap 8: Agenda-uitzonderingen ophalen

Volg deze stappen om informatie over agenda-uitzonderingen op te halen:

```csharp
public void RetrieveCalendarExceptions()
{
    var project = new Project(DataDir + "project_RetrieveExceptions_test.mpp");

    foreach (var calendar in project.Calendars)
    {
        foreach (var exception in calendar.Exceptions)
        {
            Console.WriteLine("From: " + exception.FromDate.ToShortDateString());
            Console.WriteLine("To: " + exception.ToDate.ToShortDateString());
        }
    }
}
```

Uitleg:
- Laad het projectbestand.
- Herhaal elke kalender en de uitzonderingen daarop.
- Druk de begin- en einddatum van elke uitzondering af.

## Stap 9: Haal de basisbronnenkalender op

Volg deze stappen om met de basiskalender van de agenda van een resource te werken:

```csharp
public void GetBaseResourceCalendar()
{
    var project = new Project(DataDir + "ResourceCalendar.mpp");
    var resource = project.Resources.Add("Resource1");
    var calendar = project.Calendars.Add("Resource1");
    resource.Set(Rsc.Calendar, calendar);

    foreach (var rsc in project.Resources)
    {
        if (rsc.Get(Rsc.Name) != null)
        {
            Console.WriteLine(rsc.Get(Rsc.Calendar).BaseCalendar.Name);
        }
    }
}
```

Uitleg:
- Laad het projectbestand.
- Voeg een resource en de bijbehorende agenda toe.
- Druk de basisagendanaam voor alle bronnen af.

## Stap 10: Agenda verwijderen

Volg deze stappen om een kalender uit een project te verwijderen:

```csharp
public void DeleteCalendar()
{
    var project = new Project(DataDir + "BrokenCalendar.mpp");
    var calendar = project.Calendars.GetByName("Broken Calendar");
    calendar.Delete();
}
```

Uitleg:
- Laad het projectbestand.
- Haal de kalender op naam.
- Verwijder de kalender.

## Stap 11: Verkrijg de einddatum bij start en werk

Volg deze stappen om een einddatum te berekenen op basis van startdatum en werk:

```csharp
public void GetFinishDateByStartAndWork()
{
    var project = new Project(DataDir + "Blank2010.mpp");
    var calendar = project.Calendars.GetByName("Standard");
    var start = new DateTime(2017, 10, 26, 8, 0, 0);
    var work = project.GetWork(7);
    var finish = calendar.GetFinishDateByStartAndWork(start, work);
    Console.WriteLine("Task start date: " + start);
    Console.WriteLine("Task work: " + work);
    Console.WriteLine("Task finish date: " + finish);
}
```

Uitleg:
- Laad het projectbestand.
- Download de standaardkalender.
- Definieer een startdatum en werkduur.
- Bereken de einddatum op basis van de startdatum en werkzaamheden.

## Stap 12: Begin met de volgende werkdag

Volg deze stappen om de volgende werkdag te beginnen met behulp van een kalender:

```csharp
public void GetNextWorking

DayStart()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var nextWorkingDayStart = calendar.GetNextWorkingDayStart(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(nextWorkingDayStart);
}
```

Uitleg:
- Laad het projectbestand.
- Download de kalender via UID.
- Ontvang de starttijd van de volgende werkdag.

## Stap 13: Haal het einde van de vorige werkdag op

Om de vorige werkdag te beëindigen met behulp van een kalender, volgt u deze stappen:

```csharp
public void GetPreviousWorkingDayEnd()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var previousWorkingDayEnd = calendar.GetPreviousWorkingDayEnd(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(previousWorkingDayEnd);
}
```

Uitleg:
- Laad het projectbestand.
- Download de kalender via UID.
- Haal de eindtijd van de vorige werkdag op.

## Stap 14: Krijg de startdatum vanaf het einde en de duur

Volg deze stappen om een startdatum op basis van einddatum en duur te krijgen:

```csharp
public void GetStartDateFromFinishAndDuration()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var startDate = calendar.GetStartDateFromFinishAndDuration(new DateTime(2020, 4, 10, 9, 0, 0), project.GetDuration(16, TimeUnitType.Hour));
    Console.WriteLine(startDate);
}
```

Uitleg:
- Laad het projectbestand.
- Download de kalender via UID.
- Bereken de startdatum vanaf de einddatum en de duur.

## Stap 15: Verkrijg werkuren

Volg deze stappen om de werkuren voor een specifieke datum op te halen:

```csharp
public void GetWorkingHours()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingHours = calendar.GetWorkingHours(new DateTime(2020, 4, 10));
    Console.WriteLine(workingHours.Hours);
}
```

Uitleg:
- Laad het projectbestand.
- Download de kalender via UID.
- Haal de werkuren op voor de opgegeven datum.

## Stap 16: Verkrijg werktijden

Volg deze stappen om de werktijden voor een specifieke datum te krijgen:

```csharp
public void GetWorkingTimes()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingTimes = calendar.GetWorkingTimes(new DateTime(2020, 4, 8, 8, 0, 0));

    foreach (var workingTime in workingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
}
```

Uitleg:
- Laad het projectbestand.
- Download de kalender via UID.
- Ontvang de werktijden voor de opgegeven datum.

## Conclusie

Werken met kalenders in Aspose.Tasks voor .NET is cruciaal voor het effectief beheren van projectplanningen. Met de meegeleverde voorbeelden en stapsgewijze handleidingen kunt u eenvoudig agendagegevens manipuleren, de duur van taken berekenen en uitzonderingen efficiënt afhandelen. Door deze functionaliteiten in uw applicaties te integreren, kunt u projectbeheerprocessen stroomlijnen en een nauwkeurige planning garanderen.

## Veelgestelde vragen

### V1: Heb ik een licentie nodig om Aspose.Tasks voor .NET te gebruiken?

 A1: Ja, u heeft een geldige licentie nodig om Aspose.Tasks voor .NET in uw toepassingen te gebruiken. U kunt een volledige licentie aanschaffen of een tijdelijke licentie van 30 dagen verkrijgen bij[hier](https://purchase.aspose.com/temporary-license/).

### Vraag 2: Kan ik agenda-uitzonderingen programmatisch wijzigen?

A2: Ja, u kunt agenda-uitzonderingen programmatisch toevoegen, bijwerken of verwijderen met Aspose.Tasks voor .NET API's.

### V3: Hoe kan ik de einddatums van taken met aangepaste duur berekenen?

 A3: Aspose.Tasks voor .NET biedt methoden zoals`GetTaskFinishDateFromDuration()` om de einddatums van taken te berekenen op basis van aangepaste duur.

### Vraag 4: Is het mogelijk om aangepaste kalenders te maken, zoals nachtploegkalenders?

A4: Ja, u kunt aangepaste kalenders maken, zoals nachtploegkalenders, met behulp van Aspose.Tasks voor .NET API's.

### V5: Kan ik informatie over agenda-uitzonderingen ophalen uit projectbestanden?

A5: Ja, u kunt eenvoudig informatie over agenda-uitzonderingen uit projectbestanden ophalen met Aspose.Tasks voor .NET.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
