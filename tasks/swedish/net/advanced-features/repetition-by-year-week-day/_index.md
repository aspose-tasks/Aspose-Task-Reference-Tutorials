---
date: 2026-04-03
description: Lär dig hur du använder Aspose.Tasks för att lägga till återkommande
  uppgifter i ett projekt och spara projektet som MPP. Denna guide visar funktionen
  Upprepning per år, vecka och dag steg för steg.
keywords:
- how to use aspose.tasks
- add recurring task project
- save project as mpp
linktitle: Upprepning efter år, vecka, dag i Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Hur man använder Aspose.Tasks – Upprepning per år, vecka, dag
url: /sv/net/advanced-features/repetition-by-year-week-day/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Upprepning per år veckodag i Aspose.Tasks

## Introduktion

När du behöver **how to use Aspose.Tasks** för att hantera komplexa återkommande scheman, ger biblioteket dig fin‑grained control över årliga mönster. I den här handledningen går vi igenom hur du skapar en uppgift som upprepas på en specifik veckodag i en viss månad, över flera år. I slutet kommer du att kunna **add recurring task project** poster och **save project as MPP** med bara några rader C#.

## Snabba svar
- **Vad betyder “Repetition by Year Week Day”?** Det upprepar en uppgift på en vald veckodag (t.ex. första söndag) i en given månad varje år.  
- **Vilka .NET-versioner stöds?** Alla moderna .NET Framework- och .NET Core/5/6-versioner.  
- **Behöver jag en licens för att köra koden?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.  
- **Kan jag ändra återkommande intervall?** Ja – du kan ange ett startdatum, slutdatum eller ett fast antal förekomster.  
- **Är utdata en MPP-fil?** Absolut – projektet sparas som en MPP-fil klar för Microsoft Project.

## Vad är funktionen “Repetition by Year Week Day”?

Funktionen låter dig definiera en årlig återkomst som riktar sig mot en specifik **day of the week** (t.ex. Sunday) och en **position** inom månaden (första, andra, sista osv.). Detta är idealiskt för uppgifter som kvartalsvisa granskningar, årliga revisioner eller någon händelse som följer ett kalenderbaserat rytm.

## Varför använda Aspose.Tasks för återkommande uppgifter?

- **Precision** – Full kontroll över månader, veckodagar och ordningspositioner.  
- **Kompatibilitet** – Genererar inhemska MPP-filer som öppnas felfritt i Microsoft Project.  
- **Ingen COM-interoperabilitet** – Ren .NET API, ingen behov av Office-installationer.  
- **Skalbarhet** – Fungerar för små projekt och företagsnivåplaner lika väl.

## Förutsättningar

1. **Grundläggande .NET-kunskap** – Bekantskap med C# och objekt‑orienterade koncept.  
2. **Aspose.Tasks for .NET** – Ladda ner det från [download link](https://releases.aspose.com/tasks/net/) och lägg till DLL-filen i ditt projekt.  
3. **Tillgång till den officiella dokumentationen** – [documentation](https://reference.aspose.com/tasks/net/) innehåller utförliga detaljer om alla klasser.  
4. **En utvecklings‑IDE** – Visual Studio, Rider eller någon kompatibel .NET‑redigerare.

Nu när du är klar, låt oss se implementeringen.

## Så använder du Aspose.Tasks för återkommande uppgifter

### Importera nödvändiga namnrymder

Först, importera de nödvändiga namnrymderna så att du kan arbeta med projekt, uppgifter och sparalternativ.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### Steg 1: Initiera projekt- och uppgiftsparametrar

Skapa en ny `Project`-instans och definiera sedan ett `RecurringTaskParameters`-objekt som beskriver återkommandemönstret.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearWeekDayRepetition
        {
            Month = Month.July, WeekDay = DayOfWeek.Sunday, Position = OrdinalNumber.First
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 31, 17, 0, 0)
        }
    }
};
```

> **Pro tip:** Justera `Month`, `WeekDay` och `Position` så att de matchar ditt verkliga schema.

### Steg 2: Lägg till parametrar i projektet

Infoga den återkommande uppgiftsdefinitionen i projektets rot.

```csharp
project.RootTask.Children.Add(parameters);
```

### Steg 3: Spara projekt som MPP

Slutligen, spara projektet till en MPP-fil så att den kan öppnas i Microsoft Project eller någon kompatibel visare.

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearWeekDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

> Detta demonstrerar **save project as mpp** i en enda kodrad.

## Vanliga problem och lösningar

| Symptom | Trolig orsak | Åtgärd |
|---------|--------------|--------|
| Inga uppgifter visas efter att MPP-filen öppnats | Återkommande intervalldatum ligger utanför projektkalendern | Verifiera att `Start` och `Finish`-datumen ligger inom projektets arbetstid |
| Undantag `ArgumentNullException` på `Add` | `parameters` är null eller inte fullständigt initierad | Säkerställ att alla obligatoriska egenskaper (TaskName, Duration, RecurrencePattern) är satta |
| Fel veckodag vald | `WeekDay` enum‑värde matchar inte | Använd `DayOfWeek.Monday` … `DayOfWeek.Sunday` vid behov |

## Vanliga frågor

**Q: Kan jag anpassa återkommandemönstret utöver det givna exemplet?**  
A: Ja, Aspose.Tasks låter dig kombinera `MonthlyRecurrencePattern`, `WeeklyRecurrencePattern` eller till och med anpassade `RecurrenceRange`‑objekt för att passa vilket schema som helst.

**Q: Är Aspose.Tasks för .NET kompatibel med annan projektledningsprogramvara?**  
A: Absolut – biblioteket läser och skriver MPP-, XML- och Primavera-format, vilket möjliggör smidig datautbyte.

**Q: Hur kan jag hantera undantag eller ändringar i återkommande uppgifter?**  
A: Använd klassen `ExceptionTask` för att skapa överskrivningar för specifika förekomster, eller redigera `RecurringTaskParameters` och spara projektet igen.

**Q: Stöder Aspose.Tasks molnbaserade lösningar?**  
A: Ja, du kan köra API:et i Azure Functions, AWS Lambda eller någon .NET‑kompatibel molntjänst.

**Q: Finns det en provversion av Aspose.Tasks för .NET?**  
A: Ja, du kan få en gratis provversion av Aspose.Tasks för .NET från [website](https://releases.aspose.com/), vilket låter dig utforska funktionerna innan du fattar ett köpbeslut.

**Q: Hur lägger jag till en återkommande uppgift i ett befintligt projekt utan att skriva över annan data?**  
A: Ladda det befintliga projektet med `new Project("Existing.mpp")`, lägg till `RecurringTaskParameters` i `RootTask.Children` och spara sedan filen med `Save`.

## Slutsats

Genom att behärska **how to use Aspose.Tasks** för **Repetition by Year Week Day**‑scenariot får du möjlighet att **add recurring task project** poster som exakt matchar verkliga kalendrar och **save project as MPP** för sömlöst samarbete. Integrera dessa kodsnuttar i dina egna lösningar för att förbättra schemaläggningsnoggrannheten och minska manuellt arbete.

---

**Senast uppdaterad:** 2026-04-03  
**Testad med:** Aspose.Tasks 24.12 för .NET  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}