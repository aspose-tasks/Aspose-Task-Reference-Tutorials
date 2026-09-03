---
date: 2026-05-31
description: Naučte se, jak získat verzi projektu a získat datum posledního uložení
  ze souborů MS Project pomocí Aspose.Tasks pro Java. Podrobný návod s ukázkami kódu.
keywords:
- how to get project version
- retrieve last saved date
- determine ms project version
- aspose tasks version java
- read project version java
linktitle: Určete verzi projektu pomocí Aspose.Tasks
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  headline: How to Get Project Version – Aspose Tasks Java Tutorial
  type: TechArticle
- description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  name: How to Get Project Version – Aspose Tasks Java Tutorial
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or newer.'
    text: '**Java Development Kit (JDK)** – version 8 or newer.'
  - name: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
    text: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
  - name: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
    text: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports .NET, Java, and C++ among others.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely; it can process multi‑hundred‑page projects in seconds without
      loading the entire file into memory.
    question: Is Aspose.Tasks suitable for large‑scale projects?
  - answer: Yes, you can modify tasks, resources, calendars, and any other project
      element through the API.
    question: Can I customize project data using Aspose.Tasks?
  - answer: No, the library works independently and does not need Microsoft Project
      on the host machine.
    question: Does Aspose.Tasks require Microsoft Project installation?
  - answer: Yes, you can get help from the Aspose.Tasks forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is technical support available for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: Jak získat verzi projektu – tutoriál Aspose.Tasks pro Java
url: /cs/java/project-management/determine-version/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak získat verzi projektu – Aspose Tasks Java tutoriál

V tomto **Aspose Tasks Java tutorial** se naučíte **jak získat verzi projektu** Microsoft Project souboru a také **jak získat datum posledního uložení** pomocí knihovny Aspose.Tasks pro Javu. Znalost verze souboru a časového razítka uložení vám pomůže vyhnout se problémům s kompatibilitou, vynutit migrační politiky a udržet přesné auditní záznamy. Provedeme vás každým krokem – od nastavení prostředí až po vytištění verze a data – abyste mohli tuto kontrolu vložit do jakékoli Java aplikace s jistotou.

## Rychlé odpovědi
- **Co tento tutoriál pokrývá?** Determining the MS Project file version and last‑saved date with Aspose.Tasks for Java.  
- **Potřebuji mít nainstalovaný Microsoft Project?** No, Aspose.Tasks works independently of Microsoft Project.  
- **Jaké formáty souborů jsou podporovány?** XML‑based Project files such as MPP and XML are fully supported.  
- **Jak dlouho trvá implementace?** Roughly 5‑10 minutes for a basic version check.  
- **Je vyžadována licence?** A free trial works for evaluation; a commercial license is required for production use.

## Co je Aspose Tasks Java tutoriál?
The `Aspose.Tasks` Java tutorial is a concise, hands‑on guide that demonstrates how to interact with Microsoft Project data programmatically. It shows you how to read, modify, and analyze project information without needing Microsoft Project installed on the server. Additionally, it covers loading files, accessing properties, and saving changes, enabling developers to automate project management tasks efficiently.

## Proč použít Aspose.Tasks k určení verze projektu?
Aspose.Tasks provides **exact version metadata** and **last‑saved timestamps** while running on any OS that supports Java. It processes files up to **500 pages in under 2 seconds** on a standard 2.5 GHz CPU, making it ideal for batch automation and large‑scale migration scenarios.

## Požadavky
1. **Java Development Kit (JDK)** – version 8 or newer.  
2. **Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/) and add it to your project’s classpath.  
3. **MS Project file** – an XML‑based Project file (e.g., `input.xml`) that you want to inspect.  

> **Pro tip:** Store the Project file in a dedicated `data` folder to keep paths tidy and avoid accidental overwrites.

## Import balíčků
First, import the essential Aspose.Tasks classes:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Jak nastavit adresář projektu
To correctly locate your project files, create a dedicated directory within your application structure and store all input files there. This keeps the code clean and avoids path‑related errors when loading files. Use a clear variable name for the directory path, which can be absolute or relative to the project root.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

Replace `"Your Data Directory"` with the absolute or relative path where `input.xml` resides.

