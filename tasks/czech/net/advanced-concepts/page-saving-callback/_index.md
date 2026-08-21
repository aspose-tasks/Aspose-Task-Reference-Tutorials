---
date: 2026-03-16
description: Naučte se, jak implementovat zpětné volání při ukládání stránky v Aspose.Tasks
  pro .NET, což umožňuje přizpůsobené zpracování výstupních toků vícestránkových dokumentů.
linktitle: Implement page saving callback in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Implementovat callback pro ukládání stránky v Aspose.Tasks
url: /cs/net/advanced-concepts/page-saving-callback/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Implementace zpětného volání při ukládání stránky v Aspose.Tasks

## Úvod

V tomto tutoriálu se naučíte, jak **implementovat zpětné volání při ukládání stránky** v Aspose.Tasks pro .NET. Tato výkonná funkce vám umožní směrovat každou stránku vícestránkového dokumentu do libovolného proudu, čímž získáte plnou kontrolu nad tím, jak je výstup uložen nebo dále zpracován.

## Rychlé odpovědi
- **Co dělá zpětné volání při ukládání stránky?** Zachytí každou vykreslenou stránku do samostatného proudu, takže s ní můžete pracovat individuálně.  
- **Do jakého formátu mohu exportovat?** Do libovolného formátu podporovaného `ImageSaveOptions`, např. PNG, JPEG, PDF.  
- **Potřebuji licenci?** Pro produkční použití je vyžadována platná licence Aspose.Tasks.  
- **Lze to použít s .NET Core?** Ano, Aspose.Tasks plně podporuje .NET Core a .NET 5/6+.  
- **Je zpětné volání thread‑safe?** Zpětné volání běží ve stejném vlákně, které provádí vykreslování, takže platí běžná pravidla pro thread‑safety.

## Co je **implementace zpětného volání při ukládání stránky**?
Vzor **implementace zpětného volání při ukládání stránky** vám umožňuje vložit vlastní logiku do pipeline ukládání v Aspose.Tasks. Místo přímého zápisu do souboru získáte objekt `Stream` pro každou stránku, což vám umožní uložit jej do paměti, nahrát do cloudového úložiště nebo provést další zpracování.

## Proč exportovat projekt jako PNG se zpětným voláním?
Export projektu jako PNG vám poskytne rastrový obrázek každé stránky Ganttova diagramu, což je ideální pro zprávy, e‑maily nebo vkládání do webových stránek. Použití zpětného volání vám umožní uchovat každou stránku v samostatném `MemoryStream` bez vytváření dočasných souborů na disku.

## Předpoklady

1. **Znalost C#** – základní povědomí o třídách, rozhraních a proudech.  
2. **Aspose.Tasks pro .NET** – stáhněte a nainstalujte z [zde](https://releases.aspose.com/tasks/net/).  
3. **IDE** – Visual Studio, Rider nebo jakýkoli editor kompatibilní s .NET.

## Import jmenných prostorů

Pro začátek importujte požadované jmenné prostory:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
```

## Krok 1: Vytvořte objekt projektu

Načtěte existující soubor MPP do instance `Project`:

```csharp
var project = new Project(DataDir + "Homemoveplan.mpp");
```

## Krok 2: Nakonfigurujte možnosti ukládání obrázku

Nastavte `ImageSaveOptions` pro výstup PNG a připojte vlastní zpětné volání:

```csharp
var imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
var callback = new CustomPageSavingCallback();
imageSaveOptions.PageSavingCallback = callback;
imageSaveOptions.RenderToSinglePage = false;
```

> **Tip:** Nastavení `RenderToSinglePage = false` zajistí, že každá stránka Ganttova diagramu bude vykreslena samostatně, což je nezbytné pro to, aby zpětné volání obdrželo odlišné proudy.

## Krok 3: Uložte projekt se zpětným voláním

Vyvolejte metodu `Save` a jako parametr předávejte `Stream.Null`, protože skutečné proudy jsou dodány zpětným voláním:

```csharp
project.Save(Stream.Null, imageSaveOptions);
```

## Krok 4: Zpracujte uložené proudy stránek

Po dokončení operace ukládání obsahuje zpětné volání kolekci objektů `MemoryStream` – jeden pro každou stránku. Nyní je můžete iterovat:

```csharp
foreach (var stream in callback.PageStreams)
{
    // Process each page stream, e.g., upload to Azure Blob, write to a database, etc.
}
```

## Krok 5: Implementujte vlastní zpětné volání při ukládání stránky

Vytvořte uzavřenou třídu, která implementuje `IPageSavingCallback`. Tato třída zachytí proud každé stránky a uloží jej do seznamu pro pozdější použití.

```csharp
private sealed class CustomPageSavingCallback : IPageSavingCallback
{
    public List<MemoryStream> PageStreams { get; } = new List<MemoryStream>();

    public void PageSaving(PageSavingArgs args)
    {
        var memoryStream = new MemoryStream();
        args.Stream = memoryStream;
        args.KeepStreamOpen = false;
        PageStreams.Add(memoryStream);
    }

    public void OnFinish()
    {
        // Perform any cleanup or finalization
    }
}
```

## Časté chyby a řešení problémů

| Problém | Důvod | Řešení |
|---------|-------|--------|
| **Nejsou vráceny žádné stránky** | `RenderToSinglePage` zůstalo nastaveno na `true`. | Nastavte `RenderToSinglePage = false`, aby se generovaly samostatné stránky. |
| **Proudy jsou prázdné** | `KeepStreamOpen` nastaveno na `true` bez následného uvolnění. | Nechte jej `false` (výchozí) a nechte zpětné volání automaticky uzavřít proudy. |
| **Chyby nedostatku paměti** | Velmi velké projekty generují mnoho vysoce rozlišených PNG. | Zpracovávejte proudy po jednom nebo zvýšte limity paměti virtuálního stroje. |

## Často kladené otázky

**Q1: Co je zpětné volání při ukládání stránky v Aspose.Tasks?**  
A: Zpětné volání při ukládání stránky vám umožní zachytit proces ukládání pro každou stránku vícestránkového dokumentu a poskytnout vlastní `Stream` pro tuto stránku.

**Q2: Mohu pomocí tohoto zpětného volání používat různé formáty pro ukládání stránek?**  
A: Ano. Změnou `SaveFileFormat` můžete exportovat do PNG, JPEG, PDF, SVG atd.

**Q3: Je Aspose.Tasks kompatibilní s .NET Core?**  
A: Rozhodně. Aspose.Tasks podporuje .NET Core, .NET 5 i .NET 6.

**Q4: Jak mohu ošetřit chyby během procesu ukládání stránek?**  
A: Zabalte logiku zpětného volání do bloků try/catch a zaznamenávejte výjimky. Metoda `OnFinish` je vhodné místo pro finální úklid.

**Q5: Kde najdu další zdroje a podporu pro Aspose.Tasks?**  
A: Navštivte [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pro pomoc, přístup k dokumentaci [zde](https://reference.aspose.com/tasks/net/), nebo prozkoumejte další funkce a licenční možnosti na [webu Aspose.Tasks](https://purchase.aspose.com/buy).

---

**Poslední aktualizace:** 2026-03-16  
**Testováno s:** Aspose.Tasks 24.12 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}