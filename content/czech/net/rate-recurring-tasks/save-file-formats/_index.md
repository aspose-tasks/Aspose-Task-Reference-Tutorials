---
title: Ukládání souborů MS Project v různých formátech v Aspose.Tasks
linktitle: Ukládání souborů v různých formátech v Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Naučte se ukládat soubory MS Project v různých formátech pomocí Aspose.Tasks for .NET. Snadné kroky pro efektivní řízení projektů.
type: docs
weight: 17
url: /cs/net/rate-recurring-tasks/save-file-formats/
---
## Úvod
V tomto tutoriálu prozkoumáme, jak uložit soubory Microsoft Project v různých formátech pomocí Aspose.Tasks for .NET. Aspose.Tasks je výkonné API, které umožňuje vývojářům manipulovat a spravovat soubory projektů programově.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
1.  Aspose.Tasks for .NET: Stáhněte si a nainstalujte Aspose.Tasks for .NET z[tady](https://releases.aspose.com/tasks/net/).
2. Vývojové prostředí: Nastavte vývojové prostředí .NET, jako je Visual Studio.
3. Základní porozumění C#: Výhodou bude znalost programovacího jazyka C#.

## Importovat jmenné prostory
Ujistěte se, že jste na začátku svého souboru C# importovali potřebné jmenné prostory:
```csharp

using Aspose.Tasks.Saving;
```
## Krok 1: Vytvořte objekt projektu
Nejprve vytvořte objekt projektu a načtěte soubor aplikace Microsoft Project.
```csharp
// Cesta k adresáři dokumentů.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
```
## Krok 2: Uložte projekt ve formátu CSV
Nyní uložíme projekt ve formátu CSV. 
```csharp
project.Save(DataDir + "SaveProjectAsCSV_out.csv", SaveFileFormat.Csv);
```
## Krok 3: Prozkoumejte další formáty
 Aspose.Tasks podporuje různé formáty pro ukládání souborů projektu, jako jsou XML, PDF, XLSX a další. Tyto formáty můžete prozkoumat jednoduše změnou`SaveFileFormat` parametry v`Save` metoda.
```csharp
project.Save(DataDir + "SaveProjectAsXML_out.xml", SaveFileFormat.XML);
project.Save(DataDir + "SaveProjectAsPDF_out.pdf", SaveFileFormat.PDF);
project.Save(DataDir + "SaveProjectAsXLSX_out.xlsx", SaveFileFormat.XLSX);
```
Pomocí následujících kroků můžete snadno ukládat soubory Microsoft Project v různých formátech pomocí Aspose.Tasks for .NET.

## Závěr
V tomto tutoriálu jsme se naučili ukládat soubory MS Project v různých formátech pomocí Aspose.Tasks for .NET. Aspose.Tasks zjednodušuje proces programové manipulace se soubory projektu a nabízí vývojářům flexibilitu a efektivitu.
## FAQ
### Otázka: Je Aspose.Tasks kompatibilní se všemi verzemi Microsoft Project?
Odpověď: Aspose.Tasks podporuje formáty Microsoft Project 2003 XML, Microsoft Project 2007 MPP a Microsoft Project 2010 MPP.
### Otázka: Mohu vyzkoušet Aspose.Tasks před nákupem?
 Odpověď: Ano, můžete si stáhnout bezplatnou zkušební verzi z[tady](https://releases.aspose.com/).
### Otázka: Jak mohu získat podporu pro Aspose.Tasks?
 Odpověď: Podporu můžete získat na fóru komunity Aspose.Tasks.[tady](https://forum.aspose.com/c/tasks/15).
### Otázka: Jsou pro Aspose.Tasks dostupné dočasné licence?
 Odpověď: Ano, dočasné licence jsou k dispozici pro účely hodnocení. Můžete získat jeden[tady](https://purchase.aspose.com/temporary-license/).
### Otázka: Jaká je cena za Aspose.Tasks?
 Odpověď: Informace o cenách lze nalézt na nákupní stránce Aspose.Tasks[tady](https://purchase.aspose.com/buy).