---
date: 2026-02-18
description: 学习如何使用 Aspose.Tasks for Java 将项目保存为 PDF 并读取 Microsoft Project 数据库，此外还可连接到
  Project Server，将项目转换为 HTML，并导出项目为 XML。
linktitle: Reading Project Data from Microsoft Project Database in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks for Java 将项目保存为 PDF 并读取 Project 数据库
url: /zh/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 将项目保存为 PDF 并使用 Aspose.Tasks for Java 读取 Microsoft Project 数据库

## Introduction
在本教程中，您将学习如何 **直接从 Microsoft Project Server 读取 Microsoft Project 数据库**，并使用 Aspose.Tasks Java API **将项目保存为 PDF**。无论您是需要生成报表、迁移数据，还是将项目信息集成到自己的应用程序中，本指南都会一步步带您完成——从设置数据库连接到导出项目为 PDF、XML 或 HTML。完成后，您将拥有一个可直接在未安装 Microsoft Project 的主机上运行的生产就绪解决方案。

## Quick Answers
- **Aspose.Tasks 是做什么的？** 它提供了一个纯 Java API，用于读取、写入和操作 Microsoft Project 文件和数据库。  
- **需要安装 Microsoft Project 吗？** 不需要，Aspose.Tasks 可独立于 Microsoft Project 运行。  
- **支持哪种数据库类型？** Microsoft SQL Server（Project Server 的后端）。  
- **可以导出为其他格式吗？** 可以，除了 PDF 之外，还可以保存为 XML、HTML、CSV 等。  
- **主要前置条件是什么？** JDK、Aspose.Tasks for Java 库、SQL Server JDBC 驱动，以及 **连接到 Project Server 的凭证**。

## What is “read Microsoft Project database”?
读取 Microsoft Project 数据库是指连接到 Project Server 的 SQL Server 存储库，提取其中的项目数据，并将其加载到 Aspose.Tasks 能够操作的 `Project` 对象中。这种方式非常适合自动化报表、数据迁移或自定义分析。

## Why use Aspose.Tasks for Java?
- **无 Microsoft Project 依赖** – 可在任何服务器或 CI 环境中运行。  
- **丰富的对象模型** – 可编程访问任务、资源、分配、日历和自定义字段。  
- **多种导出选项** – 只需一次 API 调用即可导出为 PDF、XML、HTML、PNG 等。  
- **高性能** – 为大型企业项目进行优化。

## Prerequisites
在开始之前，请确保您具备以下条件：

1. 工作的 Java 开发环境（JDK 8 或更高）。  
2. 已将 Aspose.Tasks for Java 库添加到项目的 classpath。  
3. 用于 **连接到 Project Server** 的 Project Server SQL 数据库访问凭证（服务器名称、端口、数据库名称、用户名、密码）。  
4. Microsoft JDBC Driver for SQL Server（例如 `sqljdbc4.jar`）。

## Import Packages
首先，导入所需的类。列表包括 Aspose.Tasks 核心类和标准 Java 工具类。

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
建立可靠的连接是读取项目数据的基础。确保 Java 主机能够访问 SQL Server 实例，并且您使用的登录拥有 Project Server 模式的 **SELECT** 权限。

## Step 1: Set Up Database Connection
创建一个 `MspDbSettings` 实例来保存 JDBC 连接字符串。将占位符值替换为实际的服务器信息。

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **Pro tip:** 将连接字符串存放在安全的配置文件或环境变量中，而不是硬编码凭证。

## Step 2: Add JDBC Driver
在运行时加载 Microsoft SQL Server JDBC 驱动，使 JVM 能够与数据库通信。

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **Warning:** 确保驱动版本与您的 SQL Server 版本匹配。使用不兼容的驱动可能导致连接失败。

## Step 3: Read Project Data
通过传入 `MspDbSettings` 实例来实例化 `Project` 对象。Aspose.Tasks 将自动从数据库中获取项目数据。

```java
Project project = new Project(settings);
```

此时您可以探索 `project` 对象——列出任务、资源，或根据需要修改字段。

## Step 4: Save project as PDF
将加载的项目导出为您选择的文件格式。下面的示例将项目保存为 **PDF**，非常适合可打印的报表。通过更改 `SaveFileFormat` 枚举，还可以 **导出项目为 XML** 或 **转换项目为 HTML**。

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

如果想要 XML，只需将 `SaveFileFormat.Pdf` 替换为 `SaveFileFormat.Xml`。若需 HTML 输出，使用 `SaveFileFormat.Html`。

## Common Issues & Solutions
| Issue | Typical Cause | Fix |
|-------|---------------|-----|
| **Connection timeout** | 错误的服务器/端口或防火墙阻塞 | 验证服务器地址，打开 1433 端口，并使用简单的 JDBC 测试程序检查连通性。 |
| **Authentication error** | 用户名/密码无效或 SQL Server 未配置为 SQL 身份验证 | 使用有效的 SQL 登录，或在服务器上启用混合模式身份验证。 |
| **Driver not found** | JDBC jar 未在 classpath 中 | 确保 `addJDBCDriver` 指向正确的 `.jar` 文件，并且路径使用双反斜杠 (`\\`)。 |
| **Empty project after load** | 没有足够的权限读取 Project Server 表 | 为登录授予 Project Server 数据库模式的 SELECT 权限。 |

## Frequently Asked Questions

**Q: Aspose.Tasks 能否从 Microsoft Project 之外的其他数据库读取项目数据？**  
A: 可以，Aspose.Tasks 支持从多种来源读取项目数据，包括 XML 文件、Primavera 和 Microsoft Project 数据库。

**Q: Aspose.Tasks 与不同版本的 Microsoft Project 兼容吗？**  
A: 兼容，Aspose.Tasks 设计用于支持多个 Microsoft Project 版本，确保无缝集成。

**Q: 我可以在保存之前操作项目数据吗？**  
A: 完全可以，Aspose.Tasks 提供了丰富的 API，可在导出前添加任务、更新资源和设置项目属性。

**Q: Aspose.Tasks 支持多种输出格式吗？**  
A: 支持，您可以将项目保存为 PDF、XML、HTML、CSV、PNG、JPEG 等多种格式。

**Q: 在哪里可以找到 Aspose.Tasks 的进一步支持或帮助？**  
A: 如需更多帮助，请访问 Aspose.Tasks 论坛或查阅网站上的文档，[here](https://forum.aspose.com/c/tasks/15)。

## Conclusion
通过本分步指南，您已经掌握了如何 **读取 Microsoft Project 数据库**、**将项目保存为 PDF**，以及使用 Aspose.Tasks for Java 导出为其他格式。此方法消除了对 Microsoft Project 的依赖，简化了自动化报表流程，并为强大的自定义集成打开了大门。

---

**Last Updated:** 2026-02-18  
**Tested With:** Aspose.Tasks for Java 24.5 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}