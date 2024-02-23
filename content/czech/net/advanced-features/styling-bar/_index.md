---
title: Styling Bar v Aspose.Tasks
linktitle: Styling Bar v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se stylovat pruhy v Aspose.Tasks pro .NET a vylepšit tak vizualizaci projektu.
type: docs
weight: 19
url: /cs/net/advanced-features/styling-bar/
---
## Úvod

Stylování pruhů v Aspose.Tasks je základním aspektem vytváření vizuálně přitažlivých projektových plánů. Díky flexibilitě, kterou nabízí Aspose.Tasks API, mohou vývojáři přizpůsobit různé aspekty pruhů, jako je barva, tvar a styl textu, a zlepšit tak vizualizaci projektu. V tomto tutoriálu prozkoumáme, jak stylovat pruhy pomocí Aspose.Tasks pro .NET, přičemž každý příklad rozdělíme do zvládnutelných kroků.

## Předpoklady

Než začneme, ujistěte se, že máte splněny následující předpoklady:

1.  Aspose.Tasks for .NET Library: Stáhněte si a nainstalujte knihovnu Aspose.Tasks for .NET z[stránka ke stažení](https://releases.aspose.com/tasks/net/).
2. Vývojové prostředí: Nastavte vývojové prostředí s podporou rámce .NET.
3. Základní porozumění C#: Výhodou bude znalost programovacího jazyka C#.

## Importovat jmenné prostory

Nejprve importujme potřebné jmenné prostory pro přístup ke třídám a metodám Aspose.Tasks:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## Krok 1: Načtěte projekt

Chcete-li začít, načtěte soubor projektu pomocí rozhraní API Aspose.Tasks:

```csharp
// Cesta k adresáři dokumentů.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## Krok 2: Nakonfigurujte možnosti uložení

Definujte možnosti uložení a určete styly pruhů, které se mají použít:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## Krok 3: Definujte styl pruhu

Vytvořte nový styl pruhu a přizpůsobte jeho vlastnosti:

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Nastavte typ položky lišty
style.BarColor = Color.Green; // Nastavit barvu pruhu
style.BarShape = BarShape.HalfHeight; //Nastavte tvar tyče
style.StartShape = Shape.LeftBracket; // Nastavte tvar na začátek lišty
style.StartShapeColor = Color.Aqua; // Nastavte barvu počátečního tvaru
style.EndShape = Shape.RightBracket; // Nastavte tvar na konci lišty
style.EndShapeColor = Color.Aquamarine; // Nastavte barvu koncového tvaru
style.TextStyle = new TextStyle(); // Nastavit styl textu
style.TextStyle.BackgroundColor = Color.Black; // Nastavit barvu pozadí textu
```

## Krok 4: Přizpůsobte převaděč textu

Volitelně upravte převaděč textu tak, aby upravil vykreslování textu:

```csharp
style.LeftBarTextConverter = task =>
{
    if (!task.Get(Tsk.Name).StartsWith("T"))
    {
        task.Set(Tsk.Name, "T" + task.Get(Tsk.Name));
    }
    return task.Get(Tsk.Name);
};
```

## Krok 5: Přidejte styl pruhu do možností

Přidejte nakonfigurovaný styl pruhu do možností uložení:

```csharp
options.BarStyles.Add(style);
```

## Krok 6: Uložte projekt

Nakonec uložte projekt s použitými styly pruhů:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## Závěr

Přizpůsobení stylů pruhů v Aspose.Tasks for .NET poskytuje vývojářům možnost vytvářet vizuálně přitažlivé projektové plány. Podle kroků uvedených v tomto kurzu můžete efektivně stylovat pruhy tak, aby splňovaly konkrétní požadavky na vizualizaci projektu.

## FAQ

### Q1: Mohu použít více stylů pruhů na jeden projekt?

Odpověď 1: Ano, můžete definovat a použít více stylů pruhů na různé typy úkolů v rámci stejného projektu.
   
### Q2: Je možné dynamicky měnit styly pruhů za běhu?

Odpověď 2: Ano, styly pruhů můžete dynamicky upravovat na základě určitých podmínek nebo uživatelských předvoleb ve vaší aplikaci.
   
### Q3: Podporuje Aspose.Tasks export projektů se stylizovanými pruhy do různých formátů souborů?

Odpověď 3: Ano, Aspose.Tasks podporuje export projektů se stylizovanými pruhy do různých formátů, jako jsou PDF, XLSX a HTML.
   
### Q4: Jsou v Aspose.Tasks k dispozici předdefinované styly pruhů?

A4: Zatímco Aspose.Tasks poskytuje výchozí styly pruhů, vývojáři mohou také vytvářet vlastní styly pruhů přizpůsobené požadavkům jejich projektu.
   
### Q5: Mohu načíst a upravit stávající styly pruhů v rámci projektu pomocí rozhraní API?

A5: Ano, můžete načíst a upravit existující styly pruhů programově pomocí Aspose.Tasks for .NET API.