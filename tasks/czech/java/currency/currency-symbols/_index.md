---
date: 2026-09-20
description: Naučte se, jak extrahovat měnový symbol mpp a aktualizovat vlastnosti
  projektu pomocí Aspose.Tasks pro Java. Změňte a načtěte symbol během několika řádků
  kódu.
keywords:
- extract currency symbol mpp
- read project properties java
- retrieve currency symbol java
lastmod: 2026-09-20
linktitle: Extrahujte měnový symbol mpp pomocí Aspose.Tasks pro Java
og_description: Naučte se, jak extrahovat měnový symbol mpp a aktualizovat vlastnosti
  projektu pomocí Aspose.Tasks pro Java. Rychlé, spolehlivé a připravené pro produkci.
og_image_alt: 'Guide: extract currency symbol mpp using Aspose.Tasks Java'
og_title: Jak extrahovat měnový symbol mpp pomocí Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-09-20'
  description: Learn how to extract currency symbol mpp and update project properties
    using Aspose.Tasks for Java. Change and retrieve the symbol in just a few lines
    of code.
  headline: How to extract currency symbol mpp with Aspose.Tasks Java
  type: TechArticle
- description: Learn how to extract currency symbol mpp and update project properties
    using Aspose.Tasks for Java. Change and retrieve the symbol in just a few lines
    of code.
  name: How to extract currency symbol mpp with Aspose.Tasks Java
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or higher.'
    text: '**Java Development Kit (JDK)** – version 8 or higher.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the [Aspose.Tasks
      download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the [Aspose.Tasks
      download page](https://releases.aspose.com/tasks/java/).'
  - name: A valid **project.mpp** file placed in a folder you can reference from your
      code.
    text: A valid **project.mpp** file placed in a folder you can reference from your
      code.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks lets you edit tasks, resources, assignments, calendars,
      and many more project properties.
    question: Can I manipulate other project attributes besides currency symbols using
      Aspose.Tasks?
  - answer: Absolutely. It supports MPP, MPT, and XML formats from Project 98 up to
      the latest releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API docs, code examples, and a dedicated support forum are
      available on the Aspose.Tasks website.
    question: Does Aspose.Tasks offer documentation and support for developers?
  - answer: Yes – a fully functional free trial can be downloaded from the [Aspose
      website](https://purchase.aspose.com/buy).
    question: Can I try Aspose.Tasks before purchasing it?
  - answer: Temporary licenses are provided on the [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)
      for evaluation purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- extract currency symbol
- Aspose.Tasks
- Java project properties
- MPP handling
title: Jak extrahovat měnový symbol mpp pomocí Aspose.Tasks Java
url: /cs/java/currency/currency-symbols/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Extrahování symbolu měny mpp pomocí Aspose.Tasks pro Java

## Úvod
V tomto tutoriálu se naučíte pracovat s **java project properties** – konkrétně jak **extract currency symbol mpp** z souboru Microsoft Project (MPP) a jak **change currency symbol java** nebo **retrieve currency symbol java** pomocí knihovny Aspose.Tasks. Ať už vytváříte nástroj pro finanční reportování, integrujete data z Projectu do ERP systému, nebo jen potřebujete zobrazit správný symbol měny ve vašem uživatelském rozhraní, zvládnutí tohoto malého, ale podstatného úkolu učiní vaše Java aplikace robustnější a uživatelsky přívětivější.

## Rychlé odpovědi
- **What does “extract currency symbol mpp” mean?** To znamená čtení symbolu měny uloženého v souboru MPP (Microsoft Project).  
- **Which library handles this?** Aspose.Tasks for Java poskytuje jednoduché API pro tento úkol.  
- **Do I need a license?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.  
- **How long does it take?** S kódem níže můžete získat symbol za méně než minutu.  
- **Can I also change the symbol?** Ano – můžete nastavit novou hodnotu pomocí stejné vlastnosti `Prj.CURRENCY_SYMBOL`.

## Co je “extract currency symbol mpp”?
Extrahování symbolu měny z MPP souboru znamená čtení jednoslovného řetězce, který Microsoft Project ukládá v hlavičce souboru pro reprezentaci měnové jednotky projektu. Tento úkon vám umožní zobrazit správný symbol (např. $, €, £) ve vašich aplikacích bez pevného zakódování hodnoty.

## Proč aktualizovat symbol měny v java project properties?
Aktualizace symbolu měny vám umožní lokalizovat zprávy, faktury a dashboardy za běhu. Podniky, které provozují projekty v několika regionech, mohou symbol změnit jedním krokem, čímž se vyhnou nutnosti duplikovat celý soubor projektu. Aspose.Tasks může vlastnost upravit v paměti a soubor znovu uložit, přičemž podporuje projekty až s 2 000 úkoly bez znatelného dopadu na výkon.

## Požadavky
Než se pustíme dál, ujistěte se, že máte:

1. **Java Development Kit (JDK)** – verze 8 nebo vyšší.  
2. **Aspose.Tasks for Java** – stáhněte nejnovější JAR ze [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/).  
3. Platný soubor **project.mpp** umístěný ve složce, na kterou můžete odkazovat z vašeho kódu.

## Import balíčků
Nejprve importujte třídy, které budeme potřebovat pro práci se soubory Project.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Krok 1: definujte adresář s daty
Sdělte aplikaci, kde se nachází váš soubor *.mpp*.

```java
String dataDir = "Your Data Directory";
```

> **Pro tip:** Použijte `System.getProperty("user.dir")` k vytvoření absolutní cesty, která funguje na jakémkoli počítači.

## Krok 2: načtěte soubor MS Project
`Project` je nejvyšší objekt Aspose.Tasks, který v paměti představuje jeden soubor Microsoft Project. Vytvořením tohoto objektu se načte struktura souboru, aniž by bylo nutné mít nainstalovaný Microsoft Project.

```java
Project project = new Project(dataDir + "project.mpp");
```

## Krok 3: načtěte (a případně změňte) symbol měny
`Prj.CURRENCY_SYMBOL` je klíč vlastnosti, který ukládá symbol měny. Při čtení vrací aktuální symbol; při přiřazení nového řetězce aktualizuje definici měny projektu.

```java
// Retrieve the current currency symbol
System.out.println(project.get(Prj.CURRENCY_SYMBOL));

// Example of changing it (uncomment to use)
// project.set(Prj.CURRENCY_SYMBOL, "€");
// System.out.println("New symbol: " + project.get(Prj.CURRENCY_SYMBOL));
```

Volání `System.out.println` vytiskne symbol (např. `$`) na konzoli, čímž potvrdí úspěšné extrahování.

## Časté problémy a jak je opravit
| Symptom | Likely cause | Solution |
|---------|--------------|----------|
| `NullPointerException` při `project.get(...)` | Špatná cesta k souboru nebo soubor nebyl nalezen | Ověřte `dataDir` a název souboru; použijte `new File(dataDir).exists()` pro ladění |
| Neočekávaný symbol (např. `?`) | Projekt vytvořený s nestandardním locale | Ujistěte se, že zdrojový MPP soubor skutečně definuje symbol měny; můžete jej nastavit programově, jak je uvedeno výše |
| Chyba licence | Používání zkušební verze bez platného licenčního souboru | Načtěte licenci pomocí `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` před vytvořením objektu `Project` |

## Často kladené otázky

**Q: Můžu pomocí Aspose.Tasks manipulovat s jinými atributy projektu kromě symbolů měny?**  
A: Ano, Aspose.Tasks vám umožní upravovat úkoly, zdroje, přiřazení, kalendáře a mnoho dalších vlastností projektu.

**Q: Je Aspose.Tasks kompatibilní s různými verzemi souborů MS Project?**  
A: Absolutně. Podporuje formáty MPP, MPT a XML od Project 98 až po nejnovější verze.

**Q: Nabízí Aspose.Tasks dokumentaci a podporu pro vývojáře?**  
A: Komplexní API dokumentace, příklady kódu a vyhrazené fórum podpory jsou k dispozici na webu Aspose.Tasks.

**Q: Můžu si Aspose.Tasks vyzkoušet před zakoupením?**  
A: Ano – plně funkční bezplatná zkušební verze je ke stažení z [Aspose website](https://purchase.aspose.com/buy).

**Q: Jak mohu získat dočasnou licenci pro Aspose.Tasks?**  
A: Dočasné licence jsou k dispozici na [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/) pro evaluační účely.

---

**Poslední aktualizace:** 2026-09-20  
**Testováno s:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Autor:** Aspose

## Související tutoriály

- [Vlastnosti projektu Java – Čtení metadat pomocí Aspose.Tasks](/tasks/java/project-properties/)
- [Jak získat měnu z MS Project pomocí Aspose.Tasks](/tasks/java/currency/currency-codes/)
- [Nastavení data zahájení projektu v MS Project pomocí Aspose.Tasks pro Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}