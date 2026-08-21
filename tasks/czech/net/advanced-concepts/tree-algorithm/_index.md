---
date: 2026-03-19
description: Naučte se, jak přidat zdroj do projektu a vypočítat dobu trvání úkolu
  pomocí algoritmu stromu v Aspose.Tasks a přiřadit zdroje k úkolům v .NET.
linktitle: Add Resource to Project with Tree Algorithm in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Přidat zdroj do projektu pomocí stromového algoritmu v Aspose.Tasks
url: /cs/net/advanced-concepts/tree-algorithm/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání zdroje do projektu pomocí algoritmu stromu v Aspose.Tasks

## Úvod

V tomto tutoriálu objevíte **jak přidat zdroj do projektu** využitím výkonného algoritmu stromu, který poskytuje Aspose.Tasks pro .NET. Provedeme vás vytvořením hierarchie úkolů, výpočtem trvání úkolu a přiřazením zdrojů k úkolům — vše v přehledném, krok za krokem postupu, který můžete zkopírovat do svého řešení.

## Rychlé odpovědi
- **Co dělá algoritmus stromu?** Prochází hierarchii úkolů a efektivně agreguje hodnoty práce.  
- **Jakou hlavní operaci tento průvodce pokrývá?** Přidání zdroje do projektu a aktualizace celkových pracovních hodnot.  
- **Potřebuji licenci?** Pro produkční použití je vyžadována dočasná nebo plná licence.  
- **Mohu to použít s .NET Core?** Ano, Aspose.Tasks podporuje .NET Framework i .NET Core.  
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro základní soubor projektu.

## Co znamená „přidat zdroj do projektu“ v Aspose.Tasks?

Přidání zdroje do projektu znamená vytvoření objektu `Resource`, definování jeho typu (např. práce) a propojení s jedním nebo více úkoly pomocí `ResourceAssignments`. To umožňuje plánovači vypočítat úsilí, náklady a celkové trvání projektu.

## Proč použít algoritmus stromu pro výpočty práce zdrojů?

Algoritmus stromu projde strom úkolů jednou, akumuluje práci od listových úkolů až po jejich souhrnné úkoly. Tento přístup je mnohem efektivnější než iterace přes každý úkol zvlášť, zejména ve velkých projektech s hlubokou hierarchií. Zajišťuje také, že souhrnné hodnoty práce zůstávají synchronizované s podřízenými úkoly.

## Předpoklady

1. **Visual Studio** – jakékoli recentní vydání (2019, 2022 nebo novější).  
2. **Aspose.Tasks for .NET** – stáhněte jej z [zde](https://releases.aspose.com/tasks/net/).  
3. **Základní znalost C#** – měli byste být obeznámeni s třídami, objekty a jednoduchým LINQ.

## Importování jmenných prostorů

Ve svém C# projektu importujte potřebné jmenné prostory pro práci s funkcionalitou Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;
```

Teď rozdělíme každý příklad do několika kroků:

## Krok 1: Načtení souboru projektu

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

Nahrajte soubor projektu do paměti pomocí třídy `Project`.

## Krok 2: Definování hierarchie úkolů

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

Definujte hierarchii úkolů přidáním nadřazených a podřízených úkolů.

## Krok 3: Nastavení vlastností úkolu (včetně **výpočtu trvání úkolu**)

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

Zde **vypočítáváme trvání úkolu** převodem pracovních hodin na objekt `Duration` a následně odvozujeme datum dokončení.

## Krok 4: Přidání zdroje (**přiřazení zdrojů k úkolům**)

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

Tento úryvek **přidává zdroj do projektu** a **přiřazuje zdroje k úkolům**, aby plánovač věděl, kdo je za práci zodpovědný.

## Krok 5: Použití algoritmu stromu

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

Inicializujte třídu `WorkAccumulator` a použijte algoritmus stromu k shromáždění společné práce napříč hierarchií.

## Krok 6: Aktualizace práce úkolu

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

Aktualizujte hodnoty práce úkolů na základě shromážděných informací.

## Časté problémy a tipy

- **Chybějící nastavení kalendáře:** Pokud datum dokončení vypadá nesprávně, ujistěte se, že kalendář projektu je správně nastaven před voláním `GetFinishDateByStartAndWork`.  
- **Neshoda typu zdroje:** Vždy nastavte `Rsc.Type` na `ResourceType.Work` pro zdroje založené na úsilí; jinak může akumulace práce vracet nulu.  
- **Profesionální tip:** Po aktualizaci práce zavolejte `project.Save("UpdatedProject.mpp")`, aby se změny uložily.

## Závěr

Po provedení těchto kroků nyní víte, jak **přidat zdroj do projektu**, **vypočítat trvání úkolu** a **přiřadit zdroje k úkolům** pomocí algoritmu stromu v Aspose.Tasks. Tato metoda zjednodušuje správu hierarchie a udržuje souhrnné hodnoty práce přesné s minimálním množstvím kódu.

## Často kladené otázky

### Q1: Co je Aspose.Tasks pro .NET?

Odpověď: Aspose.Tasks pro .NET je výkonné API, které umožňuje vývojářům programově manipulovat se soubory Microsoft Project pomocí C#.

### Q2: Mohu si stáhnout bezplatnou zkušební verzi Aspose.Tasks pro .NET?

Odpověď: Ano, můžete si stáhnout bezplatnou zkušební verzi Aspose.Tasks pro .NET z [zde](https://releases.aspose.com/).

### Q3: Kde najdu dokumentaci k Aspose.Tasks pro .NET?

Odpověď: Dokumentaci k Aspose.Tasks pro .NET najdete [zde](https://reference.aspose.com/tasks/net/).

### Q4: Jak mohu získat podporu pro Aspose.Tasks pro .NET?

Odpověď: Pro podporu související s Aspose.Tasks pro .NET můžete navštívit [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

### Q5: Je k dispozici dočasná licence pro testovací účely?

Odpověď: Ano, můžete získat dočasnou licenci pro testovací účely z [zde](https://purchase.aspose.com/temporary-license/).

## Často kladené otázky

**Q: Můžu použít tento přístup s existujícím velkým souborem projektu?**  
A: Rozhodně. Algoritmus stromu funguje na jakékoli instanci `Project`, bez ohledu na velikost.

**Q: Aktualizuje algoritmus také hodnoty nákladů?**  
A: Příklad se zaměřuje na práci, ale můžete jej rozšířit na náklady akumulací `Tsk.Cost` podobným způsobem.

**Q: Jaké verze .NET jsou podporovány?**  
A: Aspose.Tasks podporuje .NET Framework 4.5+, .NET Core 3.1+, .NET 5+ a .NET 6+.

**Q: Jak zacházet s více zdroji na úkol?**  
A: Přidejte každý zdroj pomocí `project.ResourceAssignments.Add(task, resource)`; akumulátor automaticky sečte jejich práci.

---

**Last Updated:** 2026-03-19  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}