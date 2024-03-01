---
title: Manipulace s ukládáním obrázků v Aspose.Tasks
linktitle: Manipulace s ukládáním obrázků v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se, jak zacházet s ukládáním obrázků v Aspose.Tasks pro .NET pomocí podrobných pokynů. Bezproblémově integrujte funkci ukládání obrázků do svých aplikací .NET.
type: docs
weight: 10
url: /cs/net/advanced-concepts/image-saving/
---
## Úvod

V tomto tutoriálu se ponoříme do procesu zpracování ukládání obrázků v Aspose.Tasks pro .NET. Aspose.Tasks je výkonné rozhraní API, které umožňuje vývojářům programově manipulovat se soubory aplikace Microsoft Project. Jedním z běžných úkolů při práci s projektovými soubory je potřeba ukládat obrázky, které mohou obsahovat tabulky, grafy nebo jiné vizuální prvky. Proces rozebereme krok za krokem, zajistíme srozumitelnost a pochopení.

## Předpoklady

Než začneme, ujistěte se, že máte následující předpoklady:

1. Visual Studio: Ujistěte se, že máte v systému nainstalované Visual Studio.
2.  Aspose.Tasks for .NET: Stáhněte si a nainstalujte Aspose.Tasks for .NET z[tady](https://releases.aspose.com/tasks/net/).
3. Základní porozumění C#: Seznamte se se základy programovacího jazyka C#.

## Importovat jmenné prostory

Nejprve importujme potřebné jmenné prostory do našeho projektu:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Krok 1: Vytvořte objekt projektu

Začněte vytvořením objektu Project ze souboru Microsoft Project:

```csharp
var project = new Project("Project1.mpp");
```

## Krok 2: Definujte možnosti uložení

Definujte možnosti uložení pro svůj projekt, určete stránky a další nastavení:

```csharp
var options = GetSaveOptions(1);
```

## Krok 3: Uložte projekt jako HTML

Uložte projekt jako HTML se zadanými možnostmi:

```csharp
project.Save("document_out.html", options);
```

## Krok 4: Implementujte zpětné volání funkce Image Saving

Implementujte rozhraní ImageSavingCallback, abyste zvládli ukládání obrázků:

```csharp
private class ResourcePrefixForNestedResources : IImageSavingCallback
{
    public void ImageSaving(ImageSavingArgs args)
    {
        // Zde je logika ukládání obrázků
    }
}
```

## Krok 5: Uložte obrázky do určeného adresáře

V rámci metody ImageSaving zadejte logiku pro ukládání obrázků do požadovaného adresáře:

```csharp
if (args.FileName.EndsWith("png"))
{
    // Uložte vnořené zdroje
}
else
{
    // Šetřete běžné zdroje
}
```

## Krok 6: Zadejte možnosti uložení

Zadejte možnosti uložení, včetně zpětných volání pro CSS, písma a obrázky:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Zde zadejte možnosti uložení
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## Závěr

Závěrem lze říci, že zpracování ukládání obrázků v Aspose.Tasks for .NET zahrnuje definování možností ukládání a implementaci zpětných volání pro efektivní řízení procesu ukládání. Podle kroků uvedených v tomto kurzu můžete bezproblémově integrovat funkci ukládání obrázků do aplikací .NET.

## FAQ

### Q1: Mohu použít Aspose.Tasks k manipulaci se soubory projektu v jiných formátech kromě HTML?

Odpověď 1: Ano, Aspose.Tasks podporuje různé formáty, jako je PDF, XLSX a MPP.

### Q2: Poskytuje Aspose.Tasks podporu pro integraci cloudového úložiště?

Odpověď 2: Ano, Aspose.Tasks nabízí rozhraní API pro práci s oblíbenými službami cloudového úložiště, jako je Amazon S3 a Disk Google.

### Q3: Je Aspose.Tasks kompatibilní s .NET Core?

Odpověď 3: Ano, Aspose.Tasks je kompatibilní s .NET Core, což vám umožňuje vyvíjet aplikace pro různé platformy.

### Q4: Mohu upravit vzhled uložených obrázků?

Odpověď 4: Ano, vzhled uložených obrázků můžete upravit úpravou logiky ukládání obrázků v rámci metod zpětného volání.

### Q5: Nabízí Aspose.Tasks zkušební verze pro účely hodnocení?

 A5: Ano, můžete získat bezplatnou zkušební verzi Aspose.Tasks od[tady](https://releases.aspose.com/).