---
date: 2026-10-31
description: 了解如何使用 Aspose.Tasks for Java 将项目保存为 PDF 并读取 Microsoft Project 数据库，还可以连接到
  Project Server，将项目转换为 HTML，并导出项目为 XML。
keywords:
- save project as pdf
- export project to pdf
- connect to project server
- export project to csv
- convert project to html
lastmod: 2026-10-31
linktitle: 在 Aspose.Tasks 中从 Microsoft Project 数据库读取项目数据
og_description: 使用 Aspose.Tasks for Java 将项目保存为 PDF 并读取 Microsoft Project 数据库。了解如何连接到
  Project Server，导出为 HTML、XML 和 CSV。
og_image_alt: Tutorial showing how to save a project as PDF and read data from Microsoft
  Project Server using Aspise.Tasks Java API
og_title: 将项目保存为 PDF 并使用 Aspose.Tasks for Java 读取 Microsoft Project 数据库
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
title: 将项目保存为 PDF 并使用 Aspose.Tasks for Java 读取 Microsoft Project 数据库
url: /zh/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 将项目保存为 PDF 并使用 Aspose.Tasks for Java 读取 Microsoft Project 数据库

## 介绍
在本教程中，您将了解如何直接从 Microsoft Project Server **读取 Microsoft Project 数据库**，然后使用 Aspose.Tasks Java API **将项目保存为 PDF**。无论您是需要生成可打印的报告、迁移旧版数据，还是将项目信息嵌入自定义门户，本指南都会一步步带您完成——从配置 JDBC 连接到将项目导出为 PDF、XML 或 HTML。完成后，您将拥有一个可在任何 Java 服务器上运行的生产就绪解决方案，无需安装 Microsoft Project。

## 快速答案
- **What does Aspose.Tasks do?** 它提供了一个纯 Java API，用于读取、写入和操作 Microsoft Project 文件和数据库。  
- **Do I need Microsoft Project installed?** 不需要，Aspose.Tasks 可独立于 Microsoft Project 工作。  
- **Which database type is supported?** 支持 Microsoft SQL Server，即 Project Server 的后端数据库。  
- **Can I export to other formats?** 可以——PDF、XML、HTML、CSV、PNG、JPEG 等。  
- **What are the main prerequisites?** JDK 8 或更高版本、Aspose.Tasks for Java 库、SQL Server JDBC 驱动程序，以及有效的 Project Server 凭据。

## 什么是“读取 Microsoft Project 数据库”？
阅读 Microsoft Project 数据库是指连接到 Project Server 的 SQL Server 存储库，提取存储的项目数据，并将其加载到 Aspose.Tasks 可操作的 `Project` 对象中。这种方法非常适合自动化报告、数据迁移或自定义分析。

## 为什么使用 Aspose.Tasks for Java？
Aspose.Tasks for Java 让您无需桌面应用即可处理 Microsoft Project 数据，提供了一个可在任何平台上运行的纯 Java 解决方案。它提供了任务、资源、日历和自定义字段的完整对象模型，并能高效处理大型企业项目，使其非常适合自动化报告、迁移和集成场景。

- **No Microsoft Project dependency** – 可在任何服务器或 CI 环境中运行。  
- **Rich object model** – 可编程地访问任务、资源、分配、日历和自定义字段。  
- **Multiple export options** – Aspose.Tasks 支持导出到 **20 多种文件格式**，包括 PDF、XML、HTML、CSV、PNG 和 JPEG，只需一次 API 调用。  
- **High performance** – 该库能够在一分钟以内处理包含 **多达 10,000 个任务** 的项目，并通过流式传输避免将整个文件加载到内存中。

## 先决条件
1. 工作的 Java 开发环境（JDK 8 或更高版本）。  
2. 将 Aspose.Tasks for Java 库添加到项目的 classpath。  
3. 用于连接 Project Server 的 Project Server SQL 数据库访问凭据（服务器名称、端口、数据库名称、用户名、密码）。  
4. Microsoft JDBC Driver for SQL Server（例如 `sqljdbc4.jar`）。

## 导入包
首先，导入您需要的类。列表包括 Aspose.Tasks 核心类和标准 Java 实用程序。

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

## 如何连接到 Project Server
建立可靠的连接是读取项目数据的基础。确保 SQL Server 实例可以从您的 Java 主机访问，并且您使用的登录在 Project Server 架构上具有 **SELECT** 权限。还应检查网络延迟并配置任何必需的 SSL 设置，以确保安全通信。

