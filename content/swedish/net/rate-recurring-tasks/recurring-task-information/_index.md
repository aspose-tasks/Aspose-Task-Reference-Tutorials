---
title: Extrahera information om återkommande uppgifter i Aspose.Tasks
linktitle: Extrahera information om återkommande uppgifter i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du extraherar information om återkommande uppgifter från MS Project-filer med Aspose.Tasks för .NET. Enkel integration för .NET-utvecklare.
type: docs
weight: 13
url: /sv/net/rate-recurring-tasks/recurring-task-information/
---
## Introduktion
Aspose.Tasks för .NET är ett kraftfullt bibliotek som låter utvecklare arbeta med Microsoft Project-filer i sina .NET-applikationer. I den här handledningen kommer vi att utforska hur man extraherar information om återkommande uppgifter från MS Project-filer med Aspose.Tasks.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
1. Grundläggande förståelse för programmeringsspråket C#.
2. Visual Studio installerat på ditt system.
3.  Aspose.Tasks för .NET-biblioteket installerat. Du kan ladda ner den från[här](https://releases.aspose.com/tasks/net/).
## Importera namnområden
För att komma igång, importera de nödvändiga namnrymden i din C#-kod:
```csharp
    using Aspose.Tasks;
    using System;
    
```
Låt oss nu dela upp exemplet i flera steg:
## Steg 1: Ställ in projektfilens sökväg
```csharp
String DataDir = "Your Document Directory";
```
 Byta ut`"Your Document Directory"` med sökvägen till din MS Project-fil.
## Steg 2: Ladda MS Project-filen
```csharp
var project = new Project(DataDir + "TestRecurringTask2016.mpp");
```
 Denna rad initierar en ny`Project` objekt genom att ladda MS Project-filen som anges av sökvägen.
## Steg 3: Läs återkommande information om uppgifter
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    var info = task.RecurringInfo;
    if (info == null)
    {
        continue;
    }
    // Få åtkomst till och visa information om återkommande uppgifter
    Console.WriteLine("Start Date: " + info.StartDate);
    Console.WriteLine("Duration: " + info.Duration);
    Console.WriteLine("End Date: " + info.EndDate);
    // Fortsätt att visa annan återkommande uppgiftsinformation efter behov
}
```
Denna loop itererar genom alla uppgifter i projektet och kontrollerar om varje uppgift har återkommande information kopplad till sig. Om den gör det, hämtar och visar den olika egenskaper för den återkommande uppgiften, såsom startdatum, varaktighet, slutdatum, etc.
## Slutsats
den här handledningen har vi lärt oss hur man extraherar information om återkommande uppgifter från MS Project-filer med Aspose.Tasks för .NET. Med denna kunskap kan du nu integrera den här funktionen i dina .NET-applikationer för att arbeta med återkommande uppgifter mer effektivt.
## FAQ's
### F: Kan jag ändra information om återkommande uppgifter med Aspose.Tasks för .NET?
S: Ja, du kan modifiera information om återkommande uppgifter programmatiskt med hjälp av de medföljande API:erna.
### F: Stöder Aspose.Tasks andra projektfilformat förutom MS Project?
S: Ja, Aspose.Tasks stöder olika projektfilformat som MPP, XML och CSV.
### F: Finns det en gratis testversion tillgänglig för Aspose.Tasks för .NET?
 S: Ja, du kan ladda ner en gratis testversion från[här](https://releases.aspose.com/).
### F: Var kan jag hitta dokumentation för Aspose.Tasks för .NET?
 S: Du kan hitta dokumentationen[här](https://reference.aspose.com/tasks/net/).
### F: Hur kan jag få teknisk support för Aspose.Tasks för .NET?
 S: Du kan få teknisk support från Aspose.Tasks-forumet[här](https://forum.aspose.com/c/tasks/15).