## Jak načíst projekt
`Project` is the primary Aspose.Tasks object that represents a Microsoft Project file in memory, giving you access to all project properties and collections. After creating the `Project` instance, you can query its fields, iterate over tasks, or modify data before saving the file back to disk.

```java
Project project = new Project(dataDir + "input.xml");
```

If your file has a different name, adjust `"input.xml"` accordingly.

## Jak určit verzi projektu
`Prj.SAVE_VERSION` is a property that indicates the version number of Microsoft Project that saved the file. `Prj.LAST_SAVED` is a property that stores the date and time when the file was last saved. `Prj.SAVE_VERSION` returns the numeric version of the Microsoft Project application that saved the file (e.g., 12 for Project 2010). `Prj.LAST_SAVED` provides the exact date and time of the most recent save operation.

```java
//Display project version property
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```

These values let you programmatically enforce version‑specific business rules or generate audit reports.

## Jak zobrazit výsledek
After retrieving the version and last‑saved information, you typically want to output it to the console or a log file. Use `System.out.println` to display the values, formatting the date as needed. This confirms that the extraction succeeded and provides immediate feedback during development or in automated scripts.

```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```

## Časté problémy a řešení
| Problém | Důvod | Řešení |
|-------|--------|-----|
| `NullPointerException` on `project.get(...)` | File not found or path incorrect | Verify `dataDir` and file name; use an absolute path for testing. |
| Unexpected version number (e.g., 0) | Loading a non‑Project XML file | Ensure the file is a valid Microsoft Project file (MPP/XML). |
| License exception | Using the trial without a valid license in production | Apply your Aspose.Tasks license (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Často kladené otázky

**Q: Mohu použít Aspose.Tasks s jinými programovacími jazyky?**  
A: Ano, Aspose.Tasks podporuje .NET, Javu a C++ a další.

**Q: Je Aspose.Tasks vhodný pro velké projekty?**  
A: Rozhodně; dokáže zpracovat projekty s několika stovkami stran během sekund, aniž by načítal celý soubor do paměti.

**Q: Mohu pomocí Aspose.Tasks přizpůsobit data projektu?**  
A: Ano, můžete upravovat úkoly, zdroje, kalendáře a jakýkoli jiný prvek projektu prostřednictvím API.

**Q: Vyžaduje Aspose.Tasks instalaci Microsoft Project?**  
A: Ne, knihovna funguje nezávisle a nevyžaduje Microsoft Project na hostitelském stroji.

**Q: Je k dispozici technická podpora pro Aspose.Tasks?**  
A: Ano, můžete získat pomoc na fóru Aspose.Tasks [zde](https://forum.aspose.com/c/tasks/15).

**Další otázky a odpovědi**

**Q: Jak získám další vlastnosti projektu (např. autora, společnost)?**  
A: Use `project.get(Prj.AUTHOR)` or `project.get(Prj.COMPANY)` in the same way you retrieve the version.

**Q: Mohu zkontrolovat verzi souboru MPP (binárního)?**  
A: Yes, Aspose.Tasks loads `.mpp` files directly; the `Prj.SAVE_VERSION` property works for binary formats as well.

**Q: Existuje způsob, jak programově upgradovat starší soubor projektu na novější verzi?**  
A: Load the older file, then save it with `project.save("newfile.mpp", SaveFileFormat.MPP);` – Aspose.Tasks writes the file in the latest format by default.

## Závěr
You’ve now mastered **how to get project version** and **retrieve last saved date** from MS Project files using Aspose.Tasks for Java. Incorporate these snippets into automation pipelines, reporting tools, or migration utilities to guarantee you always know the exact Project version you’re handling.

---

**Poslední aktualizace:** 2026-05-31  
**Testováno s:** Aspose.Tasks for Java 24.11  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Nastavit datum zahájení projektu v MS Project pomocí Aspose.Tasks pro Java](/tasks/java/project-properties/write-project-info/)
- [Číst databázi Microsoft Project pomocí Aspose.Tasks pro Java](/tasks/java/project-data-reading/read-project-database/)
- [Uložit projekt jako šablonu, CSV a text pomocí Aspose.Tasks pro Java](/tasks/java/project-file-operations/save-csv-text-template/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}