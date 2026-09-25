---
date: 2026-09-25
description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
  for Java – the quick way to get currency code Java developers need.
images:
- /java/currency/currency-codes/og-image.png
keywords:
- retrieve currency code java
- Aspose.Tasks Java
- MS Project currency
- read MS Project file
lastmod: 2026-09-25
linktitle: Manage Currency Codes in Aspose.Tasks
og_description: Retrieve currency code java from MS Project files using Aspose.Tasks.
  This guide shows you how to read the project, extract the ISO currency identifier,
  and apply it in Java applications.
og_image_alt: Screenshot of Java code extracting currency code from an MS Project
  file using Aspose.Tasks
og_title: Retrieve currency code java from MS Project
schemas:
- author: Aspose
  dateModified: '2026-09-25'
  description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  headline: Retrieve currency code java from MS Project with Aspose.Tasks
  type: TechArticle
- description: Learn how to retrieve currency codes from MS Project files using Aspose.Tasks
    for Java – the quick way to get currency code Java developers need.
  name: Retrieve currency code java from MS Project with Aspose.Tasks
  steps:
  - name: set up data directory
    text: Define the folder that contains your *.mpp* file. Adjust the path to match
      your environment so the runtime can locate the project file.
  - name: load the project file
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single MS Project file in memory. Creating an instance reads the file and builds
      an in‑memory model you can query.
  - name: retrieve currency code
    text: The `Prj.CURRENCY_CODE` constant identifies the property that stores the
      ISO currency identifier. Calling `prj.get(Prj.CURRENCY_CODE)` returns the three‑letter
      code in a single operation. The output will be the three‑letter ISO currency
      code (e.g., `USD`, `EUR`, `GBP`) that the project is configured
  - name: how to retrieve currency code in Java (additional context)
    text: Load your project, call `prj.get(Prj.CURRENCY_CODE)`, and store the result
      in a `String`. You can then pass this value to any financial service, reporting
      engine, or UI component that requires a currency identifier.
  - name: (optional) use the currency code
    text: 'Typical downstream scenarios include: - **Report generation** – prepend
      the code to cost columns (`USD 1,200`). - **API integration** – send the ISO
      code to payment gateways that demand a currency parameter. - **Data consolidation**
      – group multiple projects by currency for portfolio‑level analysis.'
  type: HowTo
