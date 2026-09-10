---
date: 2026-09-09
description: Learn how to change currency symbol in Aspose.Tasks Java projects, set
  currency codes, adjust symbols, and apply custom formats for Microsoft Project files.
images:
- /java/currency-properties/set-properties/og-image.png
keywords:
- how to change currency symbol
- Aspose.Tasks currency code
- Java project currency
- Microsoft Project formatting
lastmod: 2026-09-09
linktitle: Set Currency Properties in Aspose.Tasks Projects
og_description: How to change currency symbol in Aspose.Tasks using Java. Discover
  step‑by‑step instructions, prerequisites, and tips to customize project cost formatting.
og_image_alt: Screenshot of Aspose.Tasks Java code setting currency symbol
og_title: How to change currency symbol in Aspose.Tasks – Java guide
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  headline: How to change currency symbol in Aspose.Tasks projects – Java guide
  type: TechArticle
- description: Learn how to change currency symbol in Aspose.Tasks Java projects,
    set currency codes, adjust symbols, and apply custom formats for Microsoft Project
    files.
  name: How to change currency symbol in Aspose.Tasks projects – Java guide
  steps:
  - name: Define the data directory
    text: Choose a folder that holds your source files and where the output will be
      written. Make sure the directory exists and your Java process has write permission.
  - name: Create a new project instance
    text: '`Project` class is Aspose.Tasks'' top‑level object that represents a single
      Project file in memory. Instantiating it creates a blank project ready for configuration.'
  - name: Set currency properties
    text: Here you configure the currency code, number of decimal digits, the symbol
      itself, and the symbol’s position. - **Currency code** – a three‑letter ISO
      4217 code such as `AUD` or `USD`. - **Decimal digits** – typically 2 for most
      currencies. - **Currency symbol** – the character or string displayed w
  - name: Save the updated project
    text: Write the project back to disk using the desired format. The XML format
      is human‑readable, while `SaveFileFormat.MPP` preserves full compatibility with
      Microsoft Project.
  - name: Confirm success
    text: Print a short message or log entry so you know the operation completed without
      errors. This is especially useful in automated pipelines.
  type: HowTo
- questions:
  - answer: Yes, you can assign different currency settings to individual resources
      or tasks by modifying their respective cost fields after the project‑level currency
      is defined.
    question: Can I set multiple currencies in a single project using Aspose.Tasks?
  - answer: Absolutely. The library supports MPP files from Project 2000 up to the
      latest releases, as well as XML and other interchange formats.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project
      files?
  - answer: Yes, you can define custom symbols, decimal digits, and positioning to
      meet any regional requirement, and these settings are persisted in the saved
      file.
    question: Does Aspose.Tasks provide support for custom currency formats?
  - answer: Certainly. The API is pure Java, so it works seamlessly with Spring, Hibernate,
      Maven, Gradle, and other ecosystems.
    question: Can I integrate Aspose.Tasks with other Java frameworks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community assistance, or consult the official documentation for detailed API
      references.
    question: Where can I find additional help or examples?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- currency symbol
- Aspose.Tasks
- Java API
- Microsoft Project
- project cost formatting
title: How to change currency symbol in Aspose.Tasks projects – Java guide
url: /java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to change currency symbol in Aspose.Tasks – Java guide

## Introduction
In this tutorial you’ll learn **how to change currency symbol** for a Microsoft Project file using the Aspose.Tasks Java API. Whether you are preparing reports for an overseas client, consolidating budgets across multiple regions, or simply need to match your company’s accounting standards, adjusting the currency symbol ensures that every cost‑related field displays the correct monetary sign. The guide walks through every step, from setting up the development environment to persisting the changes in a new or existing project file.

## Quick answers
- **What library is required?** Aspose.Tasks for Java.  
- **Can I change the currency symbol?** Yes – set `Prj.CURRENCY_SYMBOL` and choose `CurrencySymbolPositionType`.  
- **Which file formats are supported?** XML, MPP, and many others via `SaveFileFormat`.  
- **Do I need a license for development?** A free trial works for testing; a license is required for production.  
- **How long does the implementation take?** About 5‑10 minutes for a basic setup.

## How to change currency symbol in Aspose.Tasks using Java?
Load the target project (or create a new one), set the desired currency properties, and save the file. The entire operation consists of three API calls: create or load a `Project` object, assign the currency code, symbol, and position, then invoke `project.save`. This approach works for both fresh projects and existing files without requiring Microsoft Project to be installed.

