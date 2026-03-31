---
title: Set Project Baseline – Managing Assignment Baseline in Aspose.Tasks
linktitle: Managing Assignment Baseline in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to set project baseline and manage assignment baselines efficiently with Aspose.Tasks for .NET, ensuring accurate tracking of project progress.
weight: 14
url: /net/advanced-features/assignment-baseline/
date: 2026-03-19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Set Project Baseline – Managing Assignment Baseline in Aspose.Tasks

## Introduction

When working on project management tasks, **setting a project baseline** is essential for measuring actual progress against the original plan. Aspose.Tasks for .NET not only lets you **set project baseline** but also gives you full control over assignment baselines, enabling precise performance tracking. In this tutorial we’ll walk through the entire process—loading a project, setting a baseline, reading assignment baseline data, and comparing baselines—so you can confidently monitor your projects.

## Quick Answers
- **What does “set project baseline” mean?** It records the original schedule and cost data for later comparison with actual performance.  
- **Which API method sets a baseline?** `Project.SetBaseline(BaselineType.Baseline)`.  
- **Do assignment baselines require a separate call?** No, they are stored automatically when you set a project baseline.  
- **What formats are supported?** MPP, XML, MPX and more via Aspose.Tasks.  
- **Is a license required for production?** Yes, a commercial license is needed for non‑trial use.

## Prerequisites

Before we begin, make sure you have:

- Basic knowledge of C# programming.  
- Visual Studio (any recent version).  
- Aspose.Tasks for .NET library added to your project. You can download it from [here](https://releases.aspose.com/tasks/net/).  
- Access to a project file in MPP format (e.g., `AssignmentBaseline2007.mpp`).

## Import Namespaces

Add the required namespaces at the top of your C# file so the compiler knows where to find the Aspose.Tasks classes.

```csharp
using Aspose.Tasks;
using System;
```

## Step 1: Load Project and Set Project Baseline

First, load the existing MPP file and then call `SetBaseline` to **set project baseline** for the whole project.

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## Step 2: Read Assignment Baseline Information

After the baseline is set, each resource assignment contains its own baseline records. The loop below extracts and prints those details, including start/finish dates, cost, work, and any time‑phased data.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var baseline in assignment.Baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
        Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
        Console.WriteLine("Bcwp: " + baseline.Bcwp);
        Console.WriteLine("Bcws: " + baseline.Bcws);
        Console.WriteLine("Cost: " + baseline.Cost);
        Console.WriteLine("Work: " + baseline.Work);
        if (baseline.TimephasedData != null)
        {
            foreach (var td in baseline.TimephasedData)
            {
                Console.WriteLine("TD Start: " + td.Start);
                Console.WriteLine("TD Finish: " + td.Finish);
                Console.WriteLine("TD Timephased Data Type: " + td.TimephasedDataType);
                Console.WriteLine();
            }
        }

        Console.WriteLine();
    }

    Console.WriteLine();
}
```

## Step 3: Compare Assignment Baselines

You can compare baselines of different assignments using the built‑in equality and comparison operators. This is handy when you need to detect schedule shifts or cost overruns between tasks.

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Check baseline equality
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Check baseline comparison
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Display baseline hashcodes
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## Common Issues and Solutions

| Issue | Why It Happens | Fix |
|-------|----------------|-----|
| **Baseline data appears empty** | The project file was opened in read‑only mode or the baseline was never set. | Call `project.SetBaseline(BaselineType.Baseline)` before reading assignment baselines. |
| **`NullReferenceException` on `TimephasedData`** | Not all baselines contain time‑phased entries. | Always check `baseline.TimephasedData != null` (as shown in the code). |
| **Incorrect UID retrieval** | UID values differ between file versions. | Use `ResourceAssignments.GetByUid` with the correct UID or iterate to find the assignment you need. |

## Frequently Asked Questions

**Q: Can Aspose.Tasks handle multiple baselines for a single assignment?**  
A: Yes, Aspose.Tasks supports multiple baselines for each assignment, allowing comprehensive tracking of project progress over time.

**Q: Is Aspose.Tasks compatible with various project file formats other than MPP?**  
A: Yes, Aspose.Tasks supports a wide range of project file formats, including XML, MPX, and MPP, ensuring compatibility with various project management tools.

**Q: Can I modify baseline information programmatically using Aspose.Tasks?**  
A: Absolutely, Aspose.Tasks provides extensive APIs to modify baseline information dynamically according to project requirements, offering flexibility and control over project management processes.

**Q: Does Aspose.Tasks offer documentation and support resources for developers?**  
A: Yes, developers can access comprehensive documentation, tutorials, and forums on the Aspose.Tasks website, facilitating smooth integration and troubleshooting.

**Q: Is there a trial version available for Aspose.Tasks for .NET?**  
A: Yes, developers can obtain a free trial version of Aspose.Tasks for .NET from [here](https://releases.aspose.com/), allowing them to evaluate its features and capabilities before making a purchase decision.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-19  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

---