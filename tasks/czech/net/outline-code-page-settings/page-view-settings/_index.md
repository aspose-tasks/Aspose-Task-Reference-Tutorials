---
title: Přizpůsobte nastavení zobrazení stránky MS Project v Aspose.Tasks
linktitle: Konfigurace nastavení zobrazení stránky v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak nakonfigurovat nastavení zobrazení stránky v Aspose.Tasks for .NET, abyste přizpůsobili formát tisku vašich dokumentů Microsoft Project.
weight: 21
url: /cs/net/outline-code-page-settings/page-view-settings/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přizpůsobte nastavení zobrazení stránky MS Project v Aspose.Tasks

## Úvod
Microsoft Project je výkonný nástroj pro správu projektů, ale někdy je potřeba upravit způsob zobrazení a tisku projektu. S Aspose.Tasks for .NET můžete snadno nakonfigurovat nastavení zobrazení stránky tak, aby vyhovovalo vašim specifickým požadavkům. V tomto tutoriálu vás provedeme procesem krok za krokem.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
1.  Aspose.Tasks for .NET: Ujistěte se, že jste si stáhli a nainstalovali knihovnu Aspose.Tasks for .NET. Můžete si jej stáhnout z[tady](https://releases.aspose.com/tasks/net/).
2. Soubor Microsoft Project: Připravte si soubor Microsoft Project, pro který chcete nakonfigurovat nastavení zobrazení stránky.

## Importovat jmenné prostory
Nejprve musíte importovat potřebné jmenné prostory pro práci s Aspose.Tasks ve vašem projektu .NET.
```csharp
    
    using Aspose.Tasks.Saving;
```
## Krok 1: Načtěte soubor projektu
 Začněte načtením souboru Microsoft Project do instance souboru`Project` třída.
```csharp
// Cesta k adresáři dokumentů.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Input.mpp");
```
## Krok 2: Nastavte počet prvních sloupců
Zadejte počet prvních sloupců, které se mají vytisknout na všech stránkách.
```csharp
project.DefaultView.PageInfo.PageViewSettings.FirstColumnsCount = 2;
```
## Krok 3: Tisk poznámek
Vyberte, zda chcete tisknout poznámky spolu s projektem.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintNotes = true;
```
## Krok 4: Přizpůsobte časovou osu konci stránky
Rozhodněte se, zda chcete při tisku přizpůsobit časovou osu konci stránky.
```csharp
project.DefaultView.PageInfo.PageViewSettings.FitTimescaleToEndOfPage = true;
```
## Krok 5: Vytiskněte všechny sloupce listu
Určete, zda se mají tisknout všechny sloupce listu pohledu.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintAllSheetColumns = true;
```
## Krok 6: Tisk prázdných stránek
Zvolte, zda chcete tisknout prázdné stránky pohledu.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintBlankPages = false;
```
## Krok 7: Vytiskněte první sloupce na všech stránkách
Nastavte, zda se má na všech stránkách vytisknout zadaný počet prvních sloupců.
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintFirstColumnsCountOnAllPages = true;
```
## Krok 8: Uložte projekt s nakonfigurovanými nastaveními
Nakonec uložte projekt s nakonfigurovaným nastavením zobrazení stránky a určete výstupní formát, jako je PDF.
```csharp
project.Save(DataDir + "ProjectWithComments_out.pdf", SaveFileFormat.Pdf);
```

## Závěr
Konfigurace nastavení zobrazení stránky aplikace Microsoft Project v Aspose.Tasks for .NET je přímočará a umožňuje vám přizpůsobit formát tisku přesně vašim potřebám. Podle kroků uvedených v tomto kurzu můžete zajistit, že vaše projektové dokumenty budou prezentovány přesně tak, jak je požadováno.
## FAQ
### Otázka: Mohu nakonfigurovat nastavení zobrazení stránky pro jiné formáty souborů kromě PDF?
Odpověď: Ano, Aspose.Tasks podporuje různé formáty souborů pro ukládání projektů, včetně XLSX, MPP a HTML.
### Otázka: Existují nějaká omezení počtu sloupců, které mohu vytisknout?
A: Aspose.Tasks vám umožňuje přizpůsobit počet sloupců, které se mají vytisknout, podle vašich požadavků.
### Otázka: Mohu použít různá nastavení zobrazení stránky pro různé projekty?
Odpověď: Ano, nastavení zobrazení stránky můžete upravit nezávisle pro každý soubor projektu, se kterým pracujete.
### Otázka: Je Aspose.Tasks kompatibilní se všemi verzemi Microsoft Project?
Odpověď: Aspose.Tasks nabízí kompatibilitu s Microsoft Project 2003 a novějšími verzemi.
### Otázka: Kde najdu další pomoc nebo podporu pro Aspose.Tasks?
 A: Můžete navštívit[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pro jakékoli dotazy nebo problémy, se kterými se během používání setkáte.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
