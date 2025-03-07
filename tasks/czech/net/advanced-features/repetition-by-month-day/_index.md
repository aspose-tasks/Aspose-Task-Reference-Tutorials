---
title: Opakování po měsíčním dni v Aspose.Tasks
linktitle: Opakování po měsíčním dni v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se spravovat opakující se úkoly v projektech .NET pomocí Aspose.Tasks. Průvodce krok za krokem pro zvládnutí opakování podle měsíce dne.
weight: 25
url: /cs/net/advanced-features/repetition-by-month-day/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Opakování po měsíčním dni v Aspose.Tasks

## Úvod

V oblasti vývoje .NET představuje Aspose.Tasks výkonný nástroj pro správu projektových úkolů a harmonogramů. Nabízí nepřeberné množství funkcí pro zefektivnění pracovních postupů projektového řízení, včetně zpracování opakujících se úkolů. Opakování po dnech měsíce je běžným požadavkem při plánování projektu a Aspose.Tasks poskytuje robustní podporu pro tento scénář.

## Předpoklady

Než se ponoříte do výukového programu, ujistěte se, že máte následující předpoklady:

1. Základní porozumění C#: Pro pochopení pojmů probíraných v tomto tutoriálu je nezbytná znalost programovacího jazyka C#.
2. Instalace Aspose.Tasks pro .NET: Ujistěte se, že jste nainstalovali Aspose.Tasks pro .NET. Můžete si jej stáhnout z[tady](https://releases.aspose.com/tasks/net/).
3. Integrované vývojové prostředí (IDE): Pro usnadnění kódování mějte na svém systému nainstalované IDE, jako je Visual Studio.

## Importovat jmenné prostory

Ve svém projektu C# importujte potřebné jmenné prostory pro přístup k funkcím Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

Rozdělme poskytnutý příklad kódu do formátu průvodce krok za krokem:

## Krok 1: Načtěte soubor projektu

```csharp
// Cesta k adresáři dokumentů.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

 Tento řádek kódu inicializuje novou instanci souboru`Project` třídy, načte se soubor projektu s názvem "Project1.mpp".

## Krok 2: Definujte parametry opakujících se úloh

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

Tato část definuje parametry pro opakovaný úkol, včetně jeho názvu, trvání, vzoru opakování a rozsahu opakování.

## Krok 3: Přidejte úkol do projektu

```csharp
project.RootTask.Children.Add(parameters);
```

Zde přidáme parametry opakujícího se úkolu do projektu.

## Krok 4: Uložte soubor projektu

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

Nakonec se upravený projekt uloží s přidaným opakovaným úkolem.

## Závěr

tomto tutoriálu jsme prozkoumali, jak v Aspose.Tasks pro .NET zvládnout opakování po měsíčním dni. Dodržováním uvedených kroků můžete efektivně spravovat opakující se úkoly v rámci plánů projektu.

## FAQ

### Q1: Je Aspose.Tasks kompatibilní se všemi verzemi .NET?

Odpověď 1: Aspose.Tasks podporuje různé verze rozhraní .NET a zajišťuje kompatibilitu v různých prostředích.

### Q2: Mohu dále přizpůsobit vzor opakování?

Odpověď 2: Ano, Aspose.Tasks nabízí rozsáhlé možnosti přizpůsobení pro definování vzorců opakování podle konkrétních požadavků projektu.

### Q3: Poskytuje Aspose.Tasks podporu pro další funkce projektového řízení?

Odpověď 3: Aspose.Tasks rozhodně nabízí širokou škálu funkcí pro správu projektů, včetně sledování úkolů, přidělování zdrojů a generování Ganttova diagramu.

### Q4: Je k dispozici zkušební verze pro Aspose.Tasks?

 A4: Ano, můžete využít bezplatnou zkušební verzi[tady](https://releases.aspose.com/) prozkoumat možnosti Aspose.Tasks před rozhodnutím o nákupu.

### Otázka 5: Kde mohu požádat o pomoc, pokud narazím na problémy nebo mám dotazy?

 A5: Můžete navštívit[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) hledat podporu od komunity nebo týmu Aspose.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
