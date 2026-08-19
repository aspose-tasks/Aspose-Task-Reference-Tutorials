---
date: 2026-02-26
description: 了解如何在 Aspose.Tasks for Java 中恢复任务和停止任务，包括按日期过滤任务，以实现精确的项目控制。
linktitle: How to Resume Task and Stop Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何在 Aspose.Tasks 中恢复任务和停止任务
url: /zh/java/task-properties/stop-resume-task/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中恢复任务和停止任务

## 介绍
如果您正在构建基于 Java 的项目管理解决方案，通常需要 **暂时暂停** 某个任务，然后在以后 **继续** 它。Aspose.Tasks for Java 提供了内置的停止和恢复任务属性，使这一步骤变得轻而易举。在本教程中，您将学习 **如何以编程方式恢复任务** 和 **如何以编程方式停止任务**，并了解 **如何按日期过滤任务**，以便只处理计划中相关的任务项。

## 快速答案
- **任务的 “stop” 是什么意思？** 它会设置停止日期，之后的工作将被暂停。  
- **如何恢复已停止的任务？** 为任务分配一个晚于停止日期的恢复日期即可。  
- **可以将操作限制在某个日期范围内吗？** 可以——使用最小日期来过滤任务。  
- **需要哪个库版本？** 任意近期的 Aspose.Tasks for Java 发行版（API 稳定）。  
- **开发阶段需要许可证吗？** 免费试用可用于测试；生产环境需要许可证。

## 什么是 Aspose.Tasks 中的 “how to resume task”？
恢复任务仅指在 `Task` 对象上提供一个 **RESUME** 日期。当项目引擎处理进度表时，工作将从该日期开始继续。这在资源不可用或外部依赖导致中断时尤为有用。

## 为什么要使用停止/恢复功能？
- **时间线控制：** 在不删除任务的情况下暂停工作。  
- **准确的报告：** 在甘特图中显示真实的开始/结束日期。  
- **便捷的自动化：** 配合日期过滤一次性更新多个任务。

## 前置条件
在开始之前，请确保您已经具备：

- 扎实的 Java 基础。  
- 本机已安装 JDK。  
- 已将 Aspose.Tasks for Java 库添加到项目中（可从 [here](https://releases.aspose.com/tasks/java/) 下载）。

## 导入包
首先，引入所需的类，以便能够操作项目和任务。

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
import java.util.GregorianCalendar;
```

## 步骤 1：初始化 Project 并创建 Collector
创建指向 MPP 文件的 `Project` 实例，并设置 `ChildTasksCollector` 以收集层级结构中的所有任务。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "Software Development.mpp");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

## 步骤 2：定义用于过滤的最小日期
如果只想处理具有实际停止或恢复日期的任务，请定义一个 **最小日期**。这就是 *按日期过滤任务* 技巧的核心。

```java
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
```

## 步骤 3：遍历、检查并显示停止/恢复值
现在遍历收集到的任务，应用 **how to stop task** 逻辑，并打印日期。代码还演示了通过读取 `RESUME` 属性来 **how to resume task**。

```java
for (Task tsk : collector.getTasks()) {
    if (tsk.get(Tsk.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.STOP).toString());
    }
    if (tsk.get(Tsk.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.RESUME).toString());
    }
}
```

> **专业提示：** 将 `System.out.println` 调用替换为您自己的逻辑（例如，更新日期、写入日志文件或修改任务对象），即可实际 *停止* 或 *恢复* 任务。

## 常见问题及解决方案
| 问题 | 原因 | 解决方案 |
|-------|-------|-----|
| `NullPointerException` on `tsk.get(Tsk.STOP)` | 任务未设置停止日期。 | 在调用 `.before(minDate)` 前检查是否为 `null`。 |
| 日期显示为 `NA` 即使已设置 | 最小日期设置得太近。 | 使用更早的 `minDate` 或移除过滤。 |
| 保存的 MPP 中未反映更改 | 修改后未保存项目。 | 在更新任务后调用 `project.save("output.mpp");`。 |

## 常见问答

### Aspose.Tasks for Java 适用于大规模项目吗？
当然！Aspose.Tasks for Java 旨在处理各种规模的项目，确保高效且可靠。

### 我可以自定义任务的停止和恢复日期吗？
可以，示例代码允许您根据项目需求灵活设置最小日期。

### 哪里可以获取 Aspose.Tasks for Java 的更多支持？
访问 [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) 获取社区支持和讨论。

### Aspose.Tasks for Java 有免费试用吗？
有，您可以访问 [free trial](https://releases.aspose.com/) 在购买前体验功能。

### 如何获取 Aspose.Tasks for Java 的临时许可证？
您可以在 [here](https://purchase.aspose.com/temporary-license/) 获取临时许可证用于测试。

**其他问答**

**问：如何为任务实际设置新的停止日期？**  
答：使用 `tsk.set(Tsk.STOP, new Date(...));` 然后保存项目。

**问：我可以按特定范围而不是仅仅最小日期来过滤任务吗？**  
答：可以——将任务日期同时与 `before` 和 `after` 进行比较，以匹配您的起止日期。

**问：在更改停止/恢复日期后 API 会自动重新计算进度表吗？**  
答：更改日期后，调用 `project.calculateCriticalPath();` 以刷新进度表。

## 结论
本指南介绍了使用 Aspose.Tasks for Java **如何恢复任务** 和 **如何停止任务**，并提供了实用的 **按日期过滤任务** 方法。将这些代码片段集成到您的应用程序中，您即可对项目时间线进行细粒度控制，并自信地实现进度表的自动化调整。

---

**最后更新：** 2026-02-26  
**测试环境：** Aspose.Tasks for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}