## Why use Aspose.Tasks to change currency?
Aspose.Tasks provides **full API coverage for 30+ currency‑related properties**, enabling you to define code, symbol, decimal digits, and positioning in one place. The library processes multi‑hundred‑page Project files in under a second on typical server hardware, and it works on Windows, Linux, and macOS without any additional dependencies.

## Prerequisites
Before you start, ensure you have:

1. **Java Development Kit (JDK) 8 or higher** – the API requires at least JDK 8.  
2. **Aspose.Tasks for Java** – download the latest JAR from the [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/).  
3. **An IDE** – Eclipse, IntelliJ IDEA, or any editor that supports Java.  
4. **A writable folder** – where the generated project file will be saved.

## Import packages
The following classes give you access to project properties, file handling, and currency settings.  

`Project` – represents a Microsoft Project file in memory.  
`Prj` – contains constants for all project‑level properties, including currency fields.  
`CurrencySymbolPositionType` – enumerates possible positions for the currency symbol (before or after the amount).  

These imports are required before any code can manipulate a project.

## Step‑by‑step guide

### Step 1: Define the data directory
Choose a folder that holds your source files and where the output will be written. Make sure the directory exists and your Java process has write permission.

### Step 2: Create a new project instance
`Project` class is Aspose.Tasks' top‑level object that represents a single Project file in memory. Instantiating it creates a blank project ready for configuration.

### Step 3: Set currency properties
Here you configure the currency code, number of decimal digits, the symbol itself, and the symbol’s position.  

- **Currency code** – a three‑letter ISO 4217 code such as `AUD` or `USD`.  
- **Decimal digits** – typically 2 for most currencies.  
- **Currency symbol** – the character or string displayed with amounts, e.g., `$` or `€`.  
- **Symbol position** – `CurrencySymbolPositionType.Before` places the symbol before the number; `After` places it after.

These settings affect every cost‑related field (resource rates, task budgets, etc.) in the project.

> **Pro tip:** If you need to change the currency for an existing file, load it with `new Project("file.mpp")` before applying the above settings.

### Step 4: Save the updated project
Write the project back to disk using the desired format. The XML format is human‑readable, while `SaveFileFormat.MPP` preserves full compatibility with Microsoft Project.

### Step 5: Confirm success
Print a short message or log entry so you know the operation completed without errors. This is especially useful in automated pipelines.

## Common issues & solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| **`NullPointerException` on `project.save`** | `dataDir` is not a valid path or lacks write permission. | Ensure the directory exists and your Java process has write access. |
| **Currency symbol not showing** | The symbol position is set incorrectly for your locale. | Use `CurrencySymbolPositionType.Before` if the symbol should precede the amount. |
| **Project file does not open in MS Project** | Saving in an older format with incompatible settings. | Save using `SaveFileFormat.MPP` for full compatibility with recent MS Project versions. |

## Frequently asked questions

**Q: Can I set multiple currencies in a single project using Aspose.Tasks?**  
A: Yes, you can assign different currency settings to individual resources or tasks by modifying their respective cost fields after the project‑level currency is defined.

**Q: Is Aspose.Tasks compatible with different versions of Microsoft Project files?**  
A: Absolutely. The library supports MPP files from Project 2000 up to the latest releases, as well as XML and other interchange formats.

**Q: Does Aspose.Tasks provide support for custom currency formats?**  
A: Yes, you can define custom symbols, decimal digits, and positioning to meet any regional requirement, and these settings are persisted in the saved file.

**Q: Can I integrate Aspose.Tasks with other Java frameworks?**  
A: Certainly. The API is pure Java, so it works seamlessly with Spring, Hibernate, Maven, Gradle, and other ecosystems.

**Q: Where can I find additional help or examples?**  
A: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for community assistance, or consult the official documentation for detailed API references.

## Conclusion
You now know **how to change currency symbol** in Aspose.Tasks projects using Java, how to set the currency code, adjust decimal digits, and apply a custom symbol. These capabilities let you generate locale‑specific cost reports, align project budgets with regional accounting standards, and keep your Microsoft Project files consistent across global teams.

---

**Last Updated:** 2026-09-09  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  








```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

```java
String dataDir = "Your Data Directory";
```

```java
Project project = new Project();
```

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

```java
System.out.println("Process completed Successfully");
```

## Related Tutorials

- [java project properties – Extract currency symbol from MPP using Aspose.Tasks for Java](/tasks/java/currency/currency-symbols/)
- [Read Currency Properties Java with Aspose.Tasks Projects](/tasks/java/currency-properties/read-properties/)
- [Manage Currency Codes Java with Aspose.Tasks](/tasks/java/currency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}