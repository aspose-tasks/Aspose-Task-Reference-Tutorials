---
title: Saving MS Project Files in various Formats in Aspose.Tasks
linktitle: Saving Files in Various Formats in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to save MS Project files in various formats using Aspose.Tasks for .NET. Easy steps for efficient project management.
type: docs
weight: 17
url: /net/rate-recurring-tasks/save-file-formats/
---
## Introduction
In this tutorial, we'll explore how to save Microsoft Project files in various formats using Aspose.Tasks for .NET. Aspose.Tasks is a powerful API that allows developers to manipulate and manage project files programmatically.
## Prerequisites
Before we begin, ensure you have the following:
1. Aspose.Tasks for .NET: Download and install Aspose.Tasks for .NET from [here](https://releases.aspose.com/tasks/net/).
2. Development Environment: Set up a .NET development environment, such as Visual Studio.
3. Basic Understanding of C#: Familiarity with C# programming language will be beneficial.

## Import Namespaces
Make sure to import the necessary namespaces at the beginning of your C# file:
```csharp
using NUnit.Framework;
using Saving;
```
## Step 1: Create a Project Object
First, create a Project object and load your Microsoft Project file.
```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
```
## Step 2: Save Project in CSV Format
Now, let's save the project in CSV format. 
```csharp
project.Save(DataDir + "SaveProjectAsCSV_out.csv", SaveFileFormat.Csv);
```
## Step 3: Explore Other Formats
Aspose.Tasks supports various formats for saving project files, such as XML, PDF, XLSX, and more. You can explore these formats by simply changing the `SaveFileFormat` parameter in the `Save` method.
```csharp
project.Save(DataDir + "SaveProjectAsXML_out.xml", SaveFileFormat.XML);
project.Save(DataDir + "SaveProjectAsPDF_out.pdf", SaveFileFormat.PDF);
project.Save(DataDir + "SaveProjectAsXLSX_out.xlsx", SaveFileFormat.XLSX);
```
By following these steps, you can easily save Microsoft Project files in various formats using Aspose.Tasks for .NET.

## Conclusion
In this tutorial, we learned how to save MS Project files in different formats using Aspose.Tasks for .NET. Aspose.Tasks simplifies the process of manipulating project files programmatically, offering flexibility and efficiency to developers.
## FAQ's
### Q: Is Aspose.Tasks compatible with all versions of Microsoft Project?
A: Aspose.Tasks supports Microsoft Project 2003 XML, Microsoft Project 2007 MPP, and Microsoft Project 2010 MPP formats.
### Q: Can I try Aspose.Tasks before purchasing?
A: Yes, you can download a free trial from [here](https://releases.aspose.com/).
### Q: How can I get support for Aspose.Tasks?
A: You can get support from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).
### Q: Are temporary licenses available for Aspose.Tasks?
A: Yes, temporary licenses are available for evaluation purposes. You can obtain one [here](https://purchase.aspose.com/temporary-license/).
### Q: What is the pricing for Aspose.Tasks?
A: Pricing information can be found on the Aspose.Tasks purchase page [here](https://purchase.aspose.com/buy).