- questions:
  - answer: Yes, the API reads multi‑level task hierarchies, resource pools, custom
      fields, and calendars without limitation.
    question: Can Aspose.Tasks handle complex project structures?
  - answer: Absolutely. It supports MPP, XML, XER, and other formats from Project
      98 through the latest Office releases.
    question: Is Aspose.Tasks compatible with different versions of MS Project files?
  - answer: Comprehensive API reference, code examples, and dedicated technical support
      are available on the Aspose website.
    question: Does Aspose.Tasks provide documentation and support?
  - answer: A free trial is offered so you can evaluate all features, including currency
      code extraction.
    question: Can I try Aspose.Tasks before purchasing?
  - answer: Temporary licenses are available from the [website](https://purchase.aspose.com/temporary-license/).
    question: Where can I obtain a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- retrieve currency
- Aspose.Tasks
- Java project automation
- MS Project
title: Retrieve currency code java from MS Project with Aspose.Tasks
url: /java/currency/currency-codes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Retrieve currency code java from MS Project with Aspose.Tasks

## Introduction
In this tutorial you’ll learn **how to retrieve currency code java** from an MS Project file by using the Aspose.Tasks Java API. Whether you need to generate multi‑currency financial reports, consolidate projects across different regions, or simply display the correct monetary symbol in a downstream system, the steps below will take you from environment setup to the single‑line call that returns the ISO currency identifier. By the end of the guide you’ll be comfortable loading any supported Project file format and extracting the three‑letter currency code such as `USD`, `EUR`, or `GBP`.

## Quick answers
- **What does the API do?** It reads MS Project files and exposes properties such as the currency code.  
- **Which language is used?** Java, via the Aspose.Tasks for Java library.  
- **Do I need a license?** A free trial works for development; a commercial license is required for production.  
- **Can I retrieve the code in one line?** Yes—`prj.get(Prj.CURRENCY_CODE)` returns the currency code string instantly.  
- **Is it compatible with all Project versions?** Aspose.Tasks supports more than 20 input formats, including legacy MPP, XML, and XER files.

## What is read ms project file?
Reading an MS Project file means programmatically opening a *.mpp* (or any other supported format such as XML or XER) and accessing its internal data structures. These structures include tasks, resources, calendars, cost tables and financial settings. By parsing the file you can extract information without launching Microsoft Project, enabling automated reporting, migration, and integration workflows.

## Why use Aspose.Tasks to read msproject files?
Aspose.Tasks offers a pure‑Java solution that removes the need for COM interop or a local Microsoft Project installation. It supports more than 20 file formats, can handle projects with thousands of tasks while using under 100 MB of memory, and provides a rich object model. Direct access to constants like `Prj.CURRENCY_CODE` lets you retrieve currency information instantly and reliably.

## Prerequisites
Before we dive into the code, ensure you have the following:

### Java development kit (JDK) installed
A recent JDK (11 or later) is required. Download it from the official Oracle site: [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Aspose.Tasks for Java library
Obtain the latest Aspose.Tasks for Java binaries and add them to your project’s classpath. The full documentation and download links are available [here](https://reference.aspose.com/tasks/java/).

## Import packages
The `Project` class and the `Prj` constants live in the `com.aspose.tasks` namespace. Import them at the top of your Java source file:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## Step‑by‑step guide

### Step 1: set up data directory
Define the folder that contains your *.mpp* file. Adjust the path to match your environment so the runtime can locate the project file.

```java
String dataDir = "Your Data Directory";
```

### Step 2: load the project file
The `Project` class is Aspose.Tasks' top‑level object that represents a single MS Project file in memory. Creating an instance reads the file and builds an in‑memory model you can query.

```java
Project prj = new Project(dataDir + "project.mpp");
```

### Step 3: retrieve currency code
The `Prj.CURRENCY_CODE` constant identifies the property that stores the ISO currency identifier. Calling `prj.get(Prj.CURRENCY_CODE)` returns the three‑letter code in a single operation.

```java
System.out.println(prj.get(Prj.CURRENCY_CODE));
```
The output will be the three‑letter ISO currency code (e.g., `USD`, `EUR`, `GBP`) that the project is configured to use.

### Step 4: how to retrieve currency code in Java (additional context)
Load your project, call `prj.get(Prj.CURRENCY_CODE)`, and store the result in a `String`. You can then pass this value to any financial service, reporting engine, or UI component that requires a currency identifier.

### Step 5: (optional) use the currency code
Typical downstream scenarios include:

- **Report generation** – prepend the code to cost columns (`USD 1,200`).  
- **API integration** – send the ISO code to payment gateways that demand a currency parameter.  
- **Data consolidation** – group multiple projects by currency for portfolio‑level analysis.

## Common issues and solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| **Null output** | Project file does not define a currency (default is empty). | Set the currency in Microsoft Project or assign it via `prj.set(Prj.CURRENCY_CODE, "USD");` before reading. |
| **File not found** | Incorrect `dataDir` path. | Verify the path and ensure the file name matches exactly, including case sensitivity. |
| **Unsupported file version** | Very old or corrupted *.mpp* file. | Upgrade to the latest Aspose.Tasks version or convert the file to a newer format in Microsoft Project first. |

## Frequently asked questions

**Q: Can Aspose.Tasks handle complex project structures?**  
A: Yes, the API reads multi‑level task hierarchies, resource pools, custom fields, and calendars without limitation.

**Q: Is Aspose.Tasks compatible with different versions of MS Project files?**  
A: Absolutely. It supports MPP, XML, XER, and other formats from Project 98 through the latest Office releases.

**Q: Does Aspose.Tasks provide documentation and support?**  
A: Comprehensive API reference, code examples, and dedicated technical support are available on the Aspose website.

**Q: Can I try Aspose.Tasks before purchasing?**  
A: A free trial is offered so you can evaluate all features, including currency code extraction.

**Q: Where can I obtain a temporary license for evaluation?**  
A: Temporary licenses are available from the [website](https://purchase.aspose.com/temporary-license/).

---

**Last Updated:** 2026-09-25  
**Tested with:** Aspose.Tasks for Java (latest version)  
**Author:** Aspose

## Related Tutorials

- [Project Properties Java – Read Metadata with Aspose.Tasks](/tasks/java/project-properties/)
- [How to Read Project Information from Microsoft Project with Aspose.Tasks for Java](/tasks/java/project-properties/read-project-info/)
- [Retrieve MS Project Outline Codes in Aspose.Tasks](/tasks/java/project-file-operations/retrieve-outline-codes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}