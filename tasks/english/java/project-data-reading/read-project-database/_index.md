---
date: 2026-10-31
description: Learn how to save project as PDF and read Microsoft Project database
  with Aspose.Tasks for Java, plus connect to Project Server, convert project to HTML,
  and export project to XML.
images:
- /java/project-data-reading/read-project-database/og-image.png
keywords:
- save project as pdf
- export project to pdf
- connect to project server
- export project to csv
- convert project to html
lastmod: 2026-10-31
linktitle: Reading Project Data from Microsoft Project Database in Aspose.Tasks
og_description: Save project as PDF and read Microsoft Project database using Aspose.Tasks
  for Java. Learn to connect to Project Server, export to HTML, XML, and CSV.
og_image_alt: Tutorial showing how to save a project as PDF and read data from Microsoft
  Project Server using Aspise.Tasks Java API
og_title: Save project as PDF and read Microsoft Project database with Aspose.Tasks
  for Java
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  headline: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  type: TechArticle
- description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  name: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  steps:
  - name: A working Java development environment (JDK 8 or newer).
    text: A working Java development environment (JDK 8 or newer).
  - name: Aspose.Tasks for Java library added to your project’s classpath.
    text: Aspose.Tasks for Java library added to your project’s classpath.
  - name: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
    text: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
  - name: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
    text: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports reading project data from XML files, Primavera
      databases, and other standard project formats.
    question: Can Aspose.Tasks be used to read project data from other databases besides
      Microsoft Project?
  - answer: Yes, the library works with Microsoft Project 2007 through the latest
      2024 releases, ensuring seamless integration across versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project?
  - answer: Absolutely, you can add, update, or delete tasks, resources, and custom
      fields using the rich API before exporting.
    question: Can I manipulate the project data before saving it?
  - answer: Yes, you can save projects as PDF, XML, HTML, CSV, PNG, JPEG, and more—over
      20 formats in total.
    question: Does Aspose.Tasks support multiple output formats?
  - answer: For additional help, visit the Aspose.Tasks forum or explore the documentation
      available on the website [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find further support or assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project integration
- PDF export
- Project Server
title: Save project as PDF and read Microsoft Project database with Aspose.Tasks for
  Java
url: /java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Save project as PDF and read Microsoft Project database with Aspose.Tasks for Java

## Introduction
In this tutorial you’ll discover how to **read Microsoft Project database** directly from a Microsoft Project Server and then **save the project as PDF** using the Aspose.Tasks Java API. Whether you need to generate printable reports, migrate legacy data, or embed project information into a custom portal, this guide walks you through every step—from configuring the JDBC connection to exporting the project to PDF, XML, or HTML. By the end, you’ll have a production‑ready solution that runs on any Java server without installing Microsoft Project.

## Quick answers
- **What does Aspose.Tasks do?** It provides a pure‑Java API to read, write, and manipulate Microsoft Project files and databases.  
- **Do I need Microsoft Project installed?** No, Aspose.Tasks works independently of Microsoft Project.  
- **Which database type is supported?** Microsoft SQL Server, the backend of Project Server.  
- **Can I export to other formats?** Yes—PDF, XML, HTML, CSV, PNG, JPEG, and more.  
- **What are the main prerequisites?** JDK 8 or newer, Aspose.Tasks for Java library, the SQL Server JDBC driver, and valid Project Server credentials.

## What is “read Microsoft Project database”?
Reading a Microsoft Project database means connecting to the Project Server’s SQL Server repository, extracting the stored project data, and loading it into a `Project` object that Aspose.Tasks can manipulate. This approach is ideal for automated reporting, data migration, or custom analytics.

## Why use Aspose.Tasks for Java?
Aspose.Tasks for Java lets you work with Microsoft Project data without needing the desktop application, offering a pure‑Java solution that runs on any platform. It provides a comprehensive object model for tasks, resources, calendars, and custom fields, and can handle large enterprise projects efficiently, making it ideal for automated reporting, migration, and integration scenarios.

- **No Microsoft Project dependency** – run on any server or CI environment.  
- **Rich object model** – access tasks, resources, assignments, calendars, and custom fields programmatically.  
- **Multiple export options** – Aspose.Tasks supports exporting to **over 20 file formats**, including PDF, XML, HTML, CSV, PNG, and JPEG, with a single API call.  
- **High performance** – the library can process projects containing **up to 10,000 tasks** in under a minute, and it streams data to avoid loading the entire file into memory.

## Prerequisites
Before you begin, make sure you have:

1. A working Java development environment (JDK 8 or newer).  
2. Aspose.Tasks for Java library added to your project’s classpath.  
3. Access credentials for the Project Server SQL database (server name, port, database name, username, password) to connect to Project Server.  
4. The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).  

