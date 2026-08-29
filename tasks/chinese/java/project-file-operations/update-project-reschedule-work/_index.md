---
date: 2026-03-29
description: 了解如何使用 Aspose.Tasks for Java 重新安排未完成的工作、更新项目工作，并将 MS Project 文件保存为 XML。
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks 重新安排未完成的工作并更新 MS Project 文件
url: /zh/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 重新安排未完成的工作并使用 Aspose.Tasks 更新 MS Project 文件

## 介绍
Microsoft Project 是一种广泛使用的项目管理工具，帮助团队计划任务、分配资源并跟踪时间线。Aspose.Tasks for Java 为开发者提供了丰富的 API，以编程方式操作 Microsoft Project 文件。在本教程中，您将学习如何 **更新项目工作**、**重新安排未完成的工作**，以及使用 Aspose.Tasks for Java 将 MS Project 文件以 XML 格式 **保存**。

## 快速答案
- **“重新安排未完成的工作” 是什么意思？** 它会将所有剩余的任务工作移动到所选日期之后开始，已完成的部分保持不变。  
- **哪个方法将工作标记为完成？** `project.updateProjectWorkAsComplete(date, false)`。  
- **如何持久化更改？** 使用 `project.save(<path>, SaveFileFormat.Xml)`。  
- **生产环境需要许可证吗？** 是的，商业使用需要有效的 Aspose.Tasks 许可证。  
- **支持哪个 Java 版本？** 完全支持 Java 8 及更高版本。

## 什么是“重新安排未完成的工作”？
重新安排未完成的工作会调整所有尚未完成的任务的开始日期，使其在指定的截止日期之后开始。当项目时间线因延迟或范围变更而移动时，这非常有用。

## 为什么使用 Aspose.Tasks 来更新项目工作并重新安排任务？
- **细粒度控制：** 直接设置工作完成百分比和日期。  
- **无需 UI：** 自动化对大量项目文件的批量更新。  
- **跨平台：** 在任何运行 Java 的系统上均可使用。  
- **保持数据完整性：** 所有依赖关系、约束和资源保持一致。

## 先决条件
在开始之前，请确保您具备以下条件：
1. 已在系统上安装 Java Development Kit (JDK)。  
2. Aspose.Tasks for Java 库。您可以从 [here](https://releases.aspose.com/tasks/java/) 下载。  
3. 对 Java 编程语言有基本了解。

## 导入包
首先，在 Java 代码中导入必要的包：
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

## 步骤 1：设置项目
初始化一个新的 `Project` 对象，定义任务、设置持续时间并建立依赖关系。这将创建我们后续将更新和重新安排的基线项目。
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

## 步骤 2：更新项目工作
将工作标记为在特定日期之前完成。此步骤演示 **更新项目工作** 操作，通常是重新安排之前的第一步。
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## 步骤 3：重新安排未完成的工作
现在我们将任何剩余（未完成）的工作移至相同的截止日期之后开始。这是核心的 **重新安排未完成的工作** 功能。
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## 结论
在本教程中，我们介绍了如何使用 Aspose.Tasks for Java **更新项目工作**、**重新安排未完成的工作**，以及 **将 MS Project 文件保存为 XML**。当项目时间线需要根据实际进度或业务优先级的变化进行调整时，这些功能至关重要。

## 常见问题
### 问：Aspose.Tasks for Java 能处理复杂的项目结构吗？
答：是的，Aspose.Tasks for Java 提供了强大的 API，可高效管理任务、依赖关系、资源和其他项目元素。  
### 问：是否有 Aspose.Tasks for Java 的试用版？
答：是的，您可以从 [here](https://releases.aspose.com/) 获取免费试用。  
### 问：如何获取 Aspose.Tasks for Java 的支持？
答：您可以访问 [Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15) 寻求帮助或查询。  
### 问：我可以为 Aspose.Tasks for Java 购买临时许可证吗？
答：是的，临时许可证可在 [here](https://purchase.aspose.com/temporary-license/) 购买。  
### 问：在哪里可以找到 Aspose.Tasks for Java 的详细文档？
答：您可以参考文档 [here](https://reference.aspose.com/tasks/java/) 获取全面的指南和 API 参考。

## 其他常见问题

**问：如何确保保存的文件兼容旧版本的 Microsoft Project？**  
答：使用 `SaveFileFormat.Xml` 保存项目；XML 在各版本的 Project 中得到广泛支持。

**问：我可以只重新安排项目的一部分任务吗？**  
答：可以，您可以遍历特定任务并在计算新开始日期后调用 `task.setStart(date)`。

**问：重新安排未完成的工作时资源分配会怎样？**  
答：资源分配会自动移动以匹配新的任务开始日期，保持分配逻辑。

**问：是否可以通过编程方式撤销重新安排操作？**  
答：您可以重新加载原始项目文件（或备份）以恢复更改。

**问：Aspose.Tasks 是否支持保存为其他格式，如 .mpp？**  
答：当然。使用 `SaveFileFormat.MPP` 可保存为原生 Microsoft Project 格式。

---

**最后更新：** 2026-03-29  
**测试环境：** Aspose.Tasks for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}