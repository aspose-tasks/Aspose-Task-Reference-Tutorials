---
date: 2026-10-15
description: Learn how to add custom property and manage custom project properties
  in Aspose.Tasks for .NET, boosting your project metadata control.
images:
- /net/calendar-scheduling/custom-project-property-collection/og-image.png
keywords:
- add custom property
- manage custom properties
- read custom properties
- add boolean property
- add string property
lastmod: 2026-10-15
linktitle: Managing Custom Project Property Collection in Aspose.Tasks
og_description: Add custom property to your project files with Aspose.Tasks for .NET.
  This guide shows you how to manage custom properties, read them, and add boolean
  or string values efficiently.
og_image_alt: Guide showing how to add custom property in Aspose.Tasks .NET
og_title: Add custom property using Aspose.Tasks .NET API for projects
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  headline: How to add custom property in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  name: How to add custom property in Aspose.Tasks for .NET
  steps:
  - name: initialize project
    text: '`Project` is the primary class representing a project file in Aspose.Tasks.'
  - name: check custom properties collection readiness
    text: '`CustomProperties` is the collection that holds all custom property objects
      for a project.'
  - name: add custom properties
    text: '`Add` method inserts a new custom property into the project''s collection.'
  - name: access custom properties
    text: '`CustomProperties` collection implements IEnumerable, allowing iteration
      over each `CustomProperty`.'
  - name: retrieve a custom property value
    text: '`Get` method returns the value of a custom property by its name.'
  - name: iterate over custom property names
    text: '`Names` property provides a list of all custom property names in the collection.'
  - name: remove or clear custom properties
    text: '`Remove` method deletes a specific property, while `Clear` empties the
      entire collection.'
  type: HowTo
