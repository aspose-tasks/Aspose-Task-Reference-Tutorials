---
title: Hantera kalenderinsamling i Aspose.Tasks
linktitle: Hantera kalenderinsamling i Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Lär dig hur du hanterar kalendersamlingar i Aspose.Tasks för .NET effektivt. Skapa, ändra och manipulera kalendrar med lätthet.
weight: 11
url: /sv/net/calendar-scheduling/calendar-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hantera kalenderinsamling i Aspose.Tasks

## Introduktion

I den här handledningen kommer vi att utforska hur man hanterar kalendersamlingar i Aspose.Tasks för .NET. Kalendrar spelar en avgörande roll i projektledning och definierar arbetsdagar, helgdagar och undantag. Aspose.Tasks ger robust funktionalitet för att manipulera kalendrar i dina projekt.

## Förutsättningar

Innan vi börjar, se till att du har följande:

1. Visual Studio: Installera Visual Studio eller någon annan kompatibel IDE för .NET-utveckling.
2.  Aspose.Tasks for .NET: Ladda ner och installera Aspose.Tasks for .NET från[här](https://releases.aspose.com/tasks/net/).
3. Grundläggande förståelse för C#: Bekantskap med programmeringsspråket C# kommer att vara fördelaktigt.

## Importera namnområden

Låt oss först importera de nödvändiga namnrymden för att arbeta med Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;

```

## Skapa en ny kalender

###  Steg 1: Initiera en ny`Project` object.
```csharp
var project = new Project();
```

### Steg 2: Lägg till kalendrar till projektets kalendersamling.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### Steg 3: Gå igenom kalendrarna och visa deras namn.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Ersätta en kalender med en ny kalender

### Steg 1: Ladda ett befintligt projekt.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Steg 2: Ta bort den befintliga kalendern (om den finns).
```csharp
var calendar = project.Calendars.GetByName("TestCalendar");
if (calendar != null)
{
    project.Calendars.Remove(calendar);
}
```

### Steg 3: Lägg till en ny kalender.
```csharp
project.Calendars.Add("New Calendar");
project.Save(OutDir + "ReplaceCalendarWithNewCalendar_out.mpp", SaveFileFormat.Mpp);
```

## Hämta kalender efter namn eller ID

### Steg 1: Ladda projektet.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Steg 2: Hämta kalendrar efter namn eller UID.
```csharp
var calendarByName = project.Calendars.GetByName("TestCalendar");
var calendarByUid = project.Calendars.GetByUid(4);
```

### Steg 3: Visa kalenderdetaljer.
```csharp
Console.WriteLine("Calendar Name: " + calendarByName.Name);
Console.WriteLine("Calendar Name: " + calendarByUid.Name);
Console.WriteLine("Are calendars equals: " + calendarByName.Equals(calendarByUid));
```

## Itererar över kalendrar

### Steg 1: Ladda projektet.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Steg 2: Hämta antalet kalendrar.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### Steg 3: Iterera över kalendersamlingen och visningsnamnen.
```csharp
List<Calendar> calendars = project.Calendars.ToList();
foreach (var calendar in calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Skapa en standardkalender

### Steg 1: Initiera ett nytt projekt.
```csharp
var project = new Project();
```

### Steg 2: Definiera en ny kalender och gör den till standard.
```csharp
var calendar = project.Calendars.Add("New Standard Calendar");
Calendar.MakeStandardCalendar(calendar);
```

### Steg 3: Spara projektet.
```csharp
project.Save(OutDir + "MakeAStandardCalendar_out.xml", SaveFileFormat.Xml);
```

## Slutsats

Hantera kalendersamlingar i Aspose.Tasks för .NET är avgörande för effektiv projektledning. Med de tillhandahållna funktionerna kan du effektivt skapa, ändra och manipulera kalendrar enligt dina projektkrav.

## FAQ's

### F1: Kan jag skapa anpassade arbetsdagar i Aspose.Tasks?

S1: Ja, du kan skapa anpassade arbetsdagar genom att lägga till undantag i kalendrar.

### F2: Är det möjligt att importera kalendrar från Microsoft Project-filer?

S2: Absolut, Aspose.Tasks stöder import av kalendrar från Microsoft Project-filer.

### F3: Hur kan jag ta bort en specifik kalender från ett projekt?

 S3: Du kan ta bort en kalender genom att hämta den från samlingen och sedan ringa till`Remove` metod.

### F4: Stöder Aspose.Tasks export av kalendrar till olika format?

S4: Ja, Aspose.Tasks tillåter export av kalendrar till olika format som XML, MPP, etc.

### F5: Kan jag anpassa arbetstiderna för specifika dagar i en kalender?

S5: Visst, du kan definiera arbetstider för enskilda dagar med hjälp av undantag i kalendern.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
