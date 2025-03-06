---
title: CSS ukládání argumentů v Aspose.Tasks
linktitle: CSS ukládání argumentů v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Zjistěte, jak uložit argumenty CSS v Aspose.Tasks pro .NET a přizpůsobit tak výstup HTML. Vylepšete prezentaci pomocí přizpůsobených nastavení CSS.
weight: 20
url: /cs/net/calendar-scheduling/css-saving-arguments/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# CSS ukládání argumentů v Aspose.Tasks

## Úvod

tomto tutoriálu se ponoříme do procesu ukládání argumentů CSS pomocí Aspose.Tasks for .NET. Cascading Style Sheets (CSS) jsou klíčové pro definování prezentace prvků HTML. Aspose.Tasks nám umožňuje efektivně manipulovat a ukládat tyto CSS atributy.

## Předpoklady

Než začneme, ujistěte se, že máte splněny následující předpoklady:

1.  Instalace: Ujistěte se, že jste nainstalovali Aspose.Tasks pro .NET. Můžete si jej stáhnout z[webová stránka](https://releases.aspose.com/tasks/net/).

2. Základní znalosti: Doporučuje se znalost vývojového prostředí C# a .NET.

## Importovat jmenné prostory

Chcete-li začít, importujte potřebné jmenné prostory:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```
## Krok 1: Definujte CSS Saving Callbacks

Nejprve definujeme metody zpětného volání pro ukládání CSS, abychom zvládli ukládání souborů CSS:

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // Zde implementujte svou logiku ukládání CSS
    }
}
```

## Krok 2: Implementujte zpětná volání pro ukládání písem a obrázků

Dále implementujte metody zpětného volání pro ukládání písem a obrázků podobně:

```csharp
public void FontSaving(FontSavingArgs args)
{
    // Zde implementujte svou logiku ukládání písem
}

public void ImageSaving(ImageSavingArgs args)
{
    // Zde implementujte svou logiku ukládání obrázků
}
```

## Krok 3: Nakonfigurujte možnosti uložení

Nyní nakonfigurujte možnosti uložení HTML, abyste využili implementovaná zpětná volání:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        //Nakonfigurujte možnosti ukládání HTML
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Krok 4: Uložte projekt pomocí přizpůsobeného CSS

Nakonec uložte projekt s přizpůsobeným nastavením CSS:

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## Závěr

V tomto tutoriálu jsme prozkoumali, jak uložit argumenty CSS pomocí Aspose.Tasks for .NET. Definováním zpětných volání pro ukládání CSS a konfigurací možností ukládání HTML můžeme efektivně manipulovat s atributy CSS podle našich požadavků.

## Nejčastější dotazy

### Q1: Co je Aspose.Tasks pro .NET?

Odpověď 1: Aspose.Tasks for .NET je výkonné rozhraní .NET API, které umožňuje vývojářům pracovat se soubory aplikace Microsoft Project programově.

### Q2: Mohu přizpůsobit atributy CSS při ukládání souborů HTML pomocí Aspose.Tasks?

Odpověď 2: Ano, můžete definovat zpětná volání pro ukládání CSS pro přizpůsobení atributů CSS podle vašich potřeb.

### Q3: Je Aspose.Tasks for .NET kompatibilní se všemi verzemi souborů aplikace Microsoft Project?

A3: Aspose.Tasks for .NET podporuje různé verze souborů aplikace Microsoft Project a zajišťuje kompatibilitu v různých prostředích.

### Q4: Kde najdu komplexní dokumentaci pro Aspose.Tasks pro .NET?

A4: Můžete odkazovat na[dokumentace](https://reference.aspose.com/tasks/net/) pro podrobné informace a příklady.

### Q5: Nabízí Aspose.Tasks for .NET podporu pro vývojáře?

 A5: Ano, můžete získat podporu od komunity Aspose.Tasks prostřednictvím[Fórum](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
