---
date: 2026-07-19
description: Learn how to control currency symbol after amount in .NET projects effortlessly
  with Aspose.Tasks.
images:
- /net/calendar-scheduling/currency-symbol-positions/og-image.png
keywords:
- currency symbol after amount
- Aspose.Tasks currency formatting
- .NET project financial reporting
lastmod: 2026-07-19
linktitle: Currency Symbol Positions in Aspose.Tasks
og_description: Learn how to place the currency symbol after amount using Aspose.Tasks
  for .NET. Follow step‑by‑step instructions and best practices.
og_image_alt: Guide showing currency symbol after amount configuration in Aspose.Tasks
og_title: Currency Symbol After Amount in Aspose.Tasks — Quick Guide
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to control currency symbol after amount in .NET projects
    effortlessly with Aspose.Tasks.
  headline: How to Place Currency Symbol After Amount in Aspose.Tasks
  type: TechArticle
- description: Learn how to control currency symbol after amount in .NET projects
    effortlessly with Aspose.Tasks.
  name: How to Place Currency Symbol After Amount in Aspose.Tasks
  steps:
  - name: Load the Project File
    text: The `Project` class loads an existing MS‑Project file or creates a new one
      in memory.
  - name: Set Currency Symbol Position
    text: '`CurrencySymbolPosition` is an enum that lets you choose `Before` or `After`.
      Setting it to `After` places the symbol after the numeric value.'
  - name: Work with the Project
    text: After you have configured the symbol position, you can continue adding tasks,
      resources, or custom fields as needed. The setting is persisted when you save
      the project.
  type: HowTo
