---
date: 2026-02-28
description: 学习如何使用 Aspose.Tasks for Java 获取以分钟、天、小时、周和月为单位的持续时间。详细指南并附代码示例。
linktitle: Task Duration in Different Units with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks 获取不同单位的持续时间
url: /zh/java/task-properties/task-duration-different-units/
weight: 32
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在不同单位中获取持续时间（使用 Aspose.Tasks）

## Introduction
了解 **如何获取持续时间** 是任何项目管理工作流的核心部分。无论您需要分钟级的细粒度跟踪，还是月份级的宏观规划，Aspose.Tasks for Java 都能让转换变得轻而易举。在本教程中，我们将逐步演示如何以分钟、天、小时、周和月为单位获取任务的持续时间，并说明在实际项目中每个单位的使用场景。

## Quick Answers
- **What does “how to get duration” mean?** 它是指提取任务的时间跨度并转换为所需单位的过程。  
- **Which API method performs the conversion?** `Task.get(Tsk.DURATION).convert(TimeUnitType.<Unit>)`.  
- **Do I need a license to run the code?** 免费试用可用于测试；生产环境需要商业许可证。  
- **Can I convert to custom units?** 您可以链式转换或使用 `TimeSpan` 进行自定义计算。  
- **Is the code compatible with Java 17?** 是的，Aspose.Tasks 支持 Java 8 及更高版本。

## What is “how to get duration” in Aspose.Tasks?
Aspose.Tasks 将任务的时长存储为 `Duration` 对象。通过调用 `convert` 方法并指定 `TimeUnitType`（Minute、Hour、Day、Week、Month），即可获取以所需单位表示的相同底层值。这种灵活性使您能够生成报告、执行计算，或将数据传递给其他系统，而无需手动运算。

## Why use Aspose.Tasks for duration conversion?
- **Accuracy:** 自动处理日历例外、工作时间和非标准日历。  
- **Performance:** 单行转换避免循环或自定义解析。  
- **Portability:** 在 Windows、Linux 和 macOS 环境中表现一致。  
- **Integration:** 与已使用 Aspose.Tasks 的 Java 应用无缝集成。

## Prerequisites
在开始编写代码之前，请确保您已具备：

- 已安装 Java Development Kit (JDK)  
- Aspose.Tasks for Java 库。您可以在 [here](https://releases.aspose.com/tasks/java/) 下载  
- 基本的 Java 编程知识

## Import Packages
在 Java 项目中引入 Aspose.Tasks 库。在代码开头添加以下 import 语句：

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Step 1: Set Up Your Project
在您喜欢的 IDE（IntelliJ、Eclipse、VS Code 等）中创建一个新的 Java 项目，并将 Aspose.Tasks JAR 添加到项目的 classpath。这样即可在编译时使用上述类。

## Step 2: Read Project Template
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Read MS Project template file
String fileName = dataDir + "project.xml";
// Read the input file as Project
Project project = new Project(fileName);
```

将 `"Your Document Directory"` 替换为实际存放 `.xml` 或 `.mpp` 项目文件的文件夹路径。

## Step 3: Retrieve a Task
```java
// Get a task to calculate its duration in different formats
Task task = project.getRootTask().getChildren().getById(1);
```

`getById(1)` 调用会获取 ID 为 1 的任务。请根据需要修改 ID，以定位文件中的其他任务。

## Step 4: Duration in Minutes – How to get duration in minutes?
```java
// Get the duration in Minutes
double mins = task.get(Tsk.DURATION).convert(TimeUnitType.Minute).toDouble();
```

`mins` 变量现在保存了以分钟为单位的任务时长。

## Step 5: Duration in Days – How to get duration in days?
```java
// Get the duration in Days
double days = task.get(Tsk.DURATION).convert(TimeUnitType.Day).toDouble();
```

在需要按天粒度进行报告或资源分配时使用该值。

## Step 6: Duration in Hours – How to get duration in hours?
```java
// Get the duration in Hours
double hours = task.get(Tsk.DURATION).convert(TimeUnitType.Hour).toDouble();
```

小时单位适用于工时表或将一天拆分为多个工作班次的场景。

## Step 7: Duration in Weeks – How to get duration in weeks?
```java
// Get the duration in Weeks
double weeks = task.get(Tsk.DURATION).convert(TimeUnitType.Week).toDouble();
```

周单位常用于高层甘特图或里程碑规划。

## Step 8: Duration in Months – How to get duration in months?
```java
// Get the duration in Months
double months = task.get(Tsk.DURATION).convert(TimeUnitType.Month).toDouble();
```

月份级别的时长有助于将项目阶段与财务周期对齐。

## Common Issues and Solutions
| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| `NullPointerException` on `task` | Wrong task ID or missing children | Verify the task ID exists using `project.getRootTask().getChildren()` |
| Unexpected values (e.g., 0) | Project uses a custom calendar with non‑working days | Ensure the project’s calendar is correctly defined or use `project.getCalendar()` to inspect it |
| Conversion returns fractional weeks | Weeks are calculated based on the project’s default week length (usually 5 days) | Multiply by 5 if you need calendar weeks, or adjust the calendar settings |

## Frequently Asked Questions
### Q: Can I use Aspose.Tasks for Java with any Java IDE?
A: Yes, Aspose.Tasks for Java is compatible with any Java Integrated Development Environment (IDE)。

### Q: How can I obtain a task's ID in a Microsoft Project file?
A: You can inspect the project file manually or call `project.getRootTask().getChildren()` and iterate through the collection to read each task’s `ID`。

### Q: Is Aspose.Tasks suitable for handling large‑scale projects?
A: Absolutely. Aspose.Tasks is designed to efficiently process projects with thousands of tasks and resources。

### Q: Where can I find further documentation?
A: Visit the [documentation](https://reference.aspose.com/tasks/java/) for comprehensive API references, code samples, and best‑practice guides。

### Q: Can I try Aspose.Tasks for Java before purchasing?
A: Yes, you can explore a [free trial](https://releases.aspose.com/) to evaluate its capabilities。

---

**Last Updated:** 2026-02-28  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}