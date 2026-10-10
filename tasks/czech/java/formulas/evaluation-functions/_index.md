---
date: 2026-10-10
description: Zjistěte, jak přidat rozšířený atribut v Aspose.Tasks, používat evaluační
  funkce a generovat projektové zprávy pomocí této Java knihovny pro řízení projektů.
keywords:
- how to add extended attribute
- add custom field task
- java project management library
lastmod: 2026-10-10
linktitle: Podpora evaluačních funkcí ve vzorcích Aspose.Tasks
og_description: Zjistěte, jak přidat rozšířený atribut v Aspose.Tasks, používat evaluační
  funkce a generovat projektové zprávy pomocí této Java knihovny pro řízení projektů.
og_image_alt: Aspose.Tasks Java tutorial showing how to add extended attribute and
  use evaluation functions
og_title: Jak přidat rozšířený atribut do vzorců v Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-10-10'
  description: Learn how to add extended attribute in Aspose.Tasks, use evaluation
    functions, and generate project reports with this Java project management library.
  headline: How to add extended attribute in Aspose.Tasks formulas
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java supports evaluation of a wide range of MS Project
      functions, allowing for complex calculations within Java applications.
    question: Can Aspose.Tasks for Java handle complex MS Project formulas?
  - answer: Yes, Aspose.Tasks for Java supports various versions of Microsoft Project
      files, including MPP, MPT, and XML formats.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project files?
  - answer: Yes, you can download a free trial version of Aspose.Tasks for Java from
      the website [Aspose.Tasks for Java purchase page](https://purchase.aspose.com/buy).
    question: Can I try Aspose.Tasks for Java before purchasing?
  - answer: You can get support from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, you can obtain a temporary license for testing purposes from the
      Aspose website [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Is there a temporary license available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add extended attribute
- java project management library
- Aspose.Tasks
- evaluation functions
- custom field task
title: Jak přidat rozšířený atribut do vzorců v Aspose.Tasks
url: /cs/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak přidat rozšířený atribut ve formulích Aspose.Tasks

## Úvod
Aspose.Tasks for Java je **Java knihovna pro řízení projektů**, která vám umožní generovat projektové zprávy vytvořením objektu `Project` v Javě a vyhodnocováním funkcí Microsoft Project přímo ve vašem kódu. Vkládáním těchto formulí můžete provádět složité výpočty, generovat vlastní zprávy a automatizovat analýzu projektů, aniž byste opustili vývojové prostředí. V tomto tutoriálu vás provedeme vytvořením objektu projektu, přidáním rozšířeného atributu a použitím evaluačních funkcí k **přidání úkolu s vlastním polem**.

## Rychlé odpovědi
- **Co znamená “create project object java”?** Vytváří v‑paměti instanci `Project`, kterou můžete programově manipulovat.  
- **Která knihovna je vyžadována?** Aspose.Tasks for Java (stáhněte z oficiálního webu).  
- **Potřebuji licenci?** Pro produkční použití je vyžadována dočasná nebo plná licence Aspose.Tasks; k dispozici je bezplatná zkušební verze.  
- **Mohu používat vlastní pole?** Ano – můžete **přidat rozšířený atribut** k úkolům a zacházet s ním jako s vlastním polem.  
- **Je to kompatibilní se všemi formáty souborů Project?** Aspose.Tasks podporuje 3 hlavní formáty (MPP, MPT, XML) a více než 50 dalších vstupních/výstupních formátů.

## Požadavky
Před zahájením se ujistěte, že máte:

1. **Java vývojové prostředí** – JDK 8+ a IDE jako IntelliJ IDEA nebo Eclipse.  
2. **Knihovna Aspose.Tasks pro Java** – Stáhněte a zahrňte knihovnu z [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/).

## Import balíčků
Přidejte namespace Aspose.Tasks do vaší Java třídy, abyste mohli pracovat s projekty, úkoly a rozšířenými atributy:

```java
import com.aspose.tasks.*;
```

## Vytvoření projektové zprávy – vytvoření objektu projektu v Javě
Třída `Project` představuje soubor Microsoft Project v paměti a poskytuje přístup k úkolům, zdrojům a vlastním datům. Vytvořením instance této třídy získáte kontejner pro všechny prvky projektu, které budete definovat.

```java
Project project = new Project();
```

Řádek výše **vytváří objekt projektu v Javě**, který je prázdný a připravený k úpravám.

## Jak přidat rozšířený atribut
Třída `ExtendedAttributeDefinition` definuje vlastní pole, které lze přiřadit k úkolům. Pro přidání rozšířeného atributu vytvořte instanci této třídy s typem `Number`, přiřaďte jí alias, například „Sine“, přidejte ji do kolekce `ExtendedAttributes` projektu a poté ji propojte s každým úkolem, který vyžaduje vlastní pole.

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

Zde **přidáváme rozšířený atribut** typu `Number` s názvem „Sine“ a přiřazujeme jej úkolům.

## Přidání rozšířeného atributu do projektu
Zaregistrujte definici atributu v projektu, aby na ni mohl odkazovat každý úkol.

```java
project.getExtendedAttributes().add(attr);
```

## Vytvoření nového úkolu
`Task` představuje pracovní položku v projektu a může obsahovat vlastní pole.

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## Přidání úkolu s vlastním polem do projektu
Propojte dříve definovaný rozšířený atribut s nově vytvořeným úkolem, čímž úkolu přiřadíte vlastní pole „Sine“, které můžete použít ve formulích nebo výpočtech.

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

Nyní úkol obsahuje vlastní pole „Sine“, které můžete použít ve formulích nebo výpočtech. Takto také **přidáváte data úkolu s vlastním polem** programově.

## Proč používat evaluační funkce?
Evaluační funkce vám umožňují vložit nativní Microsoft Project formule (např. `Sin([Start])`) přímo do Aspose.Tasks, což umožňuje okamžité výpočty bez externího zpracování. To udržuje veškerou logiku projektu na jednom místě, snižuje chyby synchronizace dat a urychluje generování zpráv. Aspose.Tasks podporuje vyhodnocování více než 100 funkcí MS Project, poskytující komplexní výpočetní engine v Javě.

## Časté problémy a řešení
| Problém | Řešení |
|-------|----------|
| **Formula vrací `NaN`** | Ověřte, že typ vlastního pole odpovídá očekávanému číselnému typu. |
| **Rozšířený atribut není viditelný** | Ujistěte se, že definice atributu je přidána do projektu **před** vytvořením úkolů. |
| **Výjimka licence** | Nainstalujte dočasnou nebo plnou **licenci Aspose.Tasks**; režim zkušební verze může omezovat některé funkce. |
| **Chybí dočasná licence** | Získejte **dočasnou licenci Aspose** na webu Aspose. |

## Často kladené otázky

**Q: Může Aspose.Tasks pro Java zvládnout složité MS Project formule?**  
A: Ano, Aspose.Tasks pro Java podporuje vyhodnocování široké škály funkcí MS Project, což umožňuje složité výpočty v Java aplikacích.

**Q: Je Aspose.Tasks pro Java kompatibilní s různými verzemi souborů Microsoft Project?**  
A: Ano, Aspose.Tasks pro Java podporuje různé verze souborů Microsoft Project, včetně formátů MPP, MPT a XML.

**Q: Můžu si Aspose.Tasks pro Java vyzkoušet před zakoupením?**  
A: Ano, můžete si stáhnout bezplatnou zkušební verzi Aspose.Tasks pro Java z webu [Aspose.Tasks for Java purchase page](https://purchase.aspose.com/buy).

**Q: Jak mohu získat podporu pro Aspose.Tasks pro Java?**  
A: Podporu můžete získat na fóru komunity Aspose.Tasks [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15).

**Q: Je k dispozici dočasná licence pro Aspose.Tasks pro Java?**  
A: Ano, můžete získat dočasnou licenci pro testovací účely na webu Aspose [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).

## Závěr
Postupem těchto kroků jste se naučili, jak **vytvořit objekt projektu**, **přidat rozšířený atribut** a využít evaluační funkce k **automatickému generování projektové zprávy**. Nyní můžete tuto základnu rozšířit a vytvořit pokročilejší projektovou analytiku, vlastní dashboardy nebo automatizované nástroje pro plánování – vše poháněné Aspose.Tasks pro Java.

---

**Poslední aktualizace:** 2026-10-10  
**Testováno s:** Aspose.Tasks for Java 24.10  
**Autor:** Aspose

## Související tutoriály

- [Vlastní sloupce a rozšířené atributy v Java řízení projektů](/tasks/java/project-management/extended-attributes/)
- [Čtení rozšířených atributů úkolů s Aspose.Tasks pro Java](/tasks/java/task-properties/extended-task-attributes/)
- [Jak používat Aspose.Tasks pro Java – Přidat rozšířené atributy k přiřazením zdrojů](/tasks/java/resource-assignments/add-extended-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}