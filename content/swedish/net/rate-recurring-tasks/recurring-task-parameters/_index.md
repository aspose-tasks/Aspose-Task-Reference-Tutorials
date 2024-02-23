---
title: Ställa in parametrar för återkommande uppgifter i Aspose.Tasks
linktitle: Ställa in parametrar för återkommande uppgifter i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du ställer in parametrar för återkommande uppgift i Microsoft Project med Aspose.Tasks för .NET. Omfattande handledning med steg-för-steg-guide.
type: docs
weight: 14
url: /sv/net/rate-recurring-tasks/recurring-task-parameters/
---
## Introduktion
I den här handledningen guidar vi dig genom processen att ställa in parametrar för återkommande uppgifter i Microsoft Project med Aspose.Tasks för .NET.
## Förutsättningar
Innan du börjar, se till att du har följande:
1. Grundläggande förståelse för programmeringsspråket C#.
2. Installerad Visual Studio eller någon annan C# IDE.
3. Aspose.Tasks för .NET-biblioteket installerat och refererat till i ditt projekt.

## Importera namnområden
Först måste du importera de nödvändiga namnrymden i din C#-kod:
```csharp
using Aspose.Tasks;
using System;

```
## Steg 1: Definiera dokumentkatalogen
```csharp
String DataDir = "Your Document Directory";
```
 byta ut`"Your Document Directory"` med sökvägen till din dokumentkatalog.
## Steg 2: Ladda projektfilen
```csharp
var project = new Project(DataDir + "Blank2010.mpp");
```
 Denna kodrad laddar Microsoft Project-filen i`project` variabler.
## Steg 3: Definiera parametrar för återkommande uppgift
```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "Recurring task",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new WeeklyRecurrencePattern
    {
        Repetition = new WeeklyRepetition
        {
            RepetitionInterval = 2,
            WeekDays = WeekdayType.Sunday | WeekdayType.Monday | WeekdayType.Friday
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 7, 20, 17, 0, 0)
        }
    },
    IgnoreResourceCalendar = false
};
```
Här definierar du parametrarna för den återkommande uppgiften som uppgiftens namn, varaktighet, upprepningsmönster, upprepningsintervall och om resurskalendern ska ignoreras.
## Steg 4: Ställ in kalender för återkommande uppgift
```csharp
parameters.SetCalendar(project, "Standard");
```
Detta steg ställer in kalendern för den återkommande uppgiften. I det här exemplet ställer den in kalendern till "Standard".
## Steg 5: Lägg till parametrar i projektet
```csharp
project.RootTask.Children.Add(parameters);
```
Lägg slutligen till parametrarna i projektets rotuppgift.

## Slutsats
I den här handledningen har vi visat hur du ställer in parametrar för återkommande uppgifter i Microsoft Project med Aspose.Tasks för .NET. Genom att följa dessa steg kan du effektivt hantera återkommande uppgifter i dina projekt.
## Vanliga frågor
### Kan jag anpassa återfallsmönstret ytterligare?
Ja, Aspose.Tasks tillhandahåller olika återkommande mönster och alternativ för att anpassa efter dina projektkrav.
### Finns det en testversion innan köp?
 Ja, du kan ladda ner en gratis testversion från Aspose.Tasks[hemsida](https://purchase.aspose.com/buy) för att utvärdera bibliotekets funktioner.
### Stöder Aspose.Tasks andra projektfilformat?
Ja, Aspose.Tasks stöder olika projektfilformat inklusive MPP, XML, XLSX och mer.
### Kan jag få support om jag stöter på några problem under implementeringen?
Ja, du kan besöka Aspose.Tasks-forumet för hjälp från gemenskapen eller kontakta supporten för direkt hjälp.
### Hur kan jag få en tillfällig licens för Aspose.Tasks?
 Du kan få en tillfällig licens från[hemsida](https://purchase.aspose.com/temporary-license/) för teständamål.