---
date: 2026-03-14
description: Naučte se, jak extrahovat vložené soubory a načíst projektový soubor
  pomocí Aspose.Tasks pro .NET. Tento tutoriál ukazuje krok za krokem extrakci OLE
  objektů.
linktitle: Collection of OLE Objects in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Extrahovat vložené soubory z OLE objektů v Aspose.Tasks
url: /cs/net/advanced-concepts/ole-object-collection/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extrahovat vložené soubory z OLE objektů v Aspose.Tasks

## Úvod

V tomto tutoriálu **extrahujete vložené soubory**, které jsou uloženy jako OLE objekty uvnitř souboru Microsoft Project pomocí Aspose.Tasks pro .NET. Ať už potřebujete získat propojené dokumenty Word, tabulky Excel nebo soubory rich‑text, níže uvedené kroky vám ukážou, jak **načíst projektový soubor**, objevit každý OLE záznam a zapsat binární obsah zpět na disk. Na konci budete mít kompletní **c# extract ole** workflow, které můžete znovu použít ve svých aplikacích.

## Rychlé odpovědi
- **Co znamená „extrahovat vložené soubory“?** Znamená to přečíst binární payload OLE objektů a uložit je jako samostatné soubory na disku.  
- **Která metoda API načítá projekt?** `new Project(filePath)` z namespace Aspose.Tasks.  
- **Mohu exportovat OLE objekty libovolného typu?** Podporovány jsou jen formáty, které Aspose.Tasks rozpozná (např. RTF, Word, Excel).  
- **Potřebuji k tomu licenci?** Pro hodnocení stačí bezplatná zkušební verze; pro produkční nasazení je vyžadována komerční licence.  
- **Jaké verze .NET jsou podporovány?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Co znamená „extrahovat vložené soubory“ v kontextu OLE objektů?

OLE (Object Linking and Embedding) umožňuje, aby projektový soubor obsahoval kompletní kopie externích dokumentů. Extrahování těchto vložených souborů vám poskytne přímý přístup k původnímu obsahu, aniž byste museli otevírat projekt v Microsoft Project.

## Proč extrahovat vložené soubory z OLE objektů?

- **Zachovat originální data:** Udržujte zálohu každého připojeného dokumentu.  
- **Automatizovat reportování:** Stáhněte Word nebo Excel reporty z mnoha projektů najednou.  
- **Integrovat s jinými systémy:** Vkládejte extrahované soubory do systémů pro správu dokumentů nebo analytických pipelinek.

## Předpoklady

Než začnete, ujistěte se, že máte:

1. **Visual Studio** – libovolná aktuální verze (2019, 2022 nebo novější).  
2. **Aspose.Tasks pro .NET** – stáhněte a nainstalujte z [here](https://releases.aspose.com/tasks/net/).  
3. **Základní znalosti C#** – měli byste být obeznámeni s cykly, kolekcemi a souborovým I/O.  

## Import Namespaces

Pro začátek importujte potřebné jmenné prostory do svého projektu:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;
```

## Krok 1: Načíst projektový soubor

Nejprve načtěte projektový soubor, který obsahuje OLE objekty, jež chcete extrahovat:

```csharp
var project = new Project(DataDir + "Embedded.mpp");
```

> **Tip:** `DataDir` by měl ukazovat na složku, kde se nachází váš soubor `.mpp`. Tento krok splňuje požadavek **load project file**.

## Krok 2: Definovat přípony souborů

Vytvořte vyhledávací tabulku, která mapuje identifikátory OLE `FileFormat` na požadovaná výstupní jména souborů. To usnadní **export ole objects** s správnými příponami:

```csharp
IDictionary<string, string> extensions = new Dictionary<string, string>
{
    { "RTF", "_rtfFile_out.rtf" },
    { "MSWordDoc", "_wordFile_out.docx" },
    { "ExcelML12", "_excelFile_out.xlsx" }
};
```

## Krok 3: Procházet OLE objekty a extrahovat vložené soubory

Nyní projděte každý OLE objekt v projektu, ověřte, že jeho formát je podporovaný, a zapište binární obsah do nového souboru:

```csharp
foreach (var oleObject in project.OleObjects)
{
    if (string.IsNullOrEmpty(oleObject.FileFormat) || !extensions.ContainsKey(oleObject.FileFormat))
    {
        continue;
    }

    var path = OutDir + "EmbeddedContent_" + extensions[oleObject.FileFormat];
    using (var stream = new FileStream(path, FileMode.Create))
    {
        stream.Write(oleObject.Content, 0, oleObject.Content.Length);
    }
}
```

> **Tip:** `OutDir` by měl být zapisovatelný adresář. Výše uvedený kód vytvoří soubory jako `EmbeddedContent__wordFile_out.docx`, čímž **extract ole objects** z projektu.

## Časté problémy a řešení

| Problém | Důvod | Řešení |
|-------|--------|----------|
| Nejsou vytvořeny žádné soubory | `OutDir` neexistuje nebo nemá právo zápisu | Zajistěte, aby adresář existoval a aplikace měla právo zápisu. |
| Neočekávaný formát souboru | `FileFormat` OLE objektu není ve slovníku | Přidejte chybějící formát do slovníku `extensions`. |
| Velké OLE objekty zatěžují paměť | Načítání mnoha velkých objektů najednou | Zpracovávejte objekty po jednom, jak je ukázáno, nebo je přímo streamujte na disk. |

## Často kladené otázky

**Q: Co je OLE objekt?**  
A: OLE (Object Linking and Embedding) je technologie, která umožňuje vkládat nebo propojit soubory z jiných aplikací uvnitř dokumentu.

**Q: Jak nainstaluji Aspose.Tasks pro .NET?**  
A: Aspose.Tasks pro .NET si můžete stáhnout z [here](https://releases.aspose.com/tasks/net/) a postupovat podle poskytnutých instalačních instrukcí.

**Q: Můžu pracovat s OLE objekty v Aspose.Tasks bez předchozí znalosti C#?**  
A: Základní znalost C# se doporučuje, ale Aspose.Tasks poskytuje rozsáhlou dokumentaci a tutoriály, které pomohou i uživatelům bez programátorského zázemí.

**Q: Je k dispozici bezplatná zkušební verze Aspose.Tasks?**  
A: Ano, bezplatnou zkušební verzi Aspose.Tasks získáte z [here](https://releases.aspose.com/).

**Q: Kde mohu najít podporu pro Aspose.Tasks?**  
A: Podporu a otázky můžete směřovat na fórum Aspose.Tasks [here](https://forum.aspose.com/c/tasks/15).

---

**Poslední aktualizace:** 2026-03-14  
**Testováno s:** Aspose.Tasks 24.11 pro .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}