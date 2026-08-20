---
date: 2026-03-14
description: Naučte se, jak filtrovat úkoly pomocí operace NOT v Aspose.Tasks pro
  .NET, a objevte, jak použít filtr NOT s aplikovanou podmínkou NOT pro flexibilní
  dotazy na úkoly.
linktitle: Working with NOT Operation in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Filtr úkolů, ne operace v Aspose.Tasks
url: /cs/net/advanced-concepts/not-operation/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# filtr úkolů pomocí NOT operace v Aspose.Tasks

## Úvod

V tomto tutoriálu se naučíte **jak filtrovat úkoly pomocí NOT operace** pomocí Aspose.Tasks pro .NET. NOT operace vám umožní obrátit podmínku filtru, takže můžete vybrat každý úkol, který **nesplňuje** konkrétní kritérium. Tato schopnost je nezbytná, když potřebujete vyloučit určité položky—například úkoly bez hodnoty—nebo když chcete vytvořit složité dotazy bez psaní dalšího kódu.

## Rychlé odpovědi
- **Co dělá NOT operace?** Inverzuje podmínku filtru a vrací položky, které neprojdou původním testem.  
- **Proč používat filtr úkolů pomocí NOT operace?** Zjednodušuje logiku vylučování a udržuje kód čitelný.  
- **Ve kterém jmenném prostoru se nachází třída NOT?** `Aspose.Tasks.Util`.  
- **Potřebuji licenci pro produkční použití?** Ano, pro ne‑zkušební použití je vyžadována platná licence Aspose.Tasks.  
- **Mohu kombinovat NOT s dalšími podmínkami?** Samozřejmě—kombinujte ji s `AndCondition`, `OrCondition` atd.

## Co je filtr úkolů pomocí NOT operace?
**Filtrace úkolů pomocí NOT operace** je logická negace aplikovaná na filtr úkolů. Místo výběru úkolů, které splňují podmínku, vybírá ty, které *nesplňují* podmínku. To je zvláště užitečné, když chcete ignorovat úkoly s prázdnými poli, konkrétními stavy nebo jakýmkoli jiným atributem, který chcete vyloučit.

## Proč použít NOT podmínku při filtrování úkolů?
Použití **NOT podmínky** snižuje potřebu několika průchodů vašimi projektovými daty. Umožňuje psát stručný, udržovatelný kód a zlepšuje výkon delegováním vyhodnocení na optimalizovaný engine Aspose.Tasks.

## Předpoklady

