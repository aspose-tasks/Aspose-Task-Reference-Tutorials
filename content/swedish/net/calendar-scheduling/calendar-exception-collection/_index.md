---
title: Samling av kalenderundantag i Aspose.Tasks
linktitle: Samling av kalenderundantag i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du effektivt hanterar kalenderundantag i dina .NET-projekt med Aspose.Tasks, vilket säkerställer korrekt schemaläggning och resurshantering.
type: docs
weight: 13
url: /sv/net/calendar-scheduling/calendar-exception-collection/
---
## Introduktion

Inom projektledning är exakt schemaläggning avgörande för framgång. Men verkliga scenarier kräver ofta avvikelser från standardscheman på grund av helgdagar, speciella händelser eller andra faktorer. Aspose.Tasks för .NET tillhandahåller en robust lösning för att hantera sådana undantag genom dess Calendar Exception Collection-funktion. Denna handledning guidar dig genom processen att använda den här funktionen steg för steg.

## Förutsättningar

Innan du dyker in i handledningen, se till att du har följande förutsättningar:

1.  Aspose.Tasks för .NET: Se till att du har biblioteket installerat. Du kan ladda ner den[här](https://releases.aspose.com/tasks/net/).
2. Grundläggande kunskaper i C#: Förtrogenhet med programmeringsspråket C# kommer att vara till hjälp för att förstå exemplen.
3. Utvecklingsmiljö: Konfigurera din föredragna utvecklingsmiljö, som Visual Studio eller JetBrains Rider.

## Importera namnområden

Innan du börjar arbeta med Aspose.Tasks för .NET måste du importera de nödvändiga namnrymden till ditt projekt. Detta steg ger dig tillgång till de klasser och metoder som krävs för att hantera kalenderundantag.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

Låt oss nu dela upp exemplet i flera steg:

## Steg 1: Ladda projekt och hämta kalender

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

I det här steget laddar vi en projektfil och hämtar den önskade kalendern med dess UID.

## Steg 2: Rensa befintliga undantag och ställ in standardkalender

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

Detta steg rensar alla befintliga undantag från kalendern och ställer in den på en standardkonfiguration.

## Steg 3: Definiera och lägg till undantag för arbetstid

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

Det här steget definierar ett arbetstidsundantag med specifika start- och slutdatum, tillsammans med arbetstider inom dessa datum, och lägger till det i kalendern.

## Steg 4: Definiera och lägg till undantag för icke-arbetstid

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// Lägg till fler undantag om det behövs

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

Det här steget definierar undantag för icke-arbetstid, till exempel helgdagar, och lägger till dem i kalendern.

## Steg 5: Visa kalenderundantag

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

Detta steg visar de tillagda kalenderundantagen tillsammans med deras detaljer.

## Steg 6: Ta bort alla undantag

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

Slutligen tar detta steg bort alla undantag från kalendern.

## Slutsats

Att hantera kalenderundantag är avgörande för korrekt projektschemaläggning. Aspose.Tasks för .NET förenklar denna uppgift genom att tillhandahålla en omfattande uppsättning funktioner, inklusive Calendar Exception Collection. Genom att följa stegen som beskrivs i denna handledning kan du effektivt hantera olika schemaläggningsscenarier inom dina projekt.

## FAQ's

### F1: Kan jag lägga till flera undantag i en enda kalender?

 S1: Ja, du kan lägga till flera undantag i en kalender med hjälp av`AddRange` metod.

### F2: Hur hanterar jag återkommande undantag, såsom helgdagar?

S2: Du kan programmatiskt beräkna återkommande undantag och lägga till dem i kalendern med hjälp av anpassad logik.

### F3: Är det möjligt att importera kalenderundantag från externa källor?

S3: Ja, du kan läsa kalenderundantag från externa källor som databaser eller CSV-filer och integrera dem i ditt projekt.

### F4: Vad händer om det finns överlappande undantag i kalendern?

S4: Aspose.Tasks för .NET låter dig hantera överlappande undantag genom att definiera prioriteringar eller lösa konflikter baserat på dina projektkrav.

### F5: Kan jag anpassa arbetstiderna för varje dag inom ett undantag?

S5: Ja, du kan ange anpassade arbetstider för enskilda dagar inom ett undantag för att tillgodose specifika schemaläggningsbehov.