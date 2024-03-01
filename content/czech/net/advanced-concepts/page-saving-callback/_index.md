---
title: Implementace Page Saving Callback v Aspose.Tasks
linktitle: Implementace Page Saving Callback v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Zjistěte, jak implementovat zpětné volání pro ukládání stránky v Aspose.Tasks pro .NET, umožňující přizpůsobené zpracování vícestránkových výstupních proudů dokumentů.
type: docs
weight: 12
url: /cs/net/advanced-concepts/page-saving-callback/
---
## Úvod

V tomto tutoriálu prozkoumáme, jak implementovat zpětné volání ukládání stránky v Aspose.Tasks pro .NET. Tato funkce nám umožňuje uložit vícestránkový dokument do streamů poskytovaných uživateli, což nabízí flexibilitu a přizpůsobení při zpracování výstupu.

## Předpoklady:

Než začneme, ujistěte se, že máte následující:

1. Znalost programovacího jazyka C#: Měli byste mít základní znalosti o syntaxi a konceptech C#.
   
2.  Instalace Aspose.Tasks for .NET: Ujistěte se, že jste ve svém vývojovém prostředí nainstalovali knihovnu Aspose.Tasks. Můžete si jej stáhnout z[tady](https://releases.aspose.com/tasks/net/).

3. Nastavení vývojového prostředí: Nastavte preferované IDE pro vývoj .NET, jako je Visual Studio.

## Importovat jmenné prostory:

Chcete-li začít, musíte do kódu C# importovat potřebné jmenné prostory:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;

```

## Krok 1: Vytvořte objekt projektu

 Instantovat a`Project` objekt načtením existujícího souboru projektu:

```csharp
var project = new Project(DataDir + "Homemoveplan.mpp");
```

## Krok 2: Nakonfigurujte možnosti uložení obrázku

 Definovat`ImageSaveOptions` přizpůsobit chování ukládání stránky nastavením`PageSavingCallback` vlastnictví:

```csharp
var imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
var callback = new CustomPageSavingCallback();
imageSaveOptions.PageSavingCallback = callback;
imageSaveOptions.RenderToSinglePage = false;
```

## Krok 3: Uložte projekt pomocí zpětného volání

Uložte projekt pomocí nakonfigurovaných možností uložení obrazu:

```csharp
project.Save(Stream.Null, imageSaveOptions);
```

## Krok 4: Zpracujte uložené streamy stránek

Procházejte proudy stránek poskytované zpětným voláním a zpracujte každou stránku samostatně:

```csharp
foreach (var stream in callback.PageStreams)
{
    // Zpracujte každý datový proud stránky
}
```

## Krok 5: Implementujte zpětné volání pro ukládání vlastních stránek

 Vytvořte třídu, která implementuje`IPageSavingCallback` rozhraní pro zpracování ukládání stránky:

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
        // Proveďte jakékoli čištění nebo finalizaci
    }
}
```

## Závěr:

V tomto tutoriálu jsme se naučili implementovat zpětné volání pro ukládání stránky v Aspose.Tasks pro .NET, což nám umožňuje ukládat vícestránkové dokumenty do samostatných proudů. Pomocí těchto kroků můžete vylepšit funkčnost vaší aplikace a dosáhnout přizpůsobeného zpracování výstupu.

## FAQ

### Q1: Co je zpětné volání ukládání stránky v Aspose.Tasks?

Odpověď 1: Zpětné volání pro ukládání stránky je funkce v Aspose.Tasks, která umožňuje uživatelům přizpůsobit proces ukládání vícestránkových dokumentů poskytováním datových proudů pro každou stránku jednotlivě.

### Q2: Mohu použít různé formáty pro ukládání stránek pomocí tohoto zpětného volání?

Odpověď 2: Ano, můžete použít různé formáty souborů podporované Aspose.Tasks, jako je PNG, JPEG, PDF atd., pro ukládání stránek se zpětným voláním.

### Q3: Je Aspose.Tasks kompatibilní s .NET Core?

Odpověď 3: Ano, Aspose.Tasks podporuje .NET Core a umožňuje vývojářům používat jeho funkce v aplikacích pro různé platformy.

### Q4: Jak mohu zvládnout chyby během procesu ukládání stránky?

A4: V rámci metod zpětného volání můžete implementovat mechanismy zpracování chyb, abyste mohli spravovat výjimky a zajistit robustnost vaší aplikace.

### Q5: Kde najdu další zdroje a podporu pro Aspose.Tasks?

 A5: Můžete navštívit[Fórum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pro pomoc, přístup k dokumentaci[tady](https://reference.aspose.com/tasks/net/) nebo prozkoumejte další funkce a možnosti licencování na[Web Aspose.Tasks](https://purchase.aspose.com/buy).