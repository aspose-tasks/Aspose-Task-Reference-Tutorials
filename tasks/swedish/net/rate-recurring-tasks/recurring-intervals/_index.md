---
title: Enkel MS-projekt återkommande intervaller i Aspose.Tasks
linktitle: Hantera återkommande intervaller i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Upptäck hur du enkelt hanterar återkommande intervaller i MS Project med Aspose.Tasks för .NET.
weight: 12
url: /sv/net/rate-recurring-tasks/recurring-intervals/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Enkel MS-projekt återkommande intervaller i Aspose.Tasks

## Introduktion
Vill du hantera återkommande intervall effektivt i Microsoft Project-filer med Aspose.Tasks för .NET? Denna omfattande handledning guidar dig genom processen steg för steg, och säkerställer att du utan ansträngning kan hantera återkommande intervaller i dina projekt. Innan vi dyker in i handledningen, låt oss gå igenom några förutsättningar för att säkerställa att du är redo att börja.
## Förutsättningar
Innan du fortsätter med den här handledningen, se till att du har följande:
1. Kunskaper i C#-programmering: Grundläggande förståelse av C#-programmeringsspråket och dess syntax krävs.
2. Visual Studio installerad: Se till att du har Visual Studio installerat på ditt system för kodning och kompilering av .NET-applikationerna.
3. Aspose.Tasks for .NET Library: Ladda ner och installera Aspose.Tasks for .NET-biblioteket. Du kan få det från[här](https://releases.aspose.com/tasks/net/).

## Importera namnområden
Börja med att importera de nödvändiga namnområdena för att komma åt funktionerna som tillhandahålls av Aspose.Tasks för .NET-biblioteket.
   
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
Låt oss nu dela upp varje exempel i flera steg och förklara dem i detalj.
## Steg 1: Initiera projektobjekt:
```csharp
// Sökvägen till dokumentkatalogen.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2007.mpp");
```
 Här initierar vi en ny instans av`Project` klass genom att ange sökvägen till Microsoft Project-filen.
## Steg 2: Ställ in statusdatum:
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
Detta steg ställer in projektets statusdatum till dess startdatum.
## Steg 3: Öppna Gantt-diagramvy:
```csharp
var view = (GanttChartView)project.Views.ToList()[1];
```
Vi kommer åt projektets Gantt-diagram.
## Steg 4: Läs förloppsrad:
```csharp
var interval = view.ProgressLines.RecurringInterval;
```
Detta steg hämtar det återkommande intervallet för förloppslinjer från Gantt-diagramvyn.
## Steg 5: Visa intervallinformation:
```csharp
Console.WriteLine("Interval: " + interval.Interval);
Console.WriteLine("Weekly Week Number: " + interval.WeeklyWeekNumber);
foreach (var day in interval.WeeklyDays)
{
    Console.WriteLine("Week day: " + day);
}
```
Här visar vi information om intervall, veckoveckonummer och veckodagar.
## Steg 6: Omdefiniera återkommande intervall:
```csharp
var newInterval = new RecurringInterval();
```
 Vi skapar en ny instans av`RecurringInterval` för att omdefiniera det återkommande intervallet.
## Steg 7: Ställ in månatliga framstegsrader:
```csharp
// Ställ in månatliga framstegslinjer per dag.
interval.MonthlyDay = true;
// Ställ in dagnumret för månatliga framstegsrader.
interval.MonthlyDayDayNumber = 1;
// Ställ in månadsantalet för månatliga framstegsrader.
interval.MonthlyDayMonthNumber = 1;
// Ställ in framstegslinjer efter första eller sista fördefinierade dagen.
interval.MonthlyFirstLast = true;
// Ställ in den första eller sista dagstypen av månatliga framstegsrader.
interval.MonthlyFirstLastDay = RecurringInterval.DayType.Day;
// Ställ in månadsantalet för framstegsrader.
interval.MonthlyFirstLastMonthNumber = 1;
```
Dessa steg konfigurerar de månatliga förloppsraderna enligt angivna parametrar.
## Steg 8: Uppdatera förloppsrader:
```csharp
view.ProgressLines.RecurringInterval = newInterval;
```
Vi uppdaterar förloppslinjerna i Gantt-diagramvyn med det nydefinierade återkommande intervallet.
## Steg 9: Spara projekt som PDF:
```csharp
project.Save(DataDir + "WorkWithRecurringInterval_out.pdf", SaveFileFormat.Pdf);
```
Slutligen sparar vi projektet med det uppdaterade återkommande intervallet som en PDF-fil.

## Slutsats
Sammanfattningsvis är det enkelt att hantera återkommande intervall i Microsoft Project-filer med Aspose.Tasks för .NET med de omfattande funktioner som biblioteket tillhandahåller. Genom att följa den steg-för-steg-guide som beskrivs i denna handledning kan du effektivt hantera återkommande intervaller i dina projekt, vilket förbättrar produktiviteten och organisationen.
### FAQ's
### Kan jag använda Aspose.Tasks för .NET med andra programmeringsspråk?
Ja, Aspose.Tasks för .NET kan användas med alla .NET-stödda språk som C# och VB.NET.
### Finns det en testversion tillgänglig för Aspose.Tasks för .NET?
 Ja, du kan ladda ner en gratis testversion från[här](https://releases.aspose.com/).
### Hur kan jag få support för Aspose.Tasks för .NET?
 Du kan få support från Aspose.Tasks-forumet[här](https://forum.aspose.com/c/tasks/15).
### Kan jag köpa en tillfällig licens för Aspose.Tasks för .NET?
 Ja, du kan köpa en tillfällig licens från[här](https://purchase.aspose.com/temporary-license/).
### Var kan jag hitta den fullständiga dokumentationen för Aspose.Tasks för .NET?
 Den fullständiga dokumentationen finns[här](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
