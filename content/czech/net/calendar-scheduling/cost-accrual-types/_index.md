---
title: Typy časového rozlišení nákladů v Aspose.Tasks
linktitle: Typy časového rozlišení nákladů v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se efektivně řídit náklady na projekt pomocí Aspose.Tasks for .NET. Definujte typy časového rozlišení nákladů pro přesné sledování rozpočtu.
type: docs
weight: 19
url: /cs/net/calendar-scheduling/cost-accrual-types/
---
## Úvod

V projektovém řízení je přesné sledování nákladů zásadní pro udržení rozpočtové kontroly a zajištění úspěchu projektu. Aspose.Tasks for .NET nabízí robustní sadu nástrojů pro správu projektových nákladů, včetně možnosti definovat různé typy akruálních nákladů. Tento tutoriál vás provede procesem pochopení a implementace typů časového rozlišení nákladů pomocí Aspose.Tasks for .NET.

## Předpoklady

Než začneme, ujistěte se, že máte následující předpoklady:

### 1. Nainstalujte Aspose.Tasks for .NET

 Chcete-li začít, musíte mít ve vývojovém prostředí nainstalované Aspose.Tasks for .NET. Knihovnu si můžete stáhnout z[stránka ke stažení](https://releases.aspose.com/tasks/net/) a postupujte podle dodaných pokynů k instalaci.

### 2. Seznámení s .NET Framework

Spolu s příklady v tomto tutoriálu je vyžadována základní znalost frameworku .NET a programovacího jazyka C#.

## Importovat jmenné prostory

Začněme importem potřebných jmenných prostorů pro přístup k funkci Aspose.Tasks v našem projektu .NET:

```csharp

```

Nyní, když jsme pokryli předpoklady a importovali požadované jmenné prostory, přistoupíme k rozdělení každého příkladu do několika kroků.

## Krok 1: Načtěte soubor projektu

```csharp
var project = new Project("Project2.mpp");
```

 Nejprve musíme načíst soubor projektu do naší aplikace. Vytváříme nový`Project` objekt a inicializujte jej s cestou k souboru našeho projektu.

## Krok 2: Přístup ke zdrojům

```csharp
var resource = project.Resources.GetById(1);
```

 Dále přistoupíme ke zdroji, na který chceme použít typ časového rozlišení nákladů. Používáme`GetById` metoda`Resources` kolekce a předat ID zdroje jako argument.

## Krok 3: Nastavte typ časového rozlišení nákladů

```csharp
resource.Set(Rsc.AccrueAt, CostAccrualType.End);
```

 Zde nastavíme typ časového rozlišení nákladů pro zdroj. V tomto příkladu to nastavujeme na`CostAccrualType.End`, což znamená, že náklady nebudou časově rozlišovány, dokud zbývající práce nebude nulová.

## Krok 4: Práce s projektem

Po nastavení typu časového rozlišení nákladů můžete s projektem dále pracovat podle potřeby, provádět další operace nebo kalkulace.

## Závěr

Pochopení a implementace typů akruálních nákladů je zásadní pro efektivní řízení nákladů projektu. S Aspose.Tasks for .NET můžete snadno definovat a přizpůsobit typy časového rozlišení nákladů podle požadavků vašeho projektu a zajistit tak přesné sledování nákladů a kontrolu rozpočtu v průběhu životního cyklu projektu.

## FAQ

### Q1: Mohu změnit typ časového rozlišení nákladů pro více zdrojů současně?

A1: Ano, můžete procházet kolekcí zdrojů a nastavit typ časového rozlišení nákladů pro každý zdroj jednotlivě.

### Otázka 2: Jaké jsou další dostupné typy časového rozlišení nákladů kromě „Konec“?

 A2: Aspose.Tasks for .NET poskytuje několik dalších typů časového rozlišení nákladů, jako je např`Start`, `Prorated` ,a`Duration`.

### Q3: Jak mohu určit aktuální typ časového rozlišení nákladů pro zdroj?

 A3: Aktuální typ časového rozlišení nákladů můžete získat pomocí`Get` metoda na zdrojovém objektu.

### Q4: Mohu použít různé typy časového rozlišení nákladů na různé úkoly v rámci stejného projektu?

A4: Ano, můžete nastavit typ časového rozlišení nákladů nezávisle pro každý úkol a zdroj v projektu.

### Q5: Podporuje Aspose.Tasks pro .NET vlastní typy časového rozlišení nákladů?

A5: Od nejnovější verze Aspose.Tasks for .NET nepodporuje definování vlastních typů časového rozlišení nákladů.