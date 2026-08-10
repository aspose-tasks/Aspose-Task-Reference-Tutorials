---
date: 2026-07-19
description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
  code, prerequisites, and FAQs.
images:
- /net/calendar-scheduling/custom-field-types/og-image.png
keywords:
- how to add custom field
- add custom field to project
- define extended attribute
lastmod: 2026-07-19
linktitle: Custom Field Types in Aspose.Tasks
og_description: Learn how to add custom field types in Aspose.Tasks for .NET. Follow
  this step‑by‑step guide to create, define, and use extended attributes efficiently.
og_image_alt: Guide showing how to add custom field types in Aspose.Tasks using .NET
og_title: How to Add Custom Field Types in Aspose.Tasks for .NET
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  headline: How to Add Custom Field Types in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  name: How to Add Custom Field Types in Aspose.Tasks for .NET
  steps:
  - name: Create Project Object
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Project
      file in memory. Instantiating it loads the file and gives you access to tasks,
      resources, and extended attributes.'
  - name: Define Custom Field
    text: '`ExtendedAttributeDefinition` describes a new column. In this example we
      create a **Text** type custom field for tasks and give it the alias “MyText”.
      The `ExtendedAttributeTask.Text1` enum value tells Aspose.Tasks where to store
      the value.'
  - name: Add Custom Field Definition to Project
    text: The project’s `ExtendedAttributes` collection holds all custom field definitions.
      Adding the definition makes it available for every task in the project.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks works with .NET Framework, .NET Core, and .NET 5/6/7.
    question: Can I use Aspose.Tasks with other .NET frameworks?
  - answer: Absolutely. It supports processing of projects with **up to 10,000 tasks**
      and can run in multi‑threaded server environments.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes—Aspose.Tasks reads and writes MPP, XML, HTML, and CSV formats, covering
      **all major Microsoft Project versions**.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Yes, you can add, update, and delete resources, as well as assign custom
      fields to them.
    question: Can I manipulate resource data using Aspose.Tasks?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      to interact with other users and get support from the Aspose team.
    question: Is there a community forum for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom field
- Aspose.Tasks
- .NET project management
- extended attributes
title: How to Add Custom Field Types in Aspose.Tasks for .NET
url: /net/calendar-scheduling/custom-field-types/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Add Custom Field Types in Aspose.Tasks

## Introduction

In this tutorial you’ll discover **how to add custom field** types to a Microsoft Project file using Aspose.Tasks for .NET. Custom fields let you store additional information—like risk scores, department codes, or custom notes—directly on tasks, resources, or the project itself. We’ll walk through the whole process, from setting up the environment to defining, adding, and verifying a custom text field.

## Quick Answers
- **What is a custom field?** A user‑defined column that can hold text, numbers, dates, or flags on tasks/resources.  
- **Which class defines a custom field?** `ExtendedAttributeDefinition`.  
- **Can I add a custom field to an existing project?** Yes—load the project, create the definition, then add it to the collection.  
- **Do I need a license for Aspose.Tasks?** A license is required for production; a free trial works for evaluation.  
- **Supported .NET versions?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## What is “how to add custom field” in Aspose.Tasks?
**How to add custom field** refers to the process of creating an `ExtendedAttributeDefinition` and attaching it to a project’s `ExtendedAttributes` collection. This enables you to store extra metadata that isn’t part of the standard Project schema. It can be used for tasks, resources, or the project itself, allowing you to capture information such as risk levels, department codes, or custom notes that are not available in the default fields.

## Why use custom fields in project management?
Aspose.Tasks supports **50+ built‑in extended attribute types** and lets you define **any number of custom fields** without affecting file size significantly. Using custom fields you can:  
These fields appear as additional columns in Microsoft Project and can be referenced in formulas, reports, and filters. They are stored within the project file and travel with it, ensuring that any downstream tools retain the custom data.

## Prerequisites

### 1. Visual Studio Installed
Make sure Visual Studio (2019 or later) is on your machine. You can download it from the Microsoft website.

### 2. Aspose.Tasks for .NET
Add the Aspose.Tasks NuGet package to your project. Download the latest version from [here](https://releases.aspose.com/tasks/net/).

### 3. Basic C# Knowledge
You should be comfortable with C# syntax, classes, and .NET project structure.

## Import Namespaces

The `Project`, `ExtendedAttributeDefinition`, and related enums live in the `Aspose.Tasks` namespace. Import it at the top of your file:

The `Aspose.Tasks` namespace provides all the core types for handling Microsoft Project files.

```csharp

```

## How to add custom field to a project?

Load the existing project, create a custom field definition, and add it to the project’s extended attributes collection—all in three concise steps. This pattern works for tasks, resources, and the project itself, and it ensures the custom field is persisted when you save the file.

### Step 1: Create Project Object
`Project` is Aspose.Tasks' top‑level object that represents a single Project file in memory. Instantiating it loads the file and gives you access to tasks, resources, and extended attributes.

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### Step 2: Define Custom Field
`ExtendedAttributeDefinition` describes a new column. In this example we create a **Text** type custom field for tasks and give it the alias “MyText”. The `ExtendedAttributeTask.Text1` enum value tells Aspose.Tasks where to store the value.

```csharp
var definition = ExtendedAttributeDefinition.CreateTaskDefinition(
    CustomFieldType.Text,
    ExtendedAttributeTask.Text1,
    "MyText");
```

### Step 3: Add Custom Field Definition to Project
The project’s `ExtendedAttributes` collection holds all custom field definitions. Adding the definition makes it available for every task in the project.

```csharp
project.ExtendedAttributes.Add(definition);
```

## Common Issues and Solutions
- **Field not appearing in MS Project UI** – Ensure you set the `Alias` property; MS Project displays the alias as the column header.  
- **Saving throws an exception** – Verify that the project file is not read‑only and that you have a valid license.  
- **Custom field values are lost after reload** – Make sure you call `project.Save("output.mpp")` after assigning values to tasks.

## Frequently Asked Questions

**Q: Can I use Aspose.Tasks with other .NET frameworks?**  
A: Yes, Aspose.Tasks works with .NET Framework, .NET Core, and .NET 5/6/7.

**Q: Is Aspose.Tasks suitable for enterprise‑level applications?**  
A: Absolutely. It supports processing of projects with **up to 10,000 tasks** and can run in multi‑threaded server environments.

**Q: Does Aspose.Tasks support multiple project file formats?**  
A: Yes—Aspose.Tasks reads and writes MPP, XML, HTML, and CSV formats, covering **all major Microsoft Project versions**.

**Q: Can I manipulate resource data using Aspose.Tasks?**  
A: Yes, you can add, update, and delete resources, as well as assign custom fields to them.

**Q: Is there a community forum for Aspose.Tasks users?**  
A: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to interact with other users and get support from the Aspose team.

---

**Last Updated:** 2026-07-19  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Related Tutorials

- [Master Extended Attribute Definitions MS Project in Aspose.Tasks](/tasks/net/tasks-project-management/extended-attribute-definition-collection/)
- [Manipulate MS Project Extended Attributes with Aspose.Tasks](/tasks/net/tasks-project-management/working-with-extended-attributes/)
- [Field Helper MS Project Integration in Aspose.Tasks](/tasks/net/tasks-project-management/field-helper/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}