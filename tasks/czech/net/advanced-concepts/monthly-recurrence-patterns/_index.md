---
date: 2026-03-08
description: Naučte se, jak vytvořit měsíčně se opakující úkol v Aspose.Tasks pro
  .NET pomocí tohoto krok za krokem tutoriálu.
linktitle: How to Create Monthly Recurring Task in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Jak vytvořit měsíční opakující se úkol v Aspose.Tasks
url: /cs/net/advanced-concepts/monthly-recurrence-patterns/
weight: 18
---

NET" keep.

"**Author:** Aspose" keep.

Then closing shortcodes.

Finally backtop button shortcode.

Make sure to preserve all shortcodes exactly.

Now produce final content.

Check for any missed text: after "## Introduction" paragraph we need translation of "In the next sections you’ll see how to set up the project, define the recurrence parameters, and finally save the updated file—all with clear explanations and practical tips."

Translate: "V následujících sekcích uvidíte, jak nastavit projekt, definovat parametry opakování a nakonec uložit aktualizovaný soubor – vše s jasnými vysvětleními a praktickými tipy."

Now produce final markdown.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření měsíčního opakujícího se úkolu pomocí Aspose.Tasks

## Úvod

Aspose.Tasks pro .NET vám umožňuje programově manipulovat se soubory Microsoft Project a jednou z nejčastějších reálných potřeb je **vytvořit měsíční opakující se úkol** v rozvrzích. Ať už vytváříte nástroj pro sledování projektů, automatizujete přidělování zdrojů nebo generujete opakující se úkoly údržby, tento tutoriál vás provede přesné kroky k přidání měsíčního vzoru opakování k úkolu.

V následujících sekcích uvidíte, jak nastavit projekt, definovat parametry opakování a nakonec uložit aktualizovaný soubor – vše s jasnými vysvětleními a praktickými tipy.

## Rychlé odpovědi
- **Co znamená „měsíční opakující se úkol“?** Úkol, který se opakuje podle definovaného vzoru den‑nebo‑týden každý měsíc.  
- **Která třída API zpracovává opakování?** `RecurringTaskParameters` spolu s `MonthlyRecurrencePattern`.  
- **Potřebuji licenci pro spuštění ukázky?** Bezplatná zkušební verze funguje pro hodnocení; licence je vyžadována pro produkci.  
- **Mohu změnit interval?** Ano – nastavte `RepetitionInterval` na počet měsíců mezi výskyty.  
- **Jaké formáty souborů jsou podporovány?** Lze načíst a uložit soubory projektu ve formátech `.mpp` i `.xml`.

## Co je měsíční vzor opakování?

Měsíční vzor opakování říká Microsoft Project (a Aspose.Tasks), jak často by se úkol měl opakovat každý měsíc. Můžete zadat pevný den v měsíci (např. 1.) nebo relativní pozici (např. poslední pátek). API převádí tato pravidla do podkladové struktury souboru Project.

## Proč použít Aspose.Tasks pro toto?

- **Plná kontrola** – Žádná omezení UI; definujete každý aspekt vzoru v kódu.  
- **Cross‑platform** – Funguje na .NET Framework, .NET Core a .NET 5/6+.  
- **Není vyžadován Microsoft Project** – Generujte nebo upravujte soubory na serveru nebo v CI pipeline.  

## Požadavky

Před zahájením se ujistěte, že máte:

- .NET 6 (nebo .NET 5/Framework 4.7+) nainstalován.  
- Balíček NuGet Aspose.Tasks pro .NET přidán do vašeho projektu.  
- Ukázkový soubor projektu (`Project1.mpp`) umístěn ve známé složce (`DataDir`).  

## Importujte jmenné prostory

Nejprve importujte jmenné prostory potřebné pro práci s úkoly a ukládání projektů:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

## Krok 1: Inicializace projektu

Vytvořte instanci `Project`, která ukazuje na váš existující soubor `.mpp`. Tím se soubor načte do paměti, abyste jej mohli upravit.

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

> **Tip:** Pokud soubor neexistuje, Aspose.Tasks automaticky vytvoří nový prázdný projekt.

## Krok 2: Nastavení parametrů opakujícího se úkolu

Definujte podrobnosti opakujícího se úkolu, včetně jeho názvu, trvání a měsíčního vzoru, který chcete použít.

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

- `DayPosition = 1` znamená, že úkol se koná **první den** měsíce.  
- `RepetitionInterval = 2` způsobí, že se úkol opakuje **každé dva měsíce**.  
- `Start` a `Finish` definují celkové časové okno, během kterého je opakování aktivní.

## Krok 3: Přidání parametrů do projektu

Připojte objekt `RecurringTaskParameters` ke kolekci podřízených úkolů kořenového úkolu. Tím se v hierarchii projektu vytvoří opakující se úkol.

```csharp
project.RootTask.Children.Add(parameters);
```

## Krok 4: Uložení projektu

Uložte změny tím, že projekt uložíte do nového souboru. Můžete zvolit libovolný podporovaný formát; zde používáme nativní formát `.mpp`.

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Po spuštění kódu otevřete výsledný soubor v Microsoft Project a uvidíte měsíční opakující se úkol, který jste právě vytvořili.

## Časté problémy a řešení

| Problém | Příčina | Řešení |
|-------|-------|-----|
| Úkol se po uložení nezobrazuje | Projekt není v UI obnoven | Znovu otevřete soubor nebo před uložením zavolejte `project.UpdateTaskLinks()` . |
| Špatné datum zahájení | `Start` nastaven na víkend | Použijte `DateTime`, který spadá na pracovní den, nebo upravte kalendář. |
| Interval opakování ignorován | Použití `ByMonthDayRepetition` s `DayPosition` = 0 | Ujistěte se, že `DayPosition` je 1‑31. |

## Závěr

Podle těchto kroků nyní víte, jak **vytvořit měsíční opakující se úkol** v rozvrzích pomocí Aspose.Tasks pro .NET. API vám poskytuje podrobnou kontrolu nad intervaly opakování, rozsahy start/finish a konkrétním vzorem dne, což vám umožní automatizovat složité scénáře plánování projektů.

## Často kladené otázky

### Q1: Je Aspose.Tasks kompatibilní se všemi verzemi souborů Microsoft Project?

A1: Aspose.Tasks podporuje různé verze souborů Microsoft Project, včetně MPP, MPT, XML a MPX.

### Q2: Mohu dále přizpůsobit vzor opakování?

A2: Ano, Aspose.Tasks poskytuje rozsáhlé možnosti pro přizpůsobení vzorů opakování, včetně denních, týdenních, měsíčních a ročních.

### Q3: Je k dispozici bezplatná zkušební verze Aspose.Tasks?

A3: Ano, můžete získat bezplatnou zkušební verzi Aspose.Tasks na webu [zde](https://releases.aspose.com/).

### Q4: Jak mohu získat podporu pro Aspose.Tasks?

A4: Můžete požádat o pomoc a zapojit se do diskusí na [fóru Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Q5: Kde mohu zakoupit licenci pro Aspose.Tasks?

A5: Licenci pro Aspose.Tasks můžete zakoupit na webu [zde](https://purchase.aspose.com/buy)

## Často kladené otázky

**Q: Mohu použít tento kód v aplikaci .NET Core?**  
A: Rozhodně. Aspose.Tasks pro .NET plně podporuje .NET Core 3.1 a novější verze.

**Q: Jak změním opakování na „poslední pracovní den v měsíci“?**  
A: Použijte `ByMonthDayRepetition` s `DayPosition = -1` (záporné hodnoty počítají od konce měsíce) a nastavte `WeekDay` podle potřeby.

**Q: Co se stane, pokud rozsah opakování přesáhne kalendář projektu?**  
A: API respektuje kalendář projektu; výskyty padající na nepracovní dny jsou buď přeskočeny, nebo přesunuty podle nastavení kalendáře.

**Q: Je možné smazat konkrétní výskyt opakujícího se úkolu?**  
A: Ano. Po přidání opakujícího se úkolu můžete získat jednotlivé výskyty pomocí `Task.GetOccurrences()` a smazat ty, které nepotřebujete.

**Q: Zpracovává Aspose.Tasks automaticky rozdíly časových pásem?**  
A: Knihovna ukládá data v UTC; pokud je potřeba, můžete je převést na místní čas pomocí standardních metod .NET `DateTime`.

---

**Last Updated:** 2026-03-08  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}