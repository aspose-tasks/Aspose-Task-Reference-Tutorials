---
title: Database Settings in Aspose.Tasks
linktitle: Database Settings in Aspose.Tasks
second_title: Aspose.Tasks .NET API
description: Learn how to import projects from a Primavera database using Aspose.Tasks for .NET. Get step-by-step guidance in this comprehensive tutorial.
type: docs
weight: 29
url: /net/calendar-scheduling/database-settings/
---
## Introduction

Aspose.Tasks for .NET is a powerful library that allows developers to work with Microsoft Project files in their .NET applications. In this tutorial, we'll focus on importing projects from a Primavera database using Aspose.Tasks.

## Prerequisites

Before we begin, make sure you have the following:

- Basic knowledge of C# programming language.
- Visual Studio installed on your system.
- Aspose.Tasks for .NET library installed. You can download it from [here](https://releases.aspose.com/tasks/net/).
- Access to a Primavera database, along with the necessary permissions.

## Import Namespaces

First, you need to import the necessary namespaces into your C# project. These namespaces provide access to the classes and methods needed to work with Aspose.Tasks for .NET.

```csharp
using Aspose.Tasks;
using System;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;

```

Now, let's break down the provided example code into multiple steps:

## Step 1: Define Connection String

```csharp
var connectionString = "Data Source=" + DataDir + "\\PPMDBSQLite.db";
```

In this step, we define the connection string to connect to the Primavera database. Ensure that you replace `DataDir` with the directory where your database file is located.

## Step 2: Create Database Settings

```csharp
var settings = new PrimaveraDbSettings(connectionString, 4502);
```

Here, we create an instance of `PrimaveraDbSettings` class, passing the connection string and the project ID as parameters. Adjust the project ID as per your requirement.

## Step 3: Set Provider Invariant Name

```csharp
settings.ProviderInvariantName = "System.Data.SQLite";
```

Specify the provider invariant name. In this example, we're using SQLite, but you can change it based on your database provider.

## Step 4: Load Project

```csharp
var project = new Project(settings);
```

Create a new `Project` object, passing the database settings as a parameter.

## Step 5: Save Project

```csharp
project.Save(OutDir + "SupportForSQLiteDatabase_out.mpp", SaveFileFormat.Mpp);
```

Finally, save the project to the desired location with the specified file format.

## Conclusion

In this tutorial, we learned how to import projects from a Primavera database using Aspose.Tasks for .NET. By following the provided steps, you can seamlessly integrate project import functionality into your .NET applications.

## FAQ's

### Q1: Can I import projects from different database providers using Aspose.Tasks for .NET?

A1: Yes, you can import projects from various database providers by adjusting the connection string and provider invariant name accordingly.

### Q2: Is there a free trial available for Aspose.Tasks for .NET?

A2: Yes, you can get a free trial of Aspose.Tasks for .NET from [here](https://releases.aspose.com/).

### Q3: Where can I find documentation for Aspose.Tasks for .NET?

A3: You can find the documentation [here](https://reference.aspose.com/tasks/net/).

### Q4: How can I get support for Aspose.Tasks for .NET?

A4: You can get support from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).

### Q5: Do I need a temporary license to use Aspose.Tasks for .NET?

A5: If you want to evaluate the full functionality of the library, you can obtain a temporary license from [here](https://purchase.aspose.com/temporary-license/).
