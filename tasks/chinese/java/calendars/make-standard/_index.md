---
date: 2025-12-03
description: 学习如何使用 Aspose.Tasks 在 Java 中创建日历。此分步指南向您展示如何创建标准的 MS Project 日历、添加标准日历以及有效使用
  Aspose.Tasks。
linktitle: Make Standard Calendar in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何创建日历 – 在 Aspose.Tasks 中制作标准日历
url: /zh/java/calendars/make-standard/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何创建日历 – 在 Aspose.Tasks 中制作标准日历

## 介绍
在本教程中，您将学习 **如何创建日历** 对象，以便在 Microsoft Project 文件中使用 Aspose.Tasks for Java 库。我们将演示如何创建标准的 MS Project 日历、将其设为默认（标准）日历，并保存项目文件。完成本指南后，您即可在任何基于 Java 的项目管理解决方案中集成日历创建功能。

## 快速答疑
- **“标准日历”是什么意思？** 它是未指定自定义日历的任务所使用的默认工作时间定义。  
- **需要哪个库？** Aspose.Tasks for Java（即 “如何使用 Aspose” 部分）。  
- **需要许可证吗？** 开发阶段可使用免费试用版；生产环境必须使用商业许可证。  
- **生成的文件格式是什么？** 基于 XML 的 Microsoft Project 文件（`.xml`）。  
- **实现大约需要多长时间？** 基本日历约 5‑10 分钟即可完成。

## 什么是 Microsoft Project 中的标准日历？
**标准日历** 定义了项目的默认工作日和工作时间。当您添加标准日历后，所有未分配特定日历的任务都会遵循该日历的时间表。

## 为什么使用 Aspose.Tasks 来创建日历？
Aspose.Tasks 提供纯 Java API，允许您在无需安装 Microsoft Project 的情况下操作 Project 文件。这使其非常适合服务器端自动化、CI 流水线或任何需要 **创建 MS Project 日历** 对象的 Java 应用程序。

## 前置条件
在开始之前，请确保以下条件已满足：

### Java Development Kit (JDK) 安装
从 Oracle 官方网站或 OpenJDK 发行版下载并安装最新的 JDK。

### Aspose.Tasks for Java 库
从 [download page](https://releases.aspose.com/tasks/java/) 下载库并将 JAR 添加到项目的 classpath 中。

## 导入包
本教程只需要一个导入语句：

```java
import com.aspose.tasks.*;
```

## 步骤指南

### 步骤 1：设置数据目录
定义生成的项目文件保存位置。

```java
String dataDir = "Your Data Directory";
```

将 `"Your Data Directory"` 替换为您机器上的绝对路径（例如 `C:/Projects/Output/`）。

### 步骤 2：创建 Project 实例
实例化一个新的空 Project 对象，用于保存日历。

```java
Project project = new Project();
```

### 步骤 3：定义并设为标准日历
添加一个名为 **“My Cal”** 的新日历，并将其提升为项目的标准日历。

```java
Calendar cal1 = project.getCalendars().add("My Cal");
Calendar.makeStandardCalendar(cal1);
```

> **技巧提示：** `makeStandardCalendar` 方法会自动将提供的日历标记为项目的默认日历，这正是您在实现 **添加标准日历** 功能时所需要的。

### 步骤 4：保存项目
将项目（包括新日历）持久化为 XML 文件。

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

如果需要不同的 Project 版本，可以更改文件名或格式（`SaveFileFormat.Pp`）。

### 步骤 5：显示完成信息
给自己一个可视化提示，表明过程已顺利完成且没有错误。

```java
System.out.println("Process completed Successfully");
```

## 常见问题与解决方案
| 问题 | 原因 | 解决方案 |
|------|------|----------|
| **文件未找到** | `dataDir` 指向了不存在的文件夹 | 创建该文件夹或使用绝对路径 |
| **许可证异常** | 在生产环境中未使用有效的 Aspose.Tasks 许可证 | 通过 `License license = new License(); license.setLicense("Aspose.Tasks.lic");` 加载许可证文件 |
| **日历为空** | 忘记添加工作时间定义 | 如需自定义工作时间，请使用 `cal1.getWeekDays().add(WeekDay.DayType.Monday)` 等方法 |

## 常见问答

**Q: Aspose.Tasks 是否兼容所有版本的 Microsoft Project？**  
A: 是的，Aspose.Tasks 支持从 2000 版到最新发布的广泛 Microsoft Project 版本。

**Q: 我可以进一步自定义日历设置吗？**  
A: 当然！您可以使用 `WeekDay` 和 `WorkingTime` 类修改工作日、添加例外并定义具体工作时间。

**Q: Aspose.Tasks 适合企业级应用吗？**  
A: 完全适用。该库专为高性能、可扩展环境设计，并提供对大型 Project 文件的全面支持。

**Q: Aspose.Tasks 为开发者提供技术支持吗？**  
A: 是的，Aspose 提供专门的论坛、工单支持以及丰富的文档，帮助您快速解决问题。

**Q: 我可以在购买前试用 Aspose.Tasks 吗？**  
A: 可以，您可以在 [website](https://purchase.aspose.com/buy) 上获取免费试用版，评估所有功能后再决定是否购买。

## 结论
现在，您已经掌握了 **如何在 Aspose.Tasks for Java 中创建日历** 对象、将其设为标准日历并保存生成的 Project 文件。这一功能让您能够自动化项目排程、统一工作时间，并将 Microsoft Project 数据直接集成到 Java 应用程序中。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最后更新：** 2025-12-03  
**测试环境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

---