---
title: "Determine Microsoft Project File Version and Last Saved Date Using Java"
linktitle: "Determine Project Version with Aspose.Tasks for Java"
second_title: "Aspose.Tasks Java API"
description: "Learn how to get project version and retrieve last saved date from MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples."
weight: 12
url: /java/project-management/determine-version/
date: 2026-05-31
keywords:
- how to get project version
- retrieve last saved date
- determine ms project version
- aspose tasks version java
- read project version java
schemas:
- type: TechArticle
  headline: Retrieve Project Version Using Aspose.Tasks for Java
  description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  dateModified: '2026-05-31'
  author: Aspose
- type: HowTo
  name: Retrieve Project Version Using Aspose.Tasks for Java
  description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or newer.'
    text: '**Java Development Kit (JDK)** – version 8 or newer.'
  - name: '**Aspose.Tasks for Java JAR** – download from the [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
    text: '**Aspose.Tasks for Java JAR** – download from the [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
  - name: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
    text: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
- type: FAQPage
  questions:
  - question: Can I use Aspose.Tasks with other programming languages?
    answer: Yes, Aspose.Tasks supports .NET, Java, and C++ among others.
  - question: Is Aspose.Tasks suitable for large‑scale projects?
    answer: Absolutely; it can process multi‑hundred‑page projects in seconds without
      loading the entire file into memory.
  - question: Can I customize project data using Aspose.Tasks?
    answer: Yes, you can modify tasks, resources, calendars, and any other project
      element through the API.
  - question: Does Aspose.Tasks require Microsoft Project installation?
    answer: No, the library works independently and does not need Microsoft Project
      on the host machine.
  - question: Is technical support available for Aspose.Tasks?
    answer: Yes, you can get help from the Aspose.Tasks support forum [Aspose.Tasks support forum](https://forum.aspose.com/c/tasks/15).
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Retrieve Project Version Using Aspose.Tasks for Java

In this **Aspose Tasks Java tutorial** you’ll learn **how to get project version** of a Microsoft Project file and also how to **retrieve last saved date** using the Aspose.Tasks library for Java. Knowing the file version and save timestamp helps you avoid compatibility problems, enforce migration policies, and keep accurate audit logs. We'll walk through every step—from environment setup to printing the version and date—so you can embed this check into any Java application with confidence.

## Quick Answers
- **What does this tutorial cover?** Determining the MS Project file version and last‑saved date with Aspose.Tasks for Java.  
- **Do I need Microsoft Project installed?** No, Aspose.Tasks works independently of Microsoft Project.  
- **Which file formats are supported?** XML‑based Project files such as MPP and XML are fully supported.  
- **How long does the implementation take?** Roughly 5‑10 minutes for a basic version check.  
- **Is a license required?** A free trial works for evaluation; a commercial license is required for production use.

## What is Aspose Tasks Java Tutorial?
The `Aspose.Tasks` Java tutorial is a concise, hands‑on guide that demonstrates how to interact with Microsoft Project data programmatically. It shows you how to read, modify, and analyze project information without needing Microsoft Project installed on the server. Additionally, it covers loading files, accessing properties, and saving changes, enabling developers to automate project management tasks efficiently.

## Why use Aspose.Tasks to determine project version?
Aspose.Tasks provides **exact version metadata** and **last‑saved timestamps** while running on any OS that supports Java. It processes files up to **500 pages in under 2 seconds** on a standard 2.5 GHz CPU, making it ideal for batch automation and large‑scale migration scenarios.

## Prerequisites
Before we begin, ensure you have:

1. **Java Development Kit (JDK)** – version 8 or newer.  
2. **Aspose.Tasks for Java JAR** – download from the [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/) and add it to your project’s classpath.  
3. **MS Project file** – an XML‑based Project file (e.g., `input.xml`) that you want to inspect.  

> **Pro tip:** Store the Project file in a dedicated `data` folder to keep paths tidy and avoid accidental overwrites.

## Import Packages
First, import the essential Aspose.Tasks classes:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## How to Set Up the Project Directory
To correctly locate your project files, create a dedicated directory within your application structure and store all input files there. This keeps the code clean and avoids path‑related errors when loading files. Use a clear variable name for the directory path, which can be absolute or relative to the project root.

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

Replace `"Your Data Directory"` with the absolute or relative path where `input.xml` resides.

## How to Load the Project
`Project` is the primary Aspose.Tasks object that represents a Microsoft Project file in memory, giving you access to all project properties and collections. After creating the `Project` instance, you can query its fields, iterate over tasks, or modify data before saving the file back to disk.

```java
Project project = new Project(dataDir + "input.xml");
```

If your file has a different name, adjust `"input.xml"` accordingly.

## How to Determine Project Version
`Prj.SAVE_VERSION` is a property that indicates the version number of Microsoft Project that saved the file. `Prj.LAST_SAVED` is a property that stores the date and time when the file was last saved. `Prj.SAVE_VERSION` returns the numeric version of the Microsoft Project application that saved the file (e.g., 12 for Project 2010). `Prj.LAST_SAVED` provides the exact date and time of the most recent save operation.

```java
//Display project version property
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```

These values let you programmatically enforce version‑specific business rules or generate audit reports.

## How to Display Result
After retrieving the version and last‑saved information, you typically want to output it to the console or a log file. Use `System.out.println` to display the values, formatting the date as needed. This confirms that the extraction succeeded and provides immediate feedback during development or in automated scripts.

```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```

## Common issues and solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| `NullPointerException` on `project.get(...)` | File not found or path incorrect | Verify `dataDir` and file name; use an absolute path for testing. |
| Unexpected version number (e.g., 0) | Loading a non‑Project XML file | Ensure the file is a valid Microsoft Project file (MPP/XML). |
| License exception | Using the trial without a valid license in production | Apply your Aspose.Tasks license (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## Frequently asked questions

**Q: Can I use Aspose.Tasks with other programming languages?**  
A: Yes, Aspose.Tasks supports .NET, Java, and C++ among others.

**Q: Is Aspose.Tasks suitable for large‑scale projects?**  
A: Absolutely; it can process multi‑hundred‑page projects in seconds without loading the entire file into memory.

**Q: Can I customize project data using Aspose.Tasks?**  
A: Yes, you can modify tasks, resources, calendars, and any other project element through the API.

**Q: Does Aspose.Tasks require Microsoft Project installation?**  
A: No, the library works independently and does not need Microsoft Project on the host machine.

**Q: Is technical support available for Aspose.Tasks?**  
A: Yes, you can get help from the Aspose.Tasks support forum [Aspose.Tasks support forum](https://forum.aspose.com/c/tasks/15).

**Additional Q&A**

**Q: How do I retrieve other project properties (e.g., author, company)?**  
A: Use `project.get(Prj.AUTHOR)` or `project.get(Prj.COMPANY)` in the same way you retrieve the version.

**Q: Can I check the version of an MPP (binary) file?**  
A: Yes, Aspose.Tasks loads `.mpp` files directly; the `Prj.SAVE_VERSION` property works for binary formats as well.

**Q: Is there a way to programmatically upgrade an older project file to a newer version?**  
A: Load the older file, then save it with `project.save("newfile.mpp", SaveFileFormat.MPP);` – Aspose.Tasks writes the file in the latest format by default.

## Conclusion
You’ve now mastered **how to get project version** and **retrieve last saved date** from MS Project files using Aspose.Tasks for Java. Incorporate these snippets into automation pipelines, reporting tools, or migration utilities to guarantee you always know the exact Project version you’re handling.

---

**Last Updated:** 2026-05-31  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Related Tutorials

[Set Project Start Date in MS Project using Aspose.Tasks for Java](/tasks/java/project-properties/write-project-info/)
[Read Microsoft Project database with Aspose.Tasks for Java](/tasks/java/project-data-reading/read-project-database/)
[Save Project as Template, CSV, and Text with Aspose.Tasks for Java](/tasks/java/project-file-operations/save-csv-text-template/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}