## Import packages
First, import the classes you’ll need. The list includes Aspose.Tasks core classes and standard Java utilities.

```java
import com.aspose.tasks.MspDbSettings;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.File;
import java.lang.reflect.Method;
import java.net.URL;
import java.net.URLClassLoader;
import java.util.UUID;
```

## How to connect to Project Server
Establishing a reliable connection is the foundation for reading project data. Make sure the SQL Server instance is reachable from your Java host and that the login you use has **SELECT** permissions on the Project Server schema. You should also verify network latency and configure any required SSL settings to ensure secure communication.

## Step 1: set up database connection
The `MspDbSettings` class encapsulates the JDBC connection details required to access a Microsoft Project Server database. Create an `MspDbSettings` instance that holds the JDBC connection string. Replace the placeholder values with your actual server details.

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Pro tip:** Store the connection string in a secure configuration file or environment variable rather than hard‑coding credentials.

## Step 2: add JDBC driver
Load the Microsoft SQL Server JDBC driver at runtime so the JVM can communicate with the database.

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Warning:** Ensure the driver version matches your SQL Server version. Using an incompatible driver may cause connection failures.

## Step 3: read project data
The `Project` class represents a Microsoft Project file loaded into memory, exposing tasks, resources, and assignments. Instantiate a `Project` object by passing the `MspDbSettings`. Aspose.Tasks will fetch the project data from the database automatically.

```java
Project project = new Project(settings);
```

At this point you can explore the `project` object—list tasks, resources, or modify fields as needed.

## Step 4: save project as PDF
The `SaveFileFormat` enumeration defines the output format for the `Project.save` method, such as PDF, XML, or HTML. Export the loaded project to a file format of your choice. The example below saves the project as **PDF**, which is perfect for printable reports. You can also **export project to XML** or **convert project to HTML** by changing the `SaveFileFormat` enum.

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

If you prefer XML, simply replace `SaveFileFormat.Pdf` with `SaveFileFormat.Xml`. For HTML output, use `SaveFileFormat.Html`.

## Common issues & solutions
| Issue | Typical cause | Fix |
|-------|---------------|-----|
| **Connection timeout** | Wrong server/port or firewall blocking | Verify server address, open port 1433, and test connectivity with a simple JDBC test program. |
| **Authentication error** | Invalid username/password or SQL Server not configured for SQL authentication | Use a valid SQL login or enable mixed‑mode authentication on the server. |
| **Driver not found** | JDBC jar not on classpath | Ensure `addJDBCDriver` points to the correct `.jar` file and that the path uses double backslashes (`\\`). |
| **Empty project after load** | Insufficient permissions to read Project Server tables | Grant the login SELECT rights on the Project Server database schema. |

## Frequently asked questions

**Q: Can Aspose.Tasks be used to read project data from other databases besides Microsoft Project?**  
A: Yes, Aspose.Tasks supports reading project data from XML files, Primavera databases, and other standard project formats.

**Q: Is Aspose.Tasks compatible with different versions of Microsoft Project?**  
A: Yes, the library works with Microsoft Project 2007 through the latest 2024 releases, ensuring seamless integration across versions.

**Q: Can I manipulate the project data before saving it?**  
A: Absolutely, you can add, update, or delete tasks, resources, and custom fields using the rich API before exporting.

**Q: Does Aspose.Tasks support multiple output formats?**  
A: Yes, you can save projects as PDF, XML, HTML, CSV, PNG, JPEG, and more—over 20 formats in total.

**Q: Where can I find further support or assistance with Aspose.Tasks?**  
A: For additional help, visit the Aspose.Tasks forum or explore the documentation available on the website [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).

## Conclusion
By following this step‑by‑step guide, you now know how to **read Microsoft Project database**, **save the project as PDF**, and export to other formats using Aspose.Tasks for Java. This approach eliminates the dependency on Microsoft Project, streamlines automated reporting, and opens the door to powerful custom integrations.

---

**Last Updated:** 2026-10-31  
**Tested With:** Aspose.Tasks for Java 24.5 (latest at time of writing)  
**Author:** Aspose

## Related Tutorials

- [How to Save Project as PDF with Aspose.Tasks – Export Guide](/tasks/java/project-file-operations/save-as-pdf/)
- [Save Project as PDF – Render Task Sheet with Aspose.Tasks for Java](/tasks/java/task-properties/render-task-sheet/)
- [Export Project to PDF and Reduce Gap Between Tasks List and Footer in Aspose.Tasks](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}