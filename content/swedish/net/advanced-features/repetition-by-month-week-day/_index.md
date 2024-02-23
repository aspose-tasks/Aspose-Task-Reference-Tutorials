---
title: Upprepning efter månad Veckodag i Aspose.Tasks
linktitle: Upprepning efter månad Veckodag i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du ställer in repetitioner efter månad, vecka och dag i Aspose.Tasks för .NET för att effektivt automatisera återkommande uppgifter.
type: docs
weight: 26
url: /sv/net/advanced-features/repetition-by-month-week-day/
---
## Introduktion

Inom området för mjukvaruutveckling, särskilt i projektledningsapplikationer, är förmågan att hantera återkommande uppgifter effektivt av största vikt. Aspose.Tasks för .NET är ett kraftfullt bibliotek designat för att effektivisera skapandet och hanteringen av projektuppgifter, inklusive återkommande. En sådan funktion som tillhandahålls av Aspose.Tasks är möjligheten att ställa in repetitioner per månad, vecka och dag, vilket säkerställer att uppgifterna utförs enligt schemat utan manuella ingrepp.

## Förutsättningar

Innan du dyker in i krångligheterna med att ställa in repetitioner per månad, vecka och dag med Aspose.Tasks för .NET, se till att du har följande förutsättningar:

1. Grundläggande förståelse för C#: Bekantskap med programmeringsspråket C# är avgörande för att förstå och implementera kodexemplen som tillhandahålls.
   
2.  Installation av Aspose.Tasks för .NET: Se till att du har laddat ner och installerat Aspose.Tasks for .NET-biblioteket. Du kan hämta biblioteket från[nedladdningssida](https://releases.aspose.com/tasks/net/).

3. Tillgång till en .mpp-projektfil: Ha en Microsoft Project-fil (.mpp) redo, eftersom vi kommer att använda den för att demonstrera implementeringen av repetitioner per månad, vecka och dag.

## Importera namnområden

För att komma igång med att använda Aspose.Tasks för .NET i din C#-applikation måste du importera de nödvändiga namnrymden. Så här kan du göra det:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Låt oss dela upp det medföljande kodavsnittet i flera steg för att förstå varje del grundligt.

## Steg 1: Ladda projektfilen

```csharp
// Sökvägen till dokumentkatalogen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 Detta steg innebär att skapa en ny instans av`Project` klass och laddar en befintlig Microsoft Project-fil (`Project1.mpp`) från den angivna katalogen.

## Steg 2: Definiera parametrar för återkommande uppgift

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthWeekDayRepetition
        {
            Position = OrdinalNumber.First,
            WeekDay = DayOfWeek.Sunday,
            RepetitionInterval = 2
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 2, 17, 0, 0)
        }
    }
};
```

det här steget definierar vi parametrarna för en återkommande uppgift. Vi anger uppgiftens namn, varaktighet, repetitionsmönster (månadsvis) och upprepningsintervall (slutar vid ett specifikt datum).

## Steg 3: Lägg till återkommande uppgift till projektet

```csharp
project.RootTask.Children.Add(parameters);
```

Här lägger vi till de definierade parametrarna för återkommande uppgift till projektets rotuppgift.

## Steg 4: Spara projektfil

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Slutligen sparar vi den modifierade projektfilen med den tillagda återkommande uppgiften.

## Slutsats

Sammanfattningsvis, att ställa in repetitioner per månad, vecka och dag i Aspose.Tasks för .NET är en enkel process som ger utvecklare möjlighet att automatisera hanteringen av återkommande uppgifter inom sina projekt på ett effektivt sätt. Genom att följa stegen som beskrivs i denna handledning kan du sömlöst integrera den här funktionen i dina C#-applikationer, vilket sparar tid och ansträngning i projektledning.

## FAQ's

###F1: Kan jag anpassa återfallsmönstret utöver de angivna exemplen?

S1: Ja, Aspose.Tasks för .NET erbjuder omfattande anpassningsalternativ för återkommande mönster, så att du kan skräddarsy dem efter dina specifika krav.

###F2: Finns det en testversion tillgänglig för Aspose.Tasks för .NET?

 S2: Ja, du kan få en gratis provversion av Aspose.Tasks för .NET från[släpper sida](https://releases.aspose.com/).

###F3: Hur kan jag få support för Aspose.Tasks för .NET?

 S3: Du kan söka hjälp och engagera dig i samhället på[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

###F4: Finns tillfälliga licenser tillgängliga för Aspose.Tasks för .NET?

 A4: Ja, du kan skaffa tillfälliga licenser från[köpsidan](https://purchase.aspose.com/temporary-license/) för test- och utvärderingsändamål.

###F5: Var kan jag hitta omfattande dokumentation för Aspose.Tasks för .NET?

 A5: Du kan hänvisa till detaljerna[dokumentation](https://reference.aspose.com/tasks/net/) tillgänglig på Asposes webbplats för djupgående vägledning om hur du använder biblioteket.