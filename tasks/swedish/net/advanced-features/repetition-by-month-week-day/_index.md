---
date: 2026-04-01
description: Lär dig hur du ställer in återkommande i Aspose.Tasks för .NET, lägger
  till en återkommande uppgift och automatiserar återkommande uppgifter per månad,
  vecka och dag.
keywords:
- how to set recurrence
- add recurring task
- automate recurring tasks
linktitle: Upprepning efter månad, vecka, dag i Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Hur man ställer in återkommande i Aspose.Tasks (Månad, Vecka, Dag)
url: /sv/net/advanced-features/repetition-by-month-week-day/
weight: 26
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hur man ställer in återkommande i Aspose.Tasks (Månad, Vecka, Dag)

## Introduktion

Om du behöver **hur man ställer in återkommande** för uppgifter i ett projekt, ger Aspose.Tasks för .NET dig ett rent, programmeringsmässigt sätt att lägga till återkommande uppgiftsdefinitioner som körs per månad, vecka eller dag. I den här handledningen går vi igenom ett verkligt exempel som visar hur du **lägger till återkommande uppgift**‑poster, **automatiserar återkommande uppgifter**, och hanterar dem direkt från C#‑kod. I slutet är du redo att integrera denna funktion i vilken schemaläggnings‑ eller projektledningslösning som helst.

## Snabba svar
- **Vad betyder “recurrence” i Aspose.Tasks?** Det definierar ett mönster (dagligen, veckovis, månadsvis) som automatiskt skapar uppgiftsinstanser över ett datumintervall.  
- **Vilken primär metod skapar återkommandet?** `RecurringTaskParameters` kombinerat med ett specifikt `RecurrencePattern`.  
- **Behöver jag en licens för att köra den här koden?** En provversion fungerar för utvärdering; en kommersiell licens krävs för produktion.  
- **Kan jag schemalägga veckovisa uppgifter istället för månatliga?** Ja – byt `MonthlyRecurrencePattern` mot `WeeklyRecurrencePattern`.  
- **Vilka .NET‑versioner stöds?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6 och senare.

## Vad är återkommande i Aspose.Tasks?

Återkommande är en uppsättning regler som talar om för Aspose.Tasks att generera uppgiftsinstanser med jämna mellanrum—dagligen, veckovis eller månadsvis—utan att manuellt duplicera dem. Denna funktion är avgörande för projekt som innehåller rutinaktiviteter såsom statusmöten, inspektioner eller underhållsarbete.

## Varför använda återkommande funktioner?

- **Spara tid:** Ingen behov av att kopiera‑klistra uppgifter manuellt.  
- **Minska fel:** Biblioteket garanterar konsekventa datum och varaktigheter.  
- **Flexibilitet:** Kombinera mönster (t.ex. “första söndagen varannan månad”).  
- **Automatisering:** Perfekt för att generera scheman i CI‑pipelines eller rapporteringsverktyg.

## Förutsättningar

1. **Grundläggande förståelse för C#** – du kommer att skriva några rader C#‑kod.  
2. **Aspose.Tasks för .NET installerat** – hämta det från [nedladdningssidan](https://releases.aspose.com/tasks/net/).  
3. **En .mpp‑projektfil** – vi kommer att använda `Project1.mpp` som källfil.

## Importera namnrymder

För att börja, importera de nödvändiga Aspose.Tasks‑namnrymderna:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### Steg 1: Ladda projektfilen

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

Vi skapar en `Project`‑instans som pekar på en befintlig Microsoft Project‑fil.

### Steg 2: Definiera återkommande uppgiftsparametrar

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthWeekDayRepetition
        {
            Position = OrdinalNumber.First,
            WeekDay = DayOfWeek.Sunday,
            RepetitionInterval = 2
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 2, 17, 0, 0)
        }
    }
};
```

Här **skapar vi återkommande uppgifts**‑parametrar:

- **TaskName** – namnet på den genererade uppgiften.  
- **Duration** – hur länge varje förekomst varar.  
- **RecurrencePattern** – ett månadsvis mönster som upprepas varannan månad på den första söndagen.  
- **RecurrenceRange** – start‑ och slutdatum som avgränsar schemat.

### Steg 3: Lägg till den återkommande uppgiften i projektet

```csharp
project.RootTask.Children.Add(parameters);
```

Denna rad **lägger till den återkommande uppgiften** till rotkatalogen i projektets hierarki.

### Steg 4: Spara det uppdaterade projektet

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Projektet sparas som en ny `.mpp`‑fil som nu innehåller det automatiserade schemat.

## Vanliga problem och lösningar

| Problem | Orsak | Lösning |
|-------|--------|-----|
| **Uppgift visas inte** | Återkommande intervall ligger utanför projektets datum. | Verifiera att `Start` och `Finish`‑värdena ligger inom projektkalendern. |
| **Fel veckodag** | `WeekDay`‑enum‑mismatch. | Använd `DayOfWeek.Monday` … `DayOfWeek.Sunday` efter behov. |
| **Licensundantag** | Kör utan en giltig licens i produktion. | Applicera en temporär eller full licens innan sparning. |

## Vanliga frågor

### Q1: Kan jag anpassa återkommande mönster utöver de givna exemplen?

A1: Ja, Aspose.Tasks för .NET erbjuder omfattande anpassningsalternativ för återkommande mönster, så att du kan skräddarsy dem efter dina specifika krav.

### Q2: Finns det en provversion tillgänglig för Aspose.Tasks för .NET?

A2: Ja, du kan få en gratis provversion av Aspose.Tasks för .NET från [releases‑sidan](https://releases.aspose.com/).

### Q3: Hur kan jag få support för Aspose.Tasks för .NET?

A3: Du kan söka hjälp och engagera dig i communityn på [Aspose.Tasks‑forum](https://forum.aspose.com/c/tasks/15).

### Q4: Finns tillfälliga licenser tillgängliga för Aspose.Tasks för .NET?

A4: Ja, du kan skaffa tillfälliga licenser från [köpsidan](https://purchase.aspose.com/temporary-license/) för test och utvärderingsändamål.

### Q5: Var kan jag hitta omfattande dokumentation för Aspose.Tasks för .NET?

A5: Du kan hänvisa till den detaljerade [dokumentation](https://reference.aspose.com/tasks/net/) som finns på Aspose‑webbplatsen för djupgående vägledning om hur du använder biblioteket.

---

**Senast uppdaterad:** 2026-04-01  
**Testad med:** Aspose.Tasks 24.11 för .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}