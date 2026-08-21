---
date: 2026-03-19
description: Naučte se, jak přidat více vlastních sloupců a nastavit šířku vlastního
  sloupce při exportu projektu do XML pomocí Aspose.Tasks pro .NET.
linktitle: Add Multiple Custom Columns to Assignment View in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Přidat více vlastních sloupců do zobrazení přiřazení v Aspose.Tasks
url: /cs/net/advanced-features/assignment-view-column/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidání více vlastních sloupců do zobrazení přiřazení v Aspose.Tasks

## Úvod

V tomto tutoriálu se dozvíte **jak přidat více vlastních sloupců** do zobrazení přiřazení pomocí Aspose.Tasks pro .NET. Vlastní sloupce vám umožní zobrazit další data—například poznámky, náklady nebo vlastní příznaky—přímo v exportovaných zprávách. Na konci průvodce budete schopni nastavit šířku vlastního sloupce, exportovat projekt do XML a přizpůsobit zobrazení tak, aby vyhovovalo vašim potřebám řízení projektů.

## Rychlé odpovědi
- **Co mohu dosáhnout?** Zobrazit libovolná data přiřazení ve vlastních sloupcích a řídit jejich vzhled.  
- **Jaký formát to podporuje?** Exportovat projekt do XML (nebo jiných formátů) pomocí `Spreadsheet2003SaveOptions`.  
- **Potřebuji licenci?** Ano, pro produkční použití je vyžadována platná licence Aspose.Tasks.  
- **Které verze .NET fungují?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Kolik sloupců mohu přidat?** Neomezeně – stačí vytvořit další instance `AssignmentViewColumn`.

## Co jsou více vlastních sloupců?
Více vlastních sloupců jsou uživatelem definovaná pole, která se zobrazují vedle výchozích sloupců přiřazení, když je projekt uložen nebo exportován. Poskytují vám flexibilitu zobrazit libovolnou vlastnost objektu `ResourceAssignment`, například vlastní poznámky, kódy nákladů nebo vypočítané hodnoty.

## Proč přidávat více vlastních sloupců do zobrazení přiřazení?
- **Vylepšené reportování:** Zahrnout projektově specifické informace, které nejsou pokryty vestavěnými sloupci.  
- **Lepší rozhodování:** Zainteresované strany mohou vidět přesná data, která potřebují, aniž by musely procházet surové soubory.  
- **Konzistentní formátování:** Ovládat šířku sloupce a konverzi textu pro čistý, čitelný výstup.  

## Předpoklady

Než se pustíme dál, ujistěte se, že máte:

1. Základní znalost programovacího jazyka C#.  
2. Nainstalovanou knihovnu Aspose.Tasks pro .NET. Pokud ne, můžete ji stáhnout **[zde](https://releases.aspose.com/tasks/net/)**.  
3. Integrované vývojové prostředí (IDE) jako je Visual Studio.  

## Postupný návod

### Krok 1: Importovat jmenné prostory
Nejprve importujte jmenné prostory, které poskytují třídy potřebné pro práci s projekty a vizualizacemi.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

### Krok 2: Načíst projekt
Vytvořte instanci `Project` a načtěte existující soubor MPP.

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

### Krok 3: Vytvořit možnosti uložení Spreadsheet
Vytvořte instanci `Spreadsheet2003SaveOptions` – tento objekt nám umožňuje přizpůsobit zobrazení přiřazení před exportem.

```csharp
var options = new Spreadsheet2003SaveOptions();
```

### Krok 4: Definovat vlastní sloupec
Vytvořte `AssignmentViewColumn` pro každý kus dat, který chcete zobrazit. Níže přidáváme sloupec **Notes** s šířkou 200 bodů.

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

**Tip:** Pro přidání *více* vlastních sloupců opakujte tento krok s různými názvy polí a logikou delegáta, poté přidejte každou instanci do `options.AssignmentView.Columns`.

### Krok 5: Přidat vlastní sloupec do možností
Přidejte sloupec (nebo sloupce) do kolekce `Columns` v zobrazení přiřazení.

```csharp
options.AssignmentView.Columns.Add(column);
```

### Krok 6: Procházet přiřazení (volitelné ladění)
Můžete projít přiřazení, abyste ověřili, že text vlastního sloupce je generován správně.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var col in options.AssignmentView.Columns)
    {
        var assnCol = (AssignmentViewColumn)col;
        Console.WriteLine("Column Field: " + assnCol.Field);
        Console.WriteLine("Column Text (converted): " + assnCol.GetColumnText(assignment));
        Console.WriteLine();
    }
}
```

### Krok 7: Uložit projekt s vlastními sloupci
Nakonec projekt uložte. Příklad ukládá do XML, ale můžete zvolit libovolný podporovaný formát.

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## Jak exportovat projekt do XML s vlastními sloupci?
Když zavoláte `project.Save` s nakonfigurovanými `Spreadsheet2003SaveOptions`, Aspose.Tasks zapíše data projektu — včetně všech **více vlastních sloupců** — do vybraného XML souboru. To usnadňuje sdílení obohacených informací o projektu s dalšími systémy nebo zainteresovanými stranami.

## Formátování šířky vlastního sloupce pro lepší čitelnost
Druhý parametr konstruktoru `AssignmentViewColumn` řídí šířku sloupce (měřenou v bodech). Upravit tuto hodnotu podle množství očekávaného textu. Například šířka **300** funguje dobře pro delší poznámky, zatímco **100** stačí pro krátké příznaky.

## Časté problémy a řešení
- **Text sloupce je prázdný:** Ujistěte se, že delegát vrací řetězec a že podkladová vlastnost přiřazení (např. `Asn.NotesText`) je naplněna.  
- **Sloupce nejsou viditelné v exportovaném souboru:** Ověřte, že `options.AssignmentView.Columns` obsahuje vaše vlastní sloupce před voláním `Save`.  
- **Zdá se, že šířka je ignorována:** Některé exportní formáty mají vlastní pravidla rozvržení; XML šířku respektuje, ale PDF/HTML mohou vyžadovat další stylování.

## Často kladené otázky

### Q1: Mohu přidat více vlastních sloupců do zobrazení přiřazení?
**A:** Ano, stačí vytvořit další objekty `AssignmentViewColumn` a přidat každý do `options.AssignmentView.Columns`.

### Q2: Existují předdefinované konvertory pro běžná pole přiřazení?
**A:** Ano, Aspose.Tasks poskytuje vestavěné konvertory pro mnoho standardních polí, což usnadňuje získání dat bez psaní vlastních delegátů.

### Q3: Mohu přizpůsobit vzhled vlastních sloupců, například formátování textu nebo aplikaci stylů?
**A:** Rozhodně. Kromě nastavení šířky můžete měnit písmo, zarovnání a další vizuální vlastnosti pomocí možností stylování sloupce.

### Q4: Je možné odstranit výchozí sloupce ze zobrazení přiřazení?
**A:** Výchozí sloupce můžete vyloučit jejich odstraněním z kolekce `Columns` nebo nastavením jejich šířky na nulu.

### Q5: Podporuje Aspose.Tasks export projektů do jiných formátů kromě tabulek s vlastními sloupci?
**A:** Ano, Aspose.Tasks může exportovat do PDF, HTML, XML a mnoha dalších formátů při zachování definic vlastních sloupců.

---

**Poslední aktualizace:** 2026-03-19  
**Testováno s:** Aspose.Tasks 24.12 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}