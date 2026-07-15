---
date: 2026-02-10
description: Узнайте, как извлекать коды валют из файлов MS Project с помощью Aspose.Tasks
  for Java — быстрый способ получить код валюты, необходимый Java‑разработчикам.
linktitle: Manage Currency Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Как получить валюту из MS Project с помощью Aspose.Tasks
url: /ru/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как получить валюту из MS Project с помощью Aspise.Tasks

## Introduction
Welcome! In this tutorial you'll discover **how to retrieve currency** codes from an MS Project file using the Aspose.Tasks Java API. Whether you're generating multi‑currency financial reports, consolidating projects from different regions, or simply need the correct monetary symbols for downstream processing, this guide walks you through every step—from setting up your environment to extracting the currency code programmatically. By the end, you’ll be comfortable reading MS Project files and using the **get currency code java** call to obtain the ISO currency identifier.

## Quick Answers
- **What does the API do?** It reads MS Project files and exposes properties such as currency code.  
- **Which language is used?** Java, via the Aspose.Tasks for Java library.  
- **Do I need a license?** A free trial works for development; a commercial license is required for production.  
- **Can I retrieve the code in one line?** Yes—`prj.get(Prj.CURRENCY_CODE)` returns the currency code string.  
- **Is it compatible with all Project versions?** Aspose.Tasks supports both older (MPP) and newer (XML, XER) formats.

## What is **read ms project file**?
Reading an MS Project file means programmatically opening a *.mpp* (or other supported) project document and accessing its data structures—tasks, resources, calendars, and financial settings—without manual interaction with Microsoft Project itself.

## Why use Aspose.Tasks to **read msproject** files?
- **Full format support** – works with files from Project 98 through the latest Office releases.  
- **No COM or Office installation needed** – pure Java, perfect for server‑side automation.  
- **Rich API** – gives direct access to properties like `Prj.CURRENCY_CODE`, allowing you to **how to retrieve currency** information instantly.  
- **Performance** – lightweight parsing, ideal for batch processing of many projects.

## Prerequisites
Before we dive into the code, ensure you have the following:

### Java Development Kit (JDK) Installed
Make sure a recent JDK is available on your machine. You can download and install the latest JDK version from [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Aspose.Tasks for Java Library
Download and set up the Aspose.Tasks for Java library. Detailed documentation and the latest binaries are available [here](https://reference.aspose.com/tasks/java/).

## Import Packages
To get started, let's import the necessary packages in your Java project:
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Step‑by‑step guide

### Step 1: Set Up Data Directory
Define the folder that contains your *.mpp* file. Adjust the path to match your environment.
```java
String dataDir = "Your Data Directory";
```

### Step 2: Load the Project File
Create a `Project` instance by loading the MS Project file. This is the point where you **read msproject** data into memory.
```java
Project prj = new Project(dataDir + "project.mpp");
```

### Step 3: Retrieve Currency Code
Now that the project is loaded, you can **how to retrieve currency** information with a single call. This demonstrates **get currency code java** usage.
```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
The output will be the three‑letter ISO currency code (e.g., `USD`, `EUR`, `GBP`) that the project is configured to use.

### Step 4: How to Retrieve Currency Code in Java (Additional Context)
If you need to store the value for later use, simply assign it to a variable:

*No extra code block is required* – just keep the string returned by `prj.get(Prj.CURRENCY_CODE)` and pass it to any financial service, reporting engine, or UI component.

### Step 5: (Optional) Use the Currency Code
You might want to apply the retrieved code elsewhere—such as formatting cost values in a custom report or passing it to a financial API. Typical scenarios include:

- **Report generation** – prepend the code to cost columns (`USD 1,200`).
- **API integration** – send the ISO code to payment gateways that require a currency identifier.
- **Data consolidation** – group multiple projects by currency for portfolio analysis.

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| **Null output** | Project file does not define a currency (default is empty). | Set the currency in Microsoft Project or assign it via `prj.set(Prj.CURRENCY_CODE, "USD");` before reading. |
| **File not found** | Incorrect `dataDir` path. | Verify the path and ensure the file name matches exactly, including case sensitivity. |
| **Unsupported file version** | Very old or corrupted *.mpp* file. | Use the latest Aspose.Tasks version or convert the file to a newer format in Microsoft Project first. |

## Frequently Asked Questions

**Q: Can Aspose.Tasks handle complex project structures?**  
A: Yes, the API can read and manipulate multi‑level task hierarchies, resource pools, and custom fields without issue.

**Q: Is Aspose.Tasks compatible with different versions of MS Project files?**  
A: Absolutely. It supports MPP, XML, XER, and other formats across many Microsoft Project releases.

**Q: Does Aspose.Tasks provide documentation and support?**  
A: Comprehensive documentation, code examples, and dedicated support are available on the Aspose website.

**Q: Can I try Aspose.Tasks before purchasing?**  
A: A free trial is offered so you can evaluate all features, including reading currency codes.

**Q: Where can I get temporary licenses for Aspose.Tasks?**  
A: Temporary licenses can be obtained from the [website](https://purchase.aspose.com/temporary-license/) for short‑term evaluation.

---

**Last Updated:** 2026-02-10  
**Tested With:** Aspose.Tasks for Java (latest version)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}