---
date: 2026-03-21
description: Naučte se, jak exportovat obrázek a ošetřit výjimku BitmapInvalidSizeException
  při ukládání projektu jako obrázku v Aspose.Tasks pro .NET. Obsahuje kroky k uložení
  projektu jako obrázku a exportu projektu do PNG.
linktitle: Handling Invalid Size Exception for Bitmap in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Jak exportovat obrázek a ošetřit výjimku neplatné velikosti
url: /cs/net/advanced-features/bitmap-invalid-size-exception/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak exportovat obrázek – Zpracování výjimky neplatné velikosti bitmapy v Aspose.Tasks

V tomto tutoriálu se naučíte **jak exportovat obrázek** ze souboru Microsoft Project pomocí Aspose.Tasks pro .NET a, co je ještě důležitější, jak zachytit `BitmapInvalidSizeException`, která může během procesu nastat. Export projektu jako obrázku je běžná potřeba pro reportovací dashboardy, dokumentaci nebo jednoduše sdílení vizuálního snímku plánu. Na konci tohoto průvodce budete schopni **spolehlivě uložit projekt jako obrázek** a dokonce **exportovat projekt do formátu PNG** bez neočekávaných pádů.

## Rychlé odpovědi
- **Jaká výjimka může nastat při exportu obrázku?** `BitmapInvalidSizeException`  
- **Jaký formát je použit v příkladu?** PNG (`SaveFileFormat.Png`)  
- **Potřebuji speciální licenci?** Je vyžadována platná licence Aspose.Tasks pro produkční použití.  
- **Mohu změnit časovou škálu?** Ano – můžete nastavit jednotku časové škály (minuty, hodiny, dny atd.).  
- **Je kód kompatibilní s .NET Core?** Rozhodně – stejné API funguje na .NET Framework i .NET Core.

## Co je BitmapInvalidSizeException?
`BitmapInvalidSizeException` je vyvolána, když jsou rozměry bitmapy vypočtené pro obrázek mimo podporovaný rozsah (např. šířka nebo výška je nula nebo překračuje interní limity). K tomu obvykle dochází, když nastavení časové škály nebo zobrazení vytvoří obrázek, který je příliš velký nebo příliš malý.

## Proč exportovat projekt jako obrázek?
- **Vizualizované reportování** – vložte Ganttův diagram do PDF, Word dokumentů nebo webových stránek.  
- **Sdílení napříč platformami** – soubory PNG lze zobrazit na jakémkoli zařízení bez potřeby Microsoft Project.  
- **Výkon** – obrázky jsou lehké ve srovnání s plnými soubory projektu pro rychlé náhledy.

## Předpoklady
1. Základní znalost C# a vývoje v .NET.  
2. Aspose.Tasks pro .NET nainstalováno (NuGet balíček `Aspose.Tasks`).  
3. Ukázkový soubor Microsoft Project (např. `Blank2010.mpp`).  

## Importujte jmenné prostory
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Průvodce krok za krokem

### Krok 1: Inicializace projektu a výběr zobrazení
Nejprve vytvořte instanci `Project` a vyberte zobrazení, které chcete vykreslit (zde používáme první Ganttův diagram).

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
GanttChartView view = (GanttChartView) project.Views.ToList()[0];
```

### Krok 2: Nastavení možností uložení obrázku (Export projektu do PNG)
Nastavte požadovaný formát obrázku a řekněte Aspose.Tasks, aby použil časovou škálu definovanou v zobrazení.

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png)
{
    Timescale = Timescale.DefinedInView
};
```

### Krok 3: Úprava jednotky časové škály (Kontrola velikosti obrázku)
Změna časové škály ovlivňuje rozměry bitmapy. V tomto příkladu používáme **minuty**, aby byla velikost obrázku zvládnutelná.

```csharp
view.MiddleTimescaleTier.Unit = TimescaleUnit.Minutes;
view.MiddleTimescaleTier.Count = 1;
```

### Krok 4: Pokus o uložení projektu jako obrázku
Tento řádek provádí skutečnou operaci **uložení projektu jako obrázku**.

```csharp
project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
```

### Krok 5: Zachycení a zpracování BitmapInvalidSizeException
Zabalte volání uložení do bloku `try / catch`, aby vaše aplikace mohla elegantně reagovat, pokud je velikost bitmapy neplatná.

```csharp
try
{
    // Attempt to save project as an image
    project.Save(DataDir + "SaveToStreamAndCatchException_out.mpp", options);
}
catch (BitmapInvalidSizeException ex)
{
    // Handle the exception – for example, log it or adjust the timescale
    Console.WriteLine(ex.Message);
}
```

## Časté problémy a řešení
| Problém | Příčina | Řešení |
|---------|----------|--------|
| Výjimka stále vyvolána po úpravě časové škály | Časová škála stále vede k příliš velké bitmapě | Snižte `view.MiddleTimescaleTier.Count` nebo přepněte na hrubší `TimescaleUnit` (např. Hodiny). |
| Výstupní soubor je prázdný | Nesprávná cesta k souboru nebo chybějící oprávnění k zápisu | Ověřte, že `DataDir` ukazuje na zapisovatelnou složku a název souboru končí na `.png`, pokud měníte formát. |
| Kvalita obrázku je špatná | Výchozí DPI může být nízké | Nastavte `options.DpiX` a `options.DpiY` na vyšší hodnoty (např. 300). |

## Často kladené otázky

**Q: Co způsobuje BitmapInvalidSizeException v Aspose.Tasks?**  
A: Vyskytuje se, když jsou vypočtené rozměry bitmapy neplatné – typicky protože časová škála vytvoří obrázek, který je příliš velký nebo má nulovou šířku/výšku.

**Q: Mohu přizpůsobit časovou škálu při exportu obrázku?**  
A: Ano. Můžete upravit `view.MiddleTimescaleTier.Unit` a `Count` podle svých potřeb, jak je ukázáno v tutoriálu.

**Q: Podporuje Aspose.Tasks jiné formáty obrázků kromě PNG?**  
A: Rozhodně. `SaveFileFormat` zahrnuje také JPEG, BMP, GIF a TIFF. Stačí změnit hodnotu výčtu v `ImageSaveOptions`.

**Q: Je licence vyžadována pro export obrázků v produkčním prostředí?**  
A: Ano. I když knihovna funguje v evaluačním režimu, komerční licence odstraňuje omezení hodnocení a poskytuje plnou podporu.

**Q: Jak mohu zlepšit kvalitu exportovaného PNG?**  
A: Zvyšte nastavení DPI (`options.DpiX` a `options.DpiY`) nebo upravte časovou škálu zobrazení, aby se vytvořila větší bitmapa.

## Závěr
Po provedení výše uvedených kroků nyní víte **jak exportovat obrázek** ze souboru Project, jak **uložit projekt jako obrázek** a jak elegantně zpracovat `BitmapInvalidSizeException`. Tyto techniky činí vaše reportovací kanály robustnější a zajišťují, že vizuální exporty fungují spolehlivě napříč různými velikostmi projektů a časovými škálami.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2026-03-21  
**Testováno s:** Aspose.Tasks 24.12 for .NET  
**Autor:** Aspose  

---