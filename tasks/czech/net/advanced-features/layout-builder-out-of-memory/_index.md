---
date: 2026-03-24
description: Naučte se, jak zvládat nedostatek paměti a jak uložit obrázek projektu
  pomocí Aspose.Tasks Layout Builder v .NET. Průvodce krok za krokem s příklady kódu.
linktitle: Out of Memory Handling with Aspose.Tasks Layout Builder
second_title: Aspose.Tasks .NET API
title: Zpracování nedostatku paměti s Aspose.Tasks Layout Builder (C#)
url: /cs/net/advanced-features/layout-builder-out-of-memory/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Řízení nedostatku paměti s Aspose.Tasks Layout Builder

## Úvod

Řízení nedostatku paměti je kritickou součástí tvorby spolehlivých aplikací .NET pracujících s velkými soubory projektů. Při generování vizualizací pomocí Aspose.Tasks Layout Builder můžete rychle narazit na výjimky související s pamětí, zejména u složitých Ganttových diagramů. V tomto tutoriálu vás provedeme tím, jak **zachytit výjimky paměti**, **přizpůsobit zobrazení Gantt** a **bezpečně uložit obrázek projektu**, aby vaše aplikace zůstala responzivní i při masivních plánech.

## Rychlé odpovědi
- **Co je řízení nedostatku paměti?** Správa využití paměti a zachytávání chyb typu `OutOfMemoryException` při zpracování velkých dat.
- **Které API pomáhá?** Aspose.Tasks Layout Builder pro .NET.
- **Typický scénář?** Vykreslení vysoce rozlišeného Ganttova diagramu do PNG.
- **Klíčová podmínka?** .NET (Framework 4.5+ nebo .NET 6) s nainstalovaným Aspose.Tasks.
- **Jak zachytit chyby?** Použijte bloky `try…catch` pro `ApsLayoutBuilderOutOfMemoryException` a související výjimky.

## Požadavky

Než se ponoříte do kódu, ujistěte se, že máte:

1. **Základy C#** – měli byste být pohodlní se standardní syntaxí C#.
2. **Aspose.Tasks pro .NET** nainstalovaný. Pokud jste jej ještě nepřidali, stáhněte jej z [zde](https://releases.aspose.com/tasks/net/).
3. **IDE** jako Visual Studio (nebo VS Code s rozšířením C#) pro kompilaci a spuštění ukázky.

## Import Namespaces

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## Průvodce krok za krokem

### Krok 1: Načtení projektu

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```

Tento řádek načte **Blank2010.mpp** do instance `Project`, připravujíc ji pro vizualizaci.

### Krok 2: Přizpůsobení zobrazení Ganttova diagramu

```csharp
var ganttChart = (GanttChartView)project.Views.ToList()[0];
ganttChart.MiddleTimescaleTier.Unit = TimescaleUnit.Hours;
ganttChart.BottomTimescaleTier.Unit = TimescaleUnit.Minutes;
ganttChart.BottomTimescaleTier.Count = 1;
```

Zde **přizpůsobujeme zobrazení Gantt** úpravou středních a spodních úrovní časové osy. Změna těchto úrovní snižuje množství dat vykreslovaných najednou, což může pomoci zmírnit tlak na paměť.

### Krok 3: Nastavení možností uložení obrázku

```csharp
var options = new ImageSaveOptions(SaveFileFormat.Png);
options.Timescale = Timescale.DefinedInView;
```

`ImageSaveOptions` říká Aspose.Tasks, jak diagram vykreslit. Vybereme PNG jako výstupní formát a svážeme časovou osu s právě přizpůsobeným zobrazením.

### Krok 4: Uložení projektu jako obrázku

```csharp
project.Save(DataDir + "SaveToStreamWithOptionsAndCatchException_out.mpp", options);
```

Volání `Save` **uloží obrázek projektu** pomocí výše definovaných možností. Pokud je projekt velmi velký, toto je místo, kde se nejpravděpodobněji objeví podmínka nedostatku paměti.

### Krok 5: Zpracování výjimek

```csharp
catch (ApsLayoutBuilderOutOfMemoryException ex)
{
    Console.WriteLine(ex.Message);
}
catch (BitmapInvalidSizeException ex)
{
    Console.WriteLine(ex.Message);
}
```

Zachycením `ApsLayoutBuilderOutOfMemoryException` **zpracujete výjimku paměti** elegantně, poskytujete jasnou zprávu místo zhroucení aplikace. Druhý catch řeší problémy s velikostí bitmapy, které mohou také nastat při vykreslování obrovských diagramů.

## Časté problémy a řešení

| Problém | Proč se to děje | Řešení |
|---------|----------------|--------|
| **OutOfMemoryException** | Vykreslování velmi vysoce rozlišeného obrázku spotřebuje více RAM, než může proces alokovat. | Snižte rozměry obrázku, zjednodušte úrovně časové osy nebo rozdělte diagram do více obrázků. |
| **BitmapInvalidSizeException** | Požadovaná velikost bitmapy překračuje maximální limit platformy. | Omezte šířku/výšku v `ImageSaveOptions` nebo vykreslujte po částech. |
| **Nízký výkon** | Velké soubory projektů vyžadují hodně zpracování. | Povolte `project.Set(Prj.SaveToCache, true)` před vykreslením, nebo použijte vlákno na pozadí. |

## Často kladené otázky

### Q1: Co je Aspose.Tasks pro .NET?

A1: Aspose.Tasks pro .NET je výkonné API, které umožňuje vývojářům programově manipulovat se soubory Microsoft Project v .NET aplikacích.

### Q2: Jak mohu získat dočasnou licenci pro Aspose.Tasks?

A2: Dočasnou licenci pro Aspose.Tasks můžete získat návštěvou [tohoto odkazu](https://purchase.aspose.com/temporary-license/).

### Q3: Je Aspose.Tasks vhodný pro práci s velkými soubory projektů?

A3: Ano, Aspose.Tasks poskytuje funkce a optimalizace pro efektivní práci s velkými soubory projektů, ale vývojáři by měli i nadále zvažovat strategie správy paměti.

### Q4: Mohu pomocí Aspose.Tasks přizpůsobit vzhled Ganttových diagramů?

A4: Rozhodně! Aspose.Tasks poskytuje rozsáhlé možnosti přizpůsobení vzhledu a rozvržení Ganttových diagramů podle vašich požadavků.

### Q5: Kde mohu najít další pomoc a podporu pro Aspose.Tasks?

A5: Další pomoc a podporu, stejně jako komunitní diskusi, najdete na [fóru Aspose.Tasks](https://forum.aspose.com/c/tasks/15).

## Často kladené otázky

**Q: Jak mohu snížit využití paměti při ukládání obrázku projektu?**  
A: Snižte rozlišení obrázku, omezte rozsah časové osy nebo uložte diagram do více menších segmentů.

**Q: Je možné streamovat obrázek přímo do webové odpovědi?**  
A: Ano, můžete použít `project.Save(stream, options)` a zapsat stream do HTTP odpovědi.

**Q: Podporuje Aspose.Tasks .NET Core a .NET 5/6?**  
A: Knihovna je plně kompatibilní s .NET Core, .NET 5 a .NET 6.

**Q: Co mám dělat, pokud i po optimalizaci stále narazím na chybu nedostatku paměti?**  
A: Zvažte zpracování projektu na stroji s více RAM nebo přesuňte vykreslování do služby na pozadí.

**Q: Mohu exportovat Gantt diagram do jiných formátů než PNG?**  
A: Ano, `ImageSaveOptions` podporuje JPEG, BMP a TIFF kromě PNG.

---

**Poslední aktualizace:** 2026-03-24  
**Testováno s:** Aspose.Tasks 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}