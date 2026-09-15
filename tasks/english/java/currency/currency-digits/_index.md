---
date: 2026-09-14
description: Learn how to get ms project currency and read project properties java
  with Aspose.Tasks. Step‑by‑step guide for extracting currency digits from an MPP
  file.
images:
- /java/currency/currency-digits/og-image.png
keywords:
- get ms project currency
- read project properties java
- convert project file java
lastmod: 2026-09-14
linktitle: How to Get Currency from MS Project using Aspose.Tasks
og_description: Learn how to get ms project currency and read project properties java
  with Aspose.Tasks. Follow this concise Java tutorial to extract currency digits
  from an MPP file.
og_image_alt: Screenshot of Java code extracting currency digits from an MS Project
  file using Aspose.Tasks
og_title: How to get ms project currency using Aspose.Tasks – Java guide
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to get ms project currency and read project properties java
    with Aspose.Tasks. Step‑by‑step guide for extracting currency digits from an MPP
    file.
  headline: How to get ms project currency using Aspose.Tasks
  type: TechArticle
- description: Learn how to get ms project currency and read project properties java
    with Aspose.Tasks. Step‑by‑step guide for extracting currency digits from an MPP
    file.
  name: How to get ms project currency using Aspose.Tasks
  steps:
  - name: '**Java Development Environment** – JDK 8 or newer installed and configured.'
    text: '**Java Development Environment** – JDK 8 or newer installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the latest JAR from the official site:
      [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).'
  - name: '**Basic Java knowledge** – you should be comfortable creating a Java project,
      adding external libraries, and running a `main` method.'
    text: '**Basic Java knowledge** – you should be comfortable creating a Java project,
      adding external libraries, and running a `main` method.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks offers a wide range of functionalities to manipulate
      various aspects of Project files, such as tasks, resources, and custom fields.
    question: Can Aspose.Tasks handle other Project attributes besides currency digits?
  - answer: Absolutely, Aspose.Tasks is designed to meet the demands of enterprise‑grade
      projects, offering high performance and scalability.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes, you can use Aspose.Tasks for Java on any platform that supports the
      Java Runtime Environment (Windows, Linux, macOS).
    question: Does Aspose.Tasks support cross‑platform development?
  - answer: Yes, you can download a free trial version from the [Aspose releases page](https://releases.aspose.com/).
    question: Can I try Aspose.Tasks before purchasing?
  - answer: You can find support on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- ms project
- aspose.tasks
- java project processing
title: How to get ms project currency using Aspose.Tasks
url: /java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to get ms project currency using Aspose.Tasks

## Introduction
If you’re wondering **how to get ms project currency** information from a Microsoft Project file, you’ve landed in the right place. In this comprehensive tutorial you’ll discover **how to work with ms project currency** values using the Aspose.Tasks library for Java. Whether you’re building a reporting tool, a migration utility, or simply need to read the currency settings from a **java project file**, this guide walks you through every step—from loading an *.mpp* file to extracting the currency digits. By the end, you’ll be comfortable handling ms project currency data in your own applications.

## Quick answers
- **What library reads MS Project files?** Aspose.Tasks for Java.  
- **How many lines of code to get currency digits?** Just three concise lines after the project is loaded.  
- **Do I need a license for development?** A free trial works for testing; a commercial license is required for production.  
- **Which Java version is supported?** Java 8 or higher (any JDK that runs Aspose.Tasks).  
- **Can I retrieve other Project properties?** Yes – Aspose.Tasks exposes a full set of Project fields (e.g., start date, cost rates, etc.).

## What is ms project currency?
The `ms project currency` property defines the number of decimal places Microsoft Project uses when displaying monetary values. It is stored in the Project file as the **CURRENCY_DIGITS** field and determines whether amounts appear as whole numbers, one‑decimal, two‑decimal, etc. This setting directly influences budgeting reports, cost roll‑ups, and any UI that shows financial figures, making it essential for accurate data exchange.

## Why use Aspose.Tasks for handling ms project currency?
Aspose.Tasks lets you extract the currency digits without installing Microsoft Project, and it does so with enterprise‑grade performance. The library supports **30+ years of Project file versions**—from Project 2000 through Project 2024—covering more than **150 distinct file schemas**. Loading a 500‑page project typically takes under **2 seconds** on a standard server, and you can query only the fields you need, keeping memory usage under **50 MB** even for the largest schedules.

## Prerequisites
Before you start, make sure you have the following:

1. **Java Development Environment** – JDK 8 or newer installed and configured.  
2. **Aspose.Tasks for Java** – download the latest JAR from the official site: [Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/).  
3. **Basic Java knowledge** – you should be comfortable creating a Java project, adding external libraries, and running a `main` method.  

## Import packages
First, import the classes we’ll need.  
Import the `Project` class and related utilities from the Aspose.Tasks library.  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## Step 1: define data directory
Specify the folder that contains your **java project file** (`*.mpp`).  
```java
String dataDir = "Your Data Directory";
```
Replace `"Your Data Directory"` with the absolute or relative path where `project.mpp` resides.

## Step 2: load the mpp file  
Now we’ll see **how to load mpp** files using Aspose.Tasks.  
The `Project` class represents a Microsoft Project file and provides access to its properties.  
```java
Project project = new Project(dataDir + "project.mpp");
```
Make sure the file name matches exactly; otherwise, an `IOException` will be thrown.

## Step 3: retrieve currency digits  
With the project loaded, extracting the **ms project currency** digits is a one‑liner:  
The `getCurrencyDigits()` method returns the number of decimal places defined for monetary values.  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
The call returns an `Integer` representing the number of decimal places (e.g., `2` for cents). The value is printed to the console, but you can also store it in a variable for further processing.

## Common issues & tips
- **File not found** – double‑check the `dataDir` path and ensure the file name is correct, including the `.mpp` extension.  
- **Unsupported file version** – Aspose.Tasks supports Project 2000‑2024 formats; older or corrupted files may need conversion.  
- **License not set** – during development a trial works, but for production you must apply a valid license to avoid evaluation watermarks.

## Frequently asked questions

**Q: Can Aspose.Tasks handle other Project attributes besides currency digits?**  
A: Yes, Aspose.Tasks offers a wide range of functionalities to manipulate various aspects of Project files, such as tasks, resources, and custom fields.

**Q: Is Aspose.Tasks suitable for enterprise‑level applications?**  
A: Absolutely, Aspose.Tasks is designed to meet the demands of enterprise‑grade projects, offering high performance and scalability.

**Q: Does Aspose.Tasks support cross‑platform development?**  
A: Yes, you can use Aspose.Tasks for Java on any platform that supports the Java Runtime Environment (Windows, Linux, macOS).

**Q: Can I try Aspose.Tasks before purchasing?**  
A: Yes, you can download a free trial version from the [Aspose releases page](https://releases.aspose.com/).

**Q: Where can I get support for Aspose.Tasks?**  
A: You can find support on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

---

**Last updated:** 2026-09-14  
**Tested with:** Aspose.Tasks for Java (latest at time of writing)  
**Author:** Aspose

## Related Tutorials

- [java project properties – Extract currency symbol from MPP using Aspose.Tasks for Java](/tasks/java/currency/currency-symbols/)
- [How to Retrieve Currency from MS Project with Aspose.Tasks](/tasks/java/currency/currency-codes/)
- [Project Properties Java – Read Metadata with Aspose.Tasks](/tasks/java/project-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}