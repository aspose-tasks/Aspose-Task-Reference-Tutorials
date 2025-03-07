---
title: Att bemästra arbetstider i Aspose.Tasks
linktitle: Samling av arbetstider i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Utforska kraften i Aspose.Tasks för .NET för att effektivt hantera projekttidslinjer. Anpassa kalendrar, ställ in arbetstider och effektivisera dina projekt med lätthet.
weight: 14
url: /sv/net/time-recurrence-configuration/working-time-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Att bemästra arbetstider i Aspose.Tasks

## Introduktion
Vill du behärska konsten att hantera arbetstider i Aspose.Tasks för .NET? Kolla inte vidare! I den här steg-för-steg-guiden kommer vi att fördjupa oss i krångligheterna med arbetstidsinsamling med Aspose.Tasks, vilket ger dig möjlighet att effektivt hantera anpassade kalendrar och effektivisera dina projekttidslinjer.
## Förutsättningar
Innan vi ger oss ut på denna resa, se till att du har följande förutsättningar på plats:
-  Aspose.Tasks for .NET Library: Ladda ner och installera Aspose.Tasks for .NET-biblioteket från[Aspose.Tasks release sida](https://releases.aspose.com/tasks/net/).
- Arbetsmiljö: Sätt upp en lämplig utvecklingsmiljö, helst med en .NET-kompatibel IDE.
## Importera namnområden
Importera de nödvändiga namnområdena i ditt projekt för att komma åt Aspose.Tasks-funktionerna:
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Låt oss nu dela upp handledningen i flera steg, vilket säkerställer en smidig inlärningsupplevelse.
## Steg 1: Skapa en anpassad kalender
Börja med att skapa ett nytt projekt och lägga till en anpassad kalender till det:
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Custom Calendar");
```
## Steg 2: Definiera arbetsdagar
Ställ in standardarbetsdagar från måndag till fredag:
```csharp
foreach (var dayType in Enum.GetValues(typeof(DayType)).Cast<DayType>())
{
    if (dayType != DayType.Saturday && dayType != DayType.Sunday)
    {
        calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(dayType));
    }
}
```
## Steg 3: Konfigurera lördagsarbetstider
Ange arbetstider för lördagar:
```csharp
var saturdayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(8, 12),
    new WorkingTime(13, 15)
};
var saturday = new WeekDay(DayType.Saturday, saturdayWorkingTimes);
```
## Steg 4: Skriv ut lördagsarbetsperioder
Skriv ut de konfigurerade arbetstiderna för lördag:
```csharp
Console.WriteLine("Saturday working period number: " + saturday.WorkingTimes.Count);
foreach (var time in saturday.WorkingTimes)
{
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## Steg 5: Konfigurera söndagsarbetstider
Definiera arbetstider för söndagar:
```csharp
var sundayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(10, 15)
};
var sunday = new WeekDay(DayType.Sunday, sundayWorkingTimes);
```
## Steg 6: Skriv ut söndagsarbetsperioder
Skriv ut de konfigurerade arbetstiderna för söndag:
```csharp
List<WorkingTime> workingTimes = sunday.WorkingTimes.ToList();
Console.WriteLine("Sunday working period number: " + workingTimes.Count);
for (var index = 0; index < workingTimes.Count; index++)
{
    var time = workingTimes[index];
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## Steg 7: Lägg till anpassade dagar i kalendern
Inkludera den konfigurerade lördagen och söndagen i kalendern:
```csharp
calendar.WeekDays.Add(saturday);
calendar.WeekDays.Add(sunday);
```
## Steg 8: Gå igenom arbetstider
Gå igenom arbetstiderna och visa dem för varje dag i kalendern:
```csharp
foreach (var day in calendar.WeekDays)
{
    Console.WriteLine(day.DayType + ": ");
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
    Console.WriteLine();
}
```
Nu när du framgångsrikt har navigerat genom stegen är du rustad att utnyttja kraften i Aspose.Tasks för .NET för att hantera arbetstider effektivt.
## Slutsats
Att bemästra insamlingen av arbetstider i Aspose.Tasks ger dig möjlighet att anpassa projektkalendrar, vilket säkerställer exakt schemaläggning och effektivt resursutnyttjande. Dyk in i dina projekt med självförtroende, beväpnad med kunskapen från denna omfattande guide.
## Vanliga frågor
### Är Aspose.Tasks lämplig för storskalig projektledning?
Ja, Aspose.Tasks är designat för att hantera projekt av varierande storlek, vilket ger robusta funktioner för effektiv projektledning.
### Kan jag integrera Aspose.Tasks med andra .NET-bibliotek?
Säkert! Aspose.Tasks integreras sömlöst med andra .NET-bibliotek, vilket förbättrar dess mångsidighet och kompatibilitet.
### Hur ofta uppdateras Aspose.Tasks?
 Aspose.Tasks uppdateras regelbundet för att införliva nya funktioner, förbättringar och kompatibilitetsförbättringar. Kolla[släpp sida](https://releases.aspose.com/tasks/net/) för de senaste uppdateringarna.
### Finns det en gratis testversion tillgänglig för Aspose.Tasks?
 Ja, du kan utforska Aspose.Tasks med en gratis provperiod genom att besöka[den här länken](https://releases.aspose.com/).
### Var kan jag söka stöd för Aspose.Tasks?
 För eventuella frågor eller hjälp, besök[Aspose.Tasks supportforum](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
