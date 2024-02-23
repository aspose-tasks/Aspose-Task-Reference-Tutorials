---
title: Daglig kalenderupprepning i Aspose.Tasks
linktitle: Daglig kalenderupprepning i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du skapar återkommande uppgifter med dagliga kalenderupprepningar i Aspose.Tasks för .NET. Förbättra projektledningseffektiviteten utan ansträngning.
type: docs
weight: 25
url: /sv/net/calendar-scheduling/daily-calendar-repetition/
---
## Introduktion

 Aspose.Tasks för .NET tillhandahåller en kraftfull uppsättning verktyg för att hantera uppgifter och projekt programmatiskt. En av dess anmärkningsvärda funktioner är förmågan att hantera dagliga kalenderrepetitioner effektivt. I den här handledningen kommer vi att utforska hur man använder`DailyCalendarRepetition` klass tillsammans med andra relevanta klasser för att skapa återkommande uppgifter med dagliga repetitioner baserat på en specificerad kalender.

## Förutsättningar

Innan vi börjar, se till att du har följande inställning:

1.  Installation: Se till att du har Aspose.Tasks för .NET installerat. Om inte kan du ladda ner den från[här](https://releases.aspose.com/tasks/net/).

2. Namnutrymmesimport: Importera de nödvändiga namnområdena till ditt projekt:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

using Aspose.Tasks.Saving;

```

## Steg 1: Initiera projektet

Först måste vi ladda ett befintligt projekt eller skapa ett nytt att arbeta med:

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Steg 2: Definiera kalendern

Därefter skapar vi en kalender med en 24-timmarslängd och associerar den med projektet:

```csharp
var calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(calendar);
```

## Steg 3: Ställ in parametrar för återkommande uppgifter

Låt oss nu ställa in parametrarna för vår återkommande uppgift. Vi definierar dess namn, varaktighet, återkommande mönster och intervall:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new DailyRecurrencePattern
    {
        Repetition = new DailyCalendarRepetition { RepetitionInterval = 1 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 2, 0, 0, 0),
            Finish = new DateTime(2018, 7, 8, 16, 0, 0)
        }
    }
};
```

## Steg 4: Ställ in kalender för uppgift

Koppla den definierade kalendern till uppgiften:

```csharp
parameters.SetCalendar(project, "24 Hours");
```

## Steg 5: Lägg till uppgift i projektet

Lägg till uppgiften med definierade parametrar till projektet:

```csharp
project.RootTask.Children.Add(parameters);
```

## Steg 6: Spara projektet

Slutligen, spara projektet med den tillagda återkommande uppgiften:

```csharp
project.Save(OutDir + "CanAddRecurringTask_Days_CalendarDays_24h_Test_out.mpp", SaveFileFormat.Mpp);
```

Nu har du framgångsrikt skapat ett projekt med en återkommande uppgift som ska upprepas dagligen baserat på en 24-timmarskalender med Aspose.Tasks för .NET!

## Slutsats

den här handledningen har vi visat hur man använder Aspose.Tasks för .NET för att hantera dagliga kalenderupprepningar effektivt. Genom att följa dessa steg kan du sömlöst integrera återkommande uppgifter i dina projekt, vilket förbättrar produktiviteten och organisationen.

## FAQ's

### F1: Kan jag anpassa varaktigheten för varje repetition?

S1: Ja, du kan justera varaktigheten för varje repetition enligt dina krav genom att ändra parametrarna i koden.

### F2: Är det möjligt att ställa in olika kalendrar för olika uppgifter inom samma projekt?

S2: Absolut, Aspose.Tasks låter dig tilldela specifika kalendrar till individuella uppgifter, vilket ger flexibilitet i schemaläggning.

### F3: Stöder Aspose.Tasks andra återkommande mönster förutom dagliga?

S3: Ja, Aspose.Tasks tillhandahåller ett brett utbud av återkommande mönster som veckovis, månadsvis, årligen etc., för att tillgodose olika projektbehov.

### F4: Kan jag visualisera de återkommande uppgifterna som skapats med Aspose.Tasks?

S4: Visst, Aspose.Tasks erbjuder visualiseringsalternativ som hjälper dig att analysera och spåra återkommande uppgifter effektivt.

### F5: Finns det en testversion tillgänglig för Aspose.Tasks?

 S5: Ja, du kan använda en gratis provversion av Aspose.Tasks från[här](https://releases.aspose.com/) att utforska dess funktioner innan du gör ett köp.