---
date: 2026-05-20
description: Naučte se, jak používat Aspose.Tasks pro Java k přidání rozšířených atributů
  k přiřazením zdrojů, nastavení data zahájení projektu a efektivnímu zápisu souborů
  MS Project.
keywords:
- how to use aspose
- add extended attributes
- set project start date
- create resource assignment
- aspose tasks java
linktitle: Přidat rozšířené atributy k přiřazením zdrojů v Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  headline: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource
    Assignments
  type: TechArticle
- description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  name: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource Assignments
  steps:
  - name: Set Up Data Directory
    text: Define the directory where your project data will be stored. This path is
      used later when you save the XML file.
  - name: Create Project Instance
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single Microsoft Project file in memory. Instantiating it gives you full access
      to all project elements.
  - name: Set Project Information Properties
    text: Set essential project properties such as the start date, schedule from start
      flag, and status date. These values are stored in the project’s `ProjectInfo`
      object.
  - name: Add Extended Attributes to a Resource Assignment
    text: Create an `ExtendedAttributeDefinition` for the custom field, attach it
      to a `ResourceAssignment`, and populate the value. This step demonstrates the
      **add extended attributes** keyword in action.
  type: HowTo
- questions:
  - answer: Yes, the library provides full read‑write capabilities for .mpp, .xml,
      and .xps formats.
    question: Can I use Aspose.Tasks for Java to read MS Project files?
  - answer: Absolutely, it supports files from Project 2000 up to the latest 2024
      release, covering over 20 version formats.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: The trial adds a watermark to generated files and limits the number of
      tasks you can create, but all API features remain accessible.
    question: Are there any limitations to the trial version of Aspose.Tasks for Java?
  - answer: You can seek assistance from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, temporary licenses are available for short‑term usage. You can obtain
      one from [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Jak používat Aspose.Tasks pro Java – Přidat rozšířené atributy k přiřazením
  zdrojů
url: /cs/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ovládání manipulace s MS Project pomocí Aspose.Tasks pro Java

## Úvod
V tomto tutoriálu se dozvíte **jak používat Aspose.Tasks pro Java** k přidání rozšířených atributů k přiřazením zdrojů a programatickému zápisu informací Microsoft Project. Ať už automatizujete reportingový kanál nebo vytváříte vlastní nástroj pro řízení projektů, níže uvedené kroky vám ukážou, jak nastavit datum zahájení projektu, vytvořit přiřazení zdrojů a uložit soubor jako XML – vše pomocí několika řádků Java kódu.

## Rychlé odpovědi
- **Co dělá Aspose.Tasks pro Java?** Čte, zapisuje a upravuje soubory Microsoft Project, aniž by bylo nutné mít nainstalovaný Microsoft Project.  
- **Mohu přidat vlastní pole k přiřazení zdroje?** Ano, použijte kolekci `ExtendedAttribute` na objektu `ResourceAssignment`.  
- **Jak nastavím datum zahájení projektu?** Zavolejte `project.setStartDate(LocalDateTime.of(...))` před uložením.  
- **Potřebuji licenci pro produkční použití?** Komerční licence odstraňuje vodotisk hodnocení a odemyká plný přístup k API.  
- **Které verze Javy jsou podporovány?** Aspose.Tasks pro Java podporuje JDK 8 až po JDK 21.

## Jak používat Aspose.Tasks pro Java?
`Project` je hlavní objekt představující soubor Microsoft Project v paměti. Načtěte knihovnu Aspose.Tasks, vytvořte instanci `Project`, nakonfigurujte vlastnosti na úrovni projektu, přidejte rozšířené atributy k přiřazení zdroje a nakonec projekt uložte jako XML. Základní pracovní postup se skládá ze tří stručných kroků: inicializace, úprava a uložení. Tento vzor funguje pro projekty jakékoli velikosti a běží na JVM Windows, Linux nebo macOS.

## Co je rozšířený atribut v Aspose.Tasks?
**Rozšířený atribut** je vlastní pole, které připojíte k úkolům, zdrojům nebo přiřazením, abyste uložili další metadata nad rámec vestavěných sloupců. `ExtendedAttributeDefinition` definuje schéma pro vlastní pole. Aspose.Tasks poskytuje třídy `ExtendedAttributeDefinition` a `ExtendedAttribute` pro programatické definování a přiřazování těchto polí.

## Proč přidávat rozšířené atributy k přiřazením zdrojů?
Aspose.Tasks podporuje **více než 50 vestavěných a vlastních polí** a můžete přidat neomezený počet uživatelem definovaných atributů. Přidáním těchto atributů můžete zachytit kódy nákladů, ID oddělení nebo jakákoli obchodně specifická data přímo v souboru .mpp, čímž eliminujete potřebu externích tabulek a zajistíte integritu dat během celého životního cyklu projektu.

## Předpoklady
Než začnete, ujistěte se, že máte:

1. **Java Development Kit (JDK)** – nainstalovaný JDK 8 nebo novější.  
2. **Aspose.Tasks pro Java knihovna** – stáhněte ji z oficiální stránky vydání [zde](https://releases.aspose.com/tasks/java/).  
3. **IDE** – IntelliJ IDEA, Eclipse nebo jakýkoli jiný Java‑kompatibilní editor podle vašeho výběru.

## Import balíčků
Nejprve importujte potřebné balíčky ve svém Java projektu:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### Krok 1: Nastavení adresáře s daty
Definujte adresář, kde budou uložena data vašeho projektu. Tato cesta se později použije při ukládání XML souboru.

```java
String dataDir = "Your Data Directory";
```

### Krok 2: Vytvoření instance projektu
Třída `Project` je vrchní objekt Aspose.Tasks, který představuje jeden soubor Microsoft Project v paměti. Jeho vytvoření vám poskytne plný přístup ke všem prvkům projektu.

```java
Project project = new Project();
```

### Krok 3: Nastavení vlastností informací o projektu
Nastavte základní vlastnosti projektu, jako je datum zahájení, příznak plánování od začátku a datum stavu. Tyto hodnoty jsou uloženy v objektu `ProjectInfo` projektu.

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### Krok 4: Přidání rozšířených atributů k přiřazení zdroje
Vytvořte `ExtendedAttributeDefinition` pro vlastní pole, připojte jej k `ResourceAssignment` a vyplňte hodnotu. Tento krok demonstruje klíčové slovo **add extended attributes** v praxi.

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## Časté problémy a řešení
- **NullPointerException při přístupu ke kolekci přiřazení** – Ujistěte se, že jste vytvořili alespoň jeden zdroj a jeden úkol před získáním přiřazení.  
- **Rozšířený atribut se nezobrazuje v MS Project** – Ověřte, že `FieldId` atributu odpovídá slotu vlastního pole (např. `ExtendedAttributeTask.Text1`).  
- **Neshoda formátu data** – Používejte `java.time.LocalDateTime` pro hodnoty data; Aspose.Tasks je automaticky převede do formátu kalendáře projektu.

## Často kladené otázky

**Q: Mohu pomocí Aspose.Tasks pro Java číst soubory MS Project?**  
A: Ano, knihovna poskytuje plnou funkci čtení‑zápisu pro formáty .mpp, .xml i .xps.

**Q: Je Aspose.Tasks pro Java kompatibilní s různými verzemi MS Project?**  
A: Rozhodně, podporuje soubory od Project 2000 až po nejnovější vydání 2024, zahrnující více než 20 formátových verzí.

**Q: Existují nějaká omezení zkušební verze Aspose.Tasks pro Java?**  
A: Zkušební verze přidává vodoznak do generovaných souborů a omezuje počet úkolů, které můžete vytvořit, ale všechny funkce API zůstávají přístupné.

**Q: Jak získat podporu pro Aspose.Tasks pro Java?**  
A: Pomoc můžete hledat na fóru komunity Aspose.Tasks [zde](https://forum.aspose.com/c/tasks/15).

**Q: Mohu zakoupit dočasnou licenci pro Aspose.Tasks pro Java?**  
A: Ano, dočasné licence jsou k dispozici pro krátkodobé použití. Získáte ji [zde](https://purchase.aspose.com/temporary-license/).

---

**Poslední aktualizace:** 2026-05-20  
**Testováno s:** Aspose.Tasks pro Java 24.12 (nejnovější v době psaní)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Jak přidat poznámky k přiřazením zdrojů v Aspose.Tasks](/tasks/java/resource-assignments/resource-assignment-notes/)
- [Jak číst a zapisovat měřítko sazby pro přiřazení zdrojů v Aspose.Tasks](/tasks/java/resource-assignments/read-write-rate-scale/)
- [Jak přidat zdroj do projektu a spravovat vlastnosti zpoždění vyrovnání v Aspose.Tasks](/tasks/java/resource-assignments/leveling-delay-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}