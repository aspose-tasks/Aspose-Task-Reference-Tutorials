---
title: Možnosti uložení obrázku MS Project pro Aspose.Tasks
linktitle: Možnosti uložení obrázku pro Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak uložit možnosti MS Project jako obrázky pomocí Aspose.Tasks pro .NET. Postupujte podle našeho podrobného průvodce pro bezproblémovou integraci.
type: docs
weight: 11
url: /cs/net/saving-options/image-save-options/
---

## Úvod
Ve světě vývoje softwaru je efektivní zvládnutí projektových úkolů zásadní pro úspěšné projektové řízení. Aspose.Tasks for .NET nabízí výkonné řešení pro vývojáře pracující se soubory Microsoft Project, které jim umožňuje bezproblémově manipulovat, převádět a spravovat projektové úlohy v rámci jejich aplikací .NET.
## Předpoklady
Než se pustíte do používání Aspose.Tasks for .NET k uložení možností MS Project jako obrázků, ujistěte se, že máte splněny následující předpoklady:
### 1. Nainstalujte Aspose.Tasks for .NET
 Chcete-li začít, musíte mít ve svém vývojovém prostředí nainstalované Aspose.Tasks for .NET. Knihovnu si můžete stáhnout z[webová stránka](https://releases.aspose.com/tasks/net/) a postupujte podle dodaných pokynů k instalaci.
### 2. Získejte licenci (volitelné)
 Zatímco Aspose.Tasks for .NET lze používat bez licence ve zkušebním režimu, získání licence se doporučuje pro plnou funkčnost a odstranění omezení hodnocení. Licenci můžete získat od[nákupní stránku](https://purchase.aspose.com/buy) nebo se rozhodnout pro a[dočasná licence](https://purchase.aspose.com/temporary-license/) pro testovací účely.
### 3. Základní znalost C# a .NET Development
Základní porozumění programovacímu jazyku C# a frameworku .NET je nutné následovat spolu s příklady a efektivně integrovat funkce Aspose.Tasks do vašich aplikací.
## Importovat jmenné prostory
Než začneme ukládat možnosti MS Project jako obrázky pomocí Aspose.Tasks pro .NET, ujistěte se, že do našeho projektu C# importujeme potřebné jmenné prostory:
```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;
using System.Drawing.Imaging;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Krok 1: Nastavte cestu adresáře dokumentu
Ujistěte se, že máte určený adresář pro vaše dokumenty, a podle toho nastavte cestu:
```csharp
String DataDir = "Your Document Directory";
```
## Krok 2: Načtěte soubor MS Project
 Inicializujte nový`Project` objekt načtením souboru MS Project:
```csharp
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## Krok 3: Definujte možnosti uložení obrázku
 Vytvořte instanci`ImageSaveOptions` a zadejte požadovaná nastavení:
```csharp
var options = new ImageSaveOptions(SaveFileFormat.Jpeg)
{
    RenderToSinglePage = false,
    StartDate = project.Get(Prj.StartDate),
    EndDate = project.Get(Prj.FinishDate),
    PageSize = PageSize.Letter
};
```
## Krok 4: Zadejte stránky k uložení
V případě potřeby zadejte stránky, které se mají uložit. V tomto příkladu přidáváme stránku 2:
```csharp
options.Pages.Add(2);
```
## Krok 5: Uložte obrázek
Nakonec uložte vybrané stránky jako obrázek se zadanými možnostmi:
```csharp
project.Save(DataDir + "SaveSelectedPagesImageSaveOptions_page2_out.jpeg", options);
```

## Závěr
Aspose.Tasks for .NET zjednodušuje proces práce se soubory MS Project a umožňuje vývojářům bez námahy manipulovat s projektovými úkoly. Podle kroků uvedených v tomto kurzu můžete efektivně uložit možnosti MS Project jako obrázky ve vašich aplikacích .NET.
## FAQ
### Q1: Mohu používat Aspose.Tasks pro .NET bez licence?
Odpověď: Ano, Aspose.Tasks pro .NET můžete používat bez licence ve zkušebním režimu. Je však doporučeno získat licenci pro plnou funkčnost a odstranit omezení hodnocení.
### Q2: Jak mohu získat dočasnou licenci pro testování?
 Odpověď: Dočasnou licenci pro testovací účely můžete získat od[dočasná licenční stránka](https://purchase.aspose.com/temporary-license/).
### Q3: Je Aspose.Tasks for .NET kompatibilní s jinými frameworky .NET?
Odpověď: Ano, Aspose.Tasks for .NET je kompatibilní s různými frameworky .NET, včetně .NET Core a .NET Standard.
### Q4: Mohu dále upravit možnosti ukládání obrázku?
Odpověď: Ano, můžete upravit možnosti uložení obrázku podle vašich specifických požadavků, jako je úprava velikosti stránky, rozlišení nebo výstupního formátu.
### Q5: Kde najdu podporu pro Aspose.Tasks pro .NET?
 Odpověď: Podporu a pomoc pro Aspose.Tasks pro .NET najdete na[Fórum](https://forum.aspose.com/c/tasks/15).