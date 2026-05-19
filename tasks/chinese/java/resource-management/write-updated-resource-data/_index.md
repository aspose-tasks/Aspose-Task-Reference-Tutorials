---
date: 2026-01-15
description: 了解如何使用 Aspose.Tasks for Java 将资源添加到项目、更新资源数据并将项目保存为 MPP。
linktitle: Add Resource to Project Using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks for Java 向项目添加资源
url: /zh/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks for Java 向项目添加资源

## 介绍
在本实践教程中，您将学习如何使用 Aspose.Tasks Java API 以编程方式 **向项目添加资源**。我们将演示如何加载已有的 MS Project XML 文件，插入新资源，更新其属性，最后 **将项目保存为 MPP**。完成后，您将拥有一套清晰、可重复使用的模式，可嵌入任何基于 Java 的报告或自动化工具中。

## 常见问题快速解答
- **“向项目添加资源”是什么意思？** 它在 Microsoft Project 文件中创建一个新的资源条目（人员、设备、材料）。  
- **使用哪个库实现？** Aspose.Tasks for Java —— 无需安装 Microsoft Project。  
- **是否需要许可证？** 免费试用可用于开发；生产环境需要商业许可证。  
- **可以将 XML 转换为 MPP 吗？** 可以——加载 XML 文件后，使用 `project.save(...)` **将项目保存为 MPP**。  
- **需要哪个 Java 版本？** Java 6 或更高（推荐使用 Java 8 及以上）。

## 什么是“向项目添加资源”？
向项目添加资源是指在 MS Project 文件的资源表中插入一行新记录。该记录存储名称、费用率、组别以及任务后续可引用的自定义字段等详细信息。

## 为什么使用 Aspose.Tasks for Java？
- **无需 Microsoft Project 依赖** —— 可在任何操作系统或 CI 服务器上运行。  
- **完整保真** —— 在不同格式之间转换时保留所有原生 Project 功能。  
- **丰富的 API** —— 让您能够读取、写入并操作任务、资源、日历等。

## 前置条件
在开始之前，请确保您具备：

1. 已安装 Java Development Kit（JDK）8 或更高版本。  
2. Aspose.Tasks for Java 库 —— 从 [here](https://releases.aspose.com/tasks/java/) 下载。  
3. 对 Java 语法以及 Maven/Gradle 项目设置有基本了解。

## 导入包
将所需的 Aspose.Tasks 类添加到您的 Java 源文件中：

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## 步骤 1：设置数据目录
定义源 XML 文件和生成的 MPP 文件的存放位置：

```java
String dataDir = "Your Data Directory";
```

## 步骤 2：指定输入和输出文件
指向您想要转换的 XML 文件（**将 XML 转换为 MPP**）以及将包含新资源的目标 MPP 文件：

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## 步骤 3：加载项目
从 XML 源创建一个 `Project` 对象：

```java
Project project = new Project(file);
```

## 步骤 4：添加资源并设置属性
这里我们 **向项目添加资源** 并配置其费率和组别：

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

*技巧提示：* 您可以在循环中重复调用 `add`，在一次运行中 **更新多个资源**。

## 步骤 5：保存项目
最后，**将项目保存为 MPP** 以持久化更改：

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## 结论
您刚刚学习了使用 Aspose.Tasks for Java **向项目添加资源**、更新其属性，并 **将项目保存为 MPP**。此方法非常适用于自动化报告流水线、大批量资源导入，或任何需要在没有桌面应用程序的情况下操作 MS Project 文件的场景。

## 常见问题

**Q1：可以使用 Aspose.Tasks for Java 在同一项目中更新多个资源吗？**  
A：可以，遍历 `project.getResources()` 或重复调用 `add`，根据需要设置每个资源的字段。

**Q2：Aspose.Tasks 是否支持除 MS Project 之外的其他文件格式？**  
A：当然支持——XML、MPP、MPX、Primavera 等多种格式均受支持。

**Q3：Aspose.Tasks 是否兼容不同版本的 Java？**  
A：该库兼容 Java 6 及以上版本；强烈建议使用 Java 8 及以上以获得最佳性能。

**Q4：可以使用 Aspose.Tasks 对 MS Project 文件执行其他操作吗？**  
A：可以，您可以读取/写入任务、日历、分配、自定义字段，甚至生成报告。

**Q5：在哪里可以找到 Aspose.Tasks 的其他帮助或支持？**  
A：访问 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 获取社区帮助和官方支持。

---

**最后更新：** 2026-01-15  
**测试环境：** Aspose.Tasks for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}