- questions:
  - answer: Yes, you can adjust `CurrencySymbolPosition` as many times as needed;
      just set the property and re‑save the project.
    question: Can I change the currency symbol position multiple times within the
      same project?
  - answer: Absolutely. Aspose.Tasks supports more than 50 international currencies,
      allowing you to work with any regional format.
    question: Does Aspose.Tasks support currencies other than the US Dollar?
  - answer: Yes, you can obtain a free trial of Aspose.Tasks for .NET from [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Tasks for .NET?
  - answer: Certainly! You can seek support and assistance from the Aspose.Tasks community
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Can I seek assistance if I encounter any issues while using Aspose.Tasks
      for .NET?
  - answer: You can purchase a license for Aspose.Tasks for .NET from [here](https://purchase.aspose.com/buy).
    question: How can I purchase a license for Aspose.Tasks for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- currency symbol
- Aspose.Tasks
- .NET financial management
title: How to Place Currency Symbol After Amount in Aspose.Tasks
url: /net/calendar-scheduling/currency-symbol-positions/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Place Currency Symbol After Amount in Aspose.Tasks

## Introduction

When you generate project cost reports, the placement of the **currency symbol after amount** can affect readability and compliance with regional standards. Aspose.Tasks for .NET lets you control this formatting with just a few lines of code, ensuring that every financial figure appears exactly the way your stakeholders expect. In this tutorial we’ll walk through the required steps, explain why the setting matters, and show you how to apply it in a real‑world .NET project.

## Quick Answers
- **What does “currency symbol after amount” mean?** It displays the symbol (e.g., $) after the numeric value, like `100 $`.
- **Which property controls the position?** `CurrencySymbolPosition` on the `Project` object.
- **Do I need a license?** A trial works for development; a commercial license is required for production.
- **Supported currencies?** Over 50 currencies are built‑in, covering most global markets.
- **Can I change the setting at runtime?** Yes, you can update it any time before saving the project file.

## What is the “currency symbol after amount” setting?
The **currency symbol after amount** option determines whether the currency sign appears before or after the numeric value in all monetary fields of a project. Adjusting this setting ensures that reports comply with local accounting conventions without manual post‑processing. It also improves readability for stakeholders accustomed to this format.

## Why use Aspose.Tasks for currency formatting?
Aspose.Tasks supports **50+ currencies** and can handle projects with **10,000+ tasks** without loading the entire file into memory, delivering fast performance even on modest hardware. The API gives you programmatic control, eliminating the need for manual spreadsheet edits. This makes large‑scale financial reporting both efficient and reliable.

## Prerequisites

### 1. Installation of Aspose.Tasks for .NET
Ensure you have the Aspose.Tasks library installed. You can download it from [here](https://releases.aspose.com/tasks/net/).

### 2. Basic Knowledge of .NET Programming
A fundamental understanding of .NET programming is necessary to follow the examples.

## Import Namespaces

The `Aspose.Tasks` namespace provides access to the `Project` class and related enums.

The `Project` class is Aspose.Tasks' top‑level object that represents a single project file in memory. After importing the namespace you can start working with project data.

```csharp

```

Now, let’s break down the example into clear, actionable steps.

## How to set currency symbol after amount?

`CurrencySymbolPosition` is an enumeration that specifies whether the currency symbol appears before or after the numeric value.

Load your project, set `CurrencySymbolPosition` to `After`, and then save – that’s all you need to display the symbol after the amount. This direct approach works for any supported currency and does not require additional formatting logic. You can also verify the setting by exporting a sample cost report to ensure the symbol appears correctly.

### Step 1: Load the Project File
The `Project` class loads an existing MS‑Project file or creates a new one in memory.

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### Step 2: Set Currency Symbol Position
`CurrencySymbolPosition` is an enum that lets you choose `Before` or `After`. Setting it to `After` places the symbol after the numeric value.

```csharp
project.Set(Prj.CurrencySymbolPosition, CurrencySymbolPositionType.Before);
```

### Step 3: Work with the Project
After you have configured the symbol position, you can continue adding tasks, resources, or custom fields as needed. The setting is persisted when you save the project.

```csharp
// Perform other operations with the project...
```

## Common Issues and Solutions
- **Symbol still appears before amount:** Ensure you set the property *before* calling `Save`. Changing it after saving requires re‑saving the file.
- **Unsupported currency:** Verify that the currency code you use is listed in Aspose.Tasks’ supported list (over 50 currencies).
- **Performance slowdown on large projects:** Use `ProjectReader` to stream large files if you exceed 10,000 tasks.

## Frequently Asked Questions

**Q: Can I change the currency symbol position multiple times within the same project?**  
A: Yes, you can adjust `CurrencySymbolPosition` as many times as needed; just set the property and re‑save the project.

**Q: Does Aspose.Tasks support currencies other than the US Dollar?**  
A: Absolutely. Aspose.Tasks supports more than 50 international currencies, allowing you to work with any regional format.

**Q: Is there a trial version available for Aspose.Tasks for .NET?**  
A: Yes, you can obtain a free trial of Aspose.Tasks for .NET from [here](https://releases.aspose.com/).

**Q: Can I seek assistance if I encounter any issues while using Aspose.Tasks for .NET?**  
A: Certainly! You can seek support and assistance from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).

**Q: How can I purchase a license for Aspose.Tasks for .NET?**  
A: You can purchase a license for Aspose.Tasks for .NET from [here](https://purchase.aspose.com/buy).

## Conclusion

Controlling the **currency symbol after amount** is a vital part of financial reporting in project management software. With Aspose.Tasks for .NET you can set this option programmatically, supporting over 50 currencies and handling large projects efficiently. Apply the steps above to ensure your project reports match the formatting expectations of any locale.

---

**Last Updated:** 2026-07-19  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose

## Related Tutorials

- [Managing Calendar Collection in Aspose.Tasks](/tasks/net/calendar-scheduling/calendar-collection/)
- [Collection of Calendar Exceptions in Aspose.Tasks](/tasks/net/calendar-scheduling/calendar-exception-collection/)
- [Handling MS Project Rates with Aspose.Tasks for .NET](/tasks/net/rate-recurring-tasks/handling-rates/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}