---
date: 2025-12-23
description: 了解如何使用 Aspose.Tasks for Java 更新 MS Project 文件并重新安排未完成的工作。同时了解如何保存 MS
  Project XML。
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks 更新 MS Project 并重新安排工作
url: /zh/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 更新 MS Project 并使用 Aspose.Tasks 重新安排工作

## Introduction
Microsoft Project 是一种广泛使用的项目管理工具，帮助团队计划、跟踪并按时交付工作。当进度变更时，通常需要以编程方式 **update MS Project** 文件——标记工作为完成、移动剩余任务，并保持项目基线的准确性。Aspose.Tasks for Java 为您提供干净、类型安全的 API，无需打开 GUI，即可完成这些操作。在本教程中，您将看到如何更新项目、将工作标记为截至特定日期已完成，然后 **how to reschedule MS Project** 工作仍在进行的任务。

## Quick Answers
- **What does “update MS Project” mean?** 它将任务标记为截至给定日期已完成，并将更改写回文件。  
- **Can I reschedule remaining work automatically?** 是的——使用 `rescheduleUncompletedWorkToStartAfter` 将未完成的任务向后推。  
- **Which file format is saved?** 示例将项目保存为 XML (`SaveFileFormat.Xml`)。  
- **Do I need a license to run the code?** 免费试用可用于开发；生产环境需要商业许可证。  
- **What Java version is required?** JDK 8 或更高。

## What is “update MS Project” in code?
在代码中，“update MS Project” 是指什么？

更新项目是指以编程方式更改任务日期、持续时间或完成百分比并持久化这些更改。Aspose.Tasks 提供诸如 `updateProjectWorkAsComplete` 的方法，根据您提供的参考 `Date` 应用更改。

## Why use Aspose.Tasks for Java to update MS Project?
为什么使用 Aspose.Tasks for Java 来更新 MS Project？

- **No UI dependency** – 在多个文件上自动执行批量更改。  
- **High fidelity** – 库保留所有原生 Project 数据（资源、日历、自定义字段）。  
- **Cross‑platform** – 在 Windows、Linux 或 macOS 上运行相同代码。  
- **Save MS Project XML** – 您可以将更新后的项目导出为广泛支持的 XML 格式，以供下游工具使用。

## Prerequisites
先决条件

1. 已安装 Java Development Kit (JDK)。  
2. Aspose.Tasks for Java 库 – 从 [here](https://releases.aspose.com/tasks/java/) 下载。  
3. 对 Java 语法和面向对象概念有基本了解。

## Import Packages
导入包

首先，导入必要的 Aspose.Tasks 类和 Java 工具类：

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## Step 1: Set up the Project
步骤 1：设置项目

创建一个新的 `Project` 实例，定义一些示例任务，设置它们的持续时间，并建立依赖关系。然后持久化初始状态，以便您看到前后效果。

```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Define tasks and their durations
// ...
// Define task dependencies
// ...
// Save the initial project state
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```

## Step 2: Update Project Work
步骤 2：更新项目工作

将工作标记为截至特定截止日期已完成。这是 **update MS Project** 的核心——API 将自动调整任务进度和日期。

```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Step 3: Reschedule Uncompleted Work
步骤 3：重新安排未完成的工作

标记完成的工作后，通常需要将剩余任务向后推。以下调用将所有未完成的工作移动到同一截止日期之后开始，有效地实现 **how to reschedule MS Project**。

```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Common Issues and Solutions
常见问题及解决方案

| Issue | Reason | Fix |
|-------|--------|-----|
| 任务未显示更新的日期 | 项目以不同格式（例如 `.mpp`）保存 | 使用 `SaveFileFormat.Xml` 保持 XML 结构完整。 |
| `updateProjectWorkAsComplete` 看起来没有作用 | 参考日期早于项目开始日期 | 确保 `Calendar` 日期在项目时间线内。 |
| 重新安排的任务重叠 | 未应用日历或资源平衡 | 应用 `Project` 日历或在重新安排后手动使用 `Task.setStart`。 |

## Frequently Asked Questions (Extended)

**Q: Aspose.Tasks for Java 能处理复杂的项目结构吗？**  
A: 可以，Aspose.Tasks for Java 提供强大的 API，能够高效管理任务、依赖关系、资源和其他项目元素。

**Q: 是否有 Aspose.Tasks for Java 的试用版？**  
A: 有，您可以从 [here](https://releases.aspose.com/) 获取免费试用。

**Q: 如何获取 Aspose.Tasks for Java 的支持？**  
A: 您可以访问 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 寻求帮助或提问。

**Q: 我可以购买 Aspose.Tasks for Java 的临时许可证吗？**  
A: 可以，临时许可证可在 [here](https://purchase.aspose.com/temporary-license/) 购买。

**Q: 在哪里可以找到 Aspose.Tasks for Java 的详细文档？**  
A: 您可以在 [here](https://reference.aspose.com/tasks/java/) 查看文档，获取完整指南和 API 参考。

## Conclusion
结论

在本教程中，我们演示了 **updating MS Project** 文件的完整过程，标记工作为完成，然后 **how to reschedule MS Project** 未完成的任务。通过将项目保存为 XML，您保持了与其他工具的兼容性，并保留了清晰的变更审计记录。使用这些模式可在大型项目组合中自动调整进度、集成到 CI 流水线，或构建自定义报告仪表盘。

---

**最后更新：** 2025-12-23  
**测试环境：** Aspose.Tasks for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}