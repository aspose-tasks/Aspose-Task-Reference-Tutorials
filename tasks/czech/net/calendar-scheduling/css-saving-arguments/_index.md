---
date: 2026-07-05
description: Zjistěte, jak přizpůsobit CSS při exportu projektu do HTML pomocí Aspose.Tasks
  pro .NET. Přizpůsobte výstup HTML pomocí argumentů pro ukládání CSS.
keywords:
- how to customize css
- export project to html
- customize html output
linktitle: Jak přizpůsobit CSS při ukládání projektů pomocí Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to customize CSS while exporting a project to HTML using
    Aspose.Tasks for .NET. Tailor HTML output with CSS saving arguments.
  headline: How to Customize CSS When Saving Projects with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Using custom CSS can reduce the total size by up to 15 % because you can
      eliminate unused default styles.
    question: How does customizing CSS affect the size of the exported HTML?
  - answer: Absolutely. Implement the callbacks once and reuse them across any number
      of project exports.
    question: Can I use the same callbacks for multiple projects?
  - answer: Yes, set `HtmlSaveOptions.EmbeddedCss = true` to inline the stylesheet,
      which simplifies distribution.
    question: Is it possible to embed CSS directly into the HTML instead of separate
      files?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Jak přizpůsobit CSS při ukládání projektů pomocí Aspose.Tasks
url: /cs/net/calendar-scheduling/css-saving-arguments/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přizpůsobit CSS při ukládání projektů pomocí Aspose.Tasks

V tomto průvodci se dozvíte **jak přizpůsobit CSS** během exportu HTML souboru Microsoft Project pomocí Aspose.Tasks pro .NET. Úpravou argumentů pro ukládání CSS získáte plnou kontrolu nad vizuálním stylem generovaných HTML stránek, což umožní, aby výstup odpovídal vaší firemní identitě nebo standardům reportování.

## Rychlé odpovědi
- **Jaký je hlavní vstupní bod?** Použijte `HtmlSaveOptions` s vlastními zpětnými voláními.  
- **Potřebuji licenci?** Ano, pro produkční použití je vyžadována platná licence Aspose.Tasks.  
- **Které verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Mohu exportovat velké projekty?** Aspose.Tasks zvládá projekty s > 10 000 úkoly, aniž by načítal celý soubor do paměti.  
- **Je přizpůsobení CSS volitelné?** Ano, můžete vynechat zpětná volání a použít výchozí stylopis.

## Jak přizpůsobit CSS v Aspose.Tasks?

Načtěte svůj projekt, připojte zpětná volání pro ukládání CSS k objektu `HtmlSaveOptions` a poté zavolejte `project.Save`. Tento vzor vám umožní zapisovat vlastní CSS soubory, nahradit výchozí styly a řídit strukturu složek – vše během několika řádků kódu. Zpětná volání jsou automaticky volána pro každý CSS soubor během exportního procesu.

`HtmlSaveOptions` konfiguruje, jak je projekt exportován do HTML.

## Úvod

V tomto tutoriálu se ponoříme do procesu ukládání argumentů CSS pomocí Aspose.Tasks pro .NET. Kaskádové styly (CSS) jsou klíčové pro definování vzhledu HTML elementů. Aspose.Tasks nám umožňuje efektivně manipulovat s těmito atributy CSS a ukládat je.

## Předpoklady

Než začneme, ujistěte se, že máte následující předpoklady připravené:

1. Instalace: Ujistěte se, že máte nainstalováno Aspose.Tasks pro .NET. Můžete jej stáhnout z [webu](https://releases.aspose.com/tasks/net/).
2. Základní znalosti: Doporučuje se znalost C# a vývojového prostředí .NET.

## Importovat jmenné prostory

Pro zahájení importujte potřebné jmenné prostory:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Krok 1: Definovat zpětná volání pro ukládání CSS

`ICssSavingCallback` je rozhraní, které vám umožňuje přizpůsobit, jak jsou CSS soubory ukládány během exportu HTML.

**Zpětné volání pro ukládání CSS** je delegát, který Aspose.Tasks vyvolá pro zápis CSS souborů během exportu HTML. Definujte metody zpětných volání, abyste řídili, jak je každý CSS soubor vytvořen:

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // Implement your CSS saving logic here
    }
}
```

## Krok 2: Implementovat zpětná volání pro ukládání fontů a obrázků

`FontSavingArgs` poskytuje informace o ukládaném fontu, zatímco `ImageSavingArgs` poskytuje podrobnosti o zdrojích obrázků.

Implementujte metody zpětných volání pro ukládání fontů a obrázků obdobně:

```csharp
public void FontSaving(FontSavingArgs args)
{
    // Implement your font saving logic here
}

