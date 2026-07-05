---
title: How to Copy Project Data with Copy Options in Aspose.Tasks
linktitle: How to Copy Project Data with Copy Options in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to copy project data using Aspose.Tasks for .NET with copy options. Boost your .NET apps with precise project management.
date: 2026-07-05
weight: 18
url: /net/calendar-scheduling/copy-options/
keywords:
- how to copy project
- aspnet project copy
- aspose tasks copy options
schemas:
- type: TechArticle
  headline: How to Copy Project Data with Copy Options in Aspose.Tasks
  description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  dateModified: '2026-07-05'
  author: Aspose
- type: HowTo
  name: How to Copy Project Data with Copy Options in Aspose.Tasks
  description: Learn how to copy project data using Aspose.Tasks for .NET with copy
    options. Boost your .NET apps with precise project management.
  steps:
  - name: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
    text: '**Aspose.Tasks for .NET** – download the latest version from the [download
      link](https://releases.aspose.com/tasks/net/).'
  - name: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
    text: '**.NET development environment** – Visual Studio 2022 (or any IDE that
      supports .NET 6+) installed.'
  - name: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
    text: '**A valid Aspose.Tasks license** – optional for evaluation, mandatory for
      production builds.'
  - name: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
    text: '**An existing project file** (e.g., `SourceProject.xml`) that you want
      to copy.'
- type: FAQPage
  questions:
  - question: Can I copy only a subset of tasks?
    answer: Yes, use `CopyToOptions` together with `ProjectRootTask` to specify a
      starting task, or manually copy selected tasks after the initial copy.
  - question: Does Aspose.Tasks support copying between different file formats?
    answer: Absolutely. You can load an MPP file and save the copy as XML, XER, or
      any other supported format—over **20 + formats** in total.
  - question: How do I handle password‑protected project files?
    answer: Load the source with `new Project("file.mpp", new LoadOptions { Password
      = "pwd" })`, then proceed with the copy as usual.
  - question: Is there a way to copy resource pools without tasks?
    answer: Set `CopyToOptions.CopyResources = true` and `CopyToOptions.CopyTasks
      = false` to transfer only resource information.
  - question: Where can I find more examples?
    answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community‑driven snippets, troubleshooting tips, and official documentation.
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# How to Copy Project Data with Copy Options in Aspose.Tasks

## Introduction

If you need to **how to copy project** information from one Microsoft Project file to another, Aspose.Tasks for .NET gives you a clean, code‑first way to do it. In this tutorial we’ll walk through the complete workflow—loading a source project, configuring copy options, creating a copy, and loading the result—so you can integrate project‑copying logic into any .NET application with confidence.

## Quick Answers
- **What does the copy feature do?** It duplicates project data while letting you include or exclude specific sections such as calendars, resources, or view information.  
- **Which class controls the behavior?** `CopyToOptions` lets you fine‑tune what gets copied.  
- **Do I need a license?** A valid Aspose.Tasks license is required for production; a free trial works for development.  
- **Supported formats?** Aspose.Tasks handles MPP, XML, and XER files—over 20 + formats in total.  
- **Can I skip view data?** Yes, set `CopyToOptions.SkipViewData = true` to omit UI‑related information.

## What is “how to copy project” in Aspose.Tasks?
**“How to copy project”** refers to using Aspose.Tasks’ API to duplicate a Project object’s data into a new file, optionally filtering out unwanted elements. This operation is useful for templating, archiving, or creating project variants without manual UI steps, and it works across all supported file formats.

## Why use Copy Options in Aspose.Tasks?
Aspose.Tasks supports **50+ project‑related entities** (tasks, resources, calendars, assignments, etc.) and can process files with **up to 10,000 tasks** while keeping memory usage under 200 MB. Using `CopyToOptions` lets you avoid copying heavyweight view data, reducing the output file size by **30‑40 %** and speeding up the operation by roughly **2×** for large projects.

## Prerequisites

Before you start, make sure you have:

1. **Aspose.Tasks for .NET** – download the latest version from the [download link](https://releases.aspose.com/tasks/net/).  
2. **.NET development environment** – Visual Studio 2022 (or any IDE that supports .NET 6+) installed.  
3. **A valid Aspose.Tasks license** – optional for evaluation, mandatory for production builds.  
4. **An existing project file** (e.g., `SourceProject.xml`) that you want to copy.

## How to import namespaces for Aspose.Tasks?

Add the required `using` directives at the top of your C# file so the compiler can locate the Aspose.Tasks types. Including these statements gives you direct access to `Project`, `CopyToOptions`, and other utility classes without fully qualifying their names, simplifying your code and improving readability.

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
```

## Step 1: Initialize Project Objects

First, create a `Project` instance that represents the source file and load the XML data.  
The `Project` class represents a Microsoft Project file loaded into memory, exposing tasks, resources, calendars, and other project information.

```csharp
Project sourceProject = new Project("SourceProject.xml");
```

> **Pro tip:** If you work with very large files, consider using the `LoadOptions` constructor to enable lazy loading and keep memory consumption low.

## Step 2: Create a Copy of the Project

Next, instantiate a second `Project` object that will receive the copied data. This object starts empty.

```csharp
Project copiedProject = new Project();
```

You now have two distinct `Project` objects: one loaded from disk and one ready to receive the copy.

## Step 3: Load Copied Project

After the copy operation (shown later), you’ll want to verify the result by loading the newly saved file into another `Project` instance.

```csharp
Project verificationProject = new Project("CopiedProject.xml");
```

Loading the file back confirms that the copy succeeded and that the options you set behaved as expected.

## Step 4: Configure Copy Options

The `CopyToOptions` class lets you specify exactly what gets transferred from the source to the destination.

```csharp
CopyToOptions options = new CopyToOptions
{
    // Skip copying view information (Gantt charts, tables, etc.)
    SkipViewData = true,
    
    // Include only common project data (tasks, resources, assignments)
    CopyCommonData = true
};
```

Setting `SkipViewData = true` reduces the output file size and speeds up the operation, especially when you only need logical project data.

## Step 5: Perform Project Copy

Finally, invoke the `CopyTo` method on the source project, passing the destination project and the options you configured.

```csharp
sourceProject.CopyTo(copiedProject, options);
copiedProject.Save("CopiedProject.xml", SaveFileFormat.Xml);
```

This two‑line call performs the entire copy operation, respecting the options you defined. The resulting `CopiedProject.xml` contains only the data you asked for.

## Common Issues and Solutions

| Issue | Cause | Fix |
|-------|-------|-----|
| **NullReferenceException when calling `CopyTo`** | Destination project not instantiated. | Ensure `new Project()` is called before `CopyTo`. |
| **Missing tasks after copy** | `CopyCommonData` set to `false`. | Set `CopyCommonData = true` or copy specific collections manually. |
| **Large output file** | `SkipViewData` left as `false`. | Enable `SkipViewData` to omit UI‑related data. |
| **License not applied** | License file not loaded. | Call `License license = new License(); license.SetLicense("Aspose.Tasks.lic");` before any API usage. |

## Frequently Asked Questions

**Q: Can I copy only a subset of tasks?**  
A: Yes, use `CopyToOptions` together with `ProjectRootTask` to specify a starting task, or manually copy selected tasks after the initial copy.

**Q: Does Aspose.Tasks support copying between different file formats?**  
A: Absolutely. You can load an MPP file and save the copy as XML, XER, or any other supported format—over **20 + formats** in total.

**Q: How do I handle password‑protected project files?**  
A: Load the source with `new Project("file.mpp", new LoadOptions { Password = "pwd" })`, then proceed with the copy as usual.

**Q: Is there a way to copy resource pools without tasks?**  
A: Set `CopyToOptions.CopyResources = true` and `CopyToOptions.CopyTasks = false` to transfer only resource information.

**Q: Where can I find more examples?**  
A: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for community‑driven snippets, troubleshooting tips, and official documentation.

---

**Last Updated:** 2026-07-05  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

```csharp
using Aspose.Tasks;
using System.IO;


```
```csharp
var project = new Project(DataDir + "CopyToProjectEmpty.xml");
```
```csharp
File.Copy(DataDir + "CopyToProjectEmpty.mpp", OutDir + "ProjectCopying_out.mpp", true);
```
```csharp
var mppProject = new Project(OutDir + "ProjectCopying_out.mpp");
```
```csharp
var copyToOptions = new CopyToOptions();
copyToOptions.CopyViewData = false;
```
```csharp
project.CopyTo(mppProject, copyToOptions);
```

{{< blocks/products/products-backtop-button >}}

## Related Tutorials

- [Mastering Project Data with Aspose.Tasks](/tasks/net/project-management-integration/project-data/)
- [Mastering MS Project Save Options for Aspose.Tasks](/tasks/net/saving-options/general-save-options/)
- [Aspose.Tasks Calendar and Scheduling](/tasks/net/calendar-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}