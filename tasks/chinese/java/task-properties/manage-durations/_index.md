---
date: 2026-02-20
description: 探索如何使用 Aspose.Tasks for Java 将任务添加到项目并管理持续时间。了解如何设置持续时间以及如何轻松转换持续时间。
linktitle: Manage Durations of Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks 将任务添加到项目并管理持续时间
url: /zh/java/task-properties/manage-durations/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 向项目添加任务并使用 Aspose.Tasks 管理持续时间

## 介绍
在本教程中，您将学习 **如何向项目添加任务** 并使用 Aspose.Tasks for Java 控制其持续时间。无论是构建全新的项目计划工具，还是扩展已有的解决方案，掌握任务持续时间的处理对于实现精准的进度安排和报告至关重要。

## 快速答案
- **“向项目添加任务”是什么意思？** 它会在项目的根节点或特定的汇总任务下创建一个新的任务对象。  
- **哪个类表示持续时间？** `com.aspose.tasks.Duration`。  
- **如何设置持续时间？** 使用 `task.set(Tsk.DURATION, project.getDuration(value, TimeUnitType))`。  
- **我可以将持续时间转换为其他单位吗？** 可以，调用 `duration.convert(TimeUnitType.Hour)` 或其他任意 `TimeUnitType`。  
- **生产环境需要许可证吗？** 商业使用必须拥有有效的 Aspose.Tasks 许可证。

## 什么是“向项目添加任务”？
向项目添加任务指的是创建一个 `Task` 对象并将其附加到项目的任务层级结构中。这是定义任务工作、资源或持续时间之前的第一步。

## 为什么要管理任务持续时间？
准确的持续时间能够驱动真实的时间线、资源分配和关键路径分析。使用 Aspose.Tasks，您可以以编程方式设置、读取、转换和调整持续时间，从而全面掌控项目进度。

## 前置条件
在开始之前，请确保您具备以下条件：

- Java Development Kit (JDK)：确保机器上已安装 Java。您可以在[此处](https://www.oracle.com/java/technologies/javase-downloads.html)下载。  
- Aspose.Tasks 库：下载并在项目中引用 Aspose.Tasks 库。您可以在[此处](https://releases.aspose.com/tasks/java/)获取。

## 导入包
在 Java 项目中，导入使用 Aspose.Tasks 所需的包：
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## 第一步：设置项目
```java
// Create a new project
Project project = new Project();
```

## 第二步：添加新任务（add task to project）
```java
// Add a new task to the project
Task task = project.getRootTask().getChildren().add("Task");
```

## 如何设置持续时间
任务创建后，您可以定义其长度。默认情况下，持续时间以天为单位表示。

## 第三步：获取并转换任务持续时间
```java
// Get task duration in days (default time unit)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Convert duration to hours time unit
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```

## 如何转换持续时间
`convert` 方法可将 `Duration` 从一种 `TimeUnitType` 转换为另一种（例如，天 → 小时，周 → 天）。

## 第四步：将任务持续时间更新为 1 周
```java
// Increase task duration to 1 week
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```

## 第五步：缩短任务持续时间
```java
// Decrease task duration
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```

通过上述步骤，您已成功 **向项目添加任务** 并使用 Aspose.Tasks for Java 管理其持续时间。

## 常见陷阱与技巧
- **陷阱：** 在进行算术运算前忘记转换持续时间会导致结果错误。请始终使用 `duration.getTimeUnit()` 验证单位。  
- **技巧：** 使用 `project.getDuration(value, TimeUnitType)` 直接创建所需单位的持续时间，而不是事后再转换。  
- **陷阱：** 设置负数持续时间会抛出异常。请务必验证输入值。

## 结论
本指南介绍了如何 **向项目添加任务**、读取默认持续时间、**设置持续时间**，以及 **转换持续时间** 到不同的时间单位。您现在可以将这些技术集成到更大的调度应用中，实现精确的项目规划。

## 常见问题
### Aspose.Tasks 是否兼容所有 Java 版本？
Aspose.Tasks 兼容 Java 6 及更高版本。

### 我可以在商业项目中使用 Aspose.Tasks 吗？
可以，Aspose.Tasks 可用于个人和商业项目。有关许可证详情，请访问[此处](https://purchase.aspose.com/buy)。

### 在哪里可以找到更多支持和资源？
请访问 [Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15) 获取社区支持和讨论。

### 如何获取用于测试的临时许可证？
您可以在[此处](https://purchase.aspose.com/temporary-license/)获取临时许可证，用于测试和评估。

### 是否提供 Aspose.Tasks 的免费试用？
是的，您可以在[此处](https://releases.aspose.com/)获取免费试用，先行体验 Aspose.Tasks 再决定购买。

## 常见问答

**Q: 设置后如何更改任务的持续时间？**  
A: 使用 `task.get(Tsk.DURATION)` 获取当前持续时间，进行修改（如 `add`、`subtract` 或 `convert`），然后使用 `task.set(Tsk.DURATION, newDuration)` 重新设置。

**Q: 能否以分钟为单位设置持续时间？**  
A: 可以，在调用 `project.getDuration(value, TimeUnitType.Minute)` 时使用 `TimeUnitType.Minute`。

**Q: 更改持续时间会自动更新任务的开始和结束日期吗？**  
A: 仅当项目的调度模式设置为自动时会自动更新。否则，可能需要使用 `project.calculateCriticalPath()` 重新计算进度。

**Q: 能否以原始数值形式获取持续时间？**  
A: 调用 `duration.getTimeSpan()` 可获取当前时间单位下的数值。

**Q: 如果减去的时间超过当前持续时间会怎样？**  
A: API 将抛出 `ArgumentOutOfRangeException`。请始终验证结果持续时间为正数。

---

**最后更新：** 2026-02-20  
**测试环境：** Aspose.Tasks for Java（最新）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}