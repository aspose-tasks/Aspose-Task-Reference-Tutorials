---
date: 2025-12-05
description: 学习如何通过使用 Aspose.Tasks for Java 从 MS Project 日历中提取工作时间来确定工作日并计算任务持续时间。
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
管理项目日历是成功项目规划的核心部分。在本教程中，您将使用 Aspose.Tasks for Java **确定任何任务的工作日** 并 **从 MS Project 日历中提取工作时间**。完成本指南后，您将能够 **计算任务持续时间**、自定义工作时间，并可靠地 **加载 MPP 文件** 以获取所需数据。

## 快速答案
- **What does “determine working days” mean?** 它指的是识别给定任务的哪些日历日期被视为工作日。  
- **Which library should I use?** Aspose.Tasks for Java 提供了完整的 API 用于处理 MS Project 文件。  
- **How long does the implementation take?** 通常需要 10–15 分钟进行基本提取。  
- **Do I need a license?** 提供免费试用；生产环境需要商业许可证。  
- **Can I customize working hours?** 是的——您可以修改日历、添加假期并设置自定义工作时间范围。

## 什么是“determine working days”？
当任务被安排时，项目日历定义了哪些天是工作日，哪些是非工作日（周末、假期）。确定工作日意味着查询该日历以准确了解何时可以进行工作，这精确的 **calculate task duration** 计算至关重要。

## 为什么使用 Aspose.Tasks 检索工作时间？
- **No Microsoft Project required** – 在任何平台上处理 .MPP 文件。  
- **Full calendar support** – 包括默认、资源和任务日历。  
- **High performance** – 快速处理大型项目。  
- **Extensive documentation** – 示例和 API 参考随时可用。

## 前提条件
1. **Java Development Kit (JDK)** – 版本 8 或更高。  
2. **Aspose.Tasks for Java** – 从 [here](https://releases.aspose.com/tasks/java/) 下载最新的 JAR。  
3. 基本的 Java 编程知识。  

## 导入包
首先，导入核心 Aspose.Tasks 命名空间：

```java
import com.aspose.tasks.*;
```

## 步骤 1：加载 MPP 文件
加载您的项目文件（**load mpp file** 步骤），以便使用其日历：

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## 步骤 2：检索任务和日历信息
选择要分析的任务并获取其关联的日历。这就是我们为任务 **retrieve working hours** 的位置：

```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```

## 步骤 3：定义开始和结束日期
设置您想要 **determine working days** 的时间窗口：

```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```

## 步骤 4：遍历日期
遍历任务持续期间的每个日期。如果需要，此循环将帮助我们后续 **customize working hours**。

```java
java.util.Calendar tempDate = calStartDate;
```

## 步骤 5：计算持续时间
在遍历过程中，我们检查每一天是否为工作日，累计工作小时数，最终计算任务的持续时间（分钟、小时和天）：

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

## 常见问题及解决方案
| 问题 | 解决方案 |
|-------|----------|
| **Task returns `null` for calendar** | 确保任务实际分配了日历；否则它将继承项目的默认日历。 |
| **Incorrect duration because of holidays** | 验证假期是否已在任务的日历或项目的基础日历中定义。 |
| **Time zone mismatch** | 如有需要，使用 `java.util.TimeZone` 将日历的时区与系统对齐。 |

## 常见问题
### Q: Aspose.Tasks for Java 能处理复杂的项目结构吗？
A: 是的，Aspose.Tasks for Java 提供了全面的支持，能够处理包括任务、资源和日历在内的复杂项目结构。

### Q: Aspose.Tasks for Java 与不同版本的 MS Project 兼容吗？
A: 当然，Aspose.Tasks for Java 支持各种版本的 MS Project，确保在不同环境中的兼容性。

### Q: 我可以在项目日历中自定义工作时间和假期吗？
A: 是的，您可以使用 Aspose.Tasks for Java API 根据项目需求轻松自定义工作时间和假期。

### Q: Aspose.Tasks for Java 提供支持和文档吗？
A: 是的，Aspose.Tasks for Java 提供了丰富的文档和专门的支持论坛，帮助开发者有效使用其功能。

### Q: 是否有 Aspose.Tasks for Java 的试用版？
A: 是的，您可以从 [here](https://releases.aspose.com/) 获取 Aspose.Tasks for Java 的免费试用版。

## 结论
在本指南中，我们演示了如何使用 Aspose.Tasks for Java 从 MS Project 日历中 **determine working days**、**retrieve working hours** 和 **calculate task duration**。按照上述步骤，您可以自动化进度分析、定制日历，并保持项目计划的准确和最新。

---

**Last Updated:** 2025-12-05  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}