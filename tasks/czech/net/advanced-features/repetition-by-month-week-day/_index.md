---
title: Opakování podle měsíce týdne den v Aspose.Tasks
linktitle: Opakování podle měsíce týdne den v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak nastavit opakování podle měsíce, týdne a dne v Aspose.Tasks pro .NET, abyste mohli efektivně automatizovat opakující se úkoly.
weight: 26
url: /cs/net/advanced-features/repetition-by-month-week-day/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Opakování podle měsíce týdne den v Aspose.Tasks

## Úvod

V oblasti vývoje softwaru, zejména v aplikacích pro řízení projektů, je schopnost efektivně zvládat opakující se úkoly prvořadá. Aspose.Tasks for .NET je výkonná knihovna navržená pro zefektivnění vytváření a správy projektových úkolů, včetně těch opakujících se. Jednou z takových funkcí poskytovaných Aspose.Tasks je schopnost nastavit opakování podle měsíce, týdne a dne, což zajišťuje, že úkoly jsou prováděny podle plánu bez ručního zásahu.

## Předpoklady

Než se ponoříte do složitosti nastavení opakování podle měsíce, týdne a dne pomocí Aspose.Tasks pro .NET, ujistěte se, že máte splněny následující předpoklady:

1. Základní porozumění C#: Pro pochopení a implementaci uvedených příkladů kódu je nezbytná znalost programovacího jazyka C#.
   
2.  Instalace Aspose.Tasks for .NET: Ujistěte se, že jste si stáhli a nainstalovali knihovnu Aspose.Tasks for .NET. Knihovnu můžete získat z[stránka ke stažení](https://releases.aspose.com/tasks/net/).

3. Přístup k souboru .mpp projektu: Připravte si soubor Microsoft Project (.mpp), protože jej budeme používat k demonstraci implementace opakování podle měsíce, týdne a dne.

## Importovat jmenné prostory

Chcete-li začít s používáním Aspose.Tasks for .NET ve vaší aplikaci C#, musíte importovat potřebné jmenné prostory. Můžete to udělat takto:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Pojďme si poskytnutý úryvek kódu rozdělit do několika kroků, abychom každé části důkladně porozuměli.

## Krok 1: Načtěte soubor projektu

```csharp
// Cesta k adresáři dokumentů.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 Tento krok zahrnuje vytvoření nové instance souboru`Project` třídy a načtení existujícího souboru Microsoft Project (`Project1.mpp`) ze zadaného adresáře.

## Krok 2: Definujte parametry opakujících se úloh

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

tomto kroku definujeme parametry pro opakující se úlohu. Uvádíme název úkolu, dobu trvání, vzor opakování (měsíčně) a rozsah opakování (konec k určitému datu).

## Krok 3: Přidejte opakovaný úkol do projektu

```csharp
project.RootTask.Children.Add(parameters);
```

Zde přidáme definované parametry opakující se úlohy ke kořenové úloze projektu.

## Krok 4: Uložte soubor projektu

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Nakonec uložíme upravený soubor projektu s přidanou opakovanou úlohou.

## Závěr

Na závěr, nastavení opakování podle měsíce, týdne a dne v Aspose.Tasks for .NET je přímočarý proces, který umožňuje vývojářům efektivně automatizovat správu opakujících se úkolů v rámci jejich projektů. Podle kroků uvedených v tomto kurzu můžete tuto funkci bez problémů integrovat do svých aplikací C#, čímž ušetříte čas a úsilí při řízení projektů.

## FAQ

###Q1: Mohu přizpůsobit vzor opakování nad rámec uvedených příkladů?

Odpověď 1: Ano, Aspose.Tasks for .NET nabízí rozsáhlé možnosti přizpůsobení vzorů opakování, což vám umožňuje přizpůsobit je vašim konkrétním požadavkům.

###O2: Je k dispozici zkušební verze pro Aspose.Tasks pro .NET?

 A2: Ano, můžete získat bezplatnou zkušební verzi Aspose.Tasks pro .NET z[stránka vydání](https://releases.aspose.com/).

###O3: Jak mohu získat podporu pro Aspose.Tasks pro .NET?

 A3: Můžete vyhledat pomoc a zapojit se do komunity na[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

###Q4: Jsou k dispozici dočasné licence pro Aspose.Tasks pro .NET?

 A4: Ano, můžete získat dočasné licence z[nákupní stránku](https://purchase.aspose.com/temporary-license/) pro účely testování a hodnocení.

###O5: Kde najdu komplexní dokumentaci pro Aspose.Tasks pro .NET?

 A5: Můžete se podívat na podrobné[dokumentace](https://reference.aspose.com/tasks/net/) k dispozici na webových stránkách Aspose, kde najdete podrobné pokyny k využívání knihovny.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
