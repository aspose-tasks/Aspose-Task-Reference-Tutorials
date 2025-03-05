---
title: Hantera månatliga återkommande mönster i Aspose.Tasks
linktitle: Hantera månatliga återkommande mönster i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du hanterar månatliga återkommande mönster i Aspose.Tasks för .NET med denna steg-för-steg handledning.
type: docs
weight: 18
url: /sv/net/advanced-concepts/monthly-recurrence-patterns/
---
## Introduktion

Aspose.Tasks för .NET är ett kraftfullt API som tillåter utvecklare att manipulera Microsoft Project-filer programmatiskt. En av de väsentliga funktionerna som den erbjuder är förmågan att hantera återkommande uppgifter effektivt. I den här handledningen kommer vi att fördjupa oss i hur man arbetar med månatliga återkommande mönster med hjälp av Aspose.Tasks, steg för steg.

## Förutsättningar

Innan vi börjar, se till att du har följande förutsättningar installerade:

## Importera namnområden

Se först till att du har importerat de nödvändiga namnrymden i ditt .NET-projekt:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

Låt oss nu dela upp processen för att hantera månatliga återkommande mönster i flera steg:

## Steg 1: Initiera projektet

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Steg 2: Ställ in parametrar för återkommande uppgifter

Definiera parametrarna för den återkommande uppgiften, inklusive uppgiftens namn, varaktighet och återkommande mönster:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthDayRepetition { DayPosition = 1, RepetitionInterval = 2 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 30, 17, 0, 0)
        }
    }
};
```

## Steg 3: Lägg till parametrar till projektet

```csharp
project.RootTask.Children.Add(parameters);
```

## Steg 4: Spara projektet

Spara det ändrade projektet med den återkommande uppgiften:

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

## Slutsats

Att hantera månatliga återkommande mönster i Aspose.Tasks för .NET är enkelt och effektivt. Genom att följa stegen som beskrivs i den här handledningen kan du enkelt skapa återkommande uppgifter med specifika månatliga intervall och upprepningsintervall.

## FAQ's

### F1: Är Aspose.Tasks kompatibel med alla versioner av Microsoft Project-filer?

S1: Aspose.Tasks stöder olika versioner av Microsoft Project-filer, inklusive MPP, MPT, XML och MPX.

### F2: Kan jag anpassa upprepningsmönstret ytterligare?

S2: Ja, Aspose.Tasks erbjuder omfattande alternativ för att anpassa återkommande mönster, inklusive dagliga, veckovisa, månatliga och årliga.

### F3: Finns det en gratis testversion tillgänglig för Aspose.Tasks?

 S3: Ja, du kan få en gratis testversion av Aspose.Tasks från webbplatsen[här](https://releases.aspose.com/).

### F4: Hur kan jag få support för Aspose.Tasks?

 S4: Du kan söka hjälp och delta i diskussioner om[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### F5: Var kan jag köpa en licens för Aspose.Tasks?

 S5: Du kan köpa en licens för Aspose.Tasks från webbplatsen[här](https://purchase.aspose.com/buy)