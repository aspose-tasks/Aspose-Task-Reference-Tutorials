---
date: 2026-03-27
description: 学习如何使用 Aspose 和 Aspose.Tasks 通过 Java 从 Microsoft Project 文件中提取项目日历详情。一步一步的指南，附带代码示例。
linktitle: Retrieve Calendar Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks 检索 MS Project 日历信息
url: /zh/java/project-file-operations/retrieve-calendar-info/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks 检索 MS Project 日历信息

## 介绍
在本教程中，**您将了解如何使用 Aspose.Tasks** 以编程方式从 Microsoft Project 文件中检索日历信息。访问工作日、工作时间以及例外等日历数据在您需要**提取项目日历**以进行报告、集成或自定义调度逻辑时至关重要。让我们一步一步地演示整个过程，您将看到**如何使用 Aspose** 从 *.mpp* 文件中提取这些数据。

## 快速答案
- **本教程使用的库是什么？** Aspose.Tasks for Java。  
- **覆盖的主要关键字是什么？** *how to use aspose*。  
- **可以提取什么？** 项目日历，包括工作日和工作时间。  
- **需要许可证吗？** 提供免费试用版；生产环境需要许可证。  
- **支持的 Java 版本是什么？** Java 8 或更高。

## 什么是 Aspose.Tasks，为什么使用它？
Aspose.Tasks 是一个强大的 Java API，允许开发者在不依赖 Microsoft Project 本身的情况下读取、写入和操作 Microsoft Project 文件。通过使用 Aspose.Tasks，您可以**如何提取日历**信息、自动化进度计算，并将项目数据与其他企业系统集成——全部使用纯 Java 代码。

## 为什么要提取项目日历信息？
项目日历决定任务日期、资源分配以及整体时间线计算。提取这些数据可以帮助您：
- 生成反映实际工作安排的自定义报告。  
- 将 Microsoft Project 时间线与外部系统（ERP、BI 等）同步。  
- 通过编程方式修改日历设置进行假设分析。  
- **提取 MS Project 日历**数据，以迁移到其他规划工具。

## 前置条件
在开始之前，请确保您具备：

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

这些值以微秒为单位，正是 Aspose.Tasks 在内部存储时间的方式。

## 步骤 3：创建 Project 实例
将 Microsoft Project 文件加载到 `Project` 对象中。

```java
Project project = new Project(dataDir + "project.mpp");
```

`Project` 构造函数会解析 *.mpp* 文件，并通过 API 使所有项目数据（包括日历）可访问。

## 步骤 4：检索日历信息
获取项目中定义的日历集合。

```java
CalendarCollection alCals = project.getCalendars();
```

一个项目可以包含多个日历（标准、资源和自定义日历）。此集合让您能够访问每一个日历。

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

内部循环检查每个 `WeekDay` 对象。如果该天被标记为工作日，则打印出星期类型（Monday、Tuesday、…）以及计算后的工作小时数。

## 步骤 6：显示完成信息
标识提取过程已完成。

```java
System.out.println("Process completed Successfully");
```

## 常见问题及解决方案
| 问题 | 产生原因 | 解决方案 |
|-------|----------------|-----|
| **未返回任何日历** | 项目文件可能不包含自定义日历。 | 验证 *.mpp* 实际定义了日历，或在 Microsoft Project 中打开确认。 |
| **工作时间不正确** | 不同的 Project 版本导致时间转换常量不匹配。 | 如使用了更新的 Aspose.Tasks 版本，请调整 `OneSec`、`OneMin`、`OneHour`。 |
| **`NullPointerException` 在 `cal.getName()` 上** | 某些日历对象可能为 null。 | 在访问属性之前添加空检查（示例中已演示）。 |

## 常见问答

**问：可以在其他编程语言中使用 Aspose.Tasks 吗？**  
答：可以，Aspose.Tasks 支持多平台和多语言，包括 .NET、C++、Python 和 Java。

**问：Aspose.Tasks 有免费试用版吗？**  
答：有，您可以从 [here](https://releases.aspose.com/) 下载免费试用版。

**问：如何获取 Aspose.Tasks 的支持？**  
答：您可以在 Aspose.Tasks 社区论坛 [here](https://forum.aspose.com/c/tasks/15) 获得支持。

**问：可以购买临时许可证吗？**  
答：可以，临时许可证可在 [here](https://purchase.aspose.com/temporary-license/) 购买。

**问：在哪里可以找到 Aspose.Tasks 的详细文档？**  
答：请参考文档 [here](https://reference.aspose.com/tasks/java/)。  

## 结论
通过遵循上述步骤，**您现在已经了解如何使用 Aspose.Tasks 通过 Java 从 MS Project 文件中提取项目日历**信息。您可以将此逻辑集成到更大的应用程序中，自动化报告，或与其他企业系统同步日程。记住，掌握**如何使用 aspose**将为您打开众多高级项目管理自动化场景的大门。

---

**最后更新：** 2026-03-27  
**测试环境：** Aspose.Tasks for Java 24.12（撰写时的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}