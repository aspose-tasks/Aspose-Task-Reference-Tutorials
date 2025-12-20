---
date: 2025-12-20
description: 学习如何使用 Aspose.Tasks 通过 Java 从 Microsoft Project 文件中提取项目日历详细信息。提供代码示例的分步指南。
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks 检索 MS Project 日历信息
url: /zh/java/project-file-operations/retrieve-calendar-info/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks 获取 MS Project 日历信息

## 介绍
在本教程中，**您将了解如何使用 Aspose.Tasks**以编程方式从 Microsoft Project 文件中检索日历信息。获取工作日、工作时间以及例外情况等日历数据，对于在报告、集成或自定义调度逻辑中**提取项目日历**细节至关重要。让我们一步一步地完成整个过程。

## 快速答案
- **本教程使用的库是什么？** Aspose.Tasks for Java。  
- **覆盖的主要关键词是什么？** *how to use aspose.tasks*。  
- **可以提取哪些内容？** 项目日历，包括工作日和工作时间。  
- **需要许可证吗？** 提供免费试用版；生产环境需要许可证。  
- **支持的 Java 版本是？** Java 8 或更高。

## 为什么要提取项目日历信息？
项目日历决定任务日期、资源分配以及整体时间线计算。通过提取这些数据，您可以：
- 生成反映实际工作安排的自定义报告。  
- 将 Microsoft Project 时间线与外部系统（ERP、BI 等）同步。  
- 通过编程方式修改日历设置，进行情景分析。

## 前置条件
在开始之前，请确保您已具备：

- 基本的 Java 编程知识。  
- 已在系统上安装 Java Development Kit (JDK)。  
- Aspose.Tasks for Java 库。您可以从 [here](https://releases.aspose.com/tasks/java/) 下载。

## 导入包
首先，将必要的 Aspose.Tasks 类导入到您的 Java 项目中。

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```

## 步骤 1：设置数据目录
定义包含 *.mpp* 文件的文件夹。

```java
String dataDir = "Your Data Directory";
```

将 `"Your Data Directory"` 替换为 **project.mpp** 所在文件夹的绝对路径。

## 步骤 2：定义时间单位
创建常量，以帮助将内部时间表示转换为可读的小时数。

```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

这些值以微秒为单位，这是 Aspose.Tasks 在内部存储时间的方式。

## 步骤 3：创建 Project 实例
将 Microsoft Project 文件加载到 `Project` 对象中。

```java
Project project = new Project(dataDir + "project.mpp");
```

`Project` 构造函数会解析 *.mpp* 文件，并通过 API 使包括日历在内的所有项目数据可访问。

## 步骤 4：检索日历信息
获取项目中定义的日历集合。

```java
CalendarCollection alCals = project.getCalendars();
```

一个项目可以包含多个日历（标准、资源和自定义日历）。该集合让您能够访问每一个日历。

## 步骤 5：遍历日历
循环遍历每个日历，显示其 UID、名称以及对应的工作日和工作时间。

```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        // Calendar Information
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        // Iterate Through WeekDays
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); // Time in milliseconds
            double time = ts / (OneHour); // Convert to hours
            if (wd.getDayWorking()) {
                // Display Working Days and Hours
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```

内部循环检查每个 `WeekDay` 对象。如果该天被标记为工作日，则打印出星期类型（Monday、Tuesday 等）以及计算得到的工作小时数。

## 步骤 6：显示完成消息
标识提取过程已结束。

```java
System.out.println("Process completed Successfully");
```

## 结论
通过上述步骤，**您现在已经掌握了如何使用 Aspose.Tasks 通过 Java 从 MS Project 文件中提取项目日历**信息。您可以将此逻辑集成到更大的应用程序中，实现自动化报告或与其他企业系统同步日程。

## 常见问题

**问：我可以在其他编程语言中使用 Aspose.Tasks 吗？**  
答：可以，Aspose.Tasks 支持多平台和多语言，包括 .NET、C++、Python 和 Java。

**问：Aspose.Tasks 有免费试用版吗？**  
答：有，您可以从 [here](https://releases.aspose.com/) 下载免费试用版。

**问：如何获取 Aspose.Tasks 的支持？**  
答：您可以在 Aspose.Tasks 社区论坛 [here](https://forum.aspose.com/c/tasks/15) 获取支持。

**问：可以购买临时许可证吗？**  
答：可以，临时许可证可在 [here](https://purchase.aspose.com/temporary-license/) 购买。

**问：在哪里可以找到 Aspose.Tasks 的详细文档？**  
答：请参阅文档 [here](https://reference.aspose.com/tasks/java/)。

---

**最后更新：** 2025-12-20  
**测试环境：** Aspose.Tasks for Java 24.12（撰写时的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}