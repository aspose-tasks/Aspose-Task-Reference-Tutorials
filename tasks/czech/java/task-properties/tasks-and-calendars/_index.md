---
date: 2026-02-28
description: Naučte se, jak přidat úkol do projektu a vytvořit kalendář úkolů v Javě
  pomocí Aspose.Tasks pro Javu – výkonná knihovna pro řízení projektů.
linktitle: Tasks and Calendars in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Přidat úkol do projektu a spravovat kalendáře pomocí Aspose.Tasks pro Javu
url: /cs/java/task-properties/tasks-and-calendars/
weight: 33
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidat úkol do projektu a spravovat kalendáře pomocí Aspose.Tasks pro Java

## Introduction
Připraveni **přidat úkol do projektu** a udržet svůj rozvrh dokonale sladěný? V tomto průvodci projdeme nezbytné kroky pro vytváření úkolů, přiřazování k vlastním kalendářům a využití Aspose.Tasks — průmyslově špičkové **java knihovny pro řízení projektů**. Na konci přesně vědět, jak **vytvořit kalendář úkolu v jave**‑stylu, což vám poskytne detailní kontrolu nad časovými osami projektu.

## Quick Answers
- **What is the primary purpose?** Přidat úkol do projektu a přiřadit jej k vlastnímu kalendáři.  
- **Which library should I use?** Aspose.Tasks for Java — plnohodnotné API pro řízení projektů.  
- **Do I need a license?** K dispozici je bezplatná zkušební verze; pro produkční nasazení je vyžadována komerční licence.  
- **What JDK version is required?** Java 8 nebo vyšší.  
- **How long does implementation take?** Obvykle méně než 15 minut pro základní scénáře.

## What is “add task to project”?
Přidání úkolu do projektu znamená vytvořit pracovní položku uvnitř objektu **Project** a definovat její vlastnosti (délka trvání, datum zahájení, kalendář atd.). Tato operace je stavebním kamenem každé aplikace zaměřené na plánování.

## Why use a Java project management library?
Vyhrazená knihovna jako Aspose.Tasks zpracovává složitý formát souborů MS‑Project, vyrovnávání zdrojů a výpočty kalendářů za vás. Ušetří vám čas a zajišťuje kompatibilitu s nástroji standardizovanými v odvětví.

## Prerequisites
Před tím, než se pustíte do tutoriálu, ujistěte se, že máte připravené následující předpoklady:
- Java Development Kit (JDK): Ověřte, že máte na svém systému nainstalovanou Javu.  
- Aspose.Tasks Library: Stáhněte a zahrňte knihovnu Aspose.Tasks do svého projektu. Knihovnu najdete [zde](https://releases.aspose.com/tasks/java/).

## Import Packages
Ve svém Java projektu importujte potřebné balíčky pro Aspose.Tasks:

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
```

## Step 1: Set Up Your Project
Začněte vytvořením nového Java projektu a přidáním souboru Aspose.Tasks JAR do cesty sestavení. Tím získáte přístup k úplnému API.

## Step 2: How to add task to project
Vytvořte novou instanci `Project` a přidejte úkol na úrovni kořene s názvem **Task1**. Tím demonstrujete základní operaci „add task to project“.

```java
Project project = new Project();
Task tsk = project.getRootTask().getChildren().add("Task1");
```

## Step 3: How to create task calendar java
Přidejte standardní kalendář do svého projektu. Kalendáře definují pracovní dny, svátky a další pravidla plánování.

```java
Calendar cal = project.getCalendars().add("TaskCal1");
```

## Step 4: Associate Task with Calendar
Propojte dříve vytvořený úkol s novým kalendářem, aby jeho rozvrh respektoval pracovní dobu kalendáře.

```java
tsk.set(Tsk.CALENDAR, cal);
```

*Tip:* Opakujte tyto kroky pro každý další úkol a kalendář, který potřebujete. Můžete také přizpůsobit výjimky kalendáře (např. nepracovní dny) pomocí API `Calendar`.

## Common Issues and Solutions
- **Task not reflecting calendar changes:** Ujistěte se, že po úpravě kalendářů zavoláte `project.updateStructure()`.  
- **NullPointerException on `set` call:** Ověřte, že byl kalendář úspěšně přidán do projektu před jeho přiřazením.  
- **Incorrect dates after import/export:** Použijte `project.save("output.mpp")` a znovu otevřete soubor, abyste potvrdili, že data zůstala zachována.

## Frequently Asked Questions
### How can I download Aspose.Tasks for Java?
Navštivte [this link](https://releases.aspose.com/tasks/java/) a stáhněte knihovnu.

### Where can I find the documentation for Aspose.Tasks?
Prozkoumejte dokumentaci [here](https://reference.aspose.com/tasks/java/).

### Is there a free trial available?
Ano, bezplatnou zkušební verzi získáte [here](https://releases.aspose.com/).

### How do I get support for Aspose.Tasks?
Připojte se ke komunitě na [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) a získejte podporu.

### Can I purchase a license for Aspose.Tasks?
Ano, licenci můžete zakoupit [here](https://purchase.aspose.com/buy).

**Additional Q&A**

**Q: Can I use Aspose.Tasks to read existing Microsoft Project files?**  
A: Absolutely. The `Project` class can load `.mpp` and `.xml` files directly.

**Q: Does the library support multiple calendars per project?**  
A: Yes. You can create as many `Calendar` objects as needed and assign each to different tasks.

## Conclusion
Gratulujeme! Úspěšně jste se naučili, jak **přidat úkol do projektu**, vytvořit vlastní kalendář a propojit je pomocí Aspose.Tasks pro Java. Toto výkonné spojení vám umožní rychle vytvářet robustní aplikace s vědomím časového rozvrhu.

---

**Last Updated:** 2026-02-28  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}