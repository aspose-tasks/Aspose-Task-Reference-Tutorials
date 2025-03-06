---
title: Reading Project Data from MS Project Database in Aspose.Tasks
linktitle: Reading Project Data from Microsoft Project Database in Aspose.Tasks
second_title: Aspose.Tasks Java API
description: Learn how to read project data from Microsoft Project Database using Aspose.Tasks for Java. Step-by-step guide with code examples.
weight: 12
url: /java/project-data-reading/read-project-database/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Reading Project Data from MS Project Database in Aspose.Tasks

## Introduction
In this tutorial, we'll explore how to read project data from a Microsoft Project Database using Aspose.Tasks for Java. Aspose.Tasks is a powerful Java API that allows developers to manipulate Microsoft Project documents without the need for Microsoft Project to be installed. By following the steps outlined in this guide, you'll learn how to efficiently extract project data from a database and save it in a desired format.
## Prerequisites
Before we begin, ensure you have the following prerequisites:
1. Basic knowledge of Java programming.
2. Java Development Kit (JDK) installed on your system.
3. Aspose.Tasks for Java library downloaded and configured in your project.

## Import Packages
To start, import the necessary packages:
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
## Step 1: Set Up Database Connection
Firstly, you need to set up the connection to the Microsoft Project Database. This includes specifying the database URL, server name, port number, database name, username, and password.
```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```
## Step 2: Add JDBC Driver
Next, you need to add the JDBC driver to your project. This driver facilitates communication between Java applications and the Microsoft SQL Server database.
```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```
## Step 3: Read Project Data
Now, create a `Project` object and load project data from the database using the previously defined settings.
```java
Project project = new Project(settings);
```
## Step 4: Save Project Data
Finally, save the project data to a desired format. In this example, we save it as an XML file.
```java
project.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```
Congratulations! You have successfully read project data from a Microsoft Project Database using Aspose.Tasks for Java.

## Conclusion
In this tutorial, we covered the process of reading project data from a Microsoft Project Database using Aspose.Tasks for Java. By following the outlined steps, you can seamlessly extract project information and manipulate it according to your requirements. Aspose.Tasks simplifies the handling of Microsoft Project documents, enabling efficient data extraction and manipulation.
## FAQ's
### Q: Can Aspose.Tasks be used to read project data from other databases besides Microsoft Project?
A: Yes, Aspose.Tasks supports reading project data from various sources, including XML files, Primavera, and Microsoft Project databases.
### Q: Is Aspose.Tasks compatible with different versions of Microsoft Project?
A: Yes, Aspose.Tasks is designed to work with different versions of Microsoft Project, ensuring compatibility and seamless integration.
### Q: Can I manipulate the project data before saving it?
A: Absolutely, Aspose.Tasks provides a wide range of features for manipulating project data, such as adding tasks, updating resources, and setting project properties.
### Q: Does Aspose.Tasks support multiple output formats?
A: Yes, Aspose.Tasks supports various output formats, including XML, PDF, HTML, and image formats like PNG and JPEG.
### Q: Where can I find further support or assistance with Aspose.Tasks?
A: For additional support or assistance, you can visit the Aspose.Tasks forum or explore the documentation available on the website [here](https://forum.aspose.com/c/tasks/15).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
