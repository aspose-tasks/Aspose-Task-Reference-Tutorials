---
date: 2026-03-16
description: Naučte se, jak kombinovat více podmínek a filtrovat úkoly projektu pomocí
  pokročilé operace AND v Aspose.Tasks pro .NET.
linktitle: Advanced AND Operation in Aspise.Tasks
second_title: Aspose.Tasks .NET API
title: Jak kombinovat více podmínek pomocí pokročilé operace AND v Aspose.Tasks
url: /cs/net/advanced-features/advanced-and-operation/
weight: 10
---

.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pokročilá operace AND v Aspose.Tasks

## Úvod

V tomto tutoriálu objevíte **jak kombinovat více podmínek** pomocí *pokročilé operace AND* v Aspose.Tasks pro .NET. Na konci průvodce budete schopni **filtrovat úkoly projektu** na základě několika kritérií—což je nezbytné, když potřebujete **jak filtrovat úkoly** jako souhrnné položky, ne‑null položky nebo vlastní příznaky v jediném průchodu.

## Rychlé odpovědi
- **Co dělá pokročilá operace AND?** Sloučí dvě nebo více filtrů podmínek tak, že jsou vráceny jen úkoly splňující *všechny* kritéria.  
- **Která třída kombinuje podmínky?** `Util.And<T>` (v API je vystavena jako `And<T>`).  
- **Potřebuji speciální licenci?** Pro produkční použití je vyžadována běžná licence Aspose.Tasks; k dispozici je bezplatná zkušební verze.  
- **Mohu řetězit více než dvě podmínky?** Ano—`And<T>` přijímá libovolný počet podmínek.  
- **Jaká verze .NET je podporována?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.

## Co znamená „kombinovat více podmínek“ v Aspose.Tasks?

Kombinování více podmínek znamená vytvoření složeného filtru, který hodnotí každý úkol podle několika pravidel současně. Tento přístup je mnohem efektivnější než iterovat seznam úkolů vícekrát, protože knihovna aplikuje logiku v jediném průchodu.

## Proč použít pokročilou operaci AND?

- **Výkon:** Snižuje počet průchodů přes kolekci úkolů.  
- **Čitelnost:** Udržuje logiku filtru deklarativní a snadno udržovatelnou.  
- **Flexibilita:** Můžete kombinovat vestavěné podmínky (např. `SummaryCondition`) s vlastními predikáty.  

## Požadavky

Předtím, než začneme, ujistěte se, že máte:

1. Základní znalosti programování v C#.  
2. Nainstalovaný Aspose.Tasks pro .NET. Pokud jste jej ještě ne stáhli, získáte jej **[zde](https://releases.aspose.com/tasks/net/)**.  
3. IDE jako Visual Studio (všechny edice fungují).  

## Importujte jmenné prostory

Nejprve importujte jmenné prostory, které poskytují model úkolu a pomocné třídy:

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;
```

## Krok 1: Inicializace projektu a sběr úkolů

Vytvoříme instanci `Project` a použijeme `ChildTasksCollector` k sesbírání všech úkolů v souboru. Toto demonstruje **jak použít kolektor** k získání plochého seznamu úkolů.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

## Krok 2: Definujte podmínky filtru

Zde definujeme jednotlivé podmínky, které chceme použít. V tomto příkladu **filtrujeme souhrnné úkoly** a také zajišťujeme, že objekt úkolu není null.

```csharp
var condition1 = new SummaryCondition();
var condition2 = new NotNullCondition();
```

## Krok 3: Kombinujte podmínky pomocí operace AND

Nyní **kombinujeme více podmínek** pomocí třídy `And<T>`. Toto je jádro **pokročilé operace AND**.

```csharp
var joinedCondition = new And<Task>(condition1, condition2);
```

## Krok 4: Aplikujte podmínku a filtrujte úkoly

Jakmile je složená podmínka připravena, zavoláme `Filter` k **filtrování úkolů projektu** na základě kombinované logiky.

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

## Krok 5: Výstup filtrovaných úkolů

Nakonec zobrazíme úkoly, které splnily **všechny** podmínky. Můžete nahradit volání `Console.WriteLine` libovolným vlastním zpracováním, které potřebujete.

```csharp
Console.WriteLine("Filtered tasks: ");
foreach (var task in collection)
{
    Console.WriteLine(" Name: " + task.Get(Tsk.Name));
    // Additional processing can be done here
}
```

## Časté problémy a řešení

| Problém | Proč se vyskytuje | Rychlé řešení |
|-------|----------------|-----------|
| `Filter` metoda nenalezena | Chybí `using Aspose.Tasks.Util;` | Ujistěte se, že je importován jmenný prostor Util (viz Import Namespaces). |
| Žádné úkoly nebyly vráceny | Podmínky jsou příliš restriktivní (např. filtrujete souhrnné úkoly, když žádné neexistují) | Ověřte, že projekt skutečně obsahuje souhrnné úkoly, nebo upravte podmínky. |
| NullReferenceException | `coll.Tasks` obsahuje null položky | `NotNullCondition` již chrání před tímto; ponechte ji v řetězci AND. |

## Často kladené otázky

### Q1: Co je Aspose.Tasks pro .NET?

A: Aspose.Tasks for .NET je robustní API, které umožňuje vývojářům programově manipulovat se soubory Microsoft Project v .NET aplikacích.

### Q2: Mohu použít více než dvě podmínky pomocí Util.And?

A: Ano, Util.And lze použít k kombinaci libovolného počtu podmínek pro vytvoření složitých kritérií filtrování.

### Q3: Je k dispozici bezplatná zkušební verze Aspose.Tasks pro .NET?

A: Ano, můžete si stáhnout bezplatnou zkušební verzi **[zde](https://releases.aspose.com/)**.

### Q4: Kde najdu dokumentaci k Aspose.Tasks pro .NET?

A: Dokumentaci najdete **[zde](https://reference.aspose.com/tasks/net/)**.

### Q5: Jak mohu získat podporu pro Aspose.Tasks pro .NET?

A: Podporu můžete získat na fóru komunity Aspose.Tasks **[zde](https://forum.aspose.com/c/tasks/15)**.

**Další otázky a odpovědi**

**Q: Jak filtrovat úkoly podle hodnot vlastních polí?**  
A: Vytvořte `CustomFieldCondition` (nebo implementujte `ICondition<Task>`) a přidejte jej do řetězce `And<T>`.

**Q: Mohu použít stejný přístup k filtrování zdrojů?**  
A: Ano—nahraďte `Task` za `Resource` a použijte odpovídající třídy podmínek.

## Závěr

Po provedení výše uvedených kroků nyní víte **jak kombinovat více podmínek** pomocí **pokročilé operace AND** v Aspose.Tasks pro .NET. Tato technika vám umožní **efektivně filtrovat úkoly projektu**, ať už cílíte na souhrnné položky, ne‑null položky nebo jakákoli vlastní kritéria, která definujete.

---

**Last Updated:** 2026-03-16  
**Tested With:** Aspose.Tasks for .NET (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}