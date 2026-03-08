---
date: 2026-03-08
description: Lär dig hur du skapar en månatlig återkommande uppgift i Aspose.Tasks
  för .NET med den här steg‑för‑steg‑handledningen.
linktitle: How to Create Monthly Recurring Task in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Hur man skapar en månatlig återkommande uppgift i Aspose.Tasks
url: /sv/net/advanced-concepts/monthly-recurrence-patterns/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Skapa månatlig återkommande uppgift med Aspose.Tasks

## Introduktion

Aspose.Tasks för .NET låter dig programatiskt manipulera Microsoft Project‑filer, och ett av de vanligaste behoven i verkligheten är att **skapa månatliga återkommande uppgift**‑scheman. Oavsett om du bygger ett verktyg för projektspårning, automatiserar resursallokering eller genererar återkommande underhållsarbetsuppgifter, så guidar den här handledningen dig genom de exakta stegen för att lägga till ett månatligt återkomstandemönster till en uppgift.

I de följande avsnitten kommer du att se hur du ställer in projektet, definierar återkommande parametrar och slutligen sparar den uppdaterade filen – allt med tydliga förklaringar och praktiska tips.

## Snabba svar
- **Vad betyder “monthly recurring task”?** En uppgift som upprepas enligt ett definierat dag‑eller‑veckomönster varje månad.  
- **Vilken API‑klass hanterar återkommande?** `RecurringTaskParameters` tillsammans med `MonthlyRecurrencePattern`.  
- **Behöver jag en licens för att köra exemplet?** En gratis provversion fungerar för utvärdering; en licens krävs för produktion.  
- **Kan jag ändra intervallet?** Ja – sätt `RepetitionInterval` till antalet månader mellan förekomster.  
- **Vilka filformat stöds?** Både `.mpp`‑ och `.xml`‑Project‑filer kan laddas och sparas.

## Vad är ett månatligt återkomstandemönster?

Ett månatligt återkomstandemönster talar om för Microsoft Project (och Aspose.Tasks) hur ofta en uppgift ska upprepas varje månad. Du kan ange en fast dag i månaden (t.ex. den 1:a) eller en relativ position (t.ex. sista fredagen). API‑et översätter dessa regler till den underliggande Project‑filstrukturen.

## Varför använda Aspose.Tasks för detta?

- **Full kontroll** – Inga UI‑begränsningar; du definierar varje aspekt av mönstret i kod.  
- **Plattformsoberoende** – Fungerar på .NET Framework, .NET Core och .NET 5/6+.  
- **Ingen Microsoft Project krävs** – Generera eller modifiera filer på en server eller i en CI‑pipeline.  

## Förutsättningar

Innan du börjar, se till att du har:

- .NET 6 (eller .NET 5/Framework 4.7+) installerat.  
- Aspose.Tasks för .NET NuGet‑paket tillagt i ditt projekt.  
- En exempel‑Project‑fil (`Project1.mpp`) placerad i en känd mapp (`DataDir`).  

## Importera namnrymder

Först importerar du de namnrymder som krävs för att arbeta med uppgifter och spara projekt:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

## Steg 1: Initiera projektet

Skapa en `Project`‑instans som pekar på din befintliga `.mpp`‑fil. Detta laddar filen i minnet så att du kan modifiera den.

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

> **Proffstips:** Om filen inte finns kommer Aspose.Tasks automatiskt att skapa ett nytt tomt projekt.

## Steg 2: Ställ in återkommande uppgiftsparametrar

Definiera detaljerna för den återkommande uppgiften, inklusive namn, varaktighet och det månatliga mönster du vill tillämpa.

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

- `DayPosition = 1` betyder att uppgiften sker på **första dagen** i månaden.  
- `RepetitionInterval = 2` får uppgiften att upprepas **varannan månad**.  
- `Start` och `Finish` definierar det övergripande fönstret då återkommandet är aktivt.

