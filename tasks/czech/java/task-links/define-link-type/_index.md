---
date: 2026-08-29
description: Naučte se, jak nastavit typy odkazů a spravovat závislosti úkolů pomocí
  Aspose.Tasks for Java v podrobném tutoriálu.
keywords:
- how to set link
- Aspose.Tasks link types
- Java task dependencies
lastmod: 2026-08-29
linktitle: Jak nastavit typy odkazů v Aspose.Tasks for Java
og_description: Naučte se, jak nastavit typy odkazů a spravovat závislosti úkolů pomocí
  Aspose.Tasks for Java. Podrobný průvodce pro vývojáře.
og_image_alt: Screenshot of Aspose.Tasks Java code setting task link types
og_title: Jak nastavit typy odkazů v Aspose.Tasks for Java
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set link types and manage task dependencies with Aspose.Tasks
    for Java in a step‑by‑step tutorial.
  headline: How to Set Link Types in Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates with standard Java SE, Java EE, and Android
      development kits without additional dependencies.
    question: Is Aspose.Tasks compatible with different Java environments?
  - answer: Absolutely. The `TaskLinkType` enum provides four standard types, and
      you can combine them with lag values to model complex schedules.
    question: Can I customize link types based on my project requirements?
  - answer: Refer to the [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)
      for in‑depth guidance, API reference, and code samples.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to acquire a temporary license for testing purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  - answer: Join the Aspose.Tasks community on the [support forum](https://forum.aspose.com/c/tasks/15)
      for assistance and discussions.
    question: Where can I get support for Aspose.Tasks‑related queries?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- task link
title: Jak nastavit typy odkazů v Aspose.Tasks for Java
url: /cs/java/task-links/define-link-type/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak nastavit typy odkazů v Aspose.Tasks pro Java

## Úvod
Pokud se ptáte, **jak nastavit odkaz** mezi úkoly při *spravování závislostí úkolů* v projektu, jste na správném místě. V tomto tutoriálu vás provedeme vytvořením nového projektu, přidáním úkolů a definováním typu odkazu (Start‑to‑Start, Finish‑to‑Start atd.) pomocí Aspose.Tasks pro Java. Na konci budete mít jistotu při přizpůsobování vztahů úkolů tak, aby odpovídaly reálným plánovacím potřebám, a uvidíte, jak API pracuje s rozsáhlými plány až do 10 000 úkolů.

## Rychlé odpovědi
- **Jaká třída představuje závislost?** `TaskLink` je hlavní objekt, který modeluje odkaz mezi dvěma úkoly.  
- **Který výčtový typ (enum) definuje typ vztahu?** `TaskLinkType` (např. `StartToStart`, `FinishToStart`).  
- **Mohu přečíst existující typy odkazů?** Ano – iterujte `Project.getTaskLinks()` a zavolejte `getLinkType()`.  
- **Potřebuji licenci pro tento kód?** Dočasná licence funguje pro testování; plná licence je vyžadována pro produkci.  
- **Je to kompatibilní s Java 8+?** Naprosto – Aspose.Tasks podporuje Java 8 až po Java 21, zahrnující 13 hlavních verzí.

## Co je odkaz úkolu?
**Odkaz úkolu** modeluje závislost mezi dvěma úkoly v časovém plánu projektu.  
Můžete vytvořit, upravit nebo smazat `TaskLink`, aby odrážel vztahy předchůdce‑následník, což umožňuje plánovači automaticky vypočítat data zahájení a dokončení.

## Proč používat typy odkazů v Aspose.Tasks?
Aspose.Tasks podporuje **více než 30 vstupních a výstupních formátů** a dokáže zpracovat projekty obsahující **až 10 000 úkolů** bez načítání celého souboru do paměti. Tato kvantifikovaná schopnost zajišťuje rychlý výkon i u podnikových plánů a knihovna zachovává všechny funkce Microsoft Project, jako jsou vlastní pole a přiřazení zdrojů.

## Požadavky
- **Java vývojové prostředí** – nainstalovaný a nakonfigurovaný JDK 8 nebo novější.  
- **Knihovna Aspose.Tasks** – Stáhněte nejnovější JAR z [download link](https://releases.aspose.com/tasks/java/).  
- **Adresář dokumentů** – Vytvořte složku na svém počítači, kde budete uchovávat soubory ukázkového projektu.

## Import balíčků
Začneme importováním základních tříd Aspose.Tasks. Tím připravíme IDE na rozpoznání API volání, která použijeme později.

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkCollection;
import com.aspose.tasks.TaskLinkType;
```

## Jak nastavit typy odkazů v Aspose.Tasks pro Java?
Načtěte novou instanci `Project`, přidejte dva úkoly a poté vytvořte `TaskLink` s požadovaným `TaskLinkType`. Tento dvoustupňový vzor vám umožní definovat kterýkoli ze čtyř standardních typů závislostí jedním voláním. `Project` představuje celý soubor projektu a jeho plán. `Task` je jednotlivá pracovní položka v rámci projektu. `TaskLink` spojuje předchozí úkol s následujícím úkolem. `TaskLinkType` je výčtový typ, který určuje vztah (Start‑to‑Start, Finish‑to‑Start atd.).

### Krok 1: nastavení typu odkazu
`TaskLink` představuje závislost mezi dvěma úkoly, zatímco `TaskLinkType` enumeruje možné typy vztahů, jako je `StartToStart`. V tomto kroku vytvoříme nový projekt, přidáme dva úkoly a spojíme je pomocí vztahu **Start‑to‑Start**.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";

Project project = new Project();
Task pred = project.getRootTask().getChildren().add("Task 1");
Task succ = project.getRootTask().getChildren().add("Task 2");
TaskLink link = project.getTaskLinks().add(pred, succ);
link.setLinkType(TaskLinkType.StartToStart);
```

> **Tip:** Můžete nahradit `StartToStart` za `FinishToStart`, `StartToFinish` nebo `FinishToFinish` podle závislosti, kterou potřebujete **spravovat závislosti úkolů**.

### Krok 2: získání typu odkazu
`Project.getTaskLinks()` vrací kolekci všech objektů `TaskLink` v plánu. Iterací této kolekce můžete přečíst `TaskLinkType` každého odkazu a ověřit, že byl uložen správný vztah.

```java
Project project = new Project(dataDir + "project.xml");
TaskLinkCollection allLinks = project.getTaskLinks();
for (TaskLink tskLink : allLinks) {
    System.out.println(tskLink.getLinkType());
}
```

Konzole vypíše hodnoty jako `StartToStart`, `FinishToStart` atd., čímž potvrdí typ odkazu, který jste dříve nastavili.

## Časté problémy a řešení
- **NullPointerException při přidávání odkazů** – Ujistěte se, že oba úkoly (předchůdce i následník) jsou přidány do projektu před vytvořením `TaskLink`.  
- **Nesprávný typ odkazu po uložení** – Vždy zavolejte `project.save("output.mpp")` (nebo jiný podporovaný formát) po nastavení typu odkazu, aby se změny uložily.  
- **Licence nebyla nalezena** – Umístěte soubor licence Aspose.Tasks do classpath projektu a načtěte jej pomocí `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");`.

## Často kladené otázky

**Q: Je Aspose.Tasks kompatibilní s různými Java prostředími?**  
A: Ano, Aspose.Tasks se integruje se standardním Java SE, Java EE a vývojovými sadami pro Android bez dalších závislostí.

**Q: Mohu přizpůsobit typy odkazů podle požadavků mého projektu?**  
A: Rozhodně. Výčtový typ `TaskLinkType` poskytuje čtyři standardní typy a můžete je kombinovat s hodnotami zpoždění pro modelování složitých plánů.

**Q: Kde najdu podrobnou dokumentaci k Aspose.Tasks pro Java?**  
A: Odkazujte se na [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/) pro podrobné pokyny, referenci API a ukázky kódu.

**Q: Jak mohu získat dočasnou licenci pro Aspose.Tasks?**  
A: Navštivte [temporary license page](https://purchase.aspose.com/temporary-license/) a získejte dočasnou licenci pro testovací účely.

**Q: Kde mohu získat podporu pro dotazy související s Aspose.Tasks?**  
A: Připojte se ke komunitě Aspose.Tasks na [support forum](https://forum.aspose.com/c/tasks/15) pro pomoc a diskuze.

**Q: Mohu změnit typ odkazu po uložení projektu?**  
A: Ano. Načtěte projekt, získejte `TaskLink`, zavolejte `setLinkType()` s novou hodnotou výčtu a projekt znovu uložte.

**Q: Podporuje Aspose.Tasks čtení souborů Microsoft Project (MPP)?**  
A: Ano. Použijte `new Project("file.mpp")` k načtení MPP souborů a práci s jejich odkazy úkolů stejně jako v XML příkladu výše.

---

**Last Updated:** 2026-08-29  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## Související tutoriály

- [Vytvořit křížový odkaz úkolu v Aspose.Tasks](/tasks/java/task-links/create-cross-project-task-link/)
- [Nastavit datum zahájení projektu a spravovat nadřazené a podřazené úkoly v Aspose.Tasks](/tasks/java/task-properties/parent-child-tasks/)
- [Načíst soubor MPP v Javě – spravovat vlastnosti projektu s Aspose.Tasks](/tasks/java/project-management/default-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}