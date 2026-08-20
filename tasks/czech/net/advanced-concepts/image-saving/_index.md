---
date: 2026-03-05
description: Naučte se, jak ukládat obrázky, generovat HTML s obrázky a přizpůsobit
  export obrázků pomocí Aspose.Tasks pro .NET. Podrobný návod krok za krokem, jak
  uložit projekt jako HTML.
linktitle: How to Save Images with Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Jak uložit obrázky pomocí Aspose.Tasks pro .NET
url: /cs/net/advanced-concepts/image-saving/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak ukládat obrázky pomocí Aspose.Tasks pro .NET

## Úvod

V tomto tutoriálu se dozvíte **jak ukládat obrázky** ze souborů Microsoft Project pomocí API Aspose.Tasks pro .NET. Ať už potřebujete vložit grafy do zpráv, generovat HTML stránky obsahující vizuály projektu, nebo jednoduše exportovat diagramové zdroje, níže uvedené kroky vás provedou celým procesem – od nastavení objektu projektu až po přizpůsobení callbacků pro export obrázků.

## Rychlé odpovědi
- **Co znamená „jak ukládat obrázky“ v Aspose.Tasks?**  
  Odkazuje na použití rozhraní `IImageSavingCallback` k řízení, kam a jak jsou vizuální zdroje zapisovány na disk.
- **Mohu uložit projekt jako HTML s vloženými obrázky?**  
  Ano, pomocí `HtmlSaveOptions` spolu s callbacky pro ukládání obrázků můžete **uložit projekt jako HTML**, který zahrnuje všechny vygenerované obrázky.
- **Potřebuji licenci pro export obrázků?**  
  Dočasná evaluační licence funguje pro testování; pro produkční použití je vyžadována plná licence.
- **Které verze .NET jsou podporovány?**  
  Aspose.Tasks pro .NET podporuje .NET Framework 4.5+, .NET Core 3.1+ a .NET 5/6+.
- **Je možné přizpůsobit export obrázků (formát, složka, pojmenování)?**  
  Rozhodně – callback vám dává plnou kontrolu nad názvem souboru, formátem a cílovým umístěním.

## Co znamená „jak ukládat obrázky“ v kontextu Aspose.Tasks?

Ukládání obrázků znamená extrahování vizuálních prvků (grafy, Ganttové pruhy, grafiky zdrojů) ze souboru Project a jejich zápis do souborů obrázků (PNG, JPEG atd.). Aspose.Tasks poskytuje flexibilní mechanismus callbacků, který vám umožní rozhodnout o přesném umístění, konvenci pojmenování a dokonce i o formátu obrázku.

## Proč používat Aspose.Tasks k ukládání obrázků?

- **Plná programová kontrola** – není vyžadována žádná ruční interakce s UI.  
- **Cross‑platform** – funguje na Windows, Linuxu i macOS prostřednictvím .NET Core.  
- **Vysoká věrnost renderování** – obrázky zachovávají stejnou kvalitu jako původní pohled v Projectu.  
- **Jednoduchá generace HTML** – kombinujte `HtmlSaveOptions` s callbacky pro obrázky a **automaticky generujte HTML s obrázky**.

## Předpoklady

Než začneme, ujistěte se, že máte následující:

1. Visual Studio nainstalované na vašem vývojovém počítači.  
2. Aspose.Tasks pro .NET stažené z [zde](https://releases.aspose.com/tasks/net/).  
3. Základní znalost C# a struktury .NET projektů.

## Importování jmenných prostorů

Nejprve přidejte požadované jmenné prostory do vašeho zdrojového souboru:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Krok 1: Vytvoření objektu Project

Načtěte soubor Microsoft Project, se kterým chcete pracovat:

```csharp
var project = new Project("Project1.mpp");
```

## Krok 2: Definování možností uložení

Vytvořte možnosti uložení HTML, které také budou obsahovat naše callbacky pro ukládání obrázků:

```csharp
var options = GetSaveOptions(1);
```

## Krok 3: Uložení projektu jako HTML (save project as html)

Nyní exportujte projekt do souboru HTML. Obrázky odkazované v HTML budou vygenerovány callbackem, který definujeme dále:

```csharp
project.Save("document_out.html", options);
```

## Krok 4: Implementace callbacku pro ukládání obrázků (customize image export)

Implementujte rozhraní `IImageSavingCallback`. Zde můžete **přizpůsobit chování exportu obrázků**:

```csharp
private class ResourcePrefixForNestedResources : IImageSavingCallback
{
    public void ImageSaving(ImageSavingArgs args)
    {
        // Image saving logic goes here
    }
}
```

## Krok 5: Uložení obrázků do určeného adresáře

V metodě `ImageSaving` rozhodněte, kam má být každý obrázek uložen. Níže uvedený příklad rozlišuje PNG zdroje od ostatních formátů:

```csharp
if (args.FileName.EndsWith("png"))
{
    // Save nested resources
}
else
{
    // Save regular resources
}
```

## Krok 6: Specifikace možností uložení (včetně callbacků)

Propojte callbacky pro písma, CSS a obrázky. Tím zajistíte, že každý vizuální prvek bude zpracován konzistentně:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Specify save options here
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Časté problémy a řešení

| Problém | Příčina | Řešení |
|-------|-------|-----|
| Obrázky se nezobrazují v vygenerovaném HTML | Callback nepřiřazuje platnou cestu k souboru | Ujistěte se, že `args.Path` ukazuje na zapisovatelnou složku a že `args.ImageStream` je nastaven správně. |
| PNG soubory jsou uloženy se špatnou příponou | Podmíněná logika kontroluje pouze příponu „png“ | Použijte `Path.GetExtension(args.FileName).Equals(".png", StringComparison.OrdinalIgnoreCase)` pro spolehlivou detekci. |
| Odkazy v HTML jsou po přesunu souborů poškozené | Relativní cesty se změnily po přesunu výstupní složky | Uchovejte složky HTML a obrázků společně nebo podle toho aktualizujte `options.ImageFolder`. |

## Závěr

Po provedení těchto kroků nyní víte **jak ukládat obrázky** ze souboru Project, **uložit projekt jako HTML** a **přizpůsobit export obrázků** tak, aby odpovídal struktuře složek vaší aplikace. Tento přístup vám umožní **generovat HTML s obrázky**, které lze bez problémů vložit do zpráv, dokumentačních portálů nebo webových dashboardů.

## Často kladené otázky

**Q1: Mohu použít Aspose.Tasks k manipulaci se soubory projektu v jiných formátech než HTML?**  
A1: Ano, Aspose.Tasks podporuje různé formáty jako PDF, XLSX a MPP.

**Q2: Poskytuje Aspose.Tasks podporu pro integraci cloudového úložiště?**  
A2: Ano, Aspose.Tasks nabízí API pro práci s populárními cloudovými úložišti jako Amazon S3 a Google Drive.

**Q3: Je Aspose.Tasks kompatibilní s .NET Core?**  
A3: Ano, Aspose.Tasks je kompatibilní s .NET Core, což vám umožní vyvíjet cross‑platform aplikace.

**Q4: Mohu přizpůsobit vzhled uložených obrázků?**  
A4: Ano, můžete přizpůsobit vzhled uložených obrázků úpravou logiky ukládání obrázků v metodách callbacku.

**Q5: Nabízí Aspose.Tasks zkušební verze pro evaluační účely?**  
A5: Ano, můžete získat bezplatnou zkušební verzi Aspose.Tasks z [zde](https://releases.aspose.com/).

---

**Poslední aktualizace:** 2026-03-05  
**Testováno s:** Aspose.Tasks 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}