---
title: "Specify database schema for Project DB with Aspose.Tasks"
linktitle: "Specify database schema for Project DB with Aspose.Tasks"
second_title: "Aspose.Tasks .NET API"
description: "Learn how to specify database schema for a Microsoft Project database using Aspose.Tasks, and how to import project data into .NET applications."
weight: 19
url: /net/advanced-concepts/msp-database-settings/
date: 2026-03-14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Settings for Microsoft Project Database in Aspose.Tasks

## Introduction

If you're working with Microsoft Project databases in your .NET applications using Aspose.Tasks, you’ll need to **specify database schema** and configure the necessary settings to **import project** data seamlessly. This tutorial will guide you through the process step by step, showing you **how to configure connection** details, **create .NET connection string**, and finally **save project as MPP**.

## Quick Answers
- **What is the primary goal?** To specify database schema and import a Project database into a .NET app.  
- **Which library is required?** Aspose.Tasks for .NET.  
- **How do I connect to Project Server?** By building a proper SQL connection string and using `MspDbSettings`.  
- **What file format is produced?** An MPP file saved with `SaveFileFormat.Mpp`.  
- **Can I change the schema name?** Yes, set the `Schema` property on `MspDbSettings`.

## How to specify database schema for Project DB

Understanding why you might need to **specify database schema** is essential. In many enterprise environments the Project Server database resides under a custom schema (e.g., `dbo`, `psdata`). By explicitly setting the schema, you ensure Aspose.Tasks queries the correct tables, preventing runtime errors and guaranteeing accurate data import.

## Prerequisites

Before you start, ensure you have the following:

1. Aspose.Tasks for .NET: Download and install the Aspose.Tasks library from [here](https://releases.aspose.com/tasks/net/).  
2. Access to a Microsoft Project Database: You should have access to a Microsoft Project database to import data from.  

## Import Namespaces

First, make sure you import the necessary namespaces to your project:

```csharp
using Aspose.Tasks;
using System;
using System.Data.SqlClient;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
```

## Step 1: Create Connection String

Construct the connection string to your Microsoft Project database. This is where you **create .NET connection string** and also define how to **connect to Project Server**.

```csharp
var connectionString = new SqlConnectionStringBuilder();
connectionString.DataSource = "192.168.56.2,1433";
connectionString.Encrypt = true;
connectionString.TrustServerCertificate = true;
connectionString.InitialCatalog = "ProjectServer_Published";
connectionString.NetworkLibrary = "DBMSSOCN";
connectionString.UserID = "sa";
connectionString.Password = "*";
connectionString.ConnectTimeout = 2;
```

> **Pro tip:** Double‑check the `DataSource` and `InitialCatalog` values; they must match your server’s address and the published database name.

## Step 2: Configure MspDbSettings

Create an instance of `MspDbSettings`, pass the connection string, and **specify database schema** by setting the `Schema` property. This tells Aspose.Tasks which schema to query.

```csharp
var settings = new MspDbSettings(connectionString.ConnectionString, new Guid("E6426C44-D6CB-4B9C-AF16-48910ACE0F54"));
settings.Schema = "dbo";
```

Here we also provide the project GUID that identifies the specific project you want to load.

## Step 3: Load Project Data

Instantiate a `Project` object using the configured settings. This step effectively **how to import project** data from the database into a .NET object.

```csharp
var project = new Project(settings);
```

## Step 4: Save Project Data

Finally, persist the loaded project to an MPP file on disk. This demonstrates **save project as MPP** using the Aspose.Tasks API.

```csharp
project.Save(OutDir + "ImportProjectDataFromDatabase_out.mpp", SaveFileFormat.Mpp);
```

After running the code, you’ll find the `ImportProjectDataFromDatabase_out.mpp` file in the output directory, ready to be opened in Microsoft Project.

## Conclusion

In this tutorial, you’ve learned how to **specify database schema** for a Microsoft Project database, **configure the connection**, **import project** data, and **save the project as MPP** using Aspose.Tasks for .NET. These steps enable seamless integration of Project Server data into your custom applications, helping you build robust project‑management solutions.

## Frequently Asked Questions

### Q1: Can I use Aspose.Tasks with different versions of Microsoft Project databases?
A1: Yes, Aspose.Tasks supports various versions of Microsoft Project databases, allowing flexibility in integration.

### Q2: How can I troubleshoot connection issues with the database?
A2: Ensure that your connection string is correctly configured with the appropriate credentials and database details. You can also refer to the documentation or seek support from the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

### Q3: Is there a trial version available for Aspose.Tasks?
A3: Yes, you can access a free trial version from [here](https://releases.aspose.com/).

### Q4: Can I customize the schema for database interaction?
A4: Yes, you can specify the schema for the `MspDbSettings` object according to your database structure.

### Q5: Where can I find more detailed documentation on using Aspose.Tasks?
A5: You can explore the comprehensive documentation [here](https://reference.aspose.com/tasks/net/) for detailed insights into Aspose.Tasks functionalities.

**Q: Does this approach work with Azure SQL databases?**  
A: Absolutely. Just adjust the `DataSource` to your Azure server name and ensure TLS/SSL settings are enabled.

**Q: How do I handle large Project databases without timing out?**  
A: Increase the `ConnectTimeout` value in the connection string and consider loading projects in batches if needed.

---

**Last Updated:** 2026-03-14  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}