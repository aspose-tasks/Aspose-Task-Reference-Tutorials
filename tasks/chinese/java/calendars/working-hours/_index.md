---
date: 2026-02-05
description: 了解如何通过使用 Aspose.Tasks for Java 从 MS Project 日历中提取工作时间来确定工作日并计算任务持续时间。
linktitle: Determine Working Days & Working Hours with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks 确定工作日和工作时间
url: /zh/java/calendars/working-hours/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 确定工作日和工作时间

## 介绍
管理项目日历是成功项目规划的核心部分。在本教程中，您将 **确定任何任务的工作日** 并 **从 MS Project 日历中提取工作时间**，使用 Aspose.Tasks for Java。完成本指南后，您将能够 **计算任务工期**、自定义工作时间，并可靠地 **加载 MPP 文件** 以获取所需数据。您还将看到如何 **在未安装 Microsoft Project 的情况下读取 MS Project 文件**，实现跨平台自动化。

## 快速答案
- **“确定工作日”是什么意思？** 它指的是识别给定任务的日历日期哪些被视为工作日。  
- **应该使用哪个库？** Aspose.Tasks for Java 提供了完整的 API 用于操作 MS Project 文件。  
- **实现大概需要多长时间？** 基本提取通常需要 10–15 分钟。  
- **需要许可证吗？** 提供免费试用；生产环境需要商业许可证。  
- **可以自定义工作时间吗？** 可以 – 您可以修改日历、添加假期，并设置自定义工作时间范围。  

## 什么是 “确定工作日”？
当任务被安排时，项目日历定义了哪些天是工作日，哪些是非工作日（周末、假期）。确定工作日意味着查询该日历，以准确了解何时可以进行工作，这对于精确 **计算任务工期** 至关重要。

## 为什么使用 Aspose.Tasks 来检索工作时间？
- **无需 Microsoft Project** – 您可以直接在 Java 代码中读取 MS Project 文件。  
- **完整的日历支持** – 包括默认日历、资源日历和任务日历。  
- **高性能** – 能快速处理大型项目。  
- **文档丰富** – 示例和 API 参考随手可得。

## 前置条件
在开始之前，请确保您已具备：

1. **Java Development Kit (JDK)** – 8 版或更高。  
2. **Aspose.Tasks for Java** – 从 [here](https://releases.aspose.com/tasks/java/) 下载最新 JAR。  
3. 基本的 Java 编程知识。  

## 导入包
首先，导入 Aspose.Tasks 的核心命名空间：

```java
import com.aspose.tasks.*;
```

## 如何使用 Aspose.Tasks 加载 MPP 文件？
加载项目文件是进行任何日历分析的第一步。API 让您只需一行代码即可 **加载 MPP 文件**，无需 MS Project UI。

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## 检索任务和日历信息
选择要分析的任务并获取其关联的日历。这一步是 **检索任务工作时间** 的关键：

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## 定义开始和结束日期
设置您想要 **确定工作日** 的时间窗口。使用任务的开始和结束日期可确保只评估相关期间。

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## 遍历日期
遍历任务持续期间的每一天。此循环稍后可用于 **自定义工作时间**（如有需要）：

```java
java.util.Calendar tempDate = calStartDate;
```

## 计算工期
在遍历过程中，我们检查每一天是否为工作日，累计工作小时，最终计算任务的分钟、小时和天数工期。此步骤演示了如何以编程方式 **计算工作日** 和 **计算任务工期**。

```java
double durationInMins = 0;
double durationInHours = 0;
double durationInDays = 0;
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
long timeSpan;
while (tempDate.before(calEndDate)) {
    if (taskCalendar.isDayWorking(tempDate.getTime())) {
        timeSpan = (long) taskCalendar.getWorkingHours(tempDate.getTime());
        durationInMins += (double) timeSpan / OneMin;
        durationInHours += (double) timeSpan / OneHour;
        if ((timeSpan / OneHour) > 0) {
            durationInDays += ((double) timeSpan / OneHour / 8.0);
        }
    }
    tempDate.add(java.util.Calendar.DATE, 1);
}
System.out.println("Duration in Minutes = " + durationInMins);
System.out.println("Duration in Hours = " + durationInHours);
System.out.println("Duration in Days = " + durationInDays);
System.out.println();
```

## 如何自定义工作时间和假期
Aspose.Tasks 允许您修改日历的工作时间范围并添加假期等例外。您可以调用 `taskCalendar.addWorkingTime()` 或 `taskCalendar.addException()` 来根据组织政策定制日程。当默认的 9‑5 工作制不符合实际情况时，这非常有用。

## 常见问题及解决方案
| 问题 | 解决方案 |
|-------|----------|
| **任务返回 `null` 的日历** | 确认任务实际分配了日历；否则它会继承项目的默认日历。 |
| **因假期导致工期不正确** | 检查假期是否已在任务日历或项目基础日历中定义。 |
| **时区不匹配** | 如有需要，使用 `java.util.TimeZone` 将日历时区与系统对齐。 |

## 常见问答
### Q: Aspose.Tasks for Java 能处理复杂的项目结构吗？
A: 能，Aspose.Tasks for Java 提供全面支持，能够处理包括任务、资源和日历在内的复杂项目结构。

### Q: Aspose.Tasks for Java 与不同版本的 MS Project 兼容吗？
A: 完全兼容，Aspose.Tasks for Java 支持多种 MS Project 版本，确保在不同环境下均可使用。

### Q: 我可以在项目日历中自定义工作时间和假期吗？
A: 可以，使用 Aspose.Tasks for Java API，您可以轻松根据项目需求自定义工作时间和假期。

### Q: Aspose.Tasks for Java 是否提供支持和文档？
A: 提供，Aspose.Tasks for Java 拥有丰富的文档和专门的支持论坛，帮助开发者有效使用其功能。

### Q: 是否有 Aspose.Tasks for Java 的试用版？
A: 有，您可以从 [here](https://releases.aspose.com/) 获取免费试用版。

## 结论
本指南演示了如何使用 Aspose.Tasks for Java **确定工作日**、**检索工作时间**，以及 **计算任务工期**，从 MS Project 日历中提取数据。按照上述步骤，您可以实现日程分析自动化、定制日历，并保持项目计划的准确和最新。现在，您已经掌握了 **读取 MS Project** 数据、**加载 MPP 文件** 并在无需 Microsoft Project 的情况下进行精确工期计算的工具。

---

**最后更新：** 2026-02-05  
**测试环境：** Aspose.Tasks for Java 24.12（撰写时的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}