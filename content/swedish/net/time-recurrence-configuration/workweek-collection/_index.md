---
title: Anpassa arbetsveckor i Aspose.Tasks
linktitle: Samling av arbetsveckor i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du anpassar arbetsveckor i Aspose.Tasks för .NET. Steg-för-steg-guide för att skapa personliga projektkalendrar. Ladda ner nu!
type: docs
weight: 17
url: /sv/net/time-recurrence-configuration/workweek-collection/
---
## Introduktion
Välkommen till vår handledning om att skapa en anpassad arbetsvecka med Aspose.Tasks för .NET! I den här steg-för-steg-guiden går vi igenom processen för att definiera en personlig arbetsvecka för en kalender i ditt projekt. Aspose.Tasks är ett kraftfullt bibliotek som ger utvecklare möjlighet att effektivt arbeta med Microsoft Project-dokument i sina .NET-applikationer.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar:
1. Visual Studio: Se till att du har Visual Studio installerat på din dator.
2.  Aspose.Tasks för .NET: Ladda ner och installera Aspose.Tasks-biblioteket. Du hittar nedladdningslänken[här](https://releases.aspose.com/tasks/net/).
3. Grundläggande kunskaper i C#: Bekanta dig med C#-programmeringsspråkets grunder.
## Importera namnområden
Se till att importera de nödvändiga namnrymden i ditt C#-projekt:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## Steg 1: Skapa ett projekt och en kalender
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Standard");
Calendar.MakeStandardCalendar(calendar);
```
## Steg 2: Definiera en anpassad arbetsvecka
```csharp
var customWorkWeek = new WorkWeek();
customWorkWeek.Name = "My Work Week";
customWorkWeek.FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
customWorkWeek.ToDate = new DateTime(2020, 4, 17, 17, 0, 0);
```
## Steg 3: Ställ in arbetsdagar
```csharp
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Friday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Saturday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Sunday));
calendar.WorkWeeks.Add(customWorkWeek);
```
## Steg 4: Visa information om arbetsveckor
```csharp
Console.WriteLine("Work Weeks Count: " + calendar.WorkWeeks.Count);
foreach (var workWeek in calendar.WorkWeeks)
{
    Console.WriteLine("Name: " + workWeek.Name);
    Console.WriteLine("Parent calendar name: " + calendar.Name);
    Console.WriteLine("From Date: " + workWeek.FromDate);
    Console.WriteLine("To Date: " + workWeek.ToDate);
    List<WeekDay> weekDays = workWeek.WeekDays.ToList();
    foreach (var day in weekDays)
    {
        Console.WriteLine(day.DayType.ToString());
        foreach (var workingTime in day.WorkingTimes)
        {
            Console.WriteLine(workingTime.From);
            Console.WriteLine(workingTime.To);
        }
    }
    Console.WriteLine();
}
```
Denna omfattande guide ger dig möjlighet att effektivt skapa och hantera anpassade arbetsveckor med Aspose.Tasks för .NET.
## Slutsats
Sammanfattningsvis erbjuder Aspose.Tasks för .NET en robust lösning för att hantera projektkalendrar med anpassade arbetsveckor. Genom att följa den här handledningen har du lärt dig hur du skapar och visar information om anpassade arbetsveckor i ditt projekt.
## Vanliga frågor
### Kan jag ha flera anpassade arbetsveckor i ett enda projekt?
Ja, du kan lägga till flera anpassade arbetsveckor i en projektkalender.
### Hur kan jag ändra befintliga arbetsveckor?
 Använd den medföljande`WorkWeek`egenskaper och metoder för att ändra befintliga arbetsveckor.
### Är Aspose.Tasks kompatibelt med .NET Core?
Ja, Aspose.Tasks stöder .NET Core.
### Kan jag exportera projektet med anpassade arbetsveckor till Microsoft Project-filformat?
Absolut, Aspose.Tasks låter dig spara ditt projekt i olika format, inklusive Microsoft Project.
### Var kan jag söka stöd för Aspose.Tasks-relaterade frågor?
 Besök[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) för all stöd eller hjälp.