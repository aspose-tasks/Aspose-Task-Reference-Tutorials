---
date: 2026-03-21
description: Naučte se, jak spravovat období dostupnosti zdrojů a dosáhnout efektivní
  dostupnosti projektových zdrojů pomocí Aspose.Tasks pro .NET. Tento průvodce krok
  za krokem ukazuje, jak přidávat, aktualizovat a odstraňovat období dostupnosti.
linktitle: Collection of Availability Periods in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Dostupnost zdrojů projektu – Správa období dostupnosti v Aspose.Tasks
url: /cs/net/advanced-features/availability-period-collection/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dostupnost zdrojů projektu: Sbírka období dostupnosti v Aspose.Tasks

Správa **dostupnosti zdrojů projektu** je základní součástí úspěšného plánování projektu. V tomto tutoriálu se naučíte **jak spravovat dostupnost** zdrojů pomocí API Aspose.Tasks pro .NET, krok za krokem, od načtení projektu až po kopírování období mezi zdroji.

## Rychlé odpovědi
- **Jaká je hlavní třída pro období dostupnosti?** `AvailabilityPeriod` v jmenném prostoru `Aspose.Tasks`.  
- **Mohu vymazat existující období?** Ano, zavolejte `resource.AvailabilityPeriods.Clear()`.  
- **Jak přidám nové období?** Vytvořte objekt `AvailabilityPeriod` a použijte `Add` nebo `Insert`.  
- **Je možné zkopírovat období do jiného zdroje?** Rozhodně – použijte `CopyTo` a poté přidejte každou položku do cílového zdroje.  
- **Potřebuji licenci pro produkční použití?** Ano, pro ne‑zkušební nasazení je vyžadována komerční licence Aspose.Tasks.

## Co je dostupnost zdrojů projektu?
Dostupnost zdrojů projektu určuje data a jednotky (procento kapacity), kdy může být zdroj přiřazen k úkolům. Řízením těchto období předcházíte přetížení a zlepšujete přesnost plánu.

## Proč používat Aspose.Tasks pro správu období dostupnosti?
- **Plná integrace s .NET** – bez COM interop, čistý spravovaný kód.  
- **Detailní kontrola** – nastavení přesných počátečních/koncových dat a zlomkových jednotek.  
- **Jednoduché kopírování** – přesun dat o dostupnosti mezi zdroji bez ručního parsování.  
- **Optimalizováno pro výkon** – efektivně pracuje s velkými soubory MPP.

## Požadavky
1. **Visual Studio** – jakákoli recentní verze (2019, 2022 nebo novější).  
2. **Aspose.Tasks pro .NET** – stáhněte z [zde](https://releases.aspose.com/tasks/net/).  
3. **Základní znalost C#** – měli byste být obeznámeni s třídami, kolekcemi a LINQ.

## Importování jmenných prostorů

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

Importujeme hlavní jmenný prostor Aspose.Tasks spolu se standardními .NET kolekcemi, které budeme později potřebovat.

## Krok 1: Inicializace projektu a zdroje

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

Zde načteme existující soubor MPP a získáme zdroj, jehož dostupnost chceme upravit (ID = 1).

## Krok 2: Vymazání existujících období dostupnosti

```csharp
resource.AvailabilityPeriods.Clear();
```

Vymazání odstraní všechna dříve definovaná období a poskytne nám čistý start.

## Krok 3: Přidání období dostupnosti

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

Načteme kolekci objektů `AvailabilityPeriod` (předpokládá se, že pomocná metoda `GetPeriods` je definována jinde) a přidáme každou položku, přičemž kontrolujeme, že kolekce je zapisovatelná.

## Krok 4: Vložení nového období dostupnosti

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

Tím se vytvoří vlastní období pro rok 2013 a vloží se na pozici 1 (druhé místo), pokud již není přítomno.

## Krok 5: Zobrazení období dostupnosti

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Rychlý výpis do konzole zobrazí celkový počet a podrobnosti každého období – užitečné pro ladění nebo ověření.

## Krok 6: Kopírování období dostupnosti do jiného zdroje

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

Zkopírujeme celou kolekci do pole, vymažeme období cílového zdroje a poté jej znovu naplníme. Toto ukazuje, jak duplikovat data o dostupnosti mezi zdroji.

## Krok 7: Aktualizace a odstranění období dostupnosti

```csharp
// Update available units for a specific period
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Remove a specific period
otherResource.AvailabilityPeriods.Remove(period2013);
```

Zde upravíme `AvailableUnits` pro předposlední období a poté odstraníme období z roku 2013, které jsme přidali dříve.

## Časté problémy a řešení
- **Chyba – kolekce je jen pro čtení** – Ujistěte se, že projekt není otevřen v režimu jen pro čtení nebo že jste před přidáním nových položek zavolali `resource.AvailabilityPeriods.Clear()`.  
- **Překrývající se období** – Aspose.Tasks automaticky neslučuje překryvy; může být nutné napsat vlastní logiku pro jejich detekci a řešení.  
- **Nesprávný formát data** – Vždy používejte objekty `DateTime`; parsování řetězců může vést k chybám specifickým pro locale.

## Často kladené otázky

**Q: Mohu přidat vlastní pole k obdobím dostupnosti?**  
A: Ne, období dostupnosti v Aspose.Tasks pro .NET nepodporují vlastní pole.

**Q: Jsou období dostupnosti spojena s konkrétními úkoly?**  
A: Ne, jsou spojena se zdroji a definují, kdy je zdroj obecně dostupný pro úkoly.

**Q: Mohu importovat období dostupnosti z externích zdrojů?**  
A: Ano, můžete importovat období z CSV, XML nebo databáze vytvořením objektů `AvailabilityPeriod` a jejich přidáním do kolekce.

**Q: Jak zacházet s překrývajícími se obdobími dostupnosti?**  
A: Překryvy nejsou automaticky řešeny; musíte implementovat vlastní validaci pro sloučení nebo odmítnutí konfliktních období.

**Q: Existuje limit na počet období dostupnosti, která může zdroj mít?**  
A: Neexistuje pevně zakódovaný limit, ale velmi velké kolekce mohou ovlivnit výkon; kde je to možné, zvažte konsolidaci období.

## Závěr

V tomto průvodci jsme pokryli vše, co potřebujete vědět pro správu **dostupnosti zdrojů projektu** pomocí Aspose.Tasks pro .NET – od inicializace projektu a vymazání starých dat až po přidávání, vkládání, kopírování, aktualizaci a odstraňování období dostupnosti. Ovládnutí těchto kroků vám pomůže udržet kalendáře zdrojů přesné a plány projektů realistické.

---

**Last Updated:** 2026-03-21  
**Tested With:** Aspose.Tasks for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}