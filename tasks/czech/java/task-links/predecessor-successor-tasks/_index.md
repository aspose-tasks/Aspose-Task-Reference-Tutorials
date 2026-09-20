---
date: 2026-09-20
description: Naučte se, jak spravovat project task dependencies pomocí Aspose.Tasks
  for Java. Tento průvodce vám ukáže, jak přidat predecessor links, vytisknout task
  names a efektivně set task dependencies.
keywords:
- project task dependencies
- how to add predecessor
- java project management
- manage task dependencies
- print task names
lastmod: 2026-09-20
linktitle: Spravujte project task dependencies pomocí Aspose.Tasks for Java
og_description: Naučte se, jak spravovat project task dependencies pomocí Aspose.Tasks
  for Java. Tento průvodce vám ukáže, jak přidat predecessor links, vytisknout task
  names a efektivně set task dependencies.
og_image_alt: Guide showing how to manage project task dependencies with Aspose.Tasks
  Java API
og_title: Spravujte project task dependencies pomocí Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-09-20'
  description: Learn how to manage project task dependencies using Aspose.Tasks for
    Java. This guide shows you how to add predecessor links, print task names, and
    set task dependencies efficiently.
  headline: Manage project task dependencies via Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to manage project task dependencies using Aspose.Tasks for
    Java. This guide shows you how to add predecessor links, print task names, and
    set task dependencies efficiently.
  name: Manage project task dependencies via Aspose.Tasks for Java
  steps:
  - name: initialize the project object
    text: Create a new instance of the `Project` class and provide the path to your
      project file (e.g., `"project.mpp"`).
  - name: access task links
    text: Retrieve all task links from the project using the `getTaskLinks()` method.
  - name: iterate through task links
    text: Use a loop to iterate through each task link in the collection and print
      information about the predecessor and successor tasks.
  - name: add a new predecessor link (optional)
    text: If you need to create a new dependency, instantiate a `TaskLink`, set its
      `PredecessorTaskUid`, `SuccessorTaskUid`, and `LinkType`, then add it to the
      project's link collection. Repeat these steps as needed for your specific project
      requirements.
  type: HowTo