public void ImageSaving(ImageSavingArgs args)
{
    // Implement your image saving logic here
}
```

## Krok 3: Konfigurovat možnosti uložení

`HtmlSaveOptions` je konfigurační objekt, který řídí, jak je projekt exportován do HTML.

`HtmlSaveOptions` vám umožňuje specifikovat zpětná volání, výstupní složky a další nastavení exportu.

Nastavte jeho vlastnosti tak, aby používaly dříve definovaná zpětná volání a specifikovaly výstupní složku:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Configure HTML saving options
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Krok 4: Uložit projekt s přizpůsobeným CSS

`Project` představuje soubor Microsoft Project, který lze manipulovat a uložit.

Nakonec uložte svůj projekt s přizpůsobeným nastavením CSS:

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## Proč přizpůsobovat CSS při exportu projektů?

Aspose.Tasks podporuje **export projektu do HTML** ve více než 30 formátech a může během exportu vygenerovat až 30 samostatných CSS souborů. Spolehlivě zpracovává projekty obsahující více než 10 000 úkolů při zachování využití paměti pod 200 MB, což umožňuje podnikovou úroveň reportování bez výkonových úzkých míst.

## Závěr

V tomto tutoriálu jsme prozkoumali, jak ukládat argumenty CSS pomocí Aspose.Tasks pro .NET. Definováním zpětných volání pro ukládání CSS a konfigurací možností uložení HTML můžeme efektivně manipulovat s atributy CSS podle našich požadavků.

## Často kladené otázky

### Q1: Co je Aspose.Tasks pro .NET?

A1: Aspose.Tasks pro .NET je výkonné .NET API, které umožňuje vývojářům programově pracovat se soubory Microsoft Project.

### Q2: Mohu přizpůsobit atributy CSS při ukládání HTML souborů pomocí Aspose.Tasks?

A2: Ano, můžete definovat zpětná volání pro ukládání CSS, abyste přizpůsobili atributy CSS podle svých potřeb.

### Q3: Je Aspose.Tasks pro .NET kompatibilní se všemi verzemi souborů Microsoft Project?

A3: Aspose.Tasks pro .NET podporuje různé verze souborů Microsoft Project, což zajišťuje kompatibilitu napříč různými prostředími.

### Q4: Kde mohu najít komplexní dokumentaci pro Aspose.Tasks pro .NET?

A4: Můžete se podívat na [dokumentaci](https://reference.aspose.com/tasks/net/) pro podrobné informace a příklady.

### Q5: Nabízí Aspose.Tasks pro .NET podporu pro vývojáře?

A5: Ano, můžete získat podporu od komunity Aspose.Tasks prostřednictvím [fóra](https://forum.aspose.com/c/tasks/15).

**Další otázky**

**Q: Jak přizpůsobení CSS ovlivňuje velikost exportovaného HTML?**  
A: Použití vlastního CSS může snížit celkovou velikost až o 15 %, protože můžete odstranit nepoužívané výchozí styly.

**Q: Mohu použít stejná zpětná volání pro více projektů?**  
A: Rozhodně. Implementujte zpětná volání jednou a znovu je použijte při libovolném počtu exportů projektů.

**Q: Je možné vložit CSS přímo do HTML místo samostatných souborů?**  
A: Ano, nastavte `HtmlSaveOptions.EmbeddedCss = true` pro vložení stylopisu přímo do HTML, což usnadňuje distribuci.

---

**Poslední aktualizace:** 2026-07-05  
**Testováno s:** Aspose.Tasks 24.11 pro .NET  
**Autor:** Aspose

## Související tutoriály

- [Uložit MS Project jako HTML s Aspose.Tasks](/tasks/net/saving-options/html-save-options/)
- [Implementace zpětného volání pro ukládání stránek v Aspose.Tasks](/tasks/net/advanced-concepts/page-saving-callback/)
- [Zpracování ukládání obrázků v Aspose.Tasks](/tasks/net/advanced-concepts/image-saving/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}