## Steg 3: Lägg till parametrar i projektet

Fäst `RecurringTaskParameters`‑objektet till rotuppgiftens barnsamling. Detta skapar i praktiken den återkommande uppgiften i projektets hierarki.

```csharp
project.RootTask.Children.Add(parameters);
```

## Steg 4: Spara projektet

Spara ändringarna genom att skriva projektet till en ny fil. Du kan välja vilket som helst av de stödjade formaten; här använder vi det inhemska `.mpp`‑formatet.

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Efter att ha kört koden, öppna den resulterande filen i Microsoft Project för att se den månatliga återkommande uppgift du just skapade.

## Vanliga problem och lösningar

| Problem | Orsak | Lösning |
|-------|-------|-----|
| Uppgift visas inte efter sparning | Projektet uppdateras inte i UI | Öppna filen igen eller anropa `project.UpdateTaskLinks()` innan du sparar. |
| Fel startdatum | `Start` satt till en helg | Använd ett `DateTime` som faller på en arbetsdag eller justera kalendern. |
| Återkommande intervall ignoreras | Använder `ByMonthDayRepetition` med `DayPosition` = 0 | Säkerställ att `DayPosition` är 1‑31. |

## Slutsats

Genom att följa dessa steg vet du nu hur du **skapar månatliga återkommande uppgift**‑scheman med Aspose.Tasks för .NET. API‑et ger dig detaljerad kontroll över återkommande intervall, start-/slutintervall och det specifika dagmönstret, vilket möjliggör automatisering av komplexa projektplaneringsscenarier.

## Vanliga frågor

### Q1: Är Aspose.Tasks kompatibel med alla versioner av Microsoft Project‑filer?

A1: Aspose.Tasks stöder olika versioner av Microsoft Project‑filer, inklusive MPP, MPT, XML och MPX.

### Q2: Kan jag anpassa återkomstandemönstret ytterligare?

A2: Ja, Aspose.Tasks erbjuder omfattande alternativ för att anpassa återkomstandemönster, inklusive dagliga, veckovisa, månatliga och årliga.

### Q3: Finns det en gratis provversion av Aspose.Tasks?

A3: Ja, du kan få en gratis provversion av Aspose.Tasks från webbplatsen [here](https://releases.aspose.com/).

### Q4: Hur kan jag få support för Aspose.Tasks?

A4: Du kan söka hjälp och delta i diskussioner på [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### Q5: Var kan jag köpa en licens för Aspose.Tasks?

A5: Du kan köpa en licens för Aspose.Tasks från webbplatsen [here](https://purchase.aspose.com/buy)

## Vanligt förekommande frågor

**Q: Kan jag använda den här koden i en .NET Core‑applikation?**  
A: Absolut. Aspose.Tasks för .NET stödjer fullt ut .NET Core 3.1 och senare versioner.

**Q: Hur ändrar jag återkommandet till “sista vardagen i månaden”?**  
A: Använd `ByMonthDayRepetition` med `DayPosition = -1` (negativa värden räknas från slutet av månaden) och sätt `WeekDay` därefter.

**Q: Vad händer om återkommande intervallet överskrider projektets kalender?**  
A: API‑et respekterar projektkalendern; förekomster som faller på icke‑arbetsdagar hoppas antingen över eller flyttas baserat på kalenderns inställningar.

**Q: Är det möjligt att ta bort en specifik förekomst av en återkommande uppgift?**  
A: Ja. Efter att ha lagt till den återkommande uppgiften kan du hämta enskilda förekomster via `Task.GetOccurrences()` och ta bort de du inte behöver.

**Q: Hanterar Aspose.Tasks tidszonskillnader automatiskt?**  
A: Biblioteket lagrar datum i UTC; du kan konvertera till lokal tid med standard .NET `DateTime`‑metoder om så behövs.

**Senast uppdaterad:** 2026-03-08  
**Testad med:** Aspose.Tasks 24.11 för .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}