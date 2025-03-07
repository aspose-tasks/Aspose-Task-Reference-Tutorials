---
title: Hantera kalenderundantag i Aspose.Tasks
linktitle: Hantera kalenderundantag i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du hanterar kalenderundantag i Aspose.Tasks för .NET med steg-för-steg handledning och exempel.
weight: 12
url: /sv/net/calendar-scheduling/calendar-exceptions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hantera kalenderundantag i Aspose.Tasks

## Introduktion

I den här handledningen kommer vi att utforska hur man hanterar kalenderundantag i Aspose.Tasks med .NET-ramverket. Kalenderundantag tillåter oss att definiera speciella datum eller perioder i en projektkalender där det vanliga arbetsschemat ändras, såsom helgdagar eller tillfälliga stängningar. Vi kommer att täcka olika metoder för att hantera kalenderundantag steg för steg, med Aspose.Tasks för .NET.

## Förutsättningar

Innan vi börjar, se till att du har följande förutsättningar:
- Grundläggande kunskaper i programmeringsspråket C#.
- Visual Studio installerat på ditt system.
- Aspose.Tasks för .NET-biblioteket har lagts till i ditt projekt.

## Importera namnområden

Låt oss först importera de nödvändiga namnrymden för vårt projekt:

```csharp
using Aspose.Tasks;
using System;


```

## Steg 1: Ta bort ett kalenderundantag

Följ dessa steg för att ta bort ett kalenderundantag:

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // Visa kalenderinformation
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // Ta bort det första undantaget
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

## Steg 2: Få arbetstid för ett kalenderundantag

Följ dessa steg för att hämta arbetstiden för ett kalenderundantag:

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // Visa kalender och undantagsinformation
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // Få arbetstid och visa detaljer
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## Steg 3: Definiera kalenderundantag

Följ dessa steg för att lägga till eller ta bort kalenderundantag:

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // Skapa ett nytt kalenderundantag
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // Ange undantagsdetaljer
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // Kontrollera om ett datum är ett undantag
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // Lägg till undantaget i kalendern
    calendar.Exceptions.Add(exception);

    // Ta bort ett undantag om det finns
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // Lägg till ett nytt undantag
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // Skriv ut undantag
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## Slutsats

den här artikeln har vi täckt olika aspekter av hantering av kalenderundantag i Aspose.Tasks för .NET. Genom att följa de angivna stegen kan du effektivt hantera undantag i dina projektscheman, vilket säkerställer en korrekt representation av arbetstider och speciella händelser.

## FAQ's

### F1: Kan jag lägga till flera undantag i en enda kalender?

S1: Ja, du kan lägga till flera undantag i en kalender för att ta emot olika speciella datum eller perioder.

### F2: Hur kan jag kontrollera om ett specifikt datum är ett undantag?

 A2: Du kan använda`CheckException()` metod för att verifiera om ett visst datum faller under ett undantag.

### F3: Är det möjligt att ta bort ett befintligt undantag från en kalender?

 S3: Ja, du kan ta bort undantag genom att öppna`Exceptions` samling av kalendern och använda`Remove()` metod.

### F4: Vilka typer av kalenderundantag stöds?

S4: Aspose.Tasks stöder olika typer av undantag, inklusive dagliga, veckovisa, månatliga och årliga undantag, vilket ger flexibilitet när det gäller att definiera undantagsregler.

### F5: Kan jag anpassa arbetstiden för specifika undantagsdatum?

S5: Ja, du kan definiera anpassade arbetstider för enskilda undantagsdatum med hjälp av lämpliga metoder som tillhandahålls av Aspose.Tasks.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
