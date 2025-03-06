---
title: Typy zdrojů v Aspose.Tasks
linktitle: Typy zdrojů v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak pracovat s různými typy zdrojů v Aspose.Tasks pro .NET, včetně zdrojů práce, materiálu a nákladů, pomocí podrobného kurzu.
type: docs
weight: 14
url: /cs/net/resource-risk-analysis/resource-types/
---
## Úvod
Aspose.Tasks for .NET je výkonná knihovna, která umožňuje vývojářům pracovat se soubory Microsoft Project programově. Ať už spravujete úkoly, zdroje nebo plány, Aspose.Tasks zjednodušuje proces tím, že poskytuje komplexní sadu rozhraní API. V tomto tutoriálu se ponoříme do různých typů zdrojů, které můžete využít ve svých projektech pomocí Aspose.Tasks for .NET.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
1. Visual Studio: Nainstalujte Visual Studio, výkonné integrované vývojové prostředí (IDE) pro vývoj .NET.
2.  Aspose.Tasks for .NET: Stáhněte si a nainstalujte knihovnu Aspose.Tasks for .NET z[tady](https://releases.aspose.com/tasks/net/).
3. Základní znalost C#: Seznamte se s C#, programovacím jazykem používaným pro vývoj .NET.

## Importovat jmenné prostory
Nejprve importujme potřebné jmenné prostory pro přístup k funkcím Aspose.Tasks pro .NET:
```csharp
    
```

## Krok 1: Vytvořte novou instanci projektu
```csharp
var project = new Project();
```
Tento řádek inicializuje nový objekt Project, který slouží jako kontejner pro všechna data a operace související s projektem.
## Krok 2: Přidejte pracovní zdroj
```csharp
var work = project.Resources.Add("Work resource");
work.Set(Rsc.Type, ResourceType.Work);
```
Zde vytvoříme nový pracovní zdroj s názvem "Pracovní zdroj" a určíme jeho typ jako ResourceType.Work.
## Krok 3: Přidejte materiálový zdroj
```csharp
var material = project.Resources.Add("Material resource");
material.Set(Rsc.Type, ResourceType.Material);
material.Set(Rsc.MaterialLabel, "kg");
```
Tento krok přidá materiálový zdroj s názvem "Material resource" s typem nastaveným na ResourceType.Material. Kromě toho specifikujeme štítek materiálu jako "kg" pro označení měrné jednotky.
## Krok 4: Přidejte nákladový zdroj
```csharp
var cost = project.Resources.Add("Cost resource");
cost.Set(Rsc.Type, ResourceType.Cost);
cost.Set(Rsc.Cost, 59.99m);
```
Nakonec přidáme nákladový zdroj s názvem "Cost resource" a nastavíme jeho typ jako ResourceType.Cost. Navíc jsme nastavili hodnotu nákladů na 59,99, což představuje peněžní hodnotu spojenou s tímto zdrojem.

## Závěr
V tomto tutoriálu jsme prozkoumali, jak pracovat s různými typy zdrojů v Aspose.Tasks pro .NET, včetně zdrojů práce, materiálu a nákladů. Dodržováním tohoto podrobného průvodce můžete efektivně spravovat zdroje ve svých projektech programově.
## FAQ
### Otázka: Mohu používat Aspose.Tasks pro .NET s jinými formáty softwaru pro správu projektů?
Odpověď: Ano, Aspose.Tasks podporuje různé formáty, včetně Microsoft Project (MPP), Primavera P6 a dalších.
### Otázka: Je k dispozici bezplatná zkušební verze pro Aspose.Tasks pro .NET?
 Odpověď: Ano, máte přístup k bezplatné zkušební verzi[tady](https://releases.aspose.com/).
### Otázka: Jak mohu získat technickou podporu pro Aspose.Tasks pro .NET?
 Odpověď: Můžete navštívit fórum Aspose.Tasks[tady](https://forum.aspose.com/c/tasks/15) za technickou pomoc.
### Otázka: Mohu si zakoupit dočasnou licenci pro Aspose.Tasks pro .NET?
 Odpověď: Ano, můžete si zakoupit dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
### Otázka: Poskytuje Aspose.Tasks pro .NET dokumentaci pro referenci?
 Odpověď: Ano, můžete najít dokumentaci[tady](https://reference.aspose.com/tasks/net/).