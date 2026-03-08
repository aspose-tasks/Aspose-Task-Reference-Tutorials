---
date: 2026-03-08
description: Naučte se, jak nastavit zobrazení štítků a přizpůsobit štítek dne v projektovém
  řízení pomocí Aspose.Tasks pro .NET, čímž zlepšíte čitelnost a přehlednost.
linktitle: Displaying Labels in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Jak nastavit zobrazení štítku v Aspose.Tasks pro .NET
url: /cs/net/advanced-concepts/label-display/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak nastavit zobrazení popisků v Aspose.Tasks pro .NET

## Úvod

Když vytváříte řešení pro řízení projektů s **Aspose.Tasks pro .NET**, schopnost **jak nastavit popisek** je nezbytná pro snadné čtení harmonogramů. Ať už potřebujete přesnost na minutu nebo přehled na roční úrovni, přizpůsobení zobrazení popisků vám umožní prezentovat časovou osu přesně tak, jak očekávají vaši zainteresovaní. V tomto tutoriálu vás provedeme krok za krokem procesem nastavení zobrazení popisků pro minuty, hodiny, dny, týdny, měsíce a roky a také vám ukážeme, jak **přizpůsobit formátování denního popisku** pro maximální přehlednost.

## Rychlé odpovědi
- **Co znamená “jak nastavit popisek”?** Odkazuje na konfiguraci vlastností `DisplayOptions`, které řídí, jak se časové jednotky zobrazují v souboru projektu.  
- **Který popisek mohu změnit?** Minuty, hodiny, dny, týdny, měsíce a roky jsou všechny konfigurovatelné.  
- **Potřebuji licenci?** Platná licence Aspose.Tasks je vyžadována pro produkční použití; pro testování stačí bezplatná zkušební verze.  
- **Je to podporováno na .NET Core?** Ano, API funguje s .NET Core, .NET 5/6 a s plným .NET Framework.  
- **Mohu změnit popisek za běhu?** Rozhodně – můžete upravit možnosti zobrazení kdykoli před uložením projektu.

## Co je zobrazení popisků v Aspose.Tasks?

Zobrazení popisků určuje textovou reprezentaci časových jednotek (minuta, hodina, den atd.) na Ganttově diagramu a časové ose. Nastavením příslušné vlastnosti `DisplayOptions` řeknete Aspose.Tasks, jak má tyto jednotky vykreslovat, což může výrazně zlepšit čitelnost projektu.

## Proč přizpůsobovat zobrazení popisků?

- **Zlepšená čitelnost:** Zainteresovaní mohou okamžitě pochopit úroveň detailu harmonogramu.  
- **Konzistentní reportování:** Zarovnává vizuální výstup s firemními standardy (např. používání „Mo“ pro měsíce).  
- **Flexibilita:** Přepínáte mezi podrobnými a přehlednými zobrazeními bez změny základních dat harmonogramu.

## Požadavky

1. **Znalost C#** – základní povědomí o syntaxi C# a struktuře .NET projektu.  
2. **Aspose.Tasks pro .NET** – stáhněte a nainstalujte knihovnu z [zde](https://releases.aspose.com/tasks/net/).  
3. **Vývojové prostředí** – Visual Studio, VS Code nebo jakékoli IDE podporující vývoj v .NET.

## Importujte jmenné prostory

Před začátkem importujte požadované jmenné prostory:

```csharp
using Aspose.Tasks;
using Aspose.Tasks;
```

## Jak nastavit zobrazení popisků pro minuty

### 1. Zobrazení minutových popisků

Pro nastavení minutového popisku použijte vlastnost `MinuteLabel`:

```csharp
public void WorkWithMinuteLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the minute label is displayed
    project.DisplayOptions.MinuteLabel = MinuteLabelDisplay.M;
}
```

## Jak nastavit zobrazení popisků pro hodiny

### 2. Zobrazení hodinových popisků

```csharp
public void WorkWithHourLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the hour label is displayed
    project.DisplayOptions.HourLabel = HourLabelDisplay.H;
}
```

## Přizpůsobení zobrazení denního popisku

### 3. Zobrazení denních popisků

```csharp
public void WorkWithDayLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the day label is displayed
    project.DisplayOptions.DayLabel = DayLabelDisplay.D;
}
```

## Jak nastavit zobrazení popisků pro týdny

### 4. Zobrazení týdenních popisků

```csharp
public void WorkWithWeekLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the week label is displayed
    project.DisplayOptions.WeekLabel = WeekLabelDisplay.W;
}
```

## Jak nastavit zobrazení popisků pro měsíce

### 5. Zobrazení měsíčních popisků

```csharp
public void WorkWithMonthLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the month label is displayed
    project.DisplayOptions.MonthLabel = MonthLabelDisplay.Mo;
}
```

## Jak nastavit zobrazení popisků pro roky

### 6. Zobrazení ročních popisků

```csharp
public void WorkWithYearLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the year label is displayed
    project.DisplayOptions.YearLabel = YearLabelDisplay.Y;
}
```

## Časté úskalí a tipy

- **Tip:** Vždy nastavte zobrazení popisku *před* uložením projektu; změny provedené po uložení se v souboru neodrazí.  
- **Úskalí:** Použití nepodporované hodnoty enumu vyvolá `ArgumentException`. Držte se poskytnutých enumů `*LabelDisplay`.  
- **Tip:** Pokud potřebujete různé styly popisků pro různé pohledy, vytvořte samostatné instance `Project` nebo klonujte objekt `DisplayOptions`.

## Závěr

Ovládnutím **jak nastavit popisek** v Aspose.Tasks získáte detailní kontrolu nad vizuální prezentací vašich projektových harmonogramů. Ať už přizpůsobujete denní popisek pro denní scrum board nebo upravujete roční popisek pro víceletou roadmapu, tato nastavení vám pomohou dodat přehlednější a profesionálnější projektovou dokumentaci.

## Často kladené otázky

### Q1: Mohu přizpůsobit zobrazení popisků pro konkrétní části projektu?

**A1:** Ano, Aspose.Tasks pro .NET umožňuje detailní kontrolu nad zobrazením popisků, což umožňuje přizpůsobení pro konkrétní části projektu podle potřeby.

### Q2: Je Aspose.Tasks kompatibilní s populárními .NET frameworky?

**A2:** Ano, Aspose.Tasks pro .NET je kompatibilní s různými .NET frameworky, včetně .NET Core a .NET Framework.

### Q3: Mohu dynamicky měnit zobrazení popisků na základě požadavků projektu?

**A3:** Rozhodně, flexibilita Aspose.Tasks pro .NET umožňuje dynamické úpravy zobrazení popisků podle měnících se požadavků projektu.

### Q4: Existují nějaká omezení při přizpůsobování zobrazení popisků?

**A4:** Aspose.Tasks pro .NET nabízí rozsáhlé možnosti přizpůsobení zobrazení popisků s minimálními omezeními, což uživatelům poskytuje velkou flexibilitu.

### Q5: Podporuje Aspose.Tasks integraci s jinými nástroji pro řízení projektů?

**A5:** Ano, Aspose.Tasks nabízí bezproblémové možnosti integrace, usnadňující interoperabilitu s dalšími nástroji a platformami pro řízení projektů.

---

**Last Updated:** 2026-03-08  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}