---
title: Mastering Timephased Data Collection in Aspose.Tasks
linktitle: Collection of Timephased Data in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Explore timephased data collection in Aspose.Tasks for .NET. Step-by-step guide, FAQs, and more. Enhance your project management capabilities today!
type: docs
weight: 15
url: /net/text-view-configuration/timephased-data-collection/
---
## Introduction
Are you looking to harness the power of timephased data in your .NET applications using Aspose.Tasks? Look no further! This comprehensive guide will walk you through the process of collecting timephased data with Aspose.Tasks for .NET, ensuring that you make the most out of this powerful library.
## Prerequisites
Before diving into the tutorial, ensure you have the following prerequisites in place:
1. Aspose.Tasks for .NET Library: Download and install the library from [Aspose.Tasks .NET Documentation](https://reference.aspose.com/tasks/net/).
2. .NET Development Environment: Make sure you have a working .NET development environment set up.
3. Your Document Directory: Replace the placeholder "Your Document Directory" in the code snippets with the path to your document directory.
## Import Namespaces
In your .NET project, begin by importing the necessary namespaces to leverage Aspose.Tasks functionalities:
```csharp
    using System;
    using System.Collections.Generic;
    
```
## 1. Create a Project and Resources
```csharp
var project = new Project(DataDir + "Project1.mpp");
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
var resource2 = project.Resources.Add("Resource 2");
resource2.Set(Rsc.Type, ResourceType.Work);
```
## 2. Add Tasks to the Project
```csharp
var task = project.RootTask.Children.Add("Task 1");
// Set task properties...
var task2 = project.RootTask.Children.Add("Task 2");
// Set task2 properties...
```
## 3. Assign Resources to Tasks
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
// Set assignment properties...
var assignment2 = project.ResourceAssignments.Add(task2, resource2);
// Set assignment2 properties...
```
## 4. Work with Timephased Data
```csharp
// Set contoured work contour
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
// Check if timephased data collection is read-only
Console.WriteLine("Is timephased data collection read-only?: " + assignment.TimephasedData.IsReadOnly);
// Clear generated timephased data
assignment.TimephasedData.Clear();
// Create and add timephased data
var td = new TimephasedData
{
    // Set timephased data properties...
};
assignment.TimephasedData.Add(td);
// Add a list of timephased data
var list = new List<TimephasedData>();
// Add more timephased data items to the list...
assignment.TimephasedData.AddRange(list);
// Filter timephased data by type and date range
Console.WriteLine("Print filtered timephased data:");
IList<TimephasedData> filteredTds = assignment.TimephasedData.SelectBetweenStartAndFinish(
    TimephasedDataType.AssignmentRemainingWork,
    new DateTime(2019, 11, 11, 0, 0, 0),
    new DateTime(2019, 11, 13));
// Print filtered timephased data...
```
## 5. Manipulate Timephased Data
```csharp
// Add a wrong timephased data item and then delete it
var td4 = new TimephasedData
{
    // Set wrong timephased data properties...
};
assignment.TimephasedData.Add(td4);
// Delete the wrong timephased data item
if (assignment.TimephasedData.Contains(td4))
{
    assignment.TimephasedData.Remove(td4);
}
// Iterate over all timephased items
Console.WriteLine("Print all timephased items:");
foreach (var item in assignment.TimephasedData)
{
    // Print timephased item details...
}
```
## 6. Copy Timephased Data to Another Assignment
```csharp
// Copy timephased data to another assignment
var timephasedDatas = new TimephasedData[assignment.TimephasedData.Count];
assignment.TimephasedData.CopyTo(timephasedDatas, 0);
assignment2.TimephasedData.Clear();
foreach (var data in timephasedDatas)
{
    assignment2.TimephasedData.Add(data);
}
// Convert the collection to a plain list
List<TimephasedData> tds = assignment.TimephasedData.ToList();
// Remove timephased data items one by one
foreach (var timephasedData in tds)
{
    assignment.TimephasedData.Remove(timephasedData);
}
```
## Conclusion
In conclusion, this tutorial has provided a detailed walkthrough of collecting timephased data using Aspose.Tasks for .NET. By following these steps, you can seamlessly integrate this functionality into your projects, enabling effective time tracking and resource management.
## Frequently Asked Questions
### Can I use Aspose.Tasks for .NET with other project management tools?
Yes, Aspose.Tasks for .NET is designed to work with popular project management tools and supports various file formats.
### Is there a limit to the number of resources and tasks I can manage with Aspose.Tasks?
Aspose.Tasks handles projects of varying sizes, and there is no strict limit on the number of resources and tasks.
### How can I get support for any issues or queries related to Aspose.Tasks for .NET?
For support, visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) to connect with the community and get assistance.
### Can I try Aspose.Tasks for .NET before purchasing it?
Yes, you can explore the features of Aspose.Tasks for .NET by accessing the [free trial](https://releases.aspose.com/).
### Where can I purchase a license for Aspose.Tasks for .NET?
You can purchase a license for Aspose.Tasks for .NET [here](https://purchase.aspose.com/buy).