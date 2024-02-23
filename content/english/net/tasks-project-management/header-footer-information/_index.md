---
title: Extract Header and Footer Information with Aspose.Tasks
linktitle: Header and Footer Information in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn to extract header & footer info from MS Project files using Aspose.Tasks for .NET. Easy, efficient, and developer-friendly solution.
type: docs
weight: 29
url: /net/tasks-project-management/header-footer-information/
---
## Introduction
Aspose.Tasks for .NET is a powerful library that allows developers to manipulate Microsoft Project files with ease. In this tutorial, we will learn how to retrieve header and footer information from MS Project files using Aspose.Tasks.
## Prerequisites
Before we begin, make sure you have the following prerequisites:
1. Visual Studio: Install Visual Studio on your system.
2. Aspose.Tasks for .NET: Download and install the Aspose.Tasks for .NET library from [here](https://releases.aspose.com/tasks/net/).
3. Basic Knowledge of C#: Familiarity with C# programming language.

## Import Namespaces
First, you need to import the necessary namespaces into your C# project. This will allow you to access the classes and methods provided by the Aspose.Tasks library.
```csharp
    using System;
    
```
## Step 1: Initialize Project Object
To begin, you need to initialize a `Project` object by loading an existing MS Project file.
```csharp
// The path to the documents directory.
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
```
## Step 2: Retrieve Header and Footer Information
Once you have loaded the project file, you can retrieve the header and footer information using the `PageInfo` property.
```csharp
var info = project.DefaultView.PageInfo;
// Header Information
Console.WriteLine("Header left text: {0} ", info.Header.LeftText);
Console.WriteLine("Header left image: {0} ", info.Header.LeftImage);
Console.WriteLine("Header left image size: {0} ", info.Header.LeftImageSize);
Console.WriteLine("Header center text: {0} ", info.Header.CenteredText);
Console.WriteLine("Header center image: {0} ", info.Header.CenteredImage);
Console.WriteLine("Header center image size: {0} ", info.Header.CenteredImageSize);
Console.WriteLine("Header right text: {0} ", info.Header.RightText);
Console.WriteLine("Header right image: {0} ", info.Header.RightImage);
Console.WriteLine("Header right image size: {0} ", info.Header.RightImageSize);
// Footer Information
Console.WriteLine();
Console.WriteLine("Footer left text: {0} ", info.Footer.LeftText);
Console.WriteLine("Footer left image: {0} ", info.Footer.LeftImage);
Console.WriteLine("Footer left image size: {0} ", info.Footer.LeftImageSize);
Console.WriteLine("Footer center text: {0} ", info.Footer.CenteredText);
Console.WriteLine("Footer center image: {0} ", info.Footer.CenteredImage);
Console.WriteLine("Footer center size: {0} ", info.Footer.CenteredImageSize);
Console.WriteLine("Footer right text: {0} ", info.Footer.RightText);
Console.WriteLine("Footer right image: {0} ", info.Footer.RightImage);
Console.WriteLine("Footer right image size: {0} ", info.Footer.RightImageSize);
```
By following these simple steps, you can easily retrieve header and footer information from MS Project files using Aspose.Tasks for .NET.

## Conclusion
In this tutorial, we explored how to extract header and footer information from MS Project files using Aspose.Tasks for .NET. This powerful library simplifies the task of working with Project files in C# applications, providing developers with robust tools for manipulation.
### FAQs
### Can I modify the header and footer information using Aspose.Tasks?
Yes, you can modify the header and footer information programmatically using Aspose.Tasks for .NET.
### Does Aspose.Tasks support other project file formats besides MS Project?
Yes, Aspose.Tasks supports various project file formats, including MPP, XML, and MPX.
### Is there a free trial available for Aspose.Tasks?
Yes, you can download a free trial of Aspose.Tasks from [here](https://releases.aspose.com/).
### Where can I find documentation for Aspose.Tasks?
You can find the documentation for Aspose.Tasks [here](https://reference.aspose.com/tasks/net/).
### How can I get support for Aspose.Tasks?
You can get support for Aspose.Tasks by visiting the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).