- questions:
  - answer: Yes, simply add the Aspose.Tasks JAR to your classpath or Maven/Gradle
      dependencies.
    question: Can I use Aspose.Tasks for Java in my existing Java project?
  - answer: Yes, it supports MPP, XML, CSV, and more than 30 additional formats.
    question: Is Aspose.Tasks compatible with different project file formats?
  - answer: Obtain a temporary license from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community support and discussions.
    question: Where can I find additional support for Aspose.Tasks?
  - answer: Yes, download a free trial from the [Aspose free trial page](https://releases.aspose.com/).
    question: Can I download a free trial of Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- project task dependencies
- Aspose.Tasks
- Java project management
title: Spravujte project task dependencies pomocí Aspose.Tasks for Java
url: /cs/java/task-links/predecessor-successor-tasks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Spravujte závislosti úkolů projektu pomocí Aspose.Tasks pro Java

## Úvod
Závislosti úkolů projektu jsou páteří každého realistického plánu, umožňují modelovat, která práce musí být dokončena, než může začít další. V tomto tutoriálu se naučíte, jak spravovat **project task dependencies** pomocí Aspose.Tasks pro Java, včetně toho, jak přidat předchozí odkazy, vytisknout názvy úkolů a nastavit závislosti úkolů programově.

## Rychlé odpovědi
- **Co je první krok?** Načtěte svůj soubor MPP do objektu `Project`.  
- **Jak přidáte předchůdce?** Vytvořte `TaskLink` a nastavte jeho `PredecessorTaskUid` a `SuccessorTaskUid`.  
- **Můžete vypsat všechny odkazy?** Použijte `project.getTaskLinks()` a iterujte přes kolekci.  
- **Potřebuji licenci?** Dočasná licence funguje pro hodnocení; plná licence je vyžadována pro produkci.  
- **Která verze Javy je podporována?** Java 8 nebo vyšší.

## Co jsou závislosti úkolů projektu?
Závislosti úkolů projektu definují logický vztah mezi dvěma úkoly, jako je Finish‑to‑Start nebo Start‑to‑Start, a určují pořadí, ve kterém musí být práce prováděna. Vytvořením těchto odkazů plán automaticky respektuje reálná omezení, zabraňuje překrývajícím se činnostem a zajišťuje, že následné úkoly začnou pouze tehdy, když jsou jejich předpoklady splněny.

## Proč používat Aspose.Tasks pro Java?
Aspose.Tasks pro Java podporuje více než třicet formátů projektových souborů, včetně nejnovějších verzí Microsoft Project, a dokáže zpracovávat soubory až do dvou gigabajtů, aniž by načítal celý dokument do paměti. Tato vysoce výkonná schopnost vám umožňuje manipulovat s obrovskými plány, generovat zprávy a provádět hromadné aktualizace efektivně, což z ní činí ideální řešení pro podnikovou správu projektů.

## Předpoklady
- Vývojové prostředí Java: Java 8 nebo novější nainstalovaná na vašem počítači.  
- Knihovna Aspose.Tasks pro Java: Stáhněte a nainstalujte knihovnu Aspose.Tasks z [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/).  
- Integrované vývojové prostředí (IDE): Eclipse, IntelliJ IDEA nebo jakékoli Java‑kompatibilní IDE, které preferujete.

## Import balíčků
Musíte importovat základní třídy, které umožňují manipulaci s projektem.

`Project` třída je vstupním bodem pro načítání a ukládání souborů Microsoft Project.  
`TaskLink` třída představuje závislost mezi dvěma úkoly.

## Jak přidat odkaz předchůdce mezi dvěma úkoly?
Vytvořte instanci `TaskLink`, přiřaďte UID předchozího úkolu a UID následujícího úkolu, vyberte vhodný `TaskLinkType`, například Finish‑to‑Start, a poté přidejte odkaz do kolekce odkazů úkolů projektu. Po přidání plán okamžitě odráží nový vztah závislosti.

### Krok 1: inicializujte objekt projektu
Vytvořte novou instanci třídy `Project` a zadejte cestu k vašemu souboru projektu (např. `"project.mpp"`).

```java
import com.aspose.tasks.*;
```

### Krok 2: přístup k odkazům úkolů
Získejte všechny odkazy úkolů z projektu pomocí metody `getTaskLinks()`.

```java
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "project.mpp");
```

### Krok 3: iterujte přes odkazy úkolů
Použijte smyčku k iteraci přes každý odkaz úkolu v kolekci a vytiskněte informace o předchozím a následujícím úkolu.

```java
TaskLinkCollection allinks = project.getTaskLinks();
```

### Krok 4: přidejte nový odkaz předchůdce (volitelné)
Pokud potřebujete vytvořit novou závislost, vytvořte instanci `TaskLink`, nastavte její `PredecessorTaskUid`, `SuccessorTaskUid` a `LinkType`, a poté ji přidejte do kolekce odkazů projektu.

```java
for (TaskLink tsklnk : allinks) {
    System.out.println("Predecessor " + tsklnk.getPredTask().get(Tsk.NAME));
    System.out.println("Successor " + tsklnk.getSuccTask().get(Tsk.NAME));
}
```

Opakujte tyto kroky podle potřeby pro vaše konkrétní požadavky projektu.

## Časté problémy a řešení
- **Chybějící předchůdce po přidání odkazu** – Ujistěte se, že voláte `project.updateTaskLinks()` (nebo uložíte a znovu načtete), aby se interní graf obnovil.  
- **Zpomalení výkonu u velkých souborů** – Použijte `project.setReadOnly(true)` před hromadnými operacemi, aby se snížila zátěž paměti.  
- **Nesprávný typ odkazu** – Ověřte, že používáte správnou hodnotu enumu `TaskLinkType` (např. `FinishToStart`), aby odpovídala logice vašeho plánu.

## Často kladené otázky

**Q: Mohu použít Aspose.Tasks pro Java ve svém existujícím Java projektu?**  
A: Ano, stačí přidat Aspose.Tasks JAR do classpath nebo Maven/Gradle závislostí.

**Q: Je Aspose.Tasks kompatibilní s různými formáty projektových souborů?**  
A: Ano, podporuje MPP, XML, CSV a více než 30 dalších formátů.

**Q: Jak mohu získat dočasnou licenci pro Aspose.Tasks?**  
A: Získejte dočasnou licenci na [temporary license page](https://purchase.aspose.com/temporary-license/).

**Q: Kde mohu najít další podporu pro Aspose.Tasks?**  
A: Navštivte [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) pro komunitní podporu a diskuse.

**Q: Mohu stáhnout bezplatnou zkušební verzi Aspose.Tasks pro Java?**  
A: Ano, stáhněte si bezplatnou zkušební verzi na [Aspose free trial page](https://releases.aspose.com/).

---

**Poslední aktualizace:** 2026-09-20  
**Testováno s:** Aspose.Tasks pro Java 24.12  
**Autor:** Aspose

## Související tutoriály

- [Vytvořit závislosti úkolů projektového řízení v Aspose.Tasks](/tasks/java/task-links/create-task-link/)
- [Nastavit datum zahájení projektu a spravovat nadřazené a podřízené úkoly v Aspose.Tasks](/tasks/java/task-properties/parent-child-tasks/)
- [Číst a nastavit priority úkolů pomocí Aspose.Tasks pro Java](/tasks/java/task-properties/handle-priorities/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}