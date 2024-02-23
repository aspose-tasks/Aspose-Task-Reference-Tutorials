---
title: Upprepning efter månad Dag i Aspose.Tasks
linktitle: Upprepning efter månad Dag i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du hanterar återkommande uppgifter i .NET-projekt med Aspose.Tasks. Steg-för-steg-guide för hantering av repetitioner per månad och dag.
type: docs
weight: 25
url: /sv/net/advanced-features/repetition-by-month-day/
---
## Introduktion

Inom området .NET-utveckling står Aspose.Tasks som ett kraftfullt verktyg för att hantera projektuppgifter och scheman. Det erbjuder en uppsjö av funktioner för att effektivisera arbetsflöden för projektledning, inklusive hantering av återkommande uppgifter. Upprepning per månad och dag är ett vanligt krav i projektschemaläggning, och Aspose.Tasks ger robust stöd för detta scenario.

## Förutsättningar

Innan du dyker in i handledningen, se till att du har följande förutsättningar:

1. Grundläggande förståelse för C#: Bekantskap med programmeringsspråket C# är nödvändigt för att förstå de begrepp som diskuteras i denna handledning.
2. Installation av Aspose.Tasks för .NET: Se till att du har installerat Aspose.Tasks för .NET. Du kan ladda ner den från[här](https://releases.aspose.com/tasks/net/).
3. Integrated Development Environment (IDE): Ha en IDE som Visual Studio installerad på ditt system för kodningsbekvämlighet.

## Importera namnområden

ditt C#-projekt, importera de nödvändiga namnrymden för att komma åt Aspose.Tasks-funktioner:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Låt oss dela upp det medföljande kodexemplet i steg-för-steg guideformat:

## Steg 1: Ladda projektfilen

```csharp
// Sökvägen till dokumentkatalogen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 Denna kodrad initierar en ny instans av`Project` klass, laddar projektfilen med namnet "Project1.mpp".

## Steg 2: Definiera parametrar för återkommande uppgift

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

Det här avsnittet definierar parametrarna för den återkommande uppgiften, inklusive dess namn, varaktighet, upprepningsmönster och upprepningsintervall.

## Steg 3: Lägg till uppgift i projektet

```csharp
project.RootTask.Children.Add(parameters);
```

Här lägger vi till de återkommande uppgiftsparametrarna till projektet.

## Steg 4: Spara projektfil

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Slutligen sparas det modifierade projektet med den tillagda återkommande uppgiften.

## Slutsats

den här handledningen har vi utforskat hur man hanterar upprepning per månad och dag i Aspose.Tasks för .NET. Genom att följa de angivna stegen kan du effektivt hantera återkommande uppgifter inom dina projektscheman.

## FAQ's

### F1: Är Aspose.Tasks kompatibel med alla versioner av .NET?

S1: Aspose.Tasks stöder olika versioner av .NET-ramverket, vilket säkerställer kompatibilitet mellan olika miljöer.

### F2: Kan jag anpassa upprepningsmönstret ytterligare?

S2: Ja, Aspose.Tasks erbjuder omfattande anpassningsalternativ för att definiera återkommande mönster enligt specifika projektkrav.

### F3: Ger Aspose.Tasks stöd för andra projektledningsfunktioner?

S3: Absolut, Aspose.Tasks erbjuder ett brett utbud av funktioner för projektledning, inklusive uppgiftsspårning, resursallokering och generering av Gantt-diagram.

### F4: Finns det en testversion för Aspose.Tasks?

 A4: Ja, du kan utnyttja en gratis provperiod från[här](https://releases.aspose.com/) att utforska Aspose.Tasks möjligheter innan du fattar ett köpbeslut.

### F5: Var kan jag söka hjälp om jag stöter på problem eller har frågor?

 A5: Du kan besöka[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) att söka stöd från samhället eller Aspose-teamet.