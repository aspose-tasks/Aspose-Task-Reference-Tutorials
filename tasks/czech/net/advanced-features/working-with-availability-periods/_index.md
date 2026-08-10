---
date: 2026-04-06
description: Naučte se, jak přidat zdroj do projektu a nastavit období dostupnosti
  zdroje pomocí Aspose.Tasks pro .NET. Podrobný návod krok za krokem pro správu kalendářů
  zdrojů.
keywords:
- add resource to project
- set resource availability
- configure work schedule
linktitle: Práce s obdobími dostupnosti v Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Přidat zdroj do projektu a nastavit dostupnost v Aspose.Tasks
url: /cs/net/advanced-features/working-with-availability-periods/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání zdroje do projektu a nastavení dostupnosti v Aspose.Tasks

## Úvod

V tomto tutoriálu se naučíte **jak přidat zdroj do projektu** a poté definovat jeho období dostupnosti pomocí knihovny Aspose.Tasks pro .NET. Správa kalendářů zdrojů je nezbytná pro realistické plány projektů a níže uvedené kroky vás provedou celým procesem – od vytvoření instance projektu až po výpis podrobností každého období.

## Rychlé odpovědi
- **Jaký je hlavní cíl?** Přidat zdroj do projektu a nakonfigurovat jeho období dostupnosti.  
- **Která knihovna je vyžadována?** Aspose.Tasks pro .NET.  
- **Potřebuji licenci pro produkci?** Ano, je vyžadována komerční licence.  
- **Podporované verze .NET?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Doba implementace?** Obvykle méně než 15 minut pro základní scénáře.

## Co znamená „přidat zdroj do projektu“?

Přidání zdroje do projektu vytvoří zástupný objekt pro osobu, vybavení nebo materiál, který může být přiřazen k úkolům. Jakmile zdroj existuje, můžete **nastavit dostupnost zdroje**, definovat jeho pracovní kalendář a nechat plánovač respektovat tato omezení.

## Proč konfigurovat pracovní rozvrh a období dostupnosti?

- **Přesné plánování:** Úkoly jsou plánovány pouze tehdy, když je zdroj skutečně volný.  
- **Kontrola nákladů:** Jednotky dostupnosti odrážejí práci na částečný úvazek, což pomáhá správně vypočítat náklady na pracovní sílu.  
- **Vyrovnání zdrojů:** Engine může automaticky vyrovnávat přetížení, pokud zná kalendář každého zdroje.

## Předpoklady

1. Visual Studio (nebo jakékoli IDE kompatibilní s .NET).  
2. Aspose.Tasks pro .NET – stáhněte z [zde](https://releases.aspose.com/tasks/net/).  
3. Základní znalost C#.

## Importovat jmenné prostory

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Jak přidat zdroj do projektu?

### Krok 1: Vytvořit novou instanci `Project`

```csharp
var project = new Project();
```

Tento objekt představuje celý soubor projektu v paměti.

### Krok 2: Přidat zdroj do projektu

```csharp
var resource = project.Resources.Add("Work Resource");
```

Tento volání vytvoří **zdroj** pojmenovaný *Work Resource*, který můžete později přiřadit k úkolům.

### Krok 3: Definovat období dostupnosti

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

`GetPeriods()` je pomocná metoda (implementace není zobrazena), která vrací kolekci objektů `AvailabilityPeriod`. Každé období určuje počáteční datum, koncové datum a jednotky (procento plného úvazku), během nichž je zdroj dostupný.

### Krok 4: Přidat období ke zdroji

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

Zde **nastavujeme dostupnost zdroje** pomocí procházení kolekce a přidávání každého období do kalendáře zdroje.

### Krok 5: Zobrazit podrobnosti dostupnosti

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

Výstup v konzoli vám umožní ověřit, že období byla uložena správně.

## Časté úskalí a tipy

- **Přesnost data:** `AvailableFrom` a `AvailableTo` jsou hodnoty typu `DateTime`; ujistěte se, že jsou nastaveny na půlnoc, pokud chcete období celých dnů.  
- **Rozsah jednotek:** Platné hodnoty jsou 0‑100 %; hodnoty mimo tento rozsah vyvolají výjimku.  
- **Překrývající se období:** Překrývající se období jsou automaticky sloučena, ale je přehlednější je udržovat odděleně.

## Často kladené otázky

### Q1: Mohu používat Aspose.Tasks pro .NET v komerčních projektech?

A1: Ano, Aspose.Tasks pro .NET lze používat v komerčních projektech. Licenci si můžete zakoupit [zde](https://purchase.aspose.com/buy).

### Q2: Je k dispozici bezplatná zkušební verze Aspose.Tasks pro .NET?

A2: Ano, bezplatnou zkušební verzi Aspose.Tasks pro .NET můžete získat [zde](https://releases.aspose.com/).

### Q3: Kde najdu dokumentaci k Aspose.Tasks pro .NET?

A3: Dokumentaci najdete [zde](https://reference.aspose.com/tasks/net/).

### Q4: Jak mohu získat podporu pro Aspose.Tasks pro .NET?

A4: Podporu můžete získat na komunitním fóru [zde](https://forum.aspose.com/c/tasks/15).

### Q5: Nabízíte dočasné licence pro Aspose.Tasks pro .NET?

A5: Ano, dočasné licence jsou k dispozici [zde](https://purchase.aspose.com/temporary-license/).

---

**Poslední aktualizace:** 2026-04-06  
**Testováno s:** Aspose.Tasks pro .NET (nejnovější stabilní verze)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}