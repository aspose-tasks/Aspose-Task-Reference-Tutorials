---
title: Managing MS Project Server Credentials in Aspose.Tasks
linktitle: Managing Project Server Credentials in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to manage MS Project Server credentials seamlessly with Aspose.Tasks for .NET. Enhance project management efficiency.
type: docs
weight: 22
url: /net/project-management-integration/project-server-credentials/
---
## Introduction
In the realm of project management, effective coordination and seamless communication are pivotal for successful project execution. Aspose.Tasks for .NET provides a comprehensive solution for managing Microsoft Project Server credentials, enabling users to securely access and manipulate project data. This tutorial delves into the process of managing MS Project Server credentials using Aspose.Tasks for .NET, guiding users through each step to ensure a smooth experience.
## Prerequisites
Before embarking on the journey of managing MS Project Server credentials with Aspose.Tasks for .NET, ensure the following prerequisites are met:
### 1. Installing Aspose.Tasks for .NET
To begin, download and install Aspose.Tasks for .NET from the provided [download link](https://releases.aspose.com/tasks/net/). Follow the installation instructions to integrate the library into your .NET environment seamlessly.
### 2. Access Credentials
Gather the necessary credentials required for accessing the MS Project Server. This includes the SharePoint domain address, username, and password associated with the Project Server.

## Import Namespaces
In your .NET project, import the required namespaces to utilize the functionalities provided by Aspose.Tasks for .NET efficiently.

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Diagnostics.CodeAnalysis;
using System.Net;
using System.Security;
using Microsoft.SharePoint.Client;

```

## Step 1: Define Document Directory Path
```csharp
String DataDir = "Your Document Directory";
```
## Step 2: Set SharePoint Domain Address, Username, and Password
```csharp
const string SharepointDomainAddress = "https://contoso.sharepoint.com/sites/pwa";
const string UserName = "admin@contoso.onmicrosoft.com";
const string Password = "MyPassword";
```
## Step 3: Create Project Server Credentials
```csharp
var credentials = new ProjectServerCredentials(SharepointDomainAddress, UserName, Password);
```
## Step 4: Load Project File
```csharp
var newProject = new Project(DataDir + @"Project1.mpp");
```
## Step 5: Initialize Project Server Manager
```csharp
var manager = new ProjectServerManager(credentials);
```
## Step 6: Create New Project
```csharp
manager.CreateNewProject(newProject);
```
## Step 7: Retrieve Project List
```csharp
IEnumerable<ProjectInfo> list = manager.GetProjectList();
```
## Step 8: Iterate Through Project List
```csharp
foreach (var info in list)
{
    var project = manager.GetProject(info.Id);
    Console.WriteLine("{0} - {1} - {2}", info.Name, info.CreatedDate, info.LastSavedDate);
    Console.WriteLine("Resources count: {0}", project.Resources.Count);
}
```

## Conclusion
Effectively managing MS Project Server credentials is paramount for streamlined project management. Aspose.Tasks for .NET simplifies this process by providing a robust set of functionalities. By following the step-by-step guide outlined in this tutorial, users can seamlessly integrate Aspose.Tasks for .NET into their projects, ensuring secure access and manipulation of project data.
## FAQ's
### Q: Is Aspose.Tasks for .NET compatible with all versions of Microsoft Project Server?
A: Aspose.Tasks for .NET is designed to be compatible with various versions of Microsoft Project Server, ensuring versatility and flexibility for users.
### Q: Can I integrate Aspose.Tasks for .NET into my existing .NET project?
A: Yes, Aspose.Tasks for .NET can be seamlessly integrated into existing .NET projects, facilitating efficient project management capabilities.
### Q: Does Aspose.Tasks for .NET provide support for accessing project resources?
A: Absolutely, Aspose.Tasks for .NET offers comprehensive support for accessing and manipulating project resources, enhancing project management efficiency.
### Q: Are there any licensing options available for Aspose.Tasks for .NET?
A: Yes, Aspose.Tasks for .NET offers flexible licensing options, including temporary licenses for trial purposes and full licenses for commercial use.
### Q: Where can I seek assistance or support for Aspose.Tasks for .NET?
A: For any inquiries or assistance regarding Aspose.Tasks for .NET, you can visit the support forum at [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15).## Complete Source Code
