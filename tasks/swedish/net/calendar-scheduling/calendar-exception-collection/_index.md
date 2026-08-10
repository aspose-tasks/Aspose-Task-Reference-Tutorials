---
date: 2026-04-09
description: Lär dig hur du ställer in standardkalender och hanterar projektledigheter
  i dina .NET‑projekt med Aspose.Tasks för exakt schemaläggning.
keywords:
- set standard calendar
- manage project holidays
- load project calendar
linktitle: Ställ in standardkalender och hantera undantag i Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Ställ in standardkalender och hantera undantag i Aspose.Tasks
url: /sv/net/calendar-scheduling/calendar-exception-collection/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ställ in standardkalender och hantera undantag i Aspose.Tasks

## Introduktion

Noggrann schemaläggning är ryggraden i alla framgångsrika projekt, och verkliga planer måste ofta avvika från standardarbetskalendern på grund av helgdagar, speciella evenemang eller oväntade avstängningar. Aspose.Tasks för .NET gör det enkelt att **set standard calendar**‑inställningar och sedan lägga till anpassade undantag ovanpå. I den här handledningen kommer du att lära dig hur du laddar en projektkalender, ställer in en standardkalender och hanterar projektets helgdagar via Calendar Exception Collection‑funktionen.

## Snabba svar
- **Vad gör “set standard calendar”?** Det återställer en kalender till standardarbetstid (9 AM‑5 PM, måndag‑fredag) innan du lägger till anpassade undantag.  
- **Vilken metod rensar befintliga undantag?** `Calendar.Exceptions.Clear()` tar bort alla tidigare definierade undantag.  
- **Hur kan jag lägga till en helgdag?** Skapa en `CalendarException` med `DayWorking = false` och lägg till den i samlingen.  
- **Behöver jag ladda om projektet efter ändringar?** Nej, ändringarna tillämpas direkt på det minnes‑`Project`‑objektet.  
- **Vilka bibliotek krävs?** Aspose.Tasks för .NET (valfri stödd .NET‑version) och `System`‑namnrymder.

## Förutsättningar

Innan du dyker ner i koden, se till att du har:

1. **Aspose.Tasks for .NET** – ladda ner den [här](https://releases.aspose.com/tasks/net/).  
2. Grundläggande kunskap i **C#** – du kommer att skriva några korta kodsnuttar.  
3. En utvecklingsmiljö som **Visual Studio** eller **JetBrains Rider**.

## Importera namnrymder

Dessa `using`‑direktiv ger dig åtkomst till de klasser som behövs för kalendermanipulation.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Vad är ett kalenderundantag?

*Ett kalenderundantag* representerar en period där det normala arbetsschemat ändras – till exempel en företagshelgdag eller ett tillfälligt övertidsschema. Genom att lägga till undantag i en kalender kan du modellera verkliga begränsningar utan att ändra grundkalendern.

## Så ställer du in standardkalender i Aspose.Tasks

Det första steget är att ladda din projektfil och hämta den kalender du vill arbeta med.

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

### Steg 1: Rensa befintliga undantag och återställ till en standardkalender

Innan du lägger till nya regler är det en bra praxis att rensa eventuella gamla undantag och **set standard calendar**‑inställningar. Detta säkerställer en ren grundlinje.

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

### Steg 2: Definiera ett arbetstid‑undantag

Ibland behöver du skapa ett tillfälligt schema (t.ex. förlängda timmar för en produktlansering). Följande kodsnutt definierar ett arbetstid‑undantag som sträcker sig över flera dagar och inkluderar två dagliga arbetspass.

```csharp
var exception = new CalendarException();
exception.FromDate = new DateTime(2020, 3, 30, 8, 0, 0);
exception.ToDate = new DateTime(2020, 4, 3, 17, 0, 0);
exception.DayWorking = true;
exception.Name = "Exception 1";

var wt1 = new WorkingTime(9, 13);
var wt2 = new WorkingTime(14, 19);

exception.WorkingTimes.Add(wt1);
exception.WorkingTimes.Add(wt2);
calendar.Exceptions.Add(exception);
```

### Steg 3: Lägg till icke‑arbetstid‑undantag (helgdagar)

För att **manage project holidays** skapar du undantag där `DayWorking` är `false`. Exemplet nedan lägger till ett tvådagars helgblocket.

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

// Add more exceptions if needed

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

### Steg 4: Visa kalenderundantag (verifiering)

Efter att ha lagt till undantag vill du ofta verifiera att de registrerats korrekt. Följande loop skriver ut varje undantags detaljer till konsolen.

```csharp
Console.WriteLine("Exceptions of calendar {0}: ", calendar.Exceptions.ParentCalendar.Name);
Console.WriteLine("Exceptions count: {0}", calendar.Exceptions.Count);
Console.WriteLine();
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Name: " + calendarException.Name);
    Console.WriteLine("From Date: " + calendarException.FromDate);
    Console.WriteLine("To Date: " + calendarException.ToDate);
    Console.WriteLine("Is day working: " + calendarException.DayWorking);
    Console.WriteLine();
}
```

### Steg 5: Ta bort alla undantag (rensning)

Om du behöver återställa kalendern till sitt ursprungliga tillstånd kan du ta bort alla undantag programatiskt.

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

## Vanliga problem och lösningar

| Problem | Orsak | Lösning |
|-------|--------|-----|
| Undantag visas inte efter sparning | Projektet sparas inte efter ändringar | Anropa `project.Save("output.mpp")` efter att ha gjort ändringar. |
| Överlappande undantag orsakar oväntade arbetstimmar | Aspose.Tasks använder det senast tillagda undantaget för överlappande perioder | Ordna dina `Add`‑anrop noggrant eller justera prioriteringar manuellt. |
| `MakeStandardCalendar` återställer anpassade arbetstider | Den rensar avsiktligt anpassade tider; lägg till dem igen efter anropet om det behövs. | Lägg till dina anpassade `WorkingTime`‑objekt efter att ha anropat `MakeStandardCalendar`. |

## Vanliga frågor

**Q: Kan jag lägga till flera undantag i en enda kalender?**  
A: Ja, du kan lägga till flera undantag i en kalender med `AddRange`‑metoden.

**Q: Hur hanterar jag återkommande undantag, såsom veckovisa helgdagar?**  
A: Du kan programatiskt beräkna återkommande undantag och lägga till dem i kalendern med anpassad logik.

**Q: Är det möjligt att importera kalenderundantag från externa källor?**  
A: Ja, du kan läsa kalenderundantag från externa källor som databaser eller CSV‑filer och integrera dem i ditt projekt.

**Q: Vad händer om det finns överlappande undantag i kalendern?**  
A: Aspose.Tasks för .NET låter dig hantera överlappande undantag genom att definiera prioriteringar eller lösa konflikter baserat på dina projektkrav.

**Q: Kan jag anpassa arbetstiderna för varje dag inom ett undantag?**  
A: Ja, du kan ange anpassade arbetstider för enskilda dagar inom ett undantag för att tillgodose specifika schemaläggningsbehov.

## Slutsats

Genom att först **setting a standard calendar** och sedan lägga till anpassade undantag får du full kontroll över projektschemaläggning, vilket gör det enkelt att **manage project holidays** och andra specialtidslinjer. Calendar Exception Collection i Aspose.Tasks erbjuder ett rent, programatiskt sätt att modellera verkliga kalendrar direkt i dina .NET‑applikationer.

---

**Senast uppdaterad:** 2026-04-09  
**Testat med:** Aspose.Tasks 24.12 for .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}