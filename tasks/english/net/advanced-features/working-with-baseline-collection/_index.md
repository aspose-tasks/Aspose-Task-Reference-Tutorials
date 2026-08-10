---
title: Delete All Baselines with Aspose.Tasks Baseline Collection
linktitle: Delete All Baselines with Aspose.Tasks Baseline Collection
second_title: Aspose.Tasks .NET API
description: Learn how to delete all baselines and manage baseline collections in Aspose.Tasks for .NET with step‑by‑step code examples.
weight: 20
date: 2026-04-06
url: /net/advanced-features/working-with-baseline-collection/
keywords:
- delete all baselines
- Aspose.Tasks baseline collection
- manage project baselines
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Delete All Baselines with Aspose.Tasks Baseline Collection

## Introduction

Aspose.Tasks for .NET lets you manipulate Microsoft Project files directly from your .NET applications. One of the most powerful features is the ability to **delete all baselines** for a resource, which is essential when you need to reset a project's tracking data or start a new baseline period. In this tutorial we’ll walk through the whole process—from loading a project file to removing every baseline attached to a specific resource—using clear, conversational explanations and ready‑to‑run C# code.

## Quick Answers
- **What does “delete all baselines” do?** It removes every stored baseline record for a selected resource, clearing historic cost and work data.  
- **Why would I need this?** To reset tracking after a major project change or when the original baselines are no longer relevant.  
- **Which library provides this capability?** Aspose.Tasks for .NET.  
- **Do I need a license?** A valid Aspose.Tasks license is required for production use; a free trial is available.  
- **Is the code compatible with .NET 6+?** Yes, the API works with .NET Framework 4.5+, .NET Core 3.1+, and .NET 5/6.

## What Is a Baseline and Why Delete All Baselines?

A baseline captures the original plan for cost, work, and schedule at a specific point in time. Over the life of a project you may create several baselines (Baseline 1, Baseline 2, etc.) to compare actual progress against different planning snapshots. However, there are scenarios—such as a project re‑scope or a fresh start—where keeping those historic baselines becomes confusing. Deleting all baselines gives you a clean slate, allowing you to set new baselines that reflect the current reality.

## Prerequisites

Before we dive into the code, make sure you have:

1. **Visual Studio** – any recent edition (Community, Professional, or Enterprise).  
2. **Aspose.Tasks for .NET** – download it from the [download link](https://releases.aspose.com/tasks/net/).  
3. **Basic C# knowledge** – you should be comfortable with variables, loops, and console output.  
4. **A Microsoft Project file** (`.mpp`) – a sample file named *WorkWithBaselineCollection.mpp* will be used in the examples.

## Import Namespaces

First, bring the necessary namespaces into scope so the compiler knows where to find the classes we’ll use.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## Step 1: Load the Project File

We start by loading an existing Project file. Adjust `DataDir` to point to the folder that contains your `.mpp` file.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## Step 2: Get the Target Resource

For demonstration we fetch the resource with UID = 1. In a real‑world scenario you would locate the resource by name or another identifier.

```csharp
var resource = project.Resources.GetByUid(1);
```

## Step 3: Display Existing Baseline Information

Before deleting anything, it’s helpful to see what baselines are currently attached to the resource. This gives you confidence that you’re removing the right data.

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## Step 4: Iterate Through All Baselines

Here we loop through each baseline, printing key metrics such as cost, work, and earned value (BCWP/BCWS). This step is optional but useful for logging or audit purposes.

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## Delete All Baselines

Now we perform the core action: **delete all baselines** for the selected resource. We first copy the collection to a list to avoid modifying the collection while iterating, then remove each baseline one by one.

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

After this block runs, `resource.Baselines.Count` will be `0`, confirming that all baseline records have been cleared.

## Common Issues and Tips

- **NullReferenceException** – Make sure the project file actually contains the resource you’re targeting; otherwise `GetByUid` will return `null`.  
- **Licensing** – Without a valid Aspose.Tasks license you’ll see a watermark in the output and limited functionality.  
- **Performance** – For very large projects, consider iterating with `Parallel.ForEach` to speed up the removal process, but remember that the underlying collection is not thread‑safe.

## Frequently Asked Questions

**Q: Can Aspose.Tasks handle large project files?**  
A: Yes, Aspose.Tasks is optimized for performance and can process multi‑gigabyte `.mpp` files efficiently.

**Q: Is the library compatible with all Microsoft Project versions?**  
A: Aspose.Tasks supports Project 2000 through Project 2024, covering both older `.mpp` formats and the newer XML‑based files.

**Q: Can I customize baselines before deleting them?**  
A: Absolutely. You can read or modify any baseline property (cost, work, dates) before you decide to remove it.

**Q: Does Aspose.Tasks work on cloud platforms?**  
A: Yes, the API runs on any .NET‑compatible environment, including Azure App Service, AWS Lambda (via .NET Core), and Docker containers.

**Q: Where can I ask the community for help?**  
A: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to connect with other developers and Aspose staff.

## Conclusion

In this guide we demonstrated how to **delete all baselines** from a resource using Aspose.Tasks for .NET. By following the step‑by‑step code, you can reset baseline data, keep your project tracking clean, and prepare your schedule for a fresh planning cycle. Feel free to experiment with creating new baselines after the deletion to see how the library updates the project file.

---

**Last Updated:** 2026-04-06  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}