---
date: 2025-12-02
description: 学习如何使用 Aspose.Tasks for Java 设置日历、定义 MS Project 的工作日以及自定义工作日。只需几行代码即可将项目保存为
  XML。
linktitle: How to Set Calendar and Define Weekdays in MS Project with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks 在 MS Project 中设置日历并定义工作日
url: /zh/java/calendars/define-weekdays/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 MS Project 中使用 Aspose.Tasks 设置日历并定义工作日

## 介绍
在本教程中，您将学习 **如何设置日历** 设置并使用 Aspose.Tasks for Java 在 Microsoft Project 文件中定义工作日。无论您是需要创建标准工作周、添加周末工作日，还是配置短星期五工作安排，本指南都会一步步带您完成——从项目创建到将文件保存为 XML。

## 快速答案
- **需要哪个库？** Aspose.Tasks for Java  
- **可以添加周末工作日吗？** 可以——只需将星期六和星期日设为工作日。  
- **如何保存项目？** 使用 `prj.save(..., SaveFileFormat.Xml)`。  
- **需要许可证吗？** 免费试用可用于评估；生产环境需要许可证。  
- **需要哪个 Java 版本？** Java 8 或更高。

## 在 MS Project 中 “如何设置日历” 是什么意思？
在 MS Project 中设置日历意味着定义哪些天是工作日、每日工作时间以及假期等例外情况。该日历决定任务调度、资源分配以及整体项目时间线。

## 为什么使用 Aspose.Tasks 进行日历操作？
- **完全控制** – 可在不打开 UI 的情况下以编程方式创建、修改或删除日历。  
- **跨平台** – 在任何支持 Java 的操作系统上均可运行。  
- **支持所有文件格式** – MPP、MPT 和 XML，您可以 *将项目保存为 XML*，便于与其他系统集成。  
- **无 COM 依赖** – 与 Microsoft Project Interop 库不同。

## 前置条件
在开始之前，请确保您已经：

1. **Java Development Kit (JDK) 8+** – 从 [Oracle website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) 下载。  
2. **Aspose.Tasks for Java** – 从 [Aspose.Tasks download page](https://releases.aspose.com/tasks/java/) 获取最新 JAR。  
3. 一个 IDE 或构建工具（Maven/Gradle），用于将 Aspose.Tasks JAR 添加到项目的类路径中。

## 导入包
首先，导入您需要的类。这些导入让您能够访问项目、日历和工作时间对象。

```java
import com.aspose.tasks.*;
import java.util.GregorianCalendar;
```

## 步骤指南

### 步骤 1：创建 Project 实例
创建一个新的 `Project` 对象。该对象代表您将要编辑的 MS Project 文件。

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project prj = new Project();
```

### 步骤 2：定义新日历
向项目中添加一个全新的日历。为其取一个清晰的名称有助于在拥有多个日历时进行区分。

```java
Calendar cal = prj.getCalendars().add("Calendar1");
```

### 步骤 3：添加标准工作日（周一‑周四）
使用内置帮助方法 `WeekDay.createDefaultWorkingDay` 为核心工作周设置默认的 9 am‑5 pm 工作时间表。

```java
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Monday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Tuesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Wednesday));
cal.getWeekDays().add(WeekDay.createDefaultWorkingDay(DayType.Thursday));
```

### 步骤 4：添加周末工作日
如果您的项目在周末也要运行，只需将星期六和星期日添加为常规工作日。这演示了 **添加周末工作日** 的操作。

```java
cal.getWeekDays().add(new WeekDay(DayType.Saturday));
cal.getWeekDays().add(new WeekDay(DayType.Sunday));
```

### 步骤 5：设置自定义短工作日（星期五）
这里我们 **设置自定义工作日** 为星期五：上午班（9 am‑12 pm）和下午班（1 pm‑4 pm）。

```java
WeekDay myWeekDay = new WeekDay(DayType.Friday);
WorkingTime wt1 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 9, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 12, 0, 0).getTime()
);
WorkingTime wt2 = new WorkingTime(
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 13, 0, 0).getTime(),
    new GregorianCalendar(1, java.util.Calendar.JANUARY, 1, 16, 0, 0).getTime()
);
myWeekDay.getWorkingTimes().add(wt1);
myWeekDay.getWorkingTimes().add(wt2);
myWeekDay.setDayWorking(true);
cal.getWeekDays().add(myWeekDay);
```

### 步骤 6：将项目保存为 XML
最后，持久化更改。`SaveFileFormat.Xml` 选项让您 **将项目保存为 XML**，这对于与其他工具的集成非常有用。

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

## 常见问题与解决方案
| 问题 | 解决方案 |
|-------|----------|
| **工作时间未生效** | 确保在自定义 `WeekDay` 上调用了 `setDayWorking(true)`。 |
| **保存时文件未找到** | 检查 `dataDir` 是否指向已存在的文件夹，并确认应用程序拥有写入权限。 |
| **日历未在任务中体现** | 使用 `task.setCalendar(cal)` 将新建的日历分配给资源或任务。 |

## 常见问答

**问：可以使用 Aspose.Tasks for Java 定义自定义非工作日吗？**  
答：可以。对任何想设为非工作日的 `WeekDay` 将 `DayWorking` 属性设为 `false` 即可。

**问：如何添加假期或全公司统一的例外？**  
答：创建 `CalendarException` 对象，指定例外日期，然后将其添加到 `cal.getExceptions()`。

**问：该库是否兼容旧版 MS Project？**  
答：完全兼容。Aspose.Tasks 支持跨多个 Project 版本的 MPP、MPT 和 XML 格式。

**问：可以修改已导入项目中的现有日历吗？**  
答：可以，使用 `new Project("existing.mpp")` 加载项目，获取目标日历，进行修改后保存。

**问：Aspose.Tasks 还能处理循环任务吗？**  
答：可以，使用 `RecurringTask` 类创建和编辑循环任务。

## 结论
现在，您已经掌握了 **如何设置日历** 设置、**在 MS Project 中定义工作日**、添加周末工作日以及创建短星期五工作安排——全部使用 Aspose.Tasks for Java。将结果保存为 XML，并将日历逻辑集成到任何基于 Java 的项目管理解决方案中。

---

**最后更新：** 2025-12-02  
**测试环境：** Aspose.Tasks for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}