---
date: 2026-07-05
description: Naučte se, jak pomocí Aspose.Tasks pro .NET kopírovat data projektu s
  možnostmi kopírování. Zvyšte výkon svých .NET aplikací díky přesnému řízení projektů.
keywords:
- how to copy project
- aspnet project copy
- aspose tasks copy options
linktitle: Jak kopírovat data projektu s možnostmi kopírování v Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  headline: How to Copy Project Data with Copy Options in Aspose.Tasks
  type: TechArticle
- description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  name: How to Copy Project Data with Copy Options in Aspose.Tasks
  steps:
  - name: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
    text: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
  - name: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
    text: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
  - name: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
    text: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
  - name: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
    text: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
  type: HowTo
- questions:
  - answer: Yes, use `CopyToOptions` together with `ProjectRootTask` to specify a
      starting task, or manually copy selected tasks after the initial copy.
    question: Can I copy only a subset of tasks?
  - answer: Absolutely. You can load an MPP file and save the copy as XML, XER, or
      any other supported format—over **20 + formats** in total.
    question: Does Aspose.Tasks support copying between different file formats?
  - answer: Load the source with `new Project("file.mpp", new LoadOptions { Password
      = "pwd" })`, then proceed with the copy as usual.
    question: How do I handle password‑protected project files?
  - answer: Set `CopyToOptions.CopyResources = true` and `CopyToOptions.CopyTasks
      = false` to transfer only resource information.
    question: Is there a way to copy resource pools without tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community‑driven snippets, troubleshooting tips, and official documentation.
    question: Where can I find more examples?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Jak kopírovat data projektu s možnostmi kopírování v Aspose.Tasks
url: /cs/net/calendar-scheduling/copy-options/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak zkopírovat data projektu s možnostmi kopírování v Aspose.Tasks

## Úvod

Pokud potřebujete **jak zkopírovat projekt** informace z jednoho souboru Microsoft Project do druhého, Aspose.Tasks pro .NET vám poskytuje čistý, kód‑první způsob, jak to provést. V tomto tutoriálu projdeme kompletním pracovním postupem – načtením zdrojového projektu, nastavením možností kopírování, vytvořením kopie a načtením výsledku – takže můžete logiku kopírování projektů integrovat do jakékoli .NET aplikace s jistotou.

## Rychlé odpovědi
- **Co dělá funkce kopírování?** Duplikuje data projektu a umožňuje zahrnout nebo vyloučit konkrétní sekce, jako jsou kalendáře, zdroje nebo informace o zobrazení.  
- **Která třída řídí chování?** `CopyToOptions` vám umožňuje jemně nastavit, co se kopíruje.  
- **Potřebuji licenci?** Platná licence Aspose.Tasks je vyžadována pro produkci; pro vývoj stačí bezplatná zkušební verze.  
- **Podporované formáty?** Aspose.Tasks pracuje se soubory MPP, XML a XER – celkem více než 20 formátů.  
- **Mohu vynechat data zobrazení?** Ano, nastavte `CopyToOptions.SkipViewData = true` pro vynechání informací souvisejících s UI.

## Co je „jak zkopírovat projekt“ v Aspose.Tasks?

**„Jak zkopírovat projekt“** odkazuje na použití API Aspose.Tasks k duplikaci dat objektu Project do nového souboru, s možností filtrovat nežádoucí prvky. Tento operace je užitečná pro tvorbu šablon, archivaci nebo vytváření variant projektu bez ručních kroků UI a funguje napříč všemi podporovanými formáty souborů.

## Proč používat možnosti kopírování v Aspose.Tasks?

Aspose.Tasks podporuje **více než 50 entit souvisejících s projektem** (úkoly, zdroje, kalendáře, přiřazení atd.) a dokáže zpracovat soubory s **až 10 000 úkoly**, přičemž spotřeba paměti zůstává pod 200 MB. Použití `CopyToOptions` vám umožní vyhnout se kopírování těžkopádných dat zobrazení, což snižuje velikost výstupního souboru o **30‑40 %** a urychluje operaci přibližně **2×** u velkých projektů.

## Požadavky

1. **Aspose.Tasks pro .NET** – stáhněte nejnovější verzi z [download link](https://releases.aspose.com/tasks/net/).  
2. **Vývojové prostředí .NET** – nainstalovaný Visual Studio 2022 (nebo jakékoli IDE podporující .NET 6+).  
3. **Platná licence Aspose.Tasks** – volitelná pro hodnocení, povinná pro produkční sestavení.  
4. **Existující soubor projektu** (např. `SourceProject.xml`), který chcete zkopírovat.

## Jak importovat jmenné prostory pro Aspose.Tasks?

Přidejte požadované `using` direktivy na začátek vašeho C# souboru, aby kompilátor mohl najít typy Aspose.Tasks. Zahrnutím těchto příkazů získáte přímý přístup k `Project`, `CopyToOptions` a dalším pomocným třídám bez nutnosti plně kvalifikovat jejich názvy, což zjednodušuje kód a zlepšuje čitelnost.

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
```

## Krok 1: Inicializace objektů projektu

Nejprve vytvořte instanci `Project`, která představuje zdrojový soubor, a načtěte XML data.  
Třída `Project` představuje soubor Microsoft Project načtený do paměti, který poskytuje úkoly, zdroje, kalendáře a další informace o projektu.

```csharp
Project sourceProject = new Project("SourceProject.xml");
```

> **Tip:** Pokud pracujete s velmi velkými soubory, zvažte použití konstruktoru `LoadOptions` pro povolení lazy loadingu a udržení nízké spotřeby paměti.

## Krok 2: Vytvoření kopie projektu

Dále vytvořte druhý objekt `Project`, který přijme zkopírovaná data. Tento objekt začíná prázdný.

```csharp
Project copiedProject = new Project();
```

Nyní máte dva odlišné objekty `Project`: jeden načtený z disku a druhý připravený přijmout kopii.

## Krok 3: Načtení zkopírovaného projektu

Po operaci kopírování (ukázané později) budete chtít ověřit výsledek načtením nově uloženého souboru do další instance `Project`.

```csharp
Project verificationProject = new Project("CopiedProject.xml");
```

Načtení souboru zpět potvrzuje, že kopírování bylo úspěšné a že nastavené možnosti fungovaly podle očekávání.

## Krok 4: Nastavení možností kopírování

Třída `CopyToOptions` vám umožňuje přesně určit, co se přenáší ze zdroje do cíle.

```csharp
CopyToOptions options = new CopyToOptions
{
    // Skip copying view information (Gantt charts, tables, etc.)
    SkipViewData = true,
    
    // Include only common project data (tasks, resources, assignments)
    CopyCommonData = true
};
```

Nastavení `SkipViewData = true` snižuje velikost výstupního souboru a urychluje operaci, zejména když potřebujete jen logická data projektu.

## Krok 5: Provedení kopírování projektu

Nakonec zavolejte metodu `CopyTo` na zdrojovém projektu, předáte cílový projekt a nastavené možnosti.

```csharp
sourceProject.CopyTo(copiedProject, options);
copiedProject.Save("CopiedProject.xml", SaveFileFormat.Xml);
```

Tento dvouřádkový volání provede celou operaci kopírování, respektuje definované možnosti. Výsledný `CopiedProject.xml` obsahuje pouze data, která jste požadovali.

## Časté problémy a řešení

| Problém | Příčina | Řešení |
|---------|---------|--------|
| **NullReferenceException při volání `CopyTo`** | Cílový projekt nebyl vytvořen. | Ujistěte se, že je před `CopyTo` volán `new Project()`. |
| **Chybějící úkoly po kopírování** | `CopyCommonData` nastaveno na `false`. | Nastavte `CopyCommonData = true` nebo ručně zkopírujte konkrétní kolekce. |
| **Velký výstupní soubor** | `SkipViewData` ponecháno jako `false`. | Povolte `SkipViewData` pro vynechání dat souvisejících s UI. |
| **Licence nebyla použita** | Soubor licence nebyl načten. | Zavolejte `License license = new License(); license.SetLicense("Aspose.Tasks.lic");` před jakýmkoli použitím API. |

## Často kladené otázky

**Q: Mohu zkopírovat jen podmnožinu úkolů?**  
A: Ano, použijte `CopyToOptions` spolu s `ProjectRootTask` pro určení počátečního úkolu, nebo ručně zkopírujte vybrané úkoly po počáteční kopii.

**Q: Podporuje Aspose.Tasks kopírování mezi různými formáty souborů?**  
A: Rozhodně. Můžete načíst soubor MPP a uložit kopii jako XML, XER nebo jakýkoli jiný podporovaný formát – celkem více než **20 + formátů**.

**Q: Jak zacházet se soubory projektu chráněnými heslem?**  
A: Načtěte zdroj pomocí `new Project("file.mpp", new LoadOptions { Password = "pwd" })` a poté pokračujte v kopírování jako obvykle.

**Q: Existuje způsob, jak zkopírovat zdrojové pooly bez úkolů?**  
A: Nastavte `CopyToOptions.CopyResources = true` a `CopyToOptions.CopyTasks = false` pro přenos pouze informací o zdrojích.

**Q: Kde najdu více příkladů?**  
A: Navštivte [Aspose.Tasks fórum](https://forum.aspose.com/c/tasks/15) pro komunitou vytvořené ukázky, tipy na řešení problémů a oficiální dokumentaci.

---

**Poslední aktualizace:** 2026-07-05  
**Testováno s:** Aspose.Tasks 24.12 pro .NET  
**Autor:** Aspose  

```csharp
using Aspose.Tasks;
using System.IO;


```
```csharp
var project = new Project(DataDir + "CopyToProjectEmpty.xml");
```
```csharp
File.Copy(DataDir + "CopyToProjectEmpty.mpp", OutDir + "ProjectCopying_out.mpp", true);
```
```csharp
var mppProject = new Project(OutDir + "ProjectCopying_out.mpp");
```
```csharp
var copyToOptions = new CopyToOptions();
copyToOptions.CopyViewData = false;
```
```csharp
project.CopyTo(mppProject, copyToOptions);
```

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Ovládání dat projektu s Aspose.Tasks](/tasks/net/project-management-integration/project-data/)
- [Ovládání možností ukládání MS Project pro Aspose.Tasks](/tasks/net/saving-options/general-save-options/)
- [Kalendář a plánování v Aspose.Tasks](/tasks/net/calendar-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}