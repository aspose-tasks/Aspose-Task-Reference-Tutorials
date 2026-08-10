---
title: Track Project Budget with Cost Accrual Types in Aspose.Tasks
linktitle: Cost Accrual Types in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to track project budget and manage project costs using Aspose.Tasks for .NET. Define cost accrual types for accurate cost tracking.
weight: 19
url: /net/calendar-scheduling/cost-accrual-types/
date: 2026-07-05
keywords:
- track project budget
- manage project costs
- how to set accrual
- define project cost tracking
- access resource by id
schemas:
- type: TechArticle
  headline: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  dateModified: '2026-07-05'
  author: Aspose
- type: HowTo
  name: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  steps:
  - name: Import Namespaces
    text: 'Let''s start by importing the necessary namespaces to access Aspose.Tasks
      functionality in our .NET project: Now that we have the namespaces ready, we
      can move on to loading a project file.'
  - name: Load Project File
    text: The `Project` class represents a Microsoft Project file and provides access
      to its tasks, resources, and other data. First, we need to load the project
      file into our application. We create a new `Project` object and initialize it
      with the path to our project file.
  - name: Access Resource
    text: 'The `Resources` collection holds all resources defined in the project.
      The `GetById` method retrieves a resource by its unique identifier. Next, we
      access the resource to which we want to apply the cost accrual type. We use
      the `GetById` method of the `Resources` collection and pass the resource ID '
  - name: Set Cost Accrual Type
    text: The `Set` method assigns a value to a resource field. Here, we set the cost
      accrual type for the resource. In this example, we are setting it to `CostAccrualType.End`,
      which means costs will not be accrued until remaining work is zero. Choosing
      `End` is ideal when you want to **track project budget*
  - name: Continue Working with the Project
    text: After setting the cost accrual type, you can continue working with the project
      as needed, performing additional operations or calculations such as generating
      cost reports, updating assignments, or exporting the file.
- type: FAQPage
  questions:
  - question: Can I change the cost accrual type for multiple resources simultaneously?
    answer: Yes, iterate through `project.Resources` and assign the desired `CostAccrualType`
      to each resource within a `foreach` loop.
  - question: What are the other available cost accrual types besides `End`?
    answer: Aspose.Tasks provides `Start`, `Prorated`, and `Duration`—each aligns
      with a different billing strategy.
  - question: How can I determine the current cost accrual type for a specific resource?
    answer: Retrieve the value via `resource.Get(TskResource.CostAccrualType)`; it
      returns the enum representing the current setting.
  - question: Is it possible to apply different cost accrual types to different tasks
      in the same project?
    answer: Absolutely. Both tasks and resources expose a `CostAccrualType` property,
      allowing independent configuration per entity.
  - question: Does Aspose.Tasks support custom cost accrual types?
    answer: No, the library currently supports the four built‑in types only; custom
      logic must be implemented externally if required.
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Track Project Budget with Cost Accrual Types in Aspose.Tasks

## Introduction

Accurately **track project budget** is the backbone of successful project delivery. When cost information is captured at the right moments, you can forecast overruns, adjust resources, and keep stakeholders informed. Aspose.Tasks for .NET gives developers fine‑grained control over cost accrual, letting you decide *when* a cost is recorded—whether at the start of work, continuously, or only when work completes. This tutorial walks you through the concepts, shows how to set an accrual type, and demonstrates best practices for reliable budget tracking.

## Quick Answers
- **What is the primary purpose of cost accrual types?** They determine the point in a task’s lifecycle when cost is recognized, enabling precise budget tracking.  
- **Which enum value delays cost until work finishes?** `CostAccrualType.End`.  
- **Do I need a license to run the code?** Yes, a valid Aspose.Tasks license is required for production use.  
- **Can I change accrual types for many resources at once?** Yes—loop through the `Resources` collection and assign the desired type.  
- **Which .NET versions are supported?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## What is Cost Accrual Type?
A **cost accrual type** tells Aspose.Tasks when to apply a resource’s cost to the project’s budget. It is represented by the `CostAccrualType` enumeration and can be set per‑resource or per‑task. Choosing the correct type ensures that cost data aligns with your organization’s billing policies, whether you need costs recorded at the start of work, prorated over the duration, or only after completion.

