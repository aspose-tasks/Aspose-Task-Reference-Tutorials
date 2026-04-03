---
date: 2026-04-03
description: Naučte se, jak pomocí Aspose.Tasks přidat opakující se úkol do projektu
  a uložit projekt jako MPP. Tento průvodce krok za krokem ukazuje funkci Opakování
  podle roku, týdne a dne.
keywords:
- how to use aspose.tasks
- add recurring task project
- save project as mpp
linktitle: Opakování podle roku, týdne a dne v Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Jak používat Aspose.Tasks – Opakování podle roku, týdne a dne
url: /cs/net/advanced-features/repetition-by-year-week-day/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Opakování podle roku, týdne a dne v Aspose.Tasks

## Úvod

Když potřebujete **jak používat Aspose.Tasks** pro zpracování složitých opakujících se rozvrhů, knihovna vám poskytuje detailní kontrolu nad ročními vzory. V tomto tutoriálu projdeme vytvoření úkolu, který se opakuje v konkrétní den v týdnu konkrétního měsíce během několika let. Na konci budete schopni **přidávat opakující se úkoly do projektu** a **uložit projekt jako MPP** pomocí několika řádků C#.

## Rychlé odpovědi
- **Co znamená „Opakování podle roku, týdne a dne“?** Opakuje úkol ve vybraný den v týdnu (např. první neděli) daného měsíce každý rok.  
- **Které verze .NET jsou podporovány?** Všechny moderní verze .NET Framework a .NET Core/5/6.  
- **Potřebuji licenci pro spuštění kódu?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.  
- **Mohu změnit rozsah opakování?** Ano – můžete nastavit počáteční datum, koncové datum nebo pevný počet výskytů.  
- **Je výstupem soubor MPP?** Rozhodně – projekt je uložen jako soubor MPP připravený pro Microsoft Project.

## Co je funkce „Opakování podle roku, týdne a dne“?

Funkce vám umožňuje definovat roční opakování, které cílí na konkrétní **den v týdnu** (např. neděle) a **pozici** v měsíci (první, druhá, poslední atd.). To je ideální pro úkoly jako čtvrtletní revize, roční audity nebo jakoukoli událost, která následuje kalendářní rytmus.

## Proč používat Aspose.Tasks pro opakující se úkoly?

- **Přesnost** – Plná kontrola nad měsíci, dny v týdnu a pořadovými pozicemi.  
- **Kompatibilita** – Generuje nativní soubory MPP, které se otevřou bez problémů v Microsoft Project.  
- **Žádný COM interop** – Čisté .NET API, není potřeba instalace Office.  
- **Škálovatelnost** – Funguje pro malé projekty i pro podnikové rozvrhy.

## Předpoklady

Předtím, než se ponoříte do kódu, ujistěte se, že máte:

1. **Základní znalosti .NET** – Znalost C# a objektově orientovaných konceptů.  
2. **Aspose.Tasks pro .NET** – Stáhněte jej z [download link](https://releases.aspose.com/tasks/net/) a přidejte DLL do svého projektu.  
3. **Přístup k oficiální dokumentaci** – [documentation](https://reference.aspose.com/tasks/net/) obsahuje podrobné informace o všech třídách.  
4. **Vývojové IDE** – Visual Studio, Rider nebo jakýkoli kompatibilní .NET editor.

Nyní, když jste připraveni, podívejme se na implementaci.

## Jak používat Aspose.Tasks pro opakující se úkoly

### Importování potřebných jmenných prostorů

Nejprve přiveďte požadované jmenné prostory do rozsahu, abyste mohli pracovat s projekty, úkoly a možnostmi ukládání.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### Krok 1: Inicializace projektu a parametrů úkolu

Vytvořte novou instanci `Project` a poté definujte objekt `RecurringTaskParameters`, který popisuje vzor opakování.

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

> **Tip:** Upravit `Month`, `WeekDay` a `Position` tak, aby odpovídaly vašemu reálnému plánu.

### Krok 2: Přidání parametrů do projektu

Vložte definici opakujícího se úkolu do kořene projektu.

```csharp
project.RootTask.Children.Add(parameters);
```

### Krok 3: Uložení projektu jako MPP

Nakonec uložte projekt do souboru MPP, aby jej bylo možné otevřít v Microsoft Project nebo jakémkoli kompatibilním prohlížeči.

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearWeekDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

> Toto demonstruje **uložit projekt jako mpp** v jediném řádku kódu.

## Časté problémy a řešení

| Příznak | Pravděpodobná příčina | Oprava |
|---------|-----------------------|--------|
| Žádné úkoly se neobjeví po otevření souboru MPP | Data rozsahu opakování jsou mimo kalendář projektu | Ověřte, že data `Start` a `Finish` spadají do pracovního času projektu |
| Výjimka `ArgumentNullException` při `Add` | `parameters` je null nebo není plně inicializován | Ujistěte se, že jsou nastaveny všechny požadované vlastnosti (TaskName, Duration, RecurrencePattern) |
| Špatně vybraný den v týdnu | Neshoda hodnoty výčtu `WeekDay` | Použijte `DayOfWeek.Monday` … `DayOfWeek.Sunday` podle potřeby |

## Často kladené otázky

**Q: Mohu přizpůsobit vzor opakování mimo uvedený příklad?**  
A: Ano, Aspose.Tasks vám umožní kombinovat `MonthlyRecurrencePattern`, `WeeklyRecurrencePattern` nebo i vlastní objekty `RecurrenceRange`, aby vyhovovaly libovolnému plánu.

**Q: Je Aspose.Tasks pro .NET kompatibilní s jiným softwarem pro řízení projektů?**  
A: Rozhodně – knihovna čte a zapisuje formáty MPP, XML a Primavera, což umožňuje plynulou výměnu dat.

**Q: Jak mohu zvládat výjimky nebo úpravy opakujících se úkolů?**  
A: Použijte třídu `ExceptionTask` k vytvoření výjimek pro konkrétní výskyty, nebo upravte `RecurringTaskParameters` a projekt znovu uložte.

**Q: Podporuje Aspose.Tasks řešení založená na cloudu?**  
A: Ano, můžete spouštět API v Azure Functions, AWS Lambda nebo jakékoli .NET‑kompatibilní cloudové službě.

**Q: Je k dispozici zkušební verze Aspose.Tasks pro .NET?**  
A: Ano, můžete získat bezplatnou zkušební verzi Aspose.Tasks pro .NET na [webu](https://releases.aspose.com/), která vám umožní prozkoumat jeho funkce před rozhodnutím o koupi.

**Q: Jak přidat opakující se úkol do existujícího projektu, aniž bych přepsal ostatní data?**  
A: Načtěte existující projekt pomocí `new Project("Existing.mpp")`, přidejte `RecurringTaskParameters` do `RootTask.Children` a poté soubor `Save`.

## Závěr

Když ovládnete **jak používat Aspose.Tasks** pro scénář **Opakování podle roku, týdne a dne**, získáte schopnost **přidávat opakující se úkoly do projektu**, které se dokonale shodují s reálnými kalendáři, a **uložit projekt jako MPP** pro bezproblémovou spolupráci. Začleňte tyto úryvky do svých vlastních řešení, abyste zvýšili přesnost plánování a snížili ruční úsilí.

---

**Last Updated:** 2026-04-03  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}