- questions:
  - answer: Yes, you can add custom properties supporting Boolean, DateTime, Double,
      and String types.
    question: Can I add custom properties of any data type to my project using Aspose.Tasks
      for .NET?
  - answer: Absolutely, you can iterate over custom property names using the `Names`
      property.
    question: Is it possible to iterate over custom property names in Aspose.Tasks
      for .NET?
  - answer: You can remove a custom property by its name using the `Remove` method.
    question: How can I remove a specific custom property from my project?
  - answer: Yes, you can obtain a temporary license from the Aspose website for evaluation
      purposes.
    question: Does Aspose.Tasks for .NET provide support for temporary licenses?
  - answer: You can visit the Aspose.Tasks forum [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any queries or assistance.
    question: Where can I find support or further assistance regarding Aspose.Tasks
      for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom properties
- Aspose.Tasks
- .NET project management
- C# tasks API
title: How to add custom property in Aspose.Tasks for .NET
url: /net/calendar-scheduling/custom-project-property-collection/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to add custom property in Aspose.Tasks for .NET

## Introduction

Add custom property support lets you store project‑specific metadata that the built‑in fields don’t cover. In this tutorial you’ll learn how to **add custom property**, read it back, and manage the entire custom property collection using Aspose.Tasks for .NET. By the end you’ll be able to tailor project files with Boolean, DateTime, Double, and String values that fit your business rules.

## Quick answers
- **Can I add a Boolean custom property?** Yes – use `CustomPropertyType.Boolean`.
- **How many custom property types are supported?** Four: Boolean, DateTime, Double, String.
- **Is the custom property collection read‑only?** It can be read‑only if the project is loaded from a read‑only source.
- **Do I need a license to use this feature?** A temporary license works for evaluation; a full license is required for production.
- **Which .NET versions are compatible?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## What is a custom property?

A custom property is a user‑defined metadata field that you attach to a Project object. It lets you store extra information such as “Risk Level”, “Customer ID”, or any Boolean flag that isn’t covered by the standard MS‑Project fields.

## Why add custom property in Aspose.Tasks?

Aspose.Tasks supports **50+ input and output formats** and can handle projects with **up to 10,000 tasks** without loading the entire file into memory. Adding custom properties lets you embed business‑critical data directly in the project file, eliminating the need for external databases and ensuring the data travels with the project.

## Prerequisites

- Visual Studio (any recent edition) installed on your workstation.  
- Aspose.Tasks for .NET – download it from the [download link](https://releases.aspose.com/tasks/net/).  
- Basic familiarity with C# syntax and .NET project structure.

## Import namespaces

The following namespaces give you access to the core project model and the custom property APIs.

```csharp
using Aspose.Tasks;
using System;


```

## How to add custom property in Aspose.Tasks?

To add a custom property, first load the project, then create a `CustomProperty` object, set its name, type, and value, and finally add it to the project's `CustomProperties` collection. This operation embeds the metadata directly into the project file, and the changes are saved when you call `project.Save(...)`.  

`CustomProperty` represents a single user‑defined field attached to a project.

```csharp
// Direct answer: Load the project, create a CustomProperty, set its Type and Value, then add it to project.CustomProperties.
```

### Step 1: initialize project

`Project` is the primary class representing a project file in Aspose.Tasks.

```csharp
var project = new Project(DataDir + "ReadProjectInfo.mpp");
```

### Step 2: check custom properties collection readiness

`CustomProperties` is the collection that holds all custom property objects for a project.

```csharp
Console.WriteLine("Is custom properties collection read-only?: " + project.CustomProps.IsReadOnly);
```

### Step 3: add custom properties

`Add` method inserts a new custom property into the project's collection.

```csharp
project.CustomProps.Add("IsEnterprise", true);
project.CustomProps.Add("Project Start Date", new DateTime(2020, 4, 16, 8, 0, 0));
project.CustomProps.Add("Precision", 10d);
project.CustomProps.Add("Custom Name", "MyProject");
```

### Step 4: access custom properties

`CustomProperties` collection implements IEnumerable, allowing iteration over each `CustomProperty`.

```csharp
foreach (var property in project.CustomProps)
{
    Console.WriteLine(property.Type);
    Console.WriteLine(property.Name);
    Console.WriteLine(property.Value);
    Console.WriteLine();
}
```

### Step 5: retrieve a custom property value

`Get` method returns the value of a custom property by its name.

```csharp
Console.WriteLine("Custom Name: " + project.CustomProps["Custom Name"]);
```

### Step 6: iterate over custom property names

`Names` property provides a list of all custom property names in the collection.

```csharp
foreach (var propName in project.CustomProps.Names)
{
    Console.WriteLine("Name: " + propName);
    Console.WriteLine();
}
```

### Step 7: remove or clear custom properties

`Remove` method deletes a specific property, while `Clear` empties the entire collection.

```csharp
if (project.CustomProps.Contains("Custom Name"))
{
    project.CustomProps.Remove("Custom Name");
}

project.CustomProps.Clear();
```

## Common pitfalls and troubleshooting

- **Read‑only collection** – If `project.CustomProperties.IsReadOnly` returns `true`, ensure the source file isn’t opened with exclusive read access or copy it to a writable location before editing.  
- **Type mismatch** – Assigning a value that doesn’t match the declared `CustomPropertyType` throws an `ArgumentException`. Always set the `Value` after defining the correct `Type`.  
- **Saving changes** – After adding or removing properties, call `project.Save("output.mpp")` to persist the modifications; otherwise changes remain in memory only.

## Frequently asked questions

**Q: Can I add custom properties of any data type to my project using Aspose.Tasks for .NET?**  
A: Yes, you can add custom properties supporting Boolean, DateTime, Double, and String types.

**Q: Is it possible to iterate over custom property names in Aspose.Tasks for .NET?**  
A: Absolutely, you can iterate over custom property names using the `Names` property.

**Q: How can I remove a specific custom property from my project?**  
A: You can remove a custom property by its name using the `Remove` method.

**Q: Does Aspose.Tasks for .NET provide support for temporary licenses?**  
A: Yes, you can obtain a temporary license from the Aspose website for evaluation purposes.

**Q: Where can I find support or further assistance regarding Aspose.Tasks for .NET?**  
A: You can visit the Aspose.Tasks forum [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for any queries or assistance.

---

**Last Updated:** 2026-10-15  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose

## Related Tutorials

- [How to read built‑in project properties using Aspose.Tasks for .NET](/tasks/net/advanced-features/built-in-project-property-collection/)
- [Manage MS Project Attributes Collection in Aspose.Tasks](/tasks/net/tasks-project-management/extended-attribute-collection/)
- [Aspose.Tasks Custom Field Types – Calendar and Scheduling](/tasks/net/calendar-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}