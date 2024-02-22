---
title: Server Save MS Project Options for Aspose.Tasks
linktitle: Project Server Save Options for Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to save Microsoft Project options for Aspose.Tasks using Project Server integration. Enhance your project management workflows.
type: docs
weight: 16
url: /net/saving-options/project-server-save-options/
---
## Introduction
In this tutorial, we'll delve into saving Microsoft Project options for Aspose.Tasks using Project Server. Aspose.Tasks is a powerful .NET API that allows developers to work with Microsoft Project files programmatically. Leveraging Project Server capabilities, we can seamlessly integrate Aspose.Tasks into our project management workflows. This tutorial will guide you through the process step by step.
## Prerequisites
Before getting started, ensure you have the following prerequisites:
1. Aspose.Tasks for .NET: Install Aspose.Tasks for .NET from the [download link](https://releases.aspose.com/tasks/net/).
   
2. Access to Project Server: You'll need access credentials and the URL of your Project Server instance. If you don't have one, you can obtain a free trial from [here](https://releases.aspose.com/).
3. Microsoft Project File: Prepare the Microsoft Project file (.mpp) that you want to save using Aspose.Tasks.

## Import Namespaces
First, you need to import the necessary namespaces in your project:
```csharp
    using System;
    using System.Diagnostics.CodeAnalysis;
    using System.Net;
    using NUnit.Framework;
```
## Step 1: Initialize Project and Credentials
```csharp
String DataDir = "Your Document Directory";
const string URL = "https://project_server.local/sites/pwa";
const string Domain = "CONTOSO.COM";
const string UserName = "Administrator";
const string Password = "MyPassword";
var project = new Project(DataDir + @"Project1.mpp");
var windowsCredentials = new NetworkCredential(UserName, Password, Domain);
var projectServerCredentials = new ProjectServerCredentials(URL, windowsCredentials);
```
Ensure you replace `"Your Document Directory"`, `URL`, `Domain`, `UserName`, and `Password` with your actual values.
## Step 2: Create Project Server Manager
```csharp
var manager = new ProjectServerManager(projectServerCredentials);
```
## Step 3: Define Save Options
```csharp
var options = new ProjectServerSaveOptions
{
    ProjectGuid = Guid.NewGuid(),
    ProjectName = "New project",
    Timeout = TimeSpan.FromMinutes(5),
    PollingInterval = TimeSpan.FromSeconds(3)
};
```
Adjust the `ProjectGuid`, `ProjectName`, `Timeout`, and `PollingInterval` according to your requirements.
## Step 4: Save Project to Server
```csharp
manager.CreateNewProject(project, options);
```
This will save the project to the Project Server with the specified options.

## Conclusion
In this tutorial, we learned how to save Microsoft Project options for Aspose.Tasks using Project Server integration. By following these steps, you can seamlessly incorporate Aspose.Tasks into your project management workflows, enhancing efficiency and productivity.
## FAQ's
### Q: Can I use Aspose.Tasks with different versions of Microsoft Project?
A: Yes, Aspose.Tasks supports various versions of Microsoft Project, ensuring compatibility across different environments.
### Q: Is there a trial version available for Aspose.Tasks?
A: Yes, you can obtain a free trial version of Aspose.Tasks from [here](https://releases.aspose.com/).
### Q: Does Aspose.Tasks support multi-threading?
A: Yes, Aspose.Tasks is designed to be thread-safe, allowing concurrent access to project data.
### Q: Can I customize save options when using Project Server integration?
A: Yes, you can tailor save options such as project name, timeout, and polling interval to suit your requirements.
### Q: Where can I find support for Aspose.Tasks?
A: You can find support and assistance on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