1. Visual Studio: Potřebujete funkční instalaci Visual Studio, abyste mohli sledovat příklady kódu.  
2. Aspose.Tasks pro .NET: Stáhněte a nainstalujte knihovnu Aspose.Tasks pro .NET z [webu](https://releases.aspose.com/tasks/net/).  
3. Základní znalost C#: Znalost programovacího jazyka C# vám pomůže pochopit ukázky kódu.

## Import jmenných prostorů

Nejprve importujeme potřebné jmenné prostory pro náš kód:

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## Krok 1: Nastavení projektu a úkolů

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

Začínáme načtením souboru projektu s názvem **Project2.mpp** pomocí třídy `Project` poskytované knihovnou Aspose.Tasks. Ujistěte se, že soubor projektu existuje ve zadaném adresáři.

## Krok 2: Shromáždění úkolů projektu

```csharp
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

Zde vytvoříme objekt `ChildTasksCollector`, který shromáždí všechny úkoly v projektu. Poté použijeme `TaskUtils.Apply` k procházení hierarchie úkolů projektu a sběru každého podúkolu.

## Krok 3: Definování podmínky filtru

```csharp
var filter = new NullCondition();
```

Definujeme podmínku filtru pomocí vlastní třídy nazvané `NullCondition`. Tato podmínka vybírá úkoly, které mají **null** hodnotu.  

> **Tip:** Nahraďte `NullCondition` jinou podmínkou (např. `EqualsCondition`), pokud chcete cílit na jiné atributy.

## Krok 4: Použití NOT operace

```csharp
var condition = new Not<Task>(filter);
```

Použijeme **NOT operaci** na podmínku filtru pomocí třídy `Not<T>` poskytované knihovnou Aspose.Tasks. Tím se obrátí původní podmínka, takže filtr nyní vybírá úkoly, které **nemají** null hodnotu. Toto je jádro techniky **jak použít NOT filtr**.

## Krok 5: Filtrování úkolů

```csharp
List<Task> collection = Filter(coll.Tasks, condition);
```

Filtrování shromážděných úkolů na základě aplikované podmínky pomocí vlastní metody `Filter`. Metoda přijímá výčtovou kolekci úkolů a podmínku filtru a vrací seznam úkolů, které splňují **aplikovanou NOT podmínku**.

## Krok 6: Zpracování filtrovaných úkolů

```csharp
foreach (var task in collection)
{
    Console.WriteLine("Name: " + task.Get(Tsk.Name));

    // Work with other properties...
}
```

Nakonec procházíme filtrované úkoly a provádíme požadované operace. V tomto příkladu jednoduše vypíšeme názvy úkolů do konzole, ale můžete tento blok rozšířit o aktualizaci polí, přesun úkolů nebo generování reportů.

## Běžné případy použití

- **Vyloučit dokončené úkoly** při generování seznamu nevyřízené práce.  
- **Najít úkoly chybějící vlastní pole** (např. null sloupec “Owner”).  
- **Kombinovat s dalšími podmínkami** pro vytvoření složitých dotazů, např. „úkoly, které nejsou null a mají datum zahájení před dneškem“.

## Řešení problémů a tipy

| Problém | Důvod | Řešení |
|-------|--------|-----|
| Nebyl vrácen žádný úkol | Původní podmínka může být příliš omezující. | Ověřte logiku podmínky nebo vyzkoušejte jednodušší filtr, např. `new TrueCondition()`. |
| `NullReferenceException` | Cesta `DataDir` je nesprávná. | Ujistěte se, že `DataDir` ukazuje na složku obsahující *Project2.mpp*. |
| Neočekávané výsledky | Nesprávné kombinování `Not<T>` s dalšími podmínkami. | Použijte závorky: `new AndCondition(new Not<Task>(filter), otherCondition)`. |

## Často kladené otázky

**Q: Mohu používat Aspose.Tasks s jinými .NET frameworky?**  
A: Ano, Aspose.Tasks podporuje .NET Core, .NET Standard a klasický .NET Framework.

**Q: Je k dispozici bezplatná zkušební verze Aspose.Tasks?**  
A: Ano, můžete si stáhnout bezplatnou zkušební verzi z [webu](https://releases.aspose.com/).

**Q: Jak mohu získat podporu pro Aspose.Tasks?**  
A: Navštivte [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pro jakékoli dotazy na podporu nebo technickou pomoc.

**Q: Mohu zakoupit dočasnou licenci pro Aspose.Tasks?**  
A: Ano, můžete zakoupit dočasnou licenci na [stránce nákupu](https://purchase.aspose.com/temporary-license/).

**Q: Kde najdu komplexní dokumentaci pro Aspose.Tasks?**  
A: Kompletní dokumentaci najdete na [stránce dokumentace Aspose.Tasks](https://reference.aspose.com/tasks/net/).

## Závěr

Osvojením **filtrace úkolů pomocí NOT operace** a naučením **jak použít NOT filtr** s **aplikovanou NOT podmínkou** získáte detailní kontrolu nad výběrem úkolů v Aspose.Tasks. To vám umožní psát čistší kód, vyhnout se ručnímu vylučování a vytvářet výkonné nástroje pro řízení projektů.

---

**Poslední aktualizace:** 2026-03-14  
**Testováno s:** Aspose.Tasks 24.11 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}