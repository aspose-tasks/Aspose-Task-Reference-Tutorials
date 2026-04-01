---
date: 2026-04-01
description: Naučte se, jak nastavit opakování v Aspose.Tasks pro .NET, přidat opakující
  se úkol a automatizovat opakující se úkoly podle měsíce, týdne a dne.
keywords:
- how to set recurrence
- add recurring task
- automate recurring tasks
linktitle: Opakování podle měsíce, týdne a dne v Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Jak nastavit opakování v Aspose.Tasks (měsíc, týden, den)
url: /cs/net/advanced-features/repetition-by-month-week-day/
weight: 26
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak nastavit opakování v Aspose.Tasks (Měsíc, Týden, Den)

## Úvod

Pokud potřebujete **jak nastavit opakování** úkolů v projektu, Aspose.Tasks pro .NET vám poskytuje čistý programový způsob, jak přidat definice opakujících se úkolů, které běží po měsíci, týdnu nebo dni. V tomto tutoriálu projdeme reálným příkladem, který vám ukáže, jak **přidat opakující se úkol** položky, **automatizovat opakující se úkoly** a spravovat je přímo z kódu C#. Na konci budete připraveni tuto funkci integrovat do jakéhokoli řešení plánování nebo řízení projektů.

## Rychlé odpovědi
- **Co znamená „opakování“ v Aspose.Tasks?** Definuje vzor (denní, týdenní, měsíční), který automaticky vytváří instance úkolů v rámci časového období.  
- **Která primární metoda vytváří opakování?** `RecurringTaskParameters` v kombinaci se specifickým `RecurrencePattern`.  
- **Potřebuji licenci pro spuštění tohoto kódu?** Zkušební verze funguje pro hodnocení; pro produkci je vyžadována komerční licence.  
- **Mohu naplánovat týdenní úkoly místo měsíčních?** Ano – zaměňte `MonthlyRecurrencePattern` za `WeeklyRecurrencePattern`.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6 a novější.

## Co je opakování v Aspose.Tasks?

Opakování je sada pravidel, která říká Aspose.Tasks, aby generovalo instance úkolů v pravidelných intervalech – denně, týdně nebo měsíčně – bez ručního duplikování. Tato funkce je nezbytná pro projekty, které obsahují rutinní činnosti, jako jsou stavové schůzky, inspekce nebo údržbové práce.

## Proč používat funkce opakování?

- **Ušetříte čas:** Není nutné úkoly ručně kopírovat a vkládat.  
- **Snížíte chyby:** Knihovna zaručuje konzistentní data a trvání.  
- **Flexibilita:** Kombinujte vzory (např. „první neděle každých 2 měsíce“).  
- **Automatizace:** Ideální pro generování rozvrhů v CI pipelinech nebo nástrojích pro reportování.

## Předpoklady

1. **Základní znalost C#** – budete psát několik řádků kódu C#.  
2. **Aspose.Tasks pro .NET nainstalováno** – stáhněte jej ze [download page](https://releases.aspose.com/tasks/net/).  
3. **Soubor projektu .mpp** – použijeme `Project1.mpp` jako zdrojový soubor.

## Importovat jmenné prostory

Pro začátek importujte požadované jmenné prostory Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### Krok 1: Načíst soubor projektu

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

Vytvoříme instanci `Project`, která odkazuje na existující soubor Microsoft Project.

### Krok 2: Definovat parametry opakujícího se úkolu

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

Zde **vytváříme parametry opakujícího se úkolu**:

- **TaskName** – název generovaného úkolu.  
- **Duration** – jak dlouho trvá každá instance.  
- **RecurrencePattern** – měsíční vzor, který se opakuje každé 2 měsíce v první neděli.  
- **RecurrenceRange** – počáteční a koncová data ohraničující rozvrh.

### Krok 3: Přidat opakující se úkol do projektu

```csharp
project.RootTask.Children.Add(parameters);
```

Tento řádek **přidá opakující se úkol** do kořene hierarchie projektu.

### Krok 4: Uložit aktualizovaný projekt

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Projekt je uložen jako nový soubor `.mpp`, který nyní obsahuje automatizovaný rozvrh.

## Časté problémy a řešení

| Problém | Důvod | Řešení |
|-------|--------|-----|
| **Úkol se nezobrazuje** | Rozsah opakování je mimo data projektu. | Ověřte, že hodnoty `Start` a `Finish` jsou v rámci kalendáře projektu. |
| **Špatný den v týdnu** | Neshoda v enumu `WeekDay`. | Použijte `DayOfWeek.Monday` … `DayOfWeek.Sunday` podle potřeby. |
| **Výjimka licence** | Spouštění bez platné licence v produkci. | Aplikujte dočasnou nebo plnou licenci před uložením. |

## Často kladené otázky

### Q1: Mohu přizpůsobit vzor opakování mimo poskytnuté příklady?

**A1:** Ano, Aspose.Tasks pro .NET nabízí rozsáhlé možnosti přizpůsobení vzorů opakování, což vám umožní je upravit podle vašich konkrétních požadavků.

### Q2: Je k dispozici zkušební verze Aspose.Tasks pro .NET?

**A2:** Ano, můžete získat bezplatnou zkušební verzi Aspose.Tasks pro .NET ze [releases page](https://releases.aspose.com/).

### Q3: Jak mohu získat podporu pro Aspose.Tasks pro .NET?

**A3:** Můžete vyhledat pomoc a zapojit se do komunity na [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### Q4: Jsou k dispozici dočasné licence pro Aspose.Tasks pro .NET?

**A4:** Ano, můžete získat dočasné licence na [purchase page](https://purchase.aspose.com/temporary-license/) pro testovací a evaluační účely.

### Q5: Kde mohu najít komplexní dokumentaci pro Aspose.Tasks pro .NET?

**A5:** Můžete se podívat na podrobnou [documentation](https://reference.aspose.com/tasks/net/) dostupnou na webu Aspose pro podrobný návod k využití knihovny.

---

**Poslední aktualizace:** 2026-04-01  
**Testováno s:** Aspose.Tasks 24.11 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}