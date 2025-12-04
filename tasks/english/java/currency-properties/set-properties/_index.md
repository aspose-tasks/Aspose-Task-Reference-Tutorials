---
title: "How to Set Currency in Aspose.Tasks Projects – Java Guide"
linktitle: Set Currency Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
description: "Learn how to set currency in Aspose.Tasks Java projects, including how to change currency and change currency symbol Java. Manipulate Microsoft Project files effortlessly."
weight: 11
url: /java/currency-properties/set-properties/
date: 2025-12-04
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Set Currency in Aspose.Tasks Projects – Java Guide

## Introduction
In this tutorial you’ll learn **how to set currency** for a Microsoft Project file using the Aspose.Tasks Java API. Whether you need to *change currency* for international teams or adjust the *currency symbol* in Java, the steps below will walk you through the process with clear explanations and ready‑to‑run code.

## Quick Answers
- **What library is required?** Aspose.Tasks for Java.  
- **Can I change the currency symbol?** Yes – use `CurrencySymbolPositionType` and `Prj.CURRENCY_SYMBOL`.  
- **Which file formats are supported?** XML, MPP, and many others via `SaveFileFormat`.  
- **Do I need a license for development?** A free trial works for testing; a license is required for production.  
- **How long does the implementation take?** About 5‑10 minutes for a basic setup.

## What is “currency” in a Project file?
A Project’s currency defines how cost values are displayed—code (e.g., `AUD`), number of decimal digits, symbol (`$`), and the symbol’s position. Setting these properties ensures that every cost‑related field (resource rates, task budgets, etc.) reflects the correct monetary format for your audience.

## Why use Aspose.Tasks to change currency?
- **No Microsoft Project installation needed** – manipulate files on any server.  
- **Full API coverage** – all currency‑related fields are exposed through `Prj` constants.  
- **Cross‑platform** – works on Windows, Linux, and macOS with any Java‑compatible IDE.  
- **High performance** – process large project files quickly and reliably.

## Prerequisites
Before you start, make sure you have:

1. **Java Development Kit (JDK)** – version 8 or higher.  
2. **Aspose.Tasks for Java** – download the latest JAR from the [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/).  
3. **An IDE** – Eclipse, IntelliJ IDEA, or any editor you prefer.  
4. **A writeable folder** – where the generated project file will be saved.

## Import Packages
First, import the classes that provide access to project properties and file handling.

```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Step‑by‑Step Guide

### Step 1: Define the Data Directory
Specify the folder that contains your source files and where the output will be written.

```java
String dataDir = "Your Data Directory";
```

### Step 2: Create a New Project Instance
Instantiate a fresh `Project` object. This object represents an in‑memory Microsoft Project file.

```java
Project project = new Project();
```

### Step 3: Set Currency Properties
Here’s where we **how to set currency** details such as code, digits, symbol, and symbol position.

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

> **Pro tip:** If you need to **change currency** for an existing project, simply load the file with `new Project("file.mpp")` before applying the above settings.

### Step 4: Save the Updated Project
Write the project back to disk in the desired format. In this example we use the XML format, but you can also choose `SaveFileFormat.MPP`.

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### Step 5: Confirm Success
Print a friendly message so you know the operation completed without errors.

```java
System.out.println("Process completed Successfully");
```

## Common Issues & Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| **`NullPointerException` on `project.save`** | `dataDir` is not a valid path or lacks write permission. | Ensure the directory exists and your Java process has write access. |
| **Currency symbol not showing** | The symbol position is set incorrectly for your locale. | Use `CurrencySymbolPositionType.Before` if the symbol should precede the amount. |
| **Project file does not open in MS Project** | Saving in an older format with incompatible settings. | Save using `SaveFileFormat.MPP` for full compatibility with recent MS Project versions. |

## Frequently Asked Questions

**Q: Can I set multiple currencies in a single project using Aspose.Tasks?**  
A: Yes, Aspose.Tasks allows you to handle multiple currencies within a single project file by setting currency properties on a per‑resource or per‑task basis.

**Q: Is Aspose.Tasks compatible with different versions of Microsoft Project files?**  
A: Absolutely. The library supports MPP files from Project 2000 up to the latest releases, as well as XML and other formats.

**Q: Does Aspose.Tasks provide support for custom currency formats?**  
A: Yes, you can define custom symbols, decimal digits, and positioning to meet any regional requirement.

**Q: Can I integrate Aspose.Tasks with other Java libraries or frameworks?**  
A: Certainly. The API is pure Java, so it works seamlessly with Spring, Hibernate, Maven, Gradle, and other ecosystems.

**Q: Where can I find additional support or assistance for Aspose.Tasks?**  
A: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for community help, or consult the official documentation for detailed API references.

## Conclusion
You now know **how to set currency**, how to **change currency** values, and how to **change currency symbol Java**‑style using Aspose.Tasks for Java. These capabilities let you tailor cost data for global teams, generate locale‑specific reports, and keep your project files consistent across borders.

---

**Last Updated:** 2025-12-04  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}