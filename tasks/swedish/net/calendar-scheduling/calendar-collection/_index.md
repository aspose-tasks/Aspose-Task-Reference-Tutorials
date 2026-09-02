---
date: 2026-04-13
description: Lär dig hur du ställer in arbetstimmar och hanterar kalenderkollektioner
  i Aspose.Tasks för .NET. Importera kalendrar från Microsoft Project, ta bort kalenderprojekt
  och hämta kalender efter namn enkelt.
keywords:
- set working hours
- import calendars microsoft project
- remove calendar project
- get calendar by name
linktitle: Hantera kalendersamling i Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Ställ in arbetstimmar i Aspose.Tasks kalenderkollektion
url: /sv/net/calendar-scheduling/calendar-collection/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ställ in arbetstimmar i Aspose.Tasks kalenderkollektion

I den här handledningen kommer du att lära dig hur du **ställer in arbetstimmar** och hanterar kalenderkollektioner med Aspose.Tasks för .NET. Kalendrar definierar arbetsdagar, helgdagar och undantag, så att behärska dem låter dig kontrollera projektscheman exakt. Vi kommer också att visa hur du importerar kalendrar från Microsoft Project, tar bort en kalender från ett projekt och hämtar en kalender efter namn.

## Snabba svar
- **Vad är den primära klassen för kalendrar?** `Project.Calendars` collection.
- **Hur ställer jag in arbetstimmar?** Skapa eller modifiera ett `Calendar`-objekt och definiera dess `WorkingTime`.
- **Kan jag importera kalendrar från Microsoft Project?** Ja – ladda en MPP-fil och få åtkomst till dess kalendrar.
- **Hur tar man bort en kalender från ett projekt?** Använd `Project.Calendars.Remove(calendar)`.
- **Hur hämtar man en kalender efter namn?** Anropa `Project.Calendars.GetByName("YourCalendar")`.

## Förutsättningar

Innan vi börjar, se till att du har följande:

1. Visual Studio: Installera Visual Studio eller någon annan kompatibel IDE för .NET-utveckling.  
2. Aspose.Tasks för .NET: Ladda ner och installera Aspose.Tasks för .NET från [här](https://releases.aspose.com/tasks/net/).  
3. Grundläggande förståelse för C#: Bekantskap med programmeringsspråket C# kommer att vara fördelaktigt.

## Importera namnrymder

Först, låt oss importera de nödvändiga namnrymderna för att arbeta med Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
```

## Skapa en ny kalender

### Steg 1: Initiera ett nytt `Project`-objekt.
```csharp
var project = new Project();
```

### Steg 2: Lägg till kalendrar i projektets kalenderkollektion.
```csharp
project.Calendars.Add("Calendar");
var newCalendar = project.Calendars.Add("Parent");
project.Calendars.Add("Child", newCalendar);
```

### Steg 3: Iterera genom kalendrarna och visa deras namn.
```csharp
foreach (var calendar in project.Calendars)
{
    Console.WriteLine("Calendar Name: " + calendar.Name);
}
```

## Hur man ställer in arbetstimmar för en kalender?

För att **ställa in arbetstimmar**, modifierar du `WorkingTime`-samlingen i ett `Calendar`.  
Till exempel kan du definiera en standardarbetsdag 9 – 17 eller lägga till anpassade undantag.  
Koden för detta är identisk med exemplen som visas senare när vi skapar en standardkalender.

## Ersätta en kalender med en ny kalender

### Steg 1: Ladda ett befintligt projekt.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Steg 2: Ta bort den befintliga kalendern (om den finns).  
Detta demonstrerar scenariot **remove calendar project**.
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
Detta illustrerar operationen **get calendar by name**.
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

## Iterera över kalendrar

### Steg 1: Ladda projektet.
```csharp
var project = new Project(DataDir + "Project5.mpp");
```

### Steg 2: Hämta antalet kalendrar.
```csharp
Console.WriteLine("Number of calendars in the project: " + project.Calendars.Count);
```

### Steg 3: Iterera över kalenderkollektionen och visa namn.
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

## Vanliga problem och lösningar

- **Kalender hittades inte när `GetByName` används** – Se till att det exakta namnet matchar skiftläget som användes när kalendern lades till.  
- **Arbetstimmar tillämpas inte** – Efter att ha ställt in `WorkingTime`, kom ihåg att spara projektet; annars förblir ändringarna bara i minnet.  
- **Import av kalendrar från en MPP-fil misslyckas** – Verifiera att källfilen är en giltig Microsoft Project-fil och att du har läsbehörighet.

## Vanliga frågor

### Q1: Kan jag skapa anpassade arbetsdagar i Aspose.Tasks?
A1: Ja, du kan skapa anpassade arbetsdagar genom att lägga till undantag i kalendrar.

### Q2: Är det möjligt att importera kalendrar från Microsoft Project-filer?
A2: Absolut, Aspose.Tasks stödjer import av kalendrar från Microsoft Project-filer.

### Q3: Hur kan jag ta bort en specifik kalender från ett projekt?
A3: Du kan ta bort en kalender genom att hämta den från samlingen och sedan anropa `Remove`-metoden.

### Q4: Stöder Aspose.Tasks export av kalendrar till olika format?
A4: Ja, Aspose.Tasks möjliggör export av kalendrar till olika format som XML, MPP osv.

### Q5: Kan jag anpassa arbetstimmar för specifika dagar i en kalender?
A5: Självklart, du kan definiera arbetstimmar för enskilda dagar genom att använda undantag i kalendern.

## Vanliga frågor

**Q: Vad är det bästa sättet att ställa in en 24‑timmars skiftkalender?**  
A: Skapa en ny kalender, rensa befintliga `WorkingTime`-poster och lägg till ett enda `WorkingTime`-intervall från 00:00 till 24:00 för varje veckodag.

**Q: Kan jag kopiera en kalender från ett projekt till ett annat?**  
A: Ja—exportera kalendern till XML med `project.Save` och importera den sedan till ett annat projekt med `new Project(xmlPath)`.

**Q: Hur importerar jag programmässigt kalendrar från Microsoft Project?**  
A: Ladda MPP-filen med `new Project("source.mpp")`; kalendrarna blir tillgängliga via `project.Calendars`.

**Q: Finns det någon gräns för antalet kalendrar i ett projekt?**  
A: Praktiskt taget ingen; samlingen kan hålla så många kalendrar som minnet tillåter, men håll listan hanterbar för prestanda.

**Q: Uppdateras uppgifter som använder en kalender automatiskt när kalendern ändras?**  
A: Ja—uppgifter som är länkade till en kalender återspeglar de uppdaterade arbetstiderna efter att du har sparat projektet.

---

**Senast uppdaterad:** 2026-04-13  
**Testad med:** Aspose.Tasks 24.11 for .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}