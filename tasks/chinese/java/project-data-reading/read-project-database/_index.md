---
title: 在 Aspose.Tasks 中从 MS Project 数据库读取项目数据
linktitle: 在 Aspose.Tasks 中从 Microsoft Project 数据库读取项目数据
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 从 Microsoft Project 数据库读取项目数据。带有代码示例的分步指南。
weight: 12
url: /zh/java/project-data-reading/read-project-database/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中从 MS Project 数据库读取项目数据

## 介绍
在本教程中，我们将探讨如何使用 Aspose.Tasks for Java 从 Microsoft Project 数据库读取项目数据。 Aspose.Tasks 是一个功能强大的 Java API，允许开发人员操作 Microsoft Project 文档，而无需安装 Microsoft Project。通过遵循本指南中概述的步骤，您将了解如何有效地从数据库中提取项目数据并将其保存为所需的格式。
## 先决条件
在我们开始之前，请确保您满足以下先决条件：
1. Java 编程的基础知识。
2. 您的系统上安装了 Java 开发工具包 (JDK)。
3. Aspose.Tasks for Java 库已下载并在您的项目中配置。

## 导入包
首先，导入必要的包：
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
## 第 1 步：设置数据库连接
首先，您需要设置与 Microsoft Project 数据库的连接。这包括指定数据库 URL、服务器名称、端口号、数据库名称、用户名和密码。
```java
String url = "jdbc:sqlserver://”;
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```
## 第2步：添加 JDBC 驱动程序
接下来，您需要将 JDBC 驱动程序添加到您的项目中。该驱动程序有助于 Java 应用程序和 Microsoft SQL Server 数据库之间的通信。
```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```
## 第 3 步：读取项目数据
现在，创建一个`Project`对象并使用先前定义的设置从数据库加载项目数据。
```java
Project project = new Project(settings);
```
## 第 4 步：保存项目数据
最后，将项目数据保存为所需的格式。在此示例中，我们将其另存为 XML 文件。
```java
project.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```
恭喜！您已使用 Aspose.Tasks for Java 成功从 Microsoft Project 数据库读取项目数据。

## 结论
在本教程中，我们介绍了使用 Aspose.Tasks for Java 从 Microsoft Project 数据库读取项目数据的过程。通过遵循概述的步骤，您可以无缝提取项目信息并根据您的要求对其进行操作。 Aspose.Tasks 简化了 Microsoft Project 文档的处理，从而实现高效的数据提取和操作。
## 常见问题解答
### 问：Aspose.Tasks 是否可以用于从 Microsoft Project 之外的其他数据库读取项目数据？
答：是的，Aspose.Tasks 支持从各种来源读取项目数据，包括 XML 文件、Primavera 和 Microsoft Project 数据库。
### 问：Aspose.Tasks 是否与不同版本的 Microsoft Project 兼容？
答：是的，Aspose.Tasks 旨在与不同版本的 Microsoft Project 配合使用，确保兼容性和无缝集成。
### 问：我可以在保存项目数据之前对其进行操作吗？
答：当然，Aspose.Tasks 提供了广泛的功能来操作项目数据，例如添加任务、更新资源和设置项目属性。
### 问：Aspose.Tasks 支持多种输出格式吗？
答：是的，Aspose.Tasks 支持各种输出格式，包括 XML、PDF、HTML 以及 PNG 和 JPEG 等图像格式。
### 问：我在哪里可以找到有关 Aspose.Tasks 的进一步支持或帮助？
答：如需其他支持或帮助，您可以访问 Aspose.Tasks 论坛或浏览网站上提供的文档[这里](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
