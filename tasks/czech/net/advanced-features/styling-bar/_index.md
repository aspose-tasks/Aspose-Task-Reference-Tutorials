---
date: 2026-04-06
description: Naučte se, jak změnit styl pruhů a přizpůsobit barvy pruhů v Aspose.Tasks
  pro .NET, aby se zlepšila vizualizace projektu.
keywords:
- how to change bar
- customize bar colors
- Aspose.Tasks bar styling
linktitle: Styling Bar v Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Jak změnit stylování pruhů v Aspose.Tasks
url: /cs/net/advanced-features/styling-bar/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak změnit stylování pruhů v Aspose.Tasks

## Úvod

If you need to **how to change bar** appearance in a Microsoft Project file, Aspose.Tasks for .NET gives you full control over bar colors, shapes, and text styles. By customizing bar colors and other visual attributes you can make project plans far easier to read and more aligned with your organization’s branding. In this tutorial we’ll walk through a complete, step‑by‑step example that shows you how to change bar styling, from loading a project to exporting it with the new visual rules applied.

## Rychlé odpovědi
- **Co mohu stylovat?** Bars, milestones, and task text in Gantt charts.  
- **Který formát podporuje stylované pruhy?** PDF, XLSX, HTML and native MPP when saved with `PdfSaveOptions`.  
- **Potřebuji licenci?** A commercial license is required for production use; a free trial works for testing.  
- **Mohu použít více stylů?** Yes – add as many `BarStyle` objects as you need.  
- **Je kompatibilní s .NET Core?** Absolutely – works with .NET Framework and .NET Core/5/6+.

## Co je stylování pruhů v Aspose.Tasks?

Bar styling lets you define visual rules that the Aspose.Tasks engine applies when rendering Gantt charts. Each rule (a **BarStyle**) targets a specific item type—tasks, milestones, or summary tasks—and lets you set colors, shapes, and even custom text.

## Proč přizpůsobit barvy pruhů?

Customizing bar colors helps stakeholders instantly identify critical paths, delayed tasks, or milestones. It also lets you match corporate color schemes, making reports look professional and on‑brand.

## Požadavky

Before we begin, make sure you have:

1. **Aspose.Tasks pro .NET** – download it from the [download page](https://releases.aspose.com/tasks/net/).  
2. A development environment that supports .NET (Framework 4.6+, .NET Core 3.1+, or later).  
3. Basic familiarity with C# – the examples use simple, self‑contained code.

## Importování jmenných prostorů

First, import the namespaces that contain the classes we’ll use:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Krok 1: Načtení projektu

Load an existing MPP file (or create a new one) so you have a project object to work with:

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## Krok 2: Konfigurace možností uložení

Create a `PdfSaveOptions` instance and initialise the `BarStyles` collection where we’ll store our custom styles:

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## Krok 3: Definování stylu pruhu

Now we build a `BarStyle` object and set the properties that control how the bar looks. This is where we **customize bar colors** and shapes:

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Set bar item type
style.BarColor = Color.Green; // Set bar color
style.BarShape = BarShape.HalfHeight; // Set bar shape
style.StartShape = Shape.LeftBracket; // Set shape at the beginning of the bar
style.StartShapeColor = Color.Aqua; // Set color of the start shape
style.EndShape = Shape.RightBracket; // Set shape at the end of the bar
style.EndShapeColor = Color.Aquamarine; // Set color of the end shape
style.TextStyle = new TextStyle(); // Set text style
style.TextStyle.BackgroundColor = Color.Black; // Set background color for text
```

## Krok 4: Přizpůsobení konvertoru textu (volitelné)

If you want to tweak the text that appears on the bar, you can assign a custom converter. The example prefixes task names that don’t already start with “T”:

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

## Krok 5: Přidání stylu pruhu do možností

Add the fully configured style to the `BarStyles` collection of the save options:

```csharp
options.BarStyles.Add(style);
```

## Krok 6: Uložení projektu

Finally, export the project. The PDF (or other format) will render the Gantt chart using the bar style we defined:

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## Časté problémy a řešení

| Problém | Důvod | Řešení |
|-------|--------|-----|
| **Styl pruhu nebyl aplikován** | `BarStyles` collection was empty or not attached to the save options. | Ensure you add the `BarStyle` to `options.BarStyles` before calling `Save`. |
| **Barvy vypadají v PDF jinak** | PDF rendering may use a different color profile. | Use standard `System.Drawing.Color` values or define custom ARGB colors. |
| **Konvertor textu hází výjimku null reference** | Task property `Tsk.Name` is null for some tasks. | Add a null‑check before accessing `task.Get(Tsk.Name)`. |

## Často kladené otázky

### Q1: Mohu použít více stylů pruhů v jednom projektu?

A1: Yes, you can define and apply multiple bar styles to different types of tasks within the same project.

### Q2: Je možné dynamicky měnit styly pruhů během běhu aplikace?

A2: Yes, you can dynamically modify bar styles based on certain conditions or user preferences within your application.

### Q3: Podporuje Aspose.Tasks export projektů se stylovanými pruhy do různých formátů souborů?

A3: Yes, Aspose.Tasks supports exporting projects with styled bars to various formats such as PDF, XLSX, and HTML.

### Q4: Existují předdefinované styly pruhů v Aspose.Tasks?

A4: While Aspose.Tasks provides default bar styles, developers can also create custom bar styles tailored to their project requirements.

### Q5: Mohu pomocí API získat a upravit existující styly pruhů v projektu?

A5: Yes, you can retrieve and modify existing bar styles programmatically using Aspose.Tasks for .NET API.

## Často kladené otázky

**Q: Jak změním barvu pruhu pro běžné úkoly místo milníků?**  
A: Set `style.ItemType = BarItemType.Task;` and assign `style.BarColor` to the desired `Color`.

**Q: Mohu tento přístup použít pro stylování pruhů při exportu do HTML?**  
A: Yes. Use `HtmlSaveOptions` and populate its `BarStyles` collection the same way.

**Q: Existuje limit na počet stylů pruhů, které mohu definovat?**  
A: Practically no; you can add as many as needed, but keep performance in mind for very large collections.

**Q: Musím po změně stylů zavolat `project.Calculate()`?**  
A: No, styles are applied during the save operation; recalculation is only required for schedule changes.

---

**Poslední aktualizace:** 2026-04-06  
**Testováno s:** Aspose.Tasks 24.11 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}