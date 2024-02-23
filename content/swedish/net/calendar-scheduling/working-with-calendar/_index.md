---
title: Arbeta med Kalender i Aspose.Tasks
linktitle: Arbeta med Kalender i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Hantera projektkalendrar, beräkna varaktigheter, hantera undantag med lätthet med Aspose.Tasks för .NET.
type: docs
weight: 10
url: /sv/net/calendar-scheduling/working-with-calendar/
---
## Introduktion

Aspose.Tasks för .NET tillhandahåller kraftfulla funktioner för att arbeta med kalendrar, vilket gör det möjligt för utvecklare att effektivt hantera projektscheman och resursallokeringar. I den här handledningen kommer vi att utforska hur man använder Aspose.Tasks för att interagera med kalendrar, och täcker viktiga funktioner som att hämta kalenderinformation, definiera arbetsveckor, beräkna arbetstimmar och mer.

## Förutsättningar

Innan vi börjar, se till att du har ställt in följande förutsättningar:

- Grundläggande förståelse för programmeringsspråket C#.
-  Installation av Aspose.Tasks för .NET. Om den inte är installerad, ladda ner den från[här](https://releases.aspose.com/tasks/net/).
- Kännedom om Visual Studio eller någon annan föredragen .NET-utvecklingsmiljö.

## Importera namnområden

Innan du börjar koda, se till att importera de nödvändiga namnrymden:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Låt oss nu dela upp varje exempel i flera steg i ett steg-för-steg-guideformat:

## Steg 1: Hämta kalenderinformation

Följ dessa steg för att hämta kalenderinformation från ett projekt:

```csharp
public static void RetrieveCalendarInfo()
{
    var project = new Project(DataDir + "RetrieveCalendarInfo.mpp");

    // Hämta kalendrarinformation
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

Förklaring:
- Ladda projektfilen.
- Iterera igenom varje kalender i projektet.
- Skriv ut UID och namn på varje kalender.

## Steg 2: Läs information om arbetsveckor

Följ dessa steg för att läsa arbetsveckorsinformation från en kalender:

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

Förklaring:
- Ladda projektfilen.
- Hämta kalendern med UID.
- Iterera igenom varje arbetsvecka i kalendern.
- Skriv ut namn, startdatum och slutdatum för varje arbetsvecka.
- Gå igenom arbetsdagar och arbetstider inom varje vecka.

## Steg 3: Läs kalenderegenskaper

För att läsa egenskaperna för projektkalendrar, följ dessa steg:

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

Förklaring:
- Ladda projektfilen.
- Iterera igenom varje kalender i projektet.
- Skriv ut UID, namn och om det är en baskalender.
- Skriv ut arbetstider för varje dagtyp.

## Steg 4: Beräkna arbetstimmar

Följ dessa steg för att beräkna arbetstimmar för en uppgift:

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

Förklaring:
- Ladda projektfilen.
- Få uppgiftsinformation som kalender, startdatum och slutdatum.
- Beräkna arbetstimmar genom att iterera igenom varje dag och kontrollera om det är en arbetsdag.
- Summera den totala varaktigheten i minuter.

## Steg 5: Definiera veckodagar för kalender

För att definiera veckodagar för en kalender, följ dessa steg:

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

Förklaring:
- Skapa ett nytt projekt och kalender.
- Lägg till standardarbetsdagar (måndag till torsdag) och anpassade arbetstider för fredag.
- Ange lördag och söndag som arbetsfria dagar.

## Steg 6: Skriv uppdaterad kalenderdata till MPP

För att skriva uppdaterad kalenderdata till en MPP-fil, följ dessa steg:

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
        Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase a full license or get a 30-day temporary license from [here](https://purchase.aspose.com/temporary-license/.");
    }
}
```

Förklaring:
- Ladda projektfilen och hämta standardkalendern.
- Ändra kalenderdata som undantag och arbetstider.
- Spara det uppdaterade projektet med den ändrade kalenderdatan.

## Steg 7: Beräkna slutdatum för delad uppgift

Följ dessa steg för att beräkna slutdatumet för en delad uppgift:

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

Förklaring:
- Ladda projektfilen och hämta den delade uppgiften.
- Hämta projektkalendern.
- Beräkna slutdatumet baserat på en anpassad varaktighet.

## Steg 8: Hämta kalenderundantag

Följ dessa steg för att hämta information om kalenderundantag:

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

Förklaring:
- Ladda projektfilen.
- Iterera igenom varje kalender och dess undantag.
- Skriv ut start- och slutdatum för varje undantag.

## Steg 9: Skaffa Base Resource Calendar

För att arbeta med baskalendern för en resurs kalender, följ dessa steg:

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

Förklaring:
- Ladda projektfilen.
- Lägg till en resurs och dess kalender.
- Skriv ut baskalendernamnet för alla resurser.

## Steg 10: Ta bort kalender

För att ta bort en kalender från ett projekt, följ dessa steg:

```csharp
public void DeleteCalendar()
{
    var project = new Project(DataDir + "BrokenCalendar.mpp");
    var calendar = project.Calendars.GetByName("Broken Calendar");
    calendar.Delete();
}
```

Förklaring:
- Ladda projektfilen.
- Få kalendern efter namn.
- Ta bort kalendern.

## Steg 11: Få slutdatum efter start och arbete

För att beräkna ett slutdatum efter startdatum och arbete, följ dessa steg:

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

Förklaring:
- Ladda projektfilen.
- Skaffa standardkalendern.
- Definiera ett startdatum och arbetslängd.
- Beräkna slutdatumet baserat på startdatum och arbete.

## Steg 12: Starta nästa arbetsdag

Följ dessa steg för att få igång nästa arbetsdag med hjälp av en kalender:

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

Förklaring:
- Ladda projektfilen.
- Hämta kalendern med UID.
- Få nästa arbetsdag starttid.

## Steg 13: Hämta föregående arbetsdagsslut

För att få föregående arbetsdagsslut genom att använda en kalender, följ dessa steg:

```csharp
public void GetPreviousWorkingDayEnd()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var previousWorkingDayEnd = calendar.GetPreviousWorkingDayEnd(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(previousWorkingDayEnd);
}
```

Förklaring:
- Ladda projektfilen.
- Hämta kalendern med UID.
- Hämta föregående arbetsdags sluttid.

## Steg 14: Få startdatum från mål och varaktighet

Följ dessa steg för att få ett startdatum efter slutdatum och varaktighet:

```csharp
public void GetStartDateFromFinishAndDuration()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var startDate = calendar.GetStartDateFromFinishAndDuration(new DateTime(2020, 4, 10, 9, 0, 0), project.GetDuration(16, TimeUnitType.Hour));
    Console.WriteLine(startDate);
}
```

Förklaring:
- Ladda projektfilen.
- Hämta kalendern med UID.
- Beräkna startdatumet från slutdatumet och varaktigheten.

## Steg 15: Få arbetstider

Följ dessa steg för att få arbetstider för ett specifikt datum:

```csharp
public void GetWorkingHours()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingHours = calendar.GetWorkingHours(new DateTime(2020, 4, 10));
    Console.WriteLine(workingHours.Hours);
}
```

Förklaring:
- Ladda projektfilen.
- Hämta kalendern med UID.
- Få arbetstiderna för det angivna datumet.

## Steg 16: Få arbetstider

Följ dessa steg för att få arbetstider för ett specifikt datum:

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

Förklaring:
- Ladda projektfilen.
- Hämta kalendern med UID.
- Få arbetstiderna för det angivna datumet.

## Slutsats

Att arbeta med kalendrar i Aspose.Tasks för .NET är avgörande för att hantera projektscheman effektivt. Med de medföljande exemplen och steg-för-steg-guiderna kan du enkelt manipulera kalenderdata, beräkna uppgiftens varaktighet och hantera undantag effektivt. Genom att integrera dessa funktioner i dina applikationer kan du effektivisera projektledningsprocesser och säkerställa korrekt schemaläggning.

## FAQ's

### F1: Behöver jag en licens för att använda Aspose.Tasks för .NET?

 S1: Ja, du behöver en giltig licens för att använda Aspose.Tasks för .NET i dina applikationer. Du kan köpa en fullständig licens eller få en 30-dagars tillfällig licens från[här](https://purchase.aspose.com/temporary-license/).

### F2: Kan jag ändra kalenderundantag programmatiskt?

S2: Ja, du kan programmässigt lägga till, uppdatera eller ta bort kalenderundantag med Aspose.Tasks för .NET API:er.

### F3: Hur kan jag beräkna uppgiftens slutdatum med anpassad varaktighet?

 S3: Aspose.Tasks för .NET tillhandahåller metoder som`GetTaskFinishDateFromDuration()` för att beräkna uppgiftens slutdatum baserat på anpassade varaktigheter.

### F4: Är det möjligt att skapa anpassade kalendrar, till exempel nattskiftskalendrar?

S4: Ja, du kan skapa anpassade kalendrar som nattskiftskalendrar med Aspose.Tasks för .NET API:er.

### F5: Kan jag hämta information om kalenderundantag från projektfiler?

S5: Ja, du kan enkelt hämta information om kalenderundantag från projektfiler med Aspose.Tasks för .NET.