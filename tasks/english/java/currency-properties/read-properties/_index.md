---
title: "Read Currency Properties Java with Aspose.Tasks Projects"
linktitle: "Read Currency Properties Java with Aspose.Tasks Projects"
second_title: "Aspose.Tasks Java API"
description: "Learn how to read currency properties Java from MS Project files using Aspose.Tasks for Java. Follow this step‑by‑step guide to extract currency code, symbol, digits and position programmatically."
weight: 10
url: /java/currency-properties/read-properties/
date: 2025-12-04
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Read Currency Properties Java with Aspose.Tasks Projects

## Introduction
In this tutorial you'll **read currency properties Java** from Microsoft Project files using the Aspose.Tasks for Java API. Aspose.Tasks lets you work with .mpp files without having Microsoft Project installed, making it ideal for automated reporting, data migration, or integration into Java‑based enterprise applications. By the end of this guide, you’ll be able to extract the currency code, symbol, number of decimal digits, and symbol position directly from a project file.

## Quick Answers
- **What does “read currency properties java” mean?** It refers to retrieving currency‑related metadata (code, symbol, digits, position) from an MS Project file using Java code.  
- **Do I need a license to try this?** A free trial of Aspose.Tasks is available; a commercial license is required for production use.  
- **Which JDK version is required?** Java 8 or higher.  
- **Can I modify the currency settings after reading them?** Yes, Aspose.Tasks allows both read and write operations on currency properties.  
- **Is this compatible with all .mpp versions?** The API supports files created with Microsoft Project 2003‑2021.

## What is read currency properties java?
Reading currency properties in Java means accessing the project‑level settings that define how monetary values are displayed in a Microsoft Project file. These settings include the ISO currency code (e.g., **USD**), the symbol (**$**), the number of decimal digits, and whether the symbol appears before or after the amount.

## Why read currency properties java with Aspose.Tasks?
- **No Microsoft Project installation needed** – the API works on any platform that supports Java.  
- **Fast, in‑process extraction** – ideal for batch processing large numbers of project files.  
- **Full control** – you can combine the retrieved values with custom reporting or integrate them into ERP systems.  
- **Cross‑version support** – works with .mpp files from Project 2003 up to the latest 2021 release.

## Prerequisites
Before you start, make sure you have:

1. **Java Development Kit (JDK)** – Java 8 or newer installed and configured in your `PATH`.  
2. **Aspose.Tasks for Java JAR** – download the latest library from [here](https://releases.aspose.com/tasks/java/) and add it to your project’s classpath.  

## Import Packages
Begin by importing the Aspose.Tasks namespace required for project manipulation:

```java
import com.aspose.tasks.*;
```

## Step 1: Set Up Your Project Directory
Define the folder that contains the `.mpp` file you want to analyze. Keeping the path in a variable makes the code reusable:

```java
String dataDir = "Your Data Directory";
```

*Replace `"Your Data Directory"` with the absolute or relative path to the folder where `project.mpp` resides.*

## Step 2: Create a Project Reader Instance
Load the Microsoft Project file into a `Project` object. This object gives you access to all project properties, including currency settings:

```java
Project project = new Project(dataDir + "project.mpp");
```

*If your file has a different name, change `"project.mpp"` accordingly.*

## Step 3: Display Currency Properties
Now retrieve each currency attribute using the `Prj` enumeration and print the results to the console. The API returns objects that you can convert to strings for display:

```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position : " + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```

**What you’ll see:**  
- **Currency Code** – ISO‑4217 code such as `USD`, `EUR`, `JPY`.  
- **Currency Digits** – usually `2` for most currencies, `0` for Japanese Yen.  
- **Currency Symbol** – the character shown in reports (`$`, `€`, `¥`).  
- **Currency Symbol Position** – `0` for **before** the amount, `1` for **after**.

## Step 4: Process Completion
Signal that the extraction finished successfully. This simple message is helpful when the code runs as part of a larger batch job:

```java
System.out.println("Process completed Successfully");
```

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **FileNotFoundException** | `dataDir` path is incorrect or the file name is misspelled. | Verify the directory string and ensure the `.mpp` file exists at the specified location. |
| **NullPointerException on `project.get(...)`** | The project file does not contain currency information (unlikely) or the property key is wrong. | Use `project.contains(Prj.CURRENCY_CODE)` to check existence before reading. |
| **LicenseException** | Running without a valid Aspose.Tasks license in a production environment. | Apply a license file using `License license = new License(); license.setLicense("Aspose.Tasks.lic");` before creating the `Project` object. |

## Frequently Asked Questions

**Q: Is Aspose.Tasks compatible with all versions of Microsoft Project?**  
A: Aspose.Tasks supports .mpp files generated by Microsoft Project 2003‑2021, covering both older and the latest formats.

**Q: Can I modify currency properties using Aspose.Tasks?**  
A: Yes, you can both read and write currency settings. Use `project.set(Prj.CURRENCY_CODE, "EUR");` and then save the project.

**Q: Is Aspose.Tasks suitable for commercial use?**  
A: Absolutely. It is a commercial library; you can purchase a license [here](https://purchase.aspose.com/buy).

**Q: Does Aspose.Tasks offer a free trial?**  
A: Yes, a fully functional trial is available from [here](https://releases.aspose.com/).

**Q: Where can I seek help or support for Aspose.Tasks?**  
A: The official Aspose.Tasks forum is the best place for assistance – visit it [here](https://forum.aspose.com/c/tasks/15).

## Conclusion
You’ve now learned how to **read currency properties java** from an MS Project file using Aspose.Tasks for Java. This capability enables you to incorporate currency metadata into custom reports, financial analyses, or integration pipelines without relying on Microsoft Project itself. Feel free to experiment with modifying the properties or combining this data with other project attributes to build richer solutions.

---

**Last Updated:** 2025-12-04  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}