---
title: Denní opakování kalendáře v Aspose.Tasks
linktitle: Denní opakování kalendáře v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se vytvářet opakující se úkoly s denním opakováním kalendáře v Aspose.Tasks pro .NET. Zvyšte efektivitu řízení projektů bez námahy.
type: docs
weight: 25
url: /cs/net/calendar-scheduling/daily-calendar-repetition/
---
## Úvod

 Aspose.Tasks for .NET poskytuje výkonnou sadu nástrojů pro správu úloh a projektů programově. Jednou z jeho pozoruhodných funkcí je schopnost efektivně zvládat každodenní opakování kalendáře. V tomto tutoriálu prozkoumáme, jak využít`DailyCalendarRepetition` třídy spolu s dalšími relevantními třídami k vytváření opakujících se úkolů s denním opakováním na základě zadaného kalendáře.

## Předpoklady

Než začneme, ujistěte se, že máte následující nastavení:

1.  Instalace: Ujistěte se, že máte nainstalované Aspose.Tasks for .NET. Pokud ne, můžete si jej stáhnout z[tady](https://releases.aspose.com/tasks/net/).

2. Import jmenného prostoru: Importujte potřebné jmenné prostory do svého projektu:

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

using Aspose.Tasks.Saving;

```

## Krok 1: Inicializujte projekt

Nejprve musíme načíst existující projekt nebo vytvořit nový, se kterým budeme pracovat:

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Krok 2: Definujte kalendář

Dále vytvoříme kalendář s 24hodinovým trváním a přiřadíme jej k projektu:

```csharp
var calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(calendar);
```

## Krok 3: Nastavte parametry opakujících se úloh

Nyní nastavíme parametry pro naši opakovanou úlohu. Definujeme jeho název, trvání, vzor opakování a rozsah:

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new DailyRecurrencePattern
    {
        Repetition = new DailyCalendarRepetition { RepetitionInterval = 1 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 2, 0, 0, 0),
            Finish = new DateTime(2018, 7, 8, 16, 0, 0)
        }
    }
};
```

## Krok 4: Nastavte kalendář pro úkol

Přidružte definovaný kalendář k úkolu:

```csharp
parameters.SetCalendar(project, "24 Hours");
```

## Krok 5: Přidejte úkol do projektu

Přidejte do projektu úlohu s definovanými parametry:

```csharp
project.RootTask.Children.Add(parameters);
```

## Krok 6: Uložte projekt

Nakonec uložte projekt s přidaným opakovaným úkolem:

```csharp
project.Save(OutDir + "CanAddRecurringTask_Days_CalendarDays_24h_Test_out.mpp", SaveFileFormat.Mpp);
```

Nyní jste úspěšně vytvořili projekt s opakujícím se úkolem, který se má denně opakovat na základě 24hodinového kalendáře pomocí Aspose.Tasks for .NET!

## Závěr

tomto tutoriálu jsme ukázali, jak využít Aspose.Tasks pro .NET k efektivnímu zpracování denních opakování kalendáře. Dodržováním těchto kroků můžete plynule integrovat opakující se úkoly do svých projektů a zvýšit tak produktivitu a organizaci.

## FAQ

### Q1: Mohu upravit dobu trvání každého opakování?

A1: Ano, můžete upravit dobu trvání každého opakování podle vašich požadavků úpravou parametrů v kódu.

### Q2: Je možné nastavit různé kalendáře pro různé úkoly v rámci stejného projektu?

A2: Absolutně, Aspose.Tasks umožňuje přiřadit konkrétní kalendáře k jednotlivým úkolům a nabízí flexibilitu při plánování.

### Q3: Podporuje Aspose.Tasks jiné vzorce opakování kromě každodenního?

Odpověď 3: Ano, Aspose.Tasks poskytuje širokou škálu vzorců opakování, jako je týdenní, měsíční, roční atd., které uspokojí potřeby různých projektů.

### Q4: Mohu si představit opakující se úkoly vytvořené pomocí Aspose.Tasks?

A4: Jistě, Aspose.Tasks nabízí možnosti vizualizace, které vám pomohou efektivně analyzovat a sledovat opakující se úkoly.

### Q5: Je k dispozici zkušební verze pro Aspose.Tasks?

 A5: Ano, můžete využít bezplatnou zkušební verzi Aspose.Tasks od[tady](https://releases.aspose.com/) k prozkoumání jeho funkcí před nákupem.