---
date: 2025-12-31
description: 了解如何使用 Aspose.Tasks for Java 设置项目开始日期、编写项目信息并将项目保存为 XML。
linktitle: Write Project Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks for Java 设置 MS Project 项目开始日期
url: /zh/java/project-properties/write-project-info/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks for Java 在 MS Project 中设置项目开始日期

## 介绍
在本教程中，您将学习如何 **设置项目开始日期** 并使用 Aspose.Tasks for Java 编写其他 MS Project 信息。无论是自动化项目进度、生成报告，还是将 Project 数据集成到更大的系统中，以编程方式控制开始日期都能让您精准掌控时间线。我们将逐步演示——从环境搭建到将更新后的项目保存为 XML 文件——帮助您立即应用这些技术。

## 快速回答
- **操作项目的主要类是什么？** Aspose.Tasks 库中的 `Project`。  
- **如何设置项目开始日期？** 使用 `project.set(Prj.START_DATE, <date>)`。  
- **还能设置状态日期吗？** 可以，使用 `project.set(Prj.STATUS_DATE, <date>)`。  
- **导出项目应使用哪种格式？** 使用 `SaveFileFormat.Xml` 保存为 XML。  
- **生产环境是否需要许可证？** 需要有效的 Aspose.Tasks 许可证才能获得完整功能。

## 什么是 **set project start date**？
设置项目开始日期定义了所有计划任务开始的日历天。它是任务工期、依赖关系和关键路径等计算的锚点。通过编程方式设置此日期，可确保多个项目文件之间的一致性，避免手动输入错误。

## 为什么使用 Aspose.Tasks for Java 来写入项目信息？
- **完整 API 覆盖**：读取、修改、写入每个 Project 属性，无需安装 Microsoft Project。  
- **跨平台**：支持 Windows、Linux 和 macOS。  
- **自动化就绪**：适用于批处理、CI 流水线或后端服务，能够即时生成项目进度表。  

## 前置条件
在开始之前，请确保您已具备：

1. **Java Development Kit (JDK)** – 任意近期版本（建议 8 以上）。  
2. **Aspose.Tasks for Java 库** – 从 [here](https://releases.aspose.com/tasks/java/) 下载。  
3. **IDE** – IntelliJ IDEA、Eclipse 或您喜欢的 Java 编辑器。  

## 导入包
首先，在 Java 项目中导入必要的包：
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## 步骤 1：设置数据目录
定义存放项目数据的目录。
```java
String dataDir = "Your Data Directory";
```

## 步骤 2：创建 Project 实例
初始化一个新的项目实例。
```java
Project project = new Project();
```

## 步骤 3：设置项目信息属性
在此我们设置 **项目开始日期**、从开始计划以及状态日期——涵盖主要关键词 *write project information* 和次要关键词 *how to set status*。
```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

## 步骤 4：将项目保存为 XML
最后，将更新后的项目文件持久化。这演示了次要关键词 **save project as xml**。
```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## 常见问题及解决方案
| 问题 | 原因 | 解决办法 |
|-------|--------|-----|
| **开始日期不正确** | Java 中月份是从 0 开始计数的。 | 如示例所示使用 `Calendar.JULY`（或在月份索引上加 1）。 |
| **文件未保存** | `dataDir` 不存在或没有写入权限。 | 预先创建目录或选择可写路径。 |
| **许可证警告** | 未使用许可证会在输出文件上添加水印。 | 在创建 `Project` 对象之前应用有效的 Aspose.Tasks 许可证。 |

## 常见问答
### Q: 我可以使用 Aspose.Tasks for Java 读取 MS Project 文件吗？
A: 可以，Aspose.Tasks for Java 提供了强大的读取和写入 MS Project 文件的功能。  
### Q: Aspose.Tasks for Java 是否兼容不同版本的 MS Project？
A: 完全兼容，Aspose.Tasks for Java 支持多种 MS Project 版本，确保不同文件格式之间的兼容性。  
### Q: Aspose.Tasks for Java 试用版有哪些限制？
A: 试用版可以让您体验库的功能，但会在输出文件上添加水印等限制。  
### Q: 我如何获取 Aspose.Tasks for Java 的支持？
A: 您可以在 Aspose.Tasks 社区论坛 [here](https://forum.aspose.com/c/tasks/15) 寻求帮助。  
### Q: 我可以购买临时许可证吗？
A: 可以，临时许可证适用于短期使用，您可以在 [here](https://purchase.aspose.com/temporary-license/) 获取。  

## 结论
现在，您已经学会了如何 **设置项目开始日期**、编写关键的项目信息，并使用 Aspose.Tasks for Java **将项目保存为 XML**。这些基础块使您能够自动化项目管理工作流，生成一致的进度表，并将 MS Project 数据集成到 Java 应用程序中。

---

**最后更新：** 2025-12-31  
**测试环境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}