## 步骤 1：设置数据库连接
`MspDbSettings` 类封装了访问 Microsoft Project Server 数据库所需的 JDBC 连接详细信息。创建一个包含 JDBC 连接字符串的 `MspDbSettings` 实例。将占位符值替换为实际的服务器详细信息。

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Pro tip:** 将连接字符串存储在安全的配置文件或环境变量中，而不是硬编码凭据。

## 步骤 2：添加 JDBC 驱动
在运行时加载 Microsoft SQL Server JDBC 驱动，以便 JVM 能够与数据库通信。

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Warning:** 确保驱动程序版本与您的 SQL Server 版本匹配。使用不兼容的驱动程序可能导致连接失败。

## 步骤 3：读取项目数据
`Project` 类表示加载到内存中的 Microsoft Project 文件，公开任务、资源和分配。通过传入 `MspDbSettings` 实例化一个 `Project` 对象。Aspose.Tasks 将自动从数据库获取项目数据。

```java
Project project = new Project(settings);
```

此时，您可以探索 `project` 对象——列出任务、资源，或根据需要修改字段。

## 步骤 4：将项目保存为 PDF
`SaveFileFormat` 枚举定义了 `Project.save` 方法的输出格式，例如 PDF、XML 或 HTML。将加载的项目导出为您选择的文件格式。下面的示例将项目保存为 **PDF**，非常适合可打印的报告。您还可以通过更改 `SaveFileFormat` 枚举来 **导出项目为 XML** 或 **将项目转换为 HTML**。

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

如果您更喜欢 XML，只需将 `SaveFileFormat.Pdf` 替换为 `SaveFileFormat.Xml`。若要输出 HTML，请使用 `SaveFileFormat.Html`。

## 常见问题与解决方案
| Issue | Typical cause | Fix |
|-------|---------------|-----|
| **连接超时** | 服务器/端口错误或防火墙阻止 | 验证服务器地址，打开 1433 端口，并使用简单的 JDBC 测试程序测试连通性。 |
| **身份验证错误** | 用户名/密码无效或 SQL Server 未配置为 SQL 身份验证 | 使用有效的 SQL 登录，或在服务器上启用混合模式身份验证。 |
| **未找到驱动程序** | JDBC jar 未在 classpath 中 | 确保 `addJDBCDriver` 指向正确的 `.jar` 文件，并且路径使用双反斜杠 (`\\`)。 |
| **加载后项目为空** | 没有足够的权限读取 Project Server 表 | 为登录授予 Project Server 数据库模式的 SELECT 权限。 |

## 常见问题
**Q: Aspose.Tasks 能否用于读取除 Microsoft Project 之外的其他数据库中的项目数据？**  
A: 可以，Aspose.Tasks 支持从 XML 文件、Primavera 数据库以及其他标准项目格式读取项目数据。

**Q: Aspose.Tasks 是否兼容不同版本的 Microsoft Project？**  
A: 是的，该库兼容 Microsoft Project 2007 到最新的 2024 版本，确保跨版本的无缝集成。

**Q: 我可以在保存之前操作项目数据吗？**  
A: 当然可以，您可以使用丰富的 API 在导出前添加、更新或删除任务、资源和自定义字段。

**Q: Aspose.Tasks 是否支持多种输出格式？**  
A: 是的，您可以将项目保存为 PDF、XML、HTML、CSV、PNG、JPEG 等——共超过 20 种格式。

**Q: 我在哪里可以找到关于 Aspose.Tasks 的进一步支持或帮助？**  
A: 如需更多帮助，请访问 Aspose.Tasks 论坛或查阅网站上提供的文档 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)。

## 结论
通过遵循本分步指南，您现在了解如何 **读取 Microsoft Project 数据库**、**将项目保存为 PDF**，以及使用 Aspose.Tasks for Java 导出为其他格式。这种方法消除了对 Microsoft Project 的依赖，简化了自动化报告，并为强大的自定义集成打开了大门。

---

**最后更新：** 2026-10-31  
**测试环境：** Aspose.Tasks for Java 24.5 (latest at time of writing)  
**作者：** Aspose

## 相关教程

- [如何使用 Aspose.Tasks 将项目保存为 PDF – 导出指南](/tasks/java/project-file-operations/save-as-pdf/)
- [将项目保存为 PDF – 使用 Aspose.Tasks for Java 渲染任务表](/tasks/java/task-properties/render-task-sheet/)
- [将项目导出为 PDF 并在 Aspose.Tasks 中减少任务列表与页脚之间的间距](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}