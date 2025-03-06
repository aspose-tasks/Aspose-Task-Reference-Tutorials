---
title: Extract MS Project Information in Aspose.Tasks
linktitle: Extracting Project Information in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to extract MS Project information effortlessly using Aspose.Tasks for .NET. Dive into our comprehensive tutorial.
type: docs
weight: 20
url: /net/project-management-integration/project-information/
---
## Introduction
Are you looking to efficiently extract information from Microsoft Project files using Aspose.Tasks for .NET? In this tutorial, we'll guide you through the process step by step. But before we dive into the implementation details, let's first ensure you have everything you need.
## Prerequisites
Before you begin, make sure you have the following:
### 1. Aspose.Tasks for .NET
Ensure that you have installed the Aspose.Tasks for .NET library. If you haven't done so already, you can download it from the [Aspose.Tasks for .NET website](https://releases.aspose.com/tasks/net/).
### 2. Credentials for SharePoint
You'll need the credentials to access the SharePoint where your MS Project files are stored. Make sure you have the following information:
- SharePoint Domain Address
- User Name
- Password
## Importing Namespaces
Once you've got your prerequisites sorted out, it's time to import the necessary namespaces into your project.
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
Now let's break down the process of extracting MS Project information into multiple steps.
## Step 1: Provide Credentials
First, you need to provide your SharePoint credentials to access the Project Server.
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## Step 2: Initialize Project Server Manager
Next, initialize a `ProjectServerManager` instance with the provided credentials.
```csharp
var reader = new ProjectServerManager(credentials);
```
## Step 3: Retrieve Project List
Now, you can retrieve the list of projects from the Project Server.
```csharp
IEnumerable<ProjectInfo> list = reader.GetProjectList();
```
## Step 4: Print Project Information
Finally, iterate through the list of projects and print their information.
```csharp
Console.WriteLine("Print information about projects:");
foreach (var info in list)
{
    Console.WriteLine("Id: " + info.Id);
    Console.WriteLine("Name: " + info.Name);
    Console.WriteLine("Description: " + info.Description);
    Console.WriteLine("Created Date: " + info.CreatedDate);
    Console.WriteLine("Last Saved Date: " + info.LastSavedDate);
    Console.WriteLine("Last Published Date: " + info.LastPublishedDate);
    Console.WriteLine("Is Checked Out: " + info.IsCheckedOut);
}
```
## Conclusion
Congratulations! You've successfully learned how to extract MS Project information using Aspose.Tasks for .NET. With this knowledge, you can now integrate this functionality into your .NET applications seamlessly.
## FAQ's
### Q1: Can I use Aspose.Tasks for .NET with any version of Microsoft Project?
A: Yes, Aspose.Tasks for .NET supports various versions of Microsoft Project, including 2003, 2007, 2010, 2013, 2016, and 2019.
### Q2: Is Aspose.Tasks for .NET compatible with both Windows and Linux platforms?
A: Yes, Aspose.Tasks for .NET is compatible with both Windows and Linux platforms, making it versatile for different development environments.
### Q3: Can I extract task dependencies using Aspose.Tasks for .NET?
A: Absolutely! Aspose.Tasks for .NET provides robust functionality to extract not only basic project information but also task dependencies and other intricate details.
### Q4: Does Aspose.Tasks for .NET offer technical support?
A: Yes, you can get technical support for Aspose.Tasks for .NET through the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15), where you can ask questions and seek assistance from experts.
### Q5: Can I try Aspose.Tasks for .NET before purchasing it?
A: Certainly! You can avail yourself of a free trial of Aspose.Tasks for .NET from the [releases page](https://releases.aspose.com/), allowing you to explore its features before making a purchase decision.
