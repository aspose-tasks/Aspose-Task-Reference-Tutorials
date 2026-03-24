---
date: 2026-03-24
description: Naučte se, jak nastavit výpočty v Aspose.Tasks pro .NET, s příklady výpočtu
  souhrnných hodnot, definování výpočetní formule a konfigurace souhrnu rollup.
linktitle: Calculation Type in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Jak nastavit typ výpočtu v Aspose.Tasks
url: /cs/net/advanced-features/calculation-type/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak nastavit typ výpočtu v Aspose.Tasks

## Úvod

Pokud potřebujete **jak nastavit výpočet** pravidla pro úkoly a souhrnné řádky v souboru Microsoft Project, tento tutoriál vám přesně ukáže, jak to provést pomocí Aspose.Tasks pro .NET. Provedeme kompletní **příklad typu výpočtu**, ukážeme, jak **vypočítat souhrnné hodnoty**, a vysvětlíme, jak **definovat výpočetní vzorec** a **konfigurovat souhrnné seskupení** pro rozšířené atributy. Na konci budete schopni přidat úkol do projektu, nastavit vlastní výpočetní logiku a s jistotou řídit chování seskupování.

## Rychlé odpovědi
- **Jaký je hlavní účel?** Ovládat, jak jsou v souboru Project vypočítány hodnoty úkolů a souhrnů.  
- **Která třída API se používá?** `ExtendedAttributeDefinition` spolu s `CalculationType` a `SummaryRowsCalculationType`.  
- **Mohu použít vzorec?** Ano – nastavte `CalculationType = CalculationType.Formula` a poskytněte řetězec vzorce.  
- **Jak seskupím souhrnné hodnoty?** Použijte `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` a určete `RollupType`, například `Average`.  
- **Potřebuji licenci?** Pro produkční použití je vyžadována platná licence Aspose.Tasks.

## Co je typ výpočtu a jak nastavit výpočet?

`CalculationType` říká Aspose.Tasks, jak vypočítat hodnotu rozšířeného atributu. Můžete zvolit statickou hodnotu, vzorec nebo nechat knihovnu seskupovat hodnoty z podřízených úkolů. Správné nastavení výpočtu je nezbytné, pokud chcete, aby projekt odrážel vlastní obchodní pravidla bez ručních aktualizací.

## Proč použít typ výpočtu k výpočtu souhrnných hodnot?

Když projekt obsahuje souhrnné úkoly, často potřebujete, aby souhrnné řádky zobrazovaly agregovaná data (např. celkové náklady, průměrnou dobu trvání). Konfigurací **vypočítat souhrnné hodnoty** pomocí `SummaryRowsCalculationType` a `RollupType` může Aspose.Tasks automaticky udržovat tyto agregáty v synchronizaci při úpravách jednotlivých úkolů.

## Předpoklady

1. Základní znalost C# a .NET frameworku.  
2. Visual Studio (jakákoli recentní verze) nainstalované na vašem počítači.  
3. Aspose.Tasks pro .NET nainstalovaná – můžete ji stáhnout [zde](https://releases.aspose.com/tasks/net/).  
4. Přístup k oficiální dokumentaci Aspose.Tasks pro .NET pro referenci, dostupná [zde](https://reference.aspose.com/tasks/net/).

## Importujte jmenné prostory

Předtím, než se ponoříme do příkladu, ujistěte se, že jste importovali potřebné jmenné prostory:

```csharp
using Aspose.Tasks;
using System;
```

## Krok 1: Vytvořte nový projekt

Nejprve vytvoříme prázdný objekt `Project`, který bude obsahovat naše úkoly a vlastní atributy.

```csharp
var project = new Project();
```

## Krok 2: Přidejte úkol do projektu

Nyní **add task project** data vytvořením jednoduchého úkolu, nastavením jeho počátečního data a přiřazením jednosměrné (jednodenní) doby trvání.

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## Krok 3: Definujte typ výpočtu pro rozšířený atribut (příklad vzorce)

Zde vytvoříme definici rozšířeného atributu, jehož hodnota je vypočítána ze vzorce. Tento příklad demonstruje **příklad typu výpočtu** a ukazuje, jak **definovat výpočetní vzorec**.

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## Krok 4: Definujte typ výpočtu pro souhrnné řádky (konfigurace seskupení souhrnu)

Dále vytvoříme další definici rozšířeného atributu, která říká Aspose.Tasks **konfigurovat souhrnné seskupení** pomocí typu seskupení *Average*. Toto je typický způsob, jak **vypočítat souhrnné hodnoty** pro náklady, práci nebo vlastní pole.

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## Časté problémy a řešení

| Příznak | Pravděpodobná příčina | Řešení |
|---------|-----------------------|--------|
| Vzorec vrací `null` | Nesprávný odkaz na pole ve vzorci | Ověřte název pole v hranatých závorkách (např. `[Start]` místo `[stARt]`). |
| Souhrnné řádky ukazují 0 | `SummaryRowsCalculationType` není nastaven nebo je špatný `RollupType` | Ujistěte se, že `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` a vyberte vhodný `RollupType`. |
| Projekt se nenačte po přidání atributů | Neshoda mezi definicí atributu a jeho použitím v úkolu | Přidejte definici atributu **před** jeho přiřazením k jakémukoli úkolu. |

## Závěr

V tomto tutoriálu jsme pokryli **jak nastavit výpočetní** pravidla v Aspose.Tasks pro .NET, od vytvoření jednoduchého úkolu po definování typů výpočtu založených na vzorci i seskupení. Ovládnutím těchto nastavení získáte detailní kontrolu nad **vypočítáním souhrnných hodnot**, což umožňuje bohatší analytiku projektu bez ruční práce v tabulkách.

## Často kladené otázky

### Q1: Co je typ výpočtu v Aspose.Tasks?

A1: Typ výpočtu v Aspose.Tasks určuje, jak jsou vypočítávány hodnoty pro úkoly a souhrnné úkoly v projektu, nabízí možnosti jako Formula a Rollup.

### Q2: Jak nastavit typ výpočtu pro rozšířený atribut?

A2: Typ výpočtu pro rozšířený atribut můžete nastavit definováním jeho vlastnosti CalculationType podle potřeby.

### Q3: Mohu přizpůsobit typ výpočtu pro souhrnné řádky v projektu?

A3: Ano, Aspose.Tasks umožňuje specifikovat typ výpočtu pro souhrnné řádky, což vám umožní přizpůsobit výpočty hodnot podle vašich požadavků.

### Q4: Existují různé typy seskupení dostupné pro výpočty souhrnných úkolů?

A4: Ano, Aspose.Tasks poskytuje různé typy seskupení jako Average, Sum a Count pro výpočet hodnot souhrnných úkolů.

### Q5: Kde mohu najít více zdrojů o Aspose.Tasks pro .NET?

A5: Můžete prozkoumat dokumentaci a fóra komunity dostupná na [Aspose.Tasks for .NET](https://reference.aspose.com/tasks/net/) pro komplexní vedení a podporu.

---

**Last Updated:** 2026-03-24  
**Tested With:** Aspose.Tasks for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}