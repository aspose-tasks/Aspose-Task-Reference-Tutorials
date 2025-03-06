---
title: Hantera Day Type Collection i Aspose.Tasks
linktitle: Hantera Day Type Collection i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du hanterar dagtypsamlingar effektivt i Aspose.Tasks för .NET. Skapa, ändra och manipulera kalenderundantag med lätthet.
type: docs
weight: 28
url: /sv/net/calendar-scheduling/day-type-collection/
---
## Introduktion

 Aspose.Tasks för .NET ger robust funktionalitet för att hantera dagtypsamlingar, avgörande för att definiera veckokalenderundantag i projektledningsapplikationer. I den här handledningen kommer vi att utforska hur man använder`DayTypeCollection` klass effektivt. 

## Förutsättningar

Innan vi fortsätter med handledningen, se till att du har följande förutsättningar:

1. Visual Studio: Se till att du har Visual Studio installerat på ditt system.
2.  Aspose.Tasks for .NET: Ladda ner och installera Aspose.Tasks for .NET-biblioteket från[här](https://releases.aspose.com/tasks/net/).
3. Grundläggande kunskaper i C#: Förtrogenhet med C#-programmeringsspråk och .NET framework-koncept.

## Importera namnområden

För att komma igång måste du importera de nödvändiga namnrymden till ditt C#-projekt:

```csharp
using Aspose.Tasks;
using System;


```

Låt oss nu dela upp exemplet i flera steg:

## Steg 1: Ladda projekt och få åtkomst till kalendern

```csharp
var project = new Project(DataDir + "WeeklyDayTypeException.mpp");
var calendar = project.Calendars.GetByUid(1);
```

Detta steg initierar en ny projektinstans och hämtar kalendern med dess UID.

## Steg 2: Iterera genom kalenderundantag

```csharp
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Exception Name: " + calendarException.Name);
    Console.WriteLine("Days of week count: " + calendarException.DaysOfWeek.Count);
    foreach (var dayType in calendarException.DaysOfWeek)
    {
        Console.WriteLine("Day type: " + dayType);
    }
    Console.WriteLine();
}
```

Här går vi igenom varje kalenderundantag och skriver ut dess namn och tillhörande dagtyper.

## Steg 3: Ändra kalenderundantag

```csharp
var exc1 = calendar.Exceptions.ToList()[0];
if (!exc1.DaysOfWeek.IsReadOnly && exc1.DaysOfWeek.IndexOf(DayType.Monday) < 0)
{
    exc1.DaysOfWeek.Insert(0, DayType.Wednesday);
}

var exc2 = calendar.Exceptions.ToList()[1];
if (exc2.DaysOfWeek.Contains(DayType.Sunday))
{
    exc2.DaysOfWeek.Remove(DayType.Sunday);
}

Console.WriteLine("Remove " + exc2.DaysOfWeek[0] + " day type from exception by index...");
exc2.DaysOfWeek.RemoveAt(0);
```

Det här steget visar hur du ändrar kalenderundantag genom att lägga till, ta bort eller uppdatera dagtyper.

## Steg 4: Skapa och manipulera nya kalenderundantag

```csharp
var exc4 = new CalendarException
{
    Name = "Weekly Exception 2",
    FromDate = new DateTime(2020, 4, 13),
    ToDate = new DateTime(2020, 4, 18),
    Occurrences = 3,
    Type = CalendarExceptionType.Weekly
};
exc4.DaysOfWeek.Add(DayType.Monday);
exc4.DaysOfWeek.Add(DayType.Thursday);

calendar.Exceptions.Add(exc4);

var exc3 = calendar.Exceptions.ToList()[2];

exc3.DaysOfWeek.Clear();

var dayTypes = new DayType[exc4.DaysOfWeek.Count];
exc4.DaysOfWeek.CopyTo(dayTypes, 0);

foreach (var dayType in dayTypes)
{
    exc3.DaysOfWeek.Add(dayType);
}

Console.WriteLine("Days of week for exception: " + exc3.Name);
foreach (var dayType in exc3.DaysOfWeek)
{
    Console.WriteLine("Day type: " + dayType);
}
```

I det här sista steget skapar vi nya kalenderundantag och manipulerar dem genom att lägga till och kopiera dagtyper.

## Slutsats

 Sammanfattningsvis är det viktigt att hantera dagtypsamlingar i Aspose.Tasks för .NET för att definiera och ändra veckokalenderundantag i projektledningsapplikationer. Genom att följa den steg-för-steg-guide som finns i denna handledning kan du effektivt använda`DayTypeCollection` klass för att hantera olika kalenderoperationer.

## FAQ's

### F1: Kan Aspose.Tasks för .NET användas för att skapa Gantt-diagram programmatiskt?

S1: Ja, Aspose.Tasks för .NET tillhandahåller API:er för att skapa och manipulera Gantt-diagram i .NET-applikationer.

### F2: Är Aspose.Tasks för .NET kompatibelt med både .NET Core och .NET Framework?

S2: Ja, Aspose.Tasks för .NET stöder både .NET Core och .NET Framework.

### F3: Hur kan jag få support för Aspose.Tasks för .NET?

 S3: Du kan få support genom att besöka[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) där du kan ställa frågor och interagera med andra användare.

### F4: Erbjuder Aspose.Tasks för .NET en gratis provperiod?

 S4: Ja, du kan få en gratis provversion av Aspose.Tasks för .NET från[här](https://releases.aspose.com/).

### F5: Kan jag köpa en tillfällig licens för Aspose.Tasks för .NET?

 S5: Ja, tillfälliga licenser finns att köpa från[Aspose hemsida](https://purchase.aspose.com/temporary-license/).