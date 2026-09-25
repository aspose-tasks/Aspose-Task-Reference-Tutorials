---
date: 2026-09-25
description: Naučte se, jak vytvořit projektový harmonogram v Java pomocí Aspose.Tasks.
  Tento průvodce vám ukáže, jak přidat summary tasks, spravovat project hierarchy
  a efektivně nastavit document directory.
keywords:
- create project schedule
- java project management
- java task management
- add summary task
- manage project hierarchy
lastmod: 2026-09-25
linktitle: Vytvořit úkoly v Aspose.Tasks
og_description: Naučte se, jak vytvořit projektový harmonogram v Java pomocí Aspose.Tasks.
  Postupujte podle krok‑za‑krokem návodu k přidání summary tasks, správě hierarchy
  a nastavení document directory.
og_image_alt: Tutorial image showing Aspose.Tasks Java project schedule creation
og_title: Jak vytvořit projektový harmonogram pomocí Aspose.Tasks pro Java
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  headline: How to create project schedule with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create project schedule in Java using Aspose.Tasks. This
    guide shows you how to add summary tasks, manage project hierarchy, and set document
    directory efficiently.
  name: How to create project schedule with Aspose.Tasks for Java
  steps:
  - name: set the document directory
    text: Define where the resulting project file will be written. Setting the directory
      early ensures all subsequent save operations use a consistent path. The `RootFolder`
      property specifies the base folder where project files are read from or written
      to.
  - name: create a new project
    text: Instantiate a fresh `Project` object that will hold your schedule. You can
      optionally pass a pre‑existing file path to load an existing schedule for modification.
      The `Project` constructor creates an empty schedule ready for task addition.
  - name: add a summary task
    text: A summary task groups related subtasks and appears as a collapsible node
      in Gantt charts. Use the `Task` class and set `IsSummary` to `true`. The `addTask`
      method creates a new task under a specified parent and returns its ID.
  - name: add a subtask
    text: Subtasks inherit start/finish dates from their parent summary task unless
      you override them. Adding a subtask is as simple as calling `addTask` again
      and specifying the parent ID. Calling `addTask` with a parent ID adds a subtask
      under that summary task. Continue adding as many tasks and subtasks as
  type: HowTo
