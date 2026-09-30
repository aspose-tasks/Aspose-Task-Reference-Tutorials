---
date: 2026-09-30
description: Naučte se, jak vytvořit rozšířený atribut úkolu pomocí Aspose.Tasks pro
  Java, přední knihovny pro řízení projektů v jazyce Java, určené k přidávání vlastních
  polí úkolů.
keywords:
- create task extended attribute
- java project management library
- add custom task field
lastmod: 2026-09-30
linktitle: Jak vytvořit rozšířený atribut úkolu pomocí Aspose.Tasks Java
og_description: Naučte se, jak vytvořit rozšířený atribut úkolu pomocí Aspose.Tasks
  pro Java, přední knihovny pro řízení projektů v jazyce Java, určené k přidávání
  vlastních polí úkolů.
og_image_alt: 'Developer guide: create task extended attribute in Aspose.Tasks Java'
og_title: Jak vytvořit rozšířený atribut úkolu pomocí Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Learn how to create task extended attribute using Aspose.Tasks for
    Java, the leading java project management library for adding custom task fields.
  headline: How to create task extended attribute with Aspose.Tasks Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates smoothly with any Java ecosystem,
      including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library is engineered to handle multi‑thousand‑task projects
      and supports streaming to keep memory usage low.
    question: Is Aspose.Tasks for Java suitable for large‑scale project management
      applications?
  - answer: Yes, you need a valid commercial license. You can review the details on
      the [Aspose.Tasks website](https://purchase.aspose.com/buy).
    question: Are there any licensing considerations for using Aspose.Tasks for Java
      in a commercial project?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community help, or open a support ticket through your Aspose account.
    question: How can I get support or assistance with Aspose.Tasks for Java?
  - answer: Yes, you can access a free trial version on the [Aspose.Tasks free trial](https://releases.aspose.com/)
      page.
    question: Can I try Aspose.Tasks for Java before purchasing?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project management
- extended attributes
- task customization
title: Jak vytvořit rozšířený atribut úkolu pomocí Aspose.Tasks Java
url: /cs/java/task-properties/add-extended-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit rozšířený atribut úkolu pomocí Aspose.Tasks Java

## Úvod
V tomto tutoriálu se naučíte, jak **vytvořit rozšířený atribut úkolu** v souboru Microsoft Project pomocí Aspose.Tasks pro Java. Přidání vlastních polí vám umožní zachytit projektově specifická data, která nejsou pokryta vestavěnými sloupci, a poskytuje vám jemnější kontrolu nad reportováním a plánováním zdrojů. Na konci průvodce budete schopni přidat atributy typu prostý text, s výběrem a trvání k libovolnému úkolu.

## Rychlé odpovědi
- **Co znamená „rozšířený atribut“?** Jedná se o vlastní pole, které definujete a připojíte k úkolům, zdrojům nebo přiřazením.  
- **Která knihovna tuto funkci přidává?** Aspose.Tasks pro Java, knihovna pro správu projektů v jazyce Java.  
- **Potřebuji licenci k vyzkoušení?** Ano – je k dispozici bezplatná 30‑denní zkušební verze na webu Aspose.  
- **Mohu přidat hodnoty výběru?** Rozhodně; můžete poskytnout seznam povolených hodnot pro textová nebo trvání pole.  
- **Je API kompatibilní s Java 8 a novějšími?** Ano, podporuje Java 8+ a běží na všech hlavních operačních systémech.

## Co je rozšířený atribut úkolu?
Rozšířený atribut úkolu je uživatelem definovaný sloupec, který ukládá další informace pro každý úkol v souboru Project. Chová se jako vestavěné pole, ale může obsahovat libovolný datový typ, který potřebujete, například text, čísla, data nebo trvání.

## Proč používat Aspose.Tasks pro Java?
Aspose.Tasks podporuje **více než 50 formátů souborů** a dokáže zpracovat projekty s **více než 10 000 úkoly** bez nutnosti instalace Microsoft Project. Knihovna funguje zcela offline, což zaručuje soukromí dat a deterministický výkon pro enterprise‑scale řešení.

## Předpoklady
Než začnete, ujistěte se, že máte:

- Základní znalosti programování v Javě.  
- Knihovnu Aspose.Tasks pro Java nainstalovanou. Můžete si ji stáhnout z [webu](https://releases.aspose.com/tasks/java/).  
- Java IDE (IntelliJ IDEA, Eclipse nebo VS Code) nastavené na vašem počítači.

## Import balíčků
Příkazy `import` vám poskytují přístup k základním třídám, které budete potřebovat, jako jsou `Project`, `ExtendedAttributeDefinition` a `ExtendedAttribute`.  

`Project` představuje soubor Microsoft Project a poskytuje metody pro jeho čtení, úpravu a uložení.  
`ExtendedAttributeDefinition` definuje vlastní pole, které může být připojeno k úkolům, zdrojům nebo přiřazením.  
`ExtendedAttribute` je instance definice, která drží skutečnou hodnotu pro konkrétní entitu.

## Jak přidat prostý textový rozšířený atribut k úkolu?
Pro přidání prostého textového rozšířeného atributu nejprve načtete projekt, poté vytvoříte definici typu Text, přidáte ji do kolekce projektu, vytvoříte úkol, vytvoříte atribut z definice, nastavíte jeho textovou hodnotu, připojíte jej k úkolu a nakonec projekt uložíte.

### 1. Nastavte cestu ke složce dokumentu
Určete, kde se nacházejí vaše vstupní a výstupní soubory.

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

### 2. Vytvořte nový projekt
Instancujte objekt `Project`, volitelně načtěte existující soubor .mpp.

```java
String dataDir = "Your Document Directory";
```

### 3. Vytvořte definici rozšířeného atributu typu Text1
Definujte vlastní pole jako prostý textový sloupec pojmenovaný „Text1“.

```java
Project project = new Project(dataDir + "project.mpp");
```

### 4. Přidejte definici do kolekce rozšířených atributů projektu
Zaregistrujte novou definici, aby ji projekt rozpoznal.

```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```

### 5. Přidejte úkol do projektu
Vytvořte úkol, který obdrží vlastní pole.

```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```

### 6. Vytvořte rozšířený atribut z definice atributu
Vygenerujte instanci, kterou můžete svázat s konkrétním úkolem.

```java
Task task = project.getRootTask().getChildren().add("Task 1");
```

### 7. Přiřaďte hodnotu vytvořenému rozšířenému atributu
Nastavte skutečný text, který chcete uložit, např. „Design Review“.

```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```

### 8. Přidejte rozšířený atribut k úkolu
Připojte instanci atributu ke kolekci `ExtendedAttributes` úkolu.

```java
taskExtendedAttributeText1.setTextValue("London");
```

### 9. Uložte projekt
Zapište aktualizovaný projekt zpět na disk v požadovaném formátu.

```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```

## Jak přidat textový atribut s možností výběru?
Při přidávání textového atributu s výběrem postupujete stejně jako u prostého textového atributu, ale před přidáním definice naplníte její kolekci `LookupValues` povolenými řetězci. Tyto hodnoty se zobrazí jako rozbalovací seznam v Microsoft Project, což zajišťuje konzistenci dat.

## Jak přidat atribut trvání s možností výběru?
Pro přidání atributu trvání s výběrem nahradíte typ `Text1` typem `Duration2` při vytváření definice, poté naplníte kolekci `LookupValues` řetězci trvání, jako je „1 day“, „2 days“ atd. Po přidání definice do projektu vytvoříte instanci atributu, nastavíte hodnotu trvání, připojíte ji k úkolu a soubor uložíte.

## Časté problémy a řešení
- **Hodnoty výběru se nezobrazují** – Ujistěte se, že každou položku výběru přidáte do kolekce `LookupValues` *před* voláním `project.getExtendedAttributes().add(definition)`.  
- **Hodnota atributu se neuloží** – Ověřte, že instanci `ExtendedAttribute` přidáte k úkolu *po* nastavení její hodnoty.  
- **Velikost souboru nečekaně roste** – Při práci s velmi velkými projekty zvažte volání `project.setSaveOptions(new ProjectSaveOptions())` pro povolení inkrementálního ukládání.

## Často kladené otázky

**Q: Mohu používat Aspose.Tasks pro Java s jinými knihovnami Java?**  
A: Ano, Aspose.Tasks pro Java se hladce integruje s jakýmkoli Java ekosystémem, včetně Spring, Hibernate a Apache POI.

**Q: Je Aspose.Tasks pro Java vhodný pro rozsáhlé aplikace pro správu projektů?**  
A: Rozhodně. Knihovna je navržena tak, aby zvládala projekty s tisíci úkoly a podporuje streamování pro nízkou spotřebu paměti.

**Q: Existují licenční úvahy při používání Aspose.Tasks pro Java v komerčním projektu?**  
A: Ano, potřebujete platnou komerční licenci. Podrobnosti si můžete prohlédnout na [webu Aspose.Tasks](https://purchase.aspose.com/buy).

**Q: Jak mohu získat podporu nebo pomoc s Aspose.Tasks pro Java?**  
A: Navštivte [forum Aspose.Tasks](https://forum.aspose.com/c/tasks/15) pro komunitní pomoc, nebo otevřete ticket podpory prostřednictvím svého Aspose účtu.

**Q: Můžu si Aspose.Tasks pro Java vyzkoušet před zakoupením?**  
A: Ano, můžete získat bezplatnou zkušební verzi na stránce [Aspose.Tasks free trial](https://releases.aspose.com/).

---

**Poslední aktualizace:** 2026-09-30  
**Testováno s:** Aspose.Tasks pro Java 24.10  
**Autor:** Aspose  

```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```

## Související tutoriály

- [Custom columns and extended attributes in Java project management](/tasks/java/project-management/extended-attributes/)
- [Read Extended Task Attributes with Aspose.Tasks for Java](/tasks/java/task-properties/extended-task-attributes/)
- [How to Create Project aspose.tasks – Set New Task Attributes](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}