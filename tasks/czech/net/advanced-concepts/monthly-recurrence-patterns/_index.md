---
title: Zpracování měsíčních vzorců opakování v Aspose.Tasks
linktitle: Zpracování měsíčních vzorců opakování v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak zacházet se vzorci měsíčního opakování v Aspose.Tasks pro .NET pomocí tohoto podrobného návodu.
weight: 18
url: /cs/net/advanced-concepts/monthly-recurrence-patterns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zpracování měsíčních vzorců opakování v Aspose.Tasks

## Úvod

Aspose.Tasks for .NET je výkonné rozhraní API, které umožňuje vývojářům programově manipulovat se soubory aplikace Microsoft Project. Jednou ze základních funkcí, které nabízí, je schopnost efektivně zvládat opakující se úkoly. V tomto tutoriálu se krok za krokem ponoříme do toho, jak pracovat s měsíčními vzory opakování pomocí Aspose.Tasks.

## Předpoklady

Než začneme, ujistěte se, že máte nainstalované následující předpoklady:

## Importovat jmenné prostory

Nejprve se ujistěte, že jste do svého projektu .NET importovali potřebné jmenné prostory:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

Nyní si rozdělme proces zpracování měsíčních vzorců opakování do několika kroků:

## Krok 1: Inicializujte projekt

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## Krok 2: Nastavte parametry opakujících se úloh

Definujte parametry pro opakovanou úlohu, včetně názvu úlohy, trvání a vzoru opakování:

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

## Krok 3: Přidejte parametry do projektu

```csharp
project.RootTask.Children.Add(parameters);
```

## Krok 4: Uložte projekt

Uložte upravený projekt s opakovaným úkolem:

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

## Závěr

Zpracování měsíčních vzorců opakování v Aspose.Tasks pro .NET je přímočaré a efektivní. Podle kroků uvedených v tomto kurzu můžete snadno vytvářet opakující se úlohy s konkrétními měsíčními intervaly a rozsahy opakování.

## FAQ

### Q1: Je Aspose.Tasks kompatibilní se všemi verzemi souborů aplikace?

A1: Aspose.Tasks podporuje různé verze souborů aplikace Microsoft Project, včetně MPP, MPT, XML a MPX.

### Q2: Mohu dále přizpůsobit vzor opakování?

A2: Ano, Aspose.Tasks poskytuje rozsáhlé možnosti pro přizpůsobení vzorců opakování, včetně denních, týdenních, měsíčních a ročních.

### Q3: Je k dispozici bezplatná zkušební verze pro Aspose.Tasks?

 A3: Ano, můžete získat bezplatnou zkušební verzi Aspose.Tasks z webu[tady](https://releases.aspose.com/).

### Q4: Jak mohu získat podporu pro Aspose.Tasks?

 A4: Můžete vyhledat pomoc a zúčastnit se diskuzí na webu[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Q5: Kde mohu zakoupit licenci pro Aspose.Tasks?

 A5: Můžete si zakoupit licenci pro Aspose.Tasks z webu[tady](https://purchase.aspose.com/buy)
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