- questions:
  - answer: Absolutely. The library scales from a single‑task list to enterprise‑level
      schedules with thousands of tasks.
    question: Is Aspose.Tasks suitable for small‑scale projects?
  - answer: Refer to the documentation [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license request page](https://purchase.aspose.com/temporary-license/)
      for a time‑limited license that works for development and testing.
    question: How do I obtain a temporary license for Aspose.Tasks?
  - answer: Yes, you can extend tasks with custom fields, assign resources, and modify
      calendars programmatically.
    question: Can I customize task attributes using Aspose.Tasks?
  - answer: Absolutely! Join the Aspose.Tasks community on [the support forum](https://forum.aspose.com/c/tasks/15).
    question: Is there a support community for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- create project schedule
- Aspose.Tasks
- Java project management
title: Jak vytvořit projektový harmonogram pomocí Aspose.Tasks pro Java
url: /cs/java/task-properties/create-tasks/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit plán projektu pomocí Aspose.Tasks pro Java

## Úvod
V tomto tutoriálu se naučíte, jak **vytvořit plán projektu** v Java aplikaci pomocí Aspose.Tasks. Ať už vytváříte jednoduchý seznam úkolů nebo komplexní podnikový plánovač, níže uvedené kroky vás provedou přidáváním souhrnných úkolů, správou hierarchie projektu a nastavením adresáře dokumentu – vše s jasnými, spustitelnými ukázkami kódu. Na konci budete mít plně strukturovaný plán připravený k dalším úpravám nebo exportu.

## Rychlé odpovědi
- **Co Aspose.Tasks spravuje?** Zpracovává hierarchie úkolů, zdroje, kalendáře a formáty souborů projektů (MS‑Project, Primavera atd.).  
- **Potřebuji licenci pro vývoj?** Bezplatná dočasná licence funguje pro hodnocení; pro produkci je vyžadována plná licence.  
- **Která verze Javy je podporována?** Java 8 a novější jsou plně podporovány.  
- **Mohu přidat vlastní pole k úkolům?** Ano, můžete rozšířit úkoly o uživatelem definovaná pole pomocí API.  
- **Existuje vestavěná podpora pro Ganttovy diagramy?** Aspose.Tasks může exportovat do PDF/HTML, které zahrnují Ganttovy vizualizace.

## Co je plán projektu v Aspose.Tasks?
Plán projektu je kompletní sada úkolů, závislostí a časových os, které definují, jak bude práce prováděna. Aspose.Tasks ukládá tyto informace v objektu `Project`, který můžete číst, upravovat a ukládat v různých formátech. Obsahuje datum zahájení a ukončení, omezení a přiřazení zdrojů, což umožňuje komplexní plánování a reportování.

## Proč použít Aspose.Tasks pro řízení projektů v Javě?
Aspose.Tasks podporuje **více než 30 vstupních a výstupních formátů** a může zpracovávat projekty až s **10 000 úkoly** bez načítání celého souboru do paměti, což poskytuje vysoký výkon pro rozsáhlé scénáře řízení projektů v Javě.

## Předpoklady
Než se pustíte do tutoriálu, ujistěte se, že máte následující předpoklady:
- **Java Development Kit (JDK)** – JDK 8 nebo novější nainstalovaný na vašem počítači.  
- **Aspose.Tasks for Java knihovna** – Stáhněte a nainstalujte knihovnu z [Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/).  
- **Integrované vývojové prostředí (IDE)** – Použijte Eclipse, IntelliJ IDEA nebo jakékoli jiné Java‑přátelské IDE, které preferujete.

## Import balíčků
`Project`, `Task` a související třídy se nacházejí v jmenném prostoru `com.aspose.tasks`. Načtěte je na začátku vašeho Java souboru:

Třída `Project` představuje kompletní plán projektu a poskytuje metody pro manipulaci s úkoly a zdroji.

```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

Třída `Project` je vstupním bodem pro všechny operace s projektovým souborem.

## Jak vytvořit plán projektu pomocí Aspose.Tasks?
Načtěte novou instanci `Project`, nastavte adresář dokumentu a začněte přidávat úkoly. Tento přímý odstavec popisuje základní tok: vytvoříte `Project`, nakonfigurujete jeho `RootFolder` (adresář dokumentu), poté přidáte souhrnný úkol následovaný podúkoly. Všechny změny jsou uloženy v paměti, dokud nevoláte `save` pro uložení plánu do souboru.

### Krok 1: nastavení adresáře dokumentu
Definujte, kam bude výsledný projektový soubor zapsán. Nastavení adresáře na začátku zajišťuje, že všechny následné operace uložení použijí konzistentní cestu.

Vlastnost `RootFolder` určuje základní složku, odkud jsou projektové soubory čteny nebo do které jsou zapisovány.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

### Krok 2: vytvoření nového projektu
Vytvořte novou instanci objektu `Project`, která bude obsahovat váš plán. Volitelně můžete předat existující cestu k souboru pro načtení existujícího plánu k úpravě.

Konstruktor `Project` vytvoří prázdný plán připravený k přidání úkolů.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Krok 3: přidání souhrnného úkolu
Souhrnný úkol seskupuje související podúkoly a zobrazuje se jako sbalitelný uzel v Ganttových diagramech. Použijte třídu `Task` a nastavte `IsSummary` na `true`.

Metoda `addTask` vytvoří nový úkol pod zadaným nadřazeným úkolem a vrátí jeho ID.

```java
// Create a new project
Project project = new Project(dataDir + "project.mpp");
```

### Krok 4: přidání podúkolu
Podúkoly dědí datum zahájení/ukončení od svého nadřazeného souhrnného úkolu, pokud je nepřepíšete. Přidání podúkolu je tak jednoduché jako znovu zavolat `addTask` a zadat ID nadřazeného úkolu.

Volání `addTask` s ID nadřazeného úkolu přidá podúkol pod tento souhrnný úkol.

```java
// Add a summary task
Task task = project.getRootTask().getChildren().add("Summary1");
```

Pokračujte v přidávání libovolného počtu úkolů a podúkolů podle potřeby vašeho projektu. Každý krok přispívá k vytvoření strukturované hierarchie projektu, kterou lze exportovat do MS‑Project, PDF nebo jiných podporovaných formátů.

## Časté problémy a řešení
- **Problém:** „Adresář dokumentu nebyl nalezen.“  
  **Řešení:** Ověřte, že cesta přiřazená k `RootFolder` existuje v souborovém systému a že váš Java proces má oprávnění k zápisu.
- **Problém:** Podúkoly se nezobrazují pod souhrnným úkolem.  
  **Řešení:** Ujistěte se, že při volání `addTask` předáváte správné ID nadřazeného úkolu. API vyžaduje ID nadřazeného úkolu jako druhý argument.
- **Problém:** Velké projekty způsobují OutOfMemoryError.  
  **Řešení:** Aspose.Tasks zpracovává úkoly ve streamovacím režimu; zvyšte velikost haldy JVM (`-Xmx2g`) nebo rozdělete plán do více souborů.

## Často kladené otázky
**Q: Je Aspose.Tasks vhodný pro malé projekty?**  
A: Rozhodně. Knihovna škáluje od seznamu jedné úlohy až po podnikové plány s tisíci úkoly.

**Q: Kde najdu podrobnou dokumentaci pro Aspose.Tasks pro Java?**  
A: Odkazujte na dokumentaci [Aspose.Tasks Java API reference](https://reference.aspose.com/tasks/java/).

**Q: Jak získám dočasnou licenci pro Aspose.Tasks?**  
A: Navštivte [temporary license request page](https://purchase.aspose.com/temporary-license/) pro časově omezenou licenci, která funguje pro vývoj a testování.

**Q: Mohu přizpůsobit atributy úkolů pomocí Aspose.Tasks?**  
A: Ano, můžete rozšířit úkoly o vlastní pole, přiřadit zdroje a programově upravit kalendáře.

**Q: Existuje podpora komunity pro uživatele Aspose.Tasks?**  
A: Rozhodně! Připojte se ke komunitě Aspose.Tasks na [the support forum](https://forum.aspose.com/c/tasks/15).

---

**Poslední aktualizace:** 2026-09-25  
**Testováno s:** Aspose.Tasks 24.12 for Java  
**Autor:** Aspose  

```java
// Add a subtask under the summary task
Task subtask = task.getChildren().add("Subtask1");
```

## Související tutoriály

- [Nastavit počáteční datum projektu v MS Project pomocí Aspose.Tasks pro Java](/tasks/java/project-properties/write-project-info/)
- [Vytvořit závislosti úkolů v řízení projektů v Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Jak přidat zdroj do projektu a vytvořit přiřazení zdrojů v Aspose.Tasks](/tasks/java/resource-assignments/create-resource-assignments/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}