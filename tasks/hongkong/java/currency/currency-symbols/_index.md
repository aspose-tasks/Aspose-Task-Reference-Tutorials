---
date: 2026-02-10
description: 學習如何使用 Aspose.Tasks for Java 提取和更新 Java 專案屬性，例如貨幣符號。輕鬆變更專案貨幣並取得貨幣符號。
linktitle: Extract currency symbol mpp using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: Java 專案屬性 – 使用 Aspose.Tasks for Java 從 MPP 提取貨幣符號
url: /zh-hant/java/currency/currency-symbols/
weight: 12
---

Also the backtop button shortcode.

We need to ensure we keep markdown formatting.

Let's translate.

Traditional Chinese (Hong Kong) uses Traditional characters, but sometimes use specific terms like "程式", "檔案", etc. We'll translate naturally.

Let's produce final content.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks for Java 取得 MPP 檔案的貨幣符號

## Introduction
在本教學中，你將學會如何操作 **java project properties**——特別是如何從 Microsoft Project (MPP) 檔案中取得貨幣符號，以及如何使用 Aspose.Tasks 函式庫 **change currency symbol java** 或 **retrieve currency symbol java**。無論你是要建立報表工具、將 Project 資料整合至財務系統，或只是需要在 UI 上正確顯示貨幣符號，掌握這項雖小卻關鍵的工作，都能讓你的 Java 應用程式更健全、更友善使用者。

## Quick Answers
- **What does “extract currency symbol mpp” mean?** It means reading the currency symbol stored in an MPP (Microsoft Project) file.  
- **Which library handles this?** Aspose.Tasks for Java provides a simple API for the job.  
- **Do I need a license?** A free trial works for development; a commercial license is required for production.  
- **How long does it take?** With the code below, you can get the symbol in under a minute.  
- **Can I also change the symbol?** Yes – you can set a new value using the same `Prj.CURRENCY_SYMBOL` property.

## What is “extract currency symbol mpp”?
Microsoft Project stores the currency symbol (e.g., $, €, £) in the project file header. The **extract currency symbol mpp** operation reads that value so you can display or manipulate it programmatically.

## Why update currency symbol in java project properties?
Projects often span multiple regions. Being able to **change project currency** or **update currency symbol** at runtime lets you adapt reports, invoices, or dashboards to the local market without recreating the whole project file. This flexibility is a core part of managing java project properties effectively.

## Prerequisites
Before we dive in, make sure you have:

1. **Java Development Kit (JDK)** – version 8 or higher.  
2. **Aspose.Tasks for Java** – download the latest JAR from the [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/).  
3. A valid **project.mpp** file placed in a folder you can reference from your code.

## Import Packages
First, import the classes we’ll need to work with Project files.

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Step 1: Define the Data Directory
Tell the application where your *.mpp* file lives.

```java
String dataDir = "Your Data Directory";
```

> **Pro tip:** Use `System.getProperty("user.dir")` to build an absolute path that works on any machine.

## Step 2: Load the MS Project File
Create a `Project` object that represents the MPP file in memory.

```java
Project project = new Project(dataDir + "project.mpp");
```

## Step 3: Retrieve (and optionally change) the Currency Symbol
Now we **retrieve currency symbol java** by reading the `Prj.CURRENCY_SYMBOL` property. You can also **change currency symbol java** (or **change project currency**) by assigning a new string to the same property.

```java
// Retrieve the current currency symbol
System.out.println(project.get(Prj.CURRENCY_SYMBOL));

// Example of changing it (uncomment to use)
// project.set(Prj.CURRENCY_SYMBOL, "€");
// System.out.println("New symbol: " + project.get(Prj.CURRENCY_SYMBOL));
```

The `System.out.println` call prints the symbol (e.g., `$`) to the console, confirming that **the extraction succeeded**.

## Common Issues & How to Fix Them
| Symptom | Likely Cause | Solution |
|---------|--------------|----------|
| `NullPointerException` on `project.get(...)` | Wrong file path or file not found | Verify `dataDir` and file name; use `new File(dataDir).exists()` to debug |
| Unexpected symbol (e.g., `?`) | Project created with a non‑standard locale | Ensure the source MPP file actually defines a currency symbol; you can set one programmatically as shown above |
| License error | Using the trial without a valid license file | Load your license with `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` before creating the `Project` object |

## Frequently Asked Questions

**Q: Can I manipulate other project attributes besides currency symbols using Aspose.Tasks?**  
A: Yes, Aspose.Tasks lets you edit tasks, resources, assignments, calendars, and many more project properties.

**Q: Is Aspose.Tasks compatible with different versions of MS Project files?**  
A: Absolutely. It supports MPP, MPT, and XML formats from Project 98 up to the latest releases.

**Q: Does Aspose.Tasks offer documentation and support for developers?**  
A: Comprehensive API docs, code examples, and a dedicated support forum are available on the Aspose.Tasks website.

**Q: Can I try Aspose.Tasks before purchasing it?**  
A: Yes – a fully functional free trial can be downloaded from the [Aspose website](https://purchase.aspose.com/buy).

**Q: How can I obtain a temporary license for Aspose.Tasks?**  
A: Temporary licenses are provided on the [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/) for evaluation purposes.

---

**Last Updated:** 2026-02-10  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}