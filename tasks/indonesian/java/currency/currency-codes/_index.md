---
date: 2025-12-09
description: Pelajari cara membaca file MS Project dan mengelola kode mata uang secara
  efisien menggunakan Aspose.Tasks untuk Java. Sederhanakan tugas manajemen proyek
  Anda dengan mudah.
linktitle: Manage Currency Codes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Cara membaca file MS Project dan mengelola kode mata uang dengan Aspose.Tasks
url: /id/java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara Membaca File MS Project dan Mengelola Kode Mata Uang dengan Aspose.Tasks

## Introduction
Welcome! In this tutorial you'll discover **how to read MS Project file** data and specifically **manage currency codes** using the Aspose.Tasks Java API. Whether you're generating reports, consolidating multi‑currency projects, or simply need to ensure the correct financial symbols appear, this guide walks you through every step— from setting up your environment to retrieving the currency code programmatically. By the end, you’ll be comfortable reading MS Project files and extracting the currency information you need.

## Quick Answers
- **Apa yang dilakukan API?** It reads MS Project files and exposes properties such as currency code.  
- **Bahasa apa yang digunakan?** Java, via the Aspose.Tasks for Java library.  
- **Apakah saya memerlukan lisensi?** A free trial works for development; a commercial license is required for production.  
- **Bisakah saya mengambil kode dalam satu baris?** Yes—`prj.get(Prj.CURRENCY_CODE)` returns the currency code string.  
- **Apakah kompatibel dengan semua versi Project?** Aspose.Tasks supports both older (MPP) and newer (XML, XER) formats.

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

### Step 4: (Optional) Use the Currency Code
You might want to apply the retrieved code elsewhere—such as formatting cost values in a custom report or passing it to a financial API. Here’s a quick illustration (no additional code block needed):
- Store the code in a variable.  
- Use it when constructing monetary strings.  
- Pass it to downstream services that require a currency identifier.

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| **Output null** | Project file does not define a currency (default is empty). | Set the currency in Microsoft Project or assign it via `prj.set(Prj.CURRENCY_CODE, "USD");` before reading. |
| **File tidak ditemukan** | Incorrect `dataDir` path. | Verify the path and ensure the file name matches exactly, including case sensitivity. |
| **Versi file tidak didukung** | Very old or corrupted *.mpp* file. | Use the latest Aspose.Tasks version or convert the file to a newer format in Microsoft Project first. |

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

**Last Updated:** 2025-12-09  
**Tested With:** Aspose.Tasks for Java (latest version)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
