---
title: Konfigurace MS Project Legends v Aspose.Tasks
linktitle: Nakonfigurujte legendu stránky v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se konfigurovat legendy stránek MS Project v .NET pomocí Aspose.Tasks pro efektivní řízení projektů. Poskytován průvodce krok za krokem.
type: docs
weight: 18
url: /cs/net/outline-code-page-settings/page-legend/
---
## Úvod
oblasti vývoje .NET je efektivní řízení úkolů zásadní, zejména při řízení projektů. Aspose.Tasks for .NET se ukazuje jako výkonný nástroj, který nabízí nepřeberné množství funkcí pro zefektivnění procesů správy úloh. Jednou z takových funkcí je možnost konfigurovat legendy stránek MS Project, které uživatelům poskytují cenné informace o prezentaci dat projektu.
## Předpoklady
Než se ponoříte do konfigurace legend stránek MS Project pomocí Aspose.Tasks pro .NET, ujistěte se, že jsou splněny následující předpoklady:
1.  Instalace: Nechte si ve vývojovém prostředí nainstalovat Aspose.Tasks for .NET. Můžete si jej stáhnout z[tady](https://releases.aspose.com/tasks/net/).
2. Základní znalosti .NET: Seznamte se se základy vývoje .NET, včetně nastavování projektů a práce s jmennými prostory.
3. Vývojové prostředí: Pro bezproblémové kódování použijte integrované vývojové prostředí (IDE), jako je Visual Studio.
4. Soubor projektu: Připravte si soubor Microsoft Project (MPP) pro experimentování.

## Importovat jmenné prostory
Ve svém projektu .NET importujte potřebné obory názvů pro přístup k funkcím poskytovaným Aspose.Tasks for .NET.
1. Open Your Project: Spusťte svůj .NET projekt ve vámi preferovaném IDE.
2. Import jmenných prostorů: Na začátku souboru kódu importujte požadované jmenné prostory:
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
Pojďme rozebrat poskytnutý příklad do formátu podrobného průvodce, abychom porozuměli konfiguraci legend stránek MS Project pomocí Aspose.Tasks for .NET komplexně.

## Krok 1: Zadejte adresář dokumentů
Nastavte cestu k adresáři dokumentů, kde je umístěn soubor aplikace Microsoft Project.

```csharp
String DataDir = "Your Document Directory";
```
## Krok 2: Načtěte projekt
 Inicializujte novou instanci souboru`Project` třídy načtením souboru Microsoft Project.

```csharp
var project = new Project(DataDir + "Blank2010.mpp");
```
## Krok 3: Přečtěte si informace o legendě stránky
Přístup k informacím legendy stránky z výchozího zobrazení projektu.

```csharp
var legend = project.DefaultView.PageInfo.Legend;
```
## Krok 4: Zobrazení informací legendy
Výstup podrobností legendy, jako je text vlevo, obrázek vlevo, text na střed, obrázek na střed, text vpravo, obrázek vpravo, stav legendy a šířka.

```csharp
Console.WriteLine("Legend left text: {0} ", legend.LeftText);
Console.WriteLine("Legend left image: {0} ", legend.LeftImage);
Console.WriteLine("Legend center text: {0} ", legend.CenteredText);
Console.WriteLine("Legend center image: {0} ", legend.CenteredImage);
Console.WriteLine("Legend right text: {0} ", legend.RightText);
Console.WriteLine("Legend right image: {0} ", legend.RightImage);
Console.WriteLine("Legend On: {0} ", legend.LegendOn);
Console.WriteLine("Legend Width: {0} ", legend.Width);
```
## Krok 5: Upravte legendu
Volitelně upravte legendu podle potřeby. V tomto příkladu změníme text vlevo.

```csharp
legend.LeftText = "New Left Text";
```
## Krok 6: Uložte změny
Uložte změny provedené v souboru projektu.

```csharp
project.Save(DataDir + "WorkWithPageLegend_out.mpp", SaveFileFormat.Mpp);
```

## Závěr
Závěrem lze říci, že zvládnutí konfigurace legend stránek MS Project pomocí Aspose.Tasks pro .NET může výrazně zlepšit možnosti řízení projektů v rámci ekosystému .NET. Dodržením nastíněných kroků a předpokladů mohou vývojáři bez problémů integrovat tuto funkci do svých projektů a zajistit tak lepší vizualizaci a interpretaci projektových dat.
## FAQ
### Otázka: Mohu používat Aspose.Tasks pro .NET s jinými frameworky .NET?
Odpověď: Ano, Aspose.Tasks for .NET je kompatibilní s různými .NET frameworky, což zajišťuje flexibilitu a přizpůsobivost napříč různými požadavky projektu.
### Otázka: Je k dispozici zkušební verze pro Aspose.Tasks pro .NET?
 Odpověď: Ano, máte přístup k bezplatné zkušební verzi z[tady](https://releases.aspose.com/), což vám umožní prozkoumat jeho funkce před nákupem.
### Otázka: Existují nějaká omezení při používání dočasných licencí pro Aspose.Tasks pro .NET?
Odpověď: Dočasné licence nabízejí plný přístup k funkcím Aspose.Tasks pro .NET, ale jsou časově omezené. Jsou vhodné pro krátkodobé projekty nebo účely hodnocení.
### Otázka: Mohu upravit legendy stránek dále nad rámec uvedeného příkladu?
Odpověď: Aspose.Tasks for .NET nabízí rozsáhlé možnosti přizpůsobení, které vám umožňují přizpůsobit legendy stránek podle vašich specifických požadavků projektu.
### Otázka: Kde najdu podporu nebo komunitní fóra pro Aspose.Tasks pro .NET?
 Odpověď: Můžete hledat podporu a zapojit se do komunity na[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), kde můžete najít odpovědi na dotazy a komunikovat s ostatními vývojáři.