## Why Track Project Budget Using Cost Accrual Types?
Aspose.Tasks supports **four** accrual options—`Start`, `Prorated`, `Duration`, and `End`—covering the full range of typical project accounting scenarios. Selecting the appropriate option lets you align cost recognition with contractual billing cycles, reduce variance in financial reports, and generate cost statements that integrate smoothly with ERP systems, all while keeping memory usage low for large projects.

## Prerequisites

Before we begin, ensure you have the following prerequisites:

### 1. Install Aspose.Tasks for .NET
To get started, you need to have Aspose.Tasks for .NET installed in your development environment. You can download the library from the [download page](https://releases.aspose.com/tasks/net/) and follow the installation instructions provided.

### 2. Familiarity with .NET Framework
Basic knowledge of the .NET framework and C# programming language is required to follow along with the examples in this tutorial.

## How to Set Cost Accrual Type for a Resource?

Load the project, locate the target resource, and assign the desired `CostAccrualType`. The two‑line pattern below is the standard approach: create a `Project` instance, retrieve the resource by its ID, then set `CostAccrualType`. This concise sequence ensures you **track project budget** accurately from the moment the resource is added.

### Step 1: Import Namespaces
Let's start by importing the necessary namespaces to access Aspose.Tasks functionality in our .NET project:

```csharp

```

Now that we have the namespaces ready, we can move on to loading a project file.

### Step 2: Load Project File
The `Project` class represents a Microsoft Project file and provides access to its tasks, resources, and other data.

```csharp
var project = new Project("Project2.mpp");
```

First, we need to load the project file into our application. We create a new `Project` object and initialize it with the path to our project file.

### Step 3: Access Resource
The `Resources` collection holds all resources defined in the project. The `GetById` method retrieves a resource by its unique identifier.

```csharp
var resource = project.Resources.GetById(1);
```

Next, we access the resource to which we want to apply the cost accrual type. We use the `GetById` method of the `Resources` collection and pass the resource ID as an argument. This demonstrates **access resource by id**, a common requirement when automating cost updates.

### Step 4: Set Cost Accrual Type
The `Set` method assigns a value to a resource field.

```csharp
resource.Set(Rsc.AccrueAt, CostAccrualType.End);
```

Here, we set the cost accrual type for the resource. In this example, we are setting it to `CostAccrualType.End`, which means costs will not be accrued until remaining work is zero. Choosing `End` is ideal when you want to **track project budget** only after a task is fully completed.

### Step 5: Continue Working with the Project
After setting the cost accrual type, you can continue working with the project as needed, performing additional operations or calculations such as generating cost reports, updating assignments, or exporting the file.

## Common Pitfalls and Pro Tips
- **Pro tip:** Always call `project.Save` after modifying accrual types to persist changes.  
- **Pitfall:** Setting `CostAccrualType.Start` on a resource that never starts work will inflate budget reports—verify task schedules first.  
- **Pro tip:** Use `project.Resources.ToList()` when you need to batch‑update many resources; this avoids repeated collection lookups and improves performance on large projects.

## Frequently Asked Questions

**Q: Can I change the cost accrual type for multiple resources simultaneously?**  
A: Yes, iterate through `project.Resources` and assign the desired `CostAccrualType` to each resource within a `foreach` loop.

**Q: What are the other available cost accrual types besides `End`?**  
A: Aspose.Tasks provides `Start`, `Prorated`, and `Duration`—each aligns with a different billing strategy.

**Q: How can I determine the current cost accrual type for a specific resource?**  
A: Retrieve the value via `resource.Get(TskResource.CostAccrualType)`; it returns the enum representing the current setting.

**Q: Is it possible to apply different cost accrual types to different tasks in the same project?**  
A: Absolutely. Both tasks and resources expose a `CostAccrualType` property, allowing independent configuration per entity.

**Q: Does Aspose.Tasks support custom cost accrual types?**  
A: No, the library currently supports the four built‑in types only; custom logic must be implemented externally if required.

---

**Last Updated:** 2026-07-05  
**Tested With:** Aspose.Tasks 24.8 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Related Tutorials

- [Aspose.Tasks Calendar and Scheduling](/tasks/net/calendar-scheduling/)
- [Handling MS Project Rates with Aspose.Tasks for .NET](/tasks/net/rate-recurring-tasks/handling-rates/)
- [Effortlessly Manage MS Project Resources with Aspose.Tasks](/tasks/net/resource-risk-analysis/managing-resources/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}