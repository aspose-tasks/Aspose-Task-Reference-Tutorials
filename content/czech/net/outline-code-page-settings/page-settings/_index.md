---
title: Konfigurace nastavení stránky MS Project pomocí Aspose.Tasks
linktitle: Konfigurace nastavení stránky v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se konfigurovat nastavení stránky MS Project pomocí Aspose.Tasks for .NET. Přizpůsobte si orientaci, velikost a další pomocí jednoduchých kroků.
type: docs
weight: 20
url: /cs/net/outline-code-page-settings/page-settings/
---
## Úvod
V tomto tutoriálu si projdeme procesem konfigurace nastavení stránky Microsoft Project pomocí Aspose.Tasks for .NET. Aspose.Tasks je výkonné API, které umožňuje vývojářům programově manipulovat se soubory Microsoft Project.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1.  Aspose.Tasks for .NET: Ujistěte se, že jste nainstalovali Aspose.Tasks for .NET. Můžete si jej stáhnout z[tady](https://releases.aspose.com/tasks/net/).
2. Vývojové prostředí: Nechte si nastavit vývojové prostředí pomocí sady Visual Studio nebo jiného preferovaného IDE pro vývoj .NET.

## Import jmenných prostorů
Chcete-li začít, musíte do projektu importovat potřebné jmenné prostory. Tyto jmenné prostory poskytují přístup ke třídám a metodám Aspose.Tasks potřebným pro manipulaci se soubory MS Project.
```csharp
using Aspose.Tasks;
using System.Linq;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## Krok 1: Načtěte soubor projektu
Nejprve musíte načíst soubor MS Project, pro který chcete nakonfigurovat nastavení stránky.
```csharp
// Cesta k adresáři dokumentů.
string dataDir = "Your Document Directory";
var project = new Project(dataDir + "Project2.mpp");
```
## Krok 2: Otevřete Nastavení stránky
Dále získáte přístup k nastavení stránky souboru projektu.
```csharp
// Získejte nastavení
var settings = project.DefaultView.PageInfo.PageSettings;
```
## Krok 3: Nakonfigurujte nastavení stránky
Nyní nakonfigurujeme různé vlastnosti nastavení stránky podle vašich požadavků.
```csharp
// Nastavte orientaci stránky na výšku
settings.IsPortrait = true;
// Nastavte počet stránek na šířku, které se mají vytisknout
settings.PagesInWidth = 5;
// Nastavte počet stránek na výšku, které se mají vytisknout
settings.PagesInHeight = 7;
// Nastavte procento normální velikosti pro přizpůsobení tisku
settings.PercentOfNormalSize = 200;
// Nastavte velikost papíru
settings.PaperSize = PrinterPaperSize.PaperB4;
// Nastavte číslo první stránky pro tisk
settings.FirstPageNumber = 3;
```
## Krok 4: Uložte soubor projektu
Nakonec uložte soubor projektu s aktualizovaným nastavením stránky.
```csharp
SimpleSaveOptions options = new MPPSaveOptions
{
    WriteViewData = true
};
project.Save(dataDir + "TestCanWritePageSettings.mpp", options);
```

## Závěr
V tomto tutoriálu jsme se naučili, jak nakonfigurovat nastavení stránky Microsoft Project pomocí Aspose.Tasks for .NET. Pomocí těchto kroků můžete snadno přizpůsobit orientaci stránky, velikost a další možnosti tisku podle vašich požadavků.

## FAQ
### Otázka: Mohu konfigurovat nastavení stránky pro více souborů MS Project současně?
Odpověď: Ano, můžete procházet více soubory projektu a na každý z nich použít stejná nastavení stránky.
### Otázka: Je možné vrátit nastavení stránky zpět na výchozí?
Odpověď: Rozhodně můžete jednoduše vynechat kroky konfigurace nebo obnovit nastavení na výchozí hodnoty.
### Otázka: Existují nějaká omezení ohledně podporovaných velikostí papíru?
Odpověď: Aspose.Tasks podporuje širokou škálu velikostí papíru, včetně standardních a vlastních velikostí.
### Otázka: Mohu automatizovat proces konfigurace nastavení stránky?
Odpověď: Tuto funkci jistě můžete integrovat do pracovního postupu vaší aplikace a automatizovat konfiguraci nastavení stránky.
### Otázka: Nabízí Aspose.Tasks podporu pro jiné formáty souborů kromě .mpp?
Odpověď: Ano, Aspose.Tasks podporuje různé formáty souborů, jako je mimo jiné XML, MPT a HTML.