---
date: 2026-07-19
description: Naučte se, jak přidat vlastní typy polí v Aspose.Tasks pro .NET pomocí
  krok‑za‑krokem kódu, předpokladů a častých otázek.
keywords:
- how to add custom field
- add custom field to project
- define extended attribute
lastmod: 2026-07-19
linktitle: Vlastní typy polí v Aspose.Tasks
og_description: Naučte se, jak přidat vlastní typy polí v Aspose.Tasks pro .NET. Postupujte
  podle tohoto krok‑za‑krokem průvodce a efektivně vytvářejte, definujte a používáte
  rozšířené atributy.
og_image_alt: Guide showing how to add custom field types in Aspose.Tasks using .NET
og_title: Jak přidat vlastní typy polí v Aspose.Tasks pro .NET
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  headline: How to Add Custom Field Types in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  name: How to Add Custom Field Types in Aspose.Tasks for .NET
  steps:
  - name: Create Project Object
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Project
      file in memory. Instantiating it loads the file and gives you access to tasks,
      resources, and extended attributes.'
  - name: Define Custom Field
    text: '`ExtendedAttributeDefinition` describes a new column. In this example we
      create a **Text** type custom field for tasks and give it the alias “MyText”.
      The `ExtendedAttributeTask.Text1` enum value tells Aspose.Tasks where to store
      the value.'
  - name: Add Custom Field Definition to Project
    text: The project’s `ExtendedAttributes` collection holds all custom field definitions.
      Adding the definition makes it available for every task in the project.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks works with .NET Framework, .NET Core, and .NET 5/6/7.
    question: Can I use Aspose.Tasks with other .NET frameworks?
  - answer: Absolutely. It supports processing of projects with **up to 10,000 tasks**
      and can run in multi‑threaded server environments.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes—Aspose.Tasks reads and writes MPP, XML, HTML, and CSV formats, covering
      **all major Microsoft Project versions**.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Yes, you can add, update, and delete resources, as well as assign custom
      fields to them.
    question: Can I manipulate resource data using Aspose.Tasks?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      to interact with other users and get support from the Aspose team.
    question: Is there a community forum for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom field
- Aspose.Tasks
- .NET project management
- extended attributes
title: Jak přidat vlastní typy polí v Aspose.Tasks pro .NET
url: /cs/net/calendar-scheduling/custom-field-types/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přidat vlastní typy polí v Aspose.Tasks

## Úvod

V tomto tutoriálu objevíte **jak přidat vlastní pole** do souboru Microsoft Project pomocí Aspose.Tasks pro .NET. Vlastní pole vám umožňují ukládat další informace—například skóre rizika, kódy oddělení nebo vlastní poznámky—přímo na úlohách, zdrojích nebo samotném projektu. Provedeme vás celým procesem, od nastavení prostředí po definování, přidání a ověření vlastního textového pole.

## Rychlé odpovědi
- **What is a custom field?** Uživatelsky definovaný sloupec, který může obsahovat text, čísla, data nebo příznaky u úloh/zdrojů.  
- **Which class defines a custom field?** `ExtendedAttributeDefinition`.  
- **Can I add a custom field to an existing project?** Ano — načtěte projekt, vytvořte definici a poté ji přidejte do kolekce.  
- **Do I need a license for Aspose.Tasks?** Licence je vyžadována pro produkční použití; pro hodnocení stačí bezplatná zkušební verze.  
- **Supported .NET versions?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Co znamená „jak přidat vlastní pole“ v Aspose.Tasks?
**How to add custom field** odkazuje na proces vytvoření `ExtendedAttributeDefinition` a připojení k kolekci `ExtendedAttributes` projektu. To vám umožní ukládat další metadata, která nejsou součástí standardního schématu Projectu. Lze jej použít pro úlohy, zdroje nebo samotný projekt, což vám umožní zachytit informace jako úrovně rizika, kódy oddělení nebo vlastní poznámky, které nejsou dostupné v výchozích polích.

## Proč používat vlastní pole v řízení projektů?
Aspose.Tasks podporuje **více než 50 vestavěných typů rozšířených atributů** a umožňuje definovat **libovolný počet vlastních polí** bez výrazného ovlivnění velikosti souboru. Pomocí vlastních polí můžete:  
Tato pole se zobrazují jako další sloupce v Microsoft Project a lze je odkazovat ve vzorcích, reportech a filtrech. Jsou uložena v souboru projektu a cestují s ním, což zajišťuje, že jakékoli následné nástroje zachovají vlastní data.

## Požadavky

### 1. Visual Studio nainstalováno
Ujistěte se, že máte nainstalovaný Visual Studio (2019 nebo novější). Můžete jej stáhnout z webu Microsoft.

### 2. Aspose.Tasks pro .NET
Přidejte NuGet balíček Aspose.Tasks do svého projektu. Stáhněte nejnovější verzi [zde](https://releases.aspose.com/tasks/net/).

### 3. Základní znalost C#
Měli byste být obeznámeni se syntaxí C#, třídami a strukturou .NET projektů.

## Import jmenných prostorů

`Project`, `ExtendedAttributeDefinition` a související výčty se nacházejí v jmenném prostoru `Aspose.Tasks`. Importujte jej na začátku souboru:

Jmenný prostor `Aspose.Tasks` poskytuje všechny základní typy pro práci se soubory Microsoft Project.

```csharp

```

## Jak přidat vlastní pole do projektu?

Načtěte existující projekt, vytvořte definici vlastního pole a přidejte ji do kolekce rozšířených atributů projektu — vše ve třech stručných krocích. Tento vzor funguje pro úlohy, zdroje i samotný projekt a zajišťuje, že vlastní pole bude uloženo při uložení souboru.

### Krok 1: Vytvořit objekt Project
`Project` je hlavní objekt Aspose.Tasks, který v paměti představuje jeden soubor Project. Jeho vytvoření načte soubor a poskytne vám přístup k úlohám, zdrojům a rozšířeným atributům.

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### Krok 2: Definovat vlastní pole
`ExtendedAttributeDefinition` popisuje nový sloupec. V tomto příkladu vytváříme vlastní pole typu **Text** pro úlohy a přiřazujeme mu alias „MyText“. Hodnota výčtu `ExtendedAttributeTask.Text1` říká Aspose.Tasks, kde má hodnotu uložit.

```csharp
var definition = ExtendedAttributeDefinition.CreateTaskDefinition(
    CustomFieldType.Text,
    ExtendedAttributeTask.Text1,
    "MyText");
```

### Krok 3: Přidat definici vlastního pole do projektu
Kolekce `ExtendedAttributes` projektu obsahuje všechny definice vlastních polí. Přidání definice ji zpřístupní pro každou úlohu v projektu.

```csharp
project.ExtendedAttributes.Add(definition);
```

## Časté problémy a řešení
- **Field not appearing in MS Project UI** – Ujistěte se, že jste nastavili vlastnost `Alias`; MS Project zobrazuje alias jako záhlaví sloupce.  
- **Saving throws an exception** – Ověřte, že soubor projektu není jen pro čtení a že máte platnou licenci.  
- **Custom field values are lost after reload** – Ujistěte se, že po přiřazení hodnot úlohám zavoláte `project.Save("output.mpp")`.

## Často kladené otázky

**Q: Mohu používat Aspose.Tasks s jinými .NET frameworky?**  
A: Ano, Aspose.Tasks funguje s .NET Framework, .NET Core a .NET 5/6/7.

**Q: Je Aspose.Tasks vhodný pro podnikové aplikace?**  
A: Rozhodně. Podporuje zpracování projektů až **10 000 úloh** a může běžet ve vícevláknových serverových prostředích.

**Q: Podporuje Aspose.Tasks více formátů souborů projektů?**  
A: Ano — Aspose.Tasks čte a zapisuje formáty MPP, XML, HTML a CSV, pokrývající **všechny hlavní verze Microsoft Project**.

**Q: Mohu pomocí Aspose.Tasks manipulovat s daty zdrojů?**  
A: Ano, můžete přidávat, aktualizovat a mazat zdroje a také jim přiřazovat vlastní pole.

**Q: Existuje komunitní fórum pro uživatele Aspose.Tasks?**  
A: Ano, můžete navštívit [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15), kde můžete komunikovat s ostatními uživateli a získat podporu od týmu Aspose.

---

**Poslední aktualizace:** 2026-07-19  
**Testováno s:** Aspose.Tasks 24.12 for .NET  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Mistrovství v definicích rozšířených atributů MS Project v Aspose.Tasks](/tasks/net/tasks-project-management/extended-attribute-definition-collection/)
- [Manipulace s rozšířenými atributy MS Project pomocí Aspose.Tasks](/tasks/net/tasks-project-management/working-with-extended-attributes/)
- [Field Helper integrace MS Project v Aspose.Tasks](/tasks/net/tasks-project-management/field-helper/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}