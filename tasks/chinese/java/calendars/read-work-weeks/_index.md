---
date: 2025-12-03
description: 学习如何使用 Aspose.Tasks 从 Microsoft Project 日历中读取工作周（Java），并按照逐步指南查看完整代码示例。
linktitle: Read Work Weeks from Calendar with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks 从 MS Project 日历读取工作周（Java）
url: /zh/java/calendars/read-work-weeks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 读取工作周 Java（来自 MS Project 日历） Aspose.Tasks

## 介绍
在本教程中，您将使用 Aspose.Tasks 库 **读取工作周 Java**，从 Microsoft Project 日历中提取工作周信息。无论您是在构建报表工具、同步进度表，还是自动化项目数据提取，能够以编程方式访问工作周定义都能节省大量手动工作时间。我们将演示所需的设置步骤，展示获取工作周详细信息的完整代码，并解释每一步，以便您将该方案应用到自己的项目中。

## 快速答案
- **“read work weeks java” 是什么意思？** 它指的是使用 Java 代码从 Project 文件中提取工作周定义。  
- **需要哪个库？** Aspose.Tasks for Java（提供免费试用）。  
- **开发时需要许可证吗？** 试用版可用于测试；生产环境需要商业许可证。  
- **支持哪些文件格式？** 同时支持 *.mpp* 和 Project XML 文件。  
- **实现需要多长时间？** 在库配置完成后，通常不到 10 分钟。

## 什么是 “read work weeks java”？
在 Java 中读取工作周是指使用 Aspose.Tasks API 访问 Microsoft Project 文件中日历对象的 `WorkWeekCollection`。每个 `WorkWeek` 包含起止日期以及每日工作时间定义，这些定义决定资源的排程方式。

## 为什么要从 Microsoft Project 日历读取工作周 Java？
- **自动化：** 消除手动复制粘贴进度数据的过程。  
- **集成：** 将工作周信息导入 ERP、HR 或自定义报表系统。  
- **一致性：** 确保所有下游工具遵循 Project 文件中定义的相同日历规则。

## 先决条件
在开始编写代码之前，请确保您已具备以下条件：

1. **Java Development Kit (JDK)** – 已安装 8 版或更高。  
2. **Aspose.Tasks for Java** – 从官方站点下载最新 JAR 包：[Aspose.Tasks for Java download](https://releases.aspose.com/tasks/java/)。  
3. 一个 **示例 Project 文件**（`ReadWorkWeeksInformation.mpp`），放置在已知文件夹中。

## 导入包
首先，导入与日历和工作周交互所需的类：

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
import com.aspose.tasks.WorkWeek;
import com.aspose.tasks.WorkWeekCollection;
import com.aspose.tasks.WorkingTimeCollection;
```

## 步骤 1：设置数据目录
定义包含 `.mpp` 文件的文件夹。将占位符替换为您机器上的实际路径：

```java
String dataDir = "Your Data Directory";
```

## 步骤 2：创建 Project 实例并访问日历
实例化 `Project` 对象，按 UID 选择所需日历，并获取其 `WorkWeekCollection`：

```java
Project project = new Project(dataDir + "ReadWorkWeeksInformation.mpp");
Calendar calendar = project.getCalendars().getByUid(3);
WorkWeekCollection collection = calendar.getWorkWeeks();
```

> **专业提示：** 如果不确定日历 UID，可以遍历 `project.getCalendars()` 并打印每个日历的名称和 UID。

## 步骤 3：遍历工作周
循环遍历每个 `WorkWeek`，显示其名称、起止日期以及每日工作时间：

```java
for (WorkWeek workWeek : collection) {
    // Display work week name, from and to dates
    System.out.println(workWeek.getName());
    System.out.println(workWeek.getFromDate());
    System.out.println(workWeek.getToDate());
    // Access week days and working times
    WeekDayCollection weekDays = workWeek.getWeekDays();
    for (WeekDay day : weekDays) {
        WorkingTimeCollection workingTimes = day.getWorkingTimes();
        // Further process working times if needed
    }
}
```

**您将看到的结果：** 控制台会打印每个工作周的标签（例如 “Standard”）、其有效日期范围，并可进一步查看每一天的具体工作时间。

## 常见问题及解决方案
| 问题 | 原因 | 解决方案 |
|------|------|----------|
| `NullPointerException` 在访问 `calendar` 时出现 | UID 错误或日历不存在 | 使用 `project.getCalendars().size()` 验证 UID，并先列出可用日历 |
| 工作周没有输出 | 所选日历没有自定义工作周（使用默认） | 使用默认日历 (`project.getDefaultCalendar()`) 或通过代码创建工作周 |
| 日期格式异常 | `System.out.println` 使用默认的 `java.util.Date` 格式 | 使用 `SimpleDateFormat` 按需格式化日期 |

## 常见问题

**问：我可以使用 Aspose.Tasks for Java 修改工作周信息吗？**  
答：可以。API 提供 `addWorkWeek()`、`removeWorkWeek()` 等方法，以及属性 setter 用于更改名称、日期和工作时间。

**问：Aspose.Tasks 是否兼容不同版本的 Microsoft Project 文件？**  
答：完全兼容。它支持从 Project 98 到最新版本的 MPP 文件，以及 Project XML 文件。

**问：我可以将 Aspose.Tasks 与其他 Java 框架集成吗？**  
答：可以。该库是纯 Java 实现，可与 Spring、Jakarta EE 或任何其他框架一起使用。

**问：Aspose.Tasks 是否提供试用版？**  
答：提供。您可以从官方站点下载 30 天免费试用版：[Aspose.Tasks trial](https://releases.aspose.com/)。

**问：在哪里可以获得 Aspose.Tasks 的支持？**  
答：Aspose 社区论坛是最佳渠道：[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)。

## 结论
您已经掌握了使用 Aspose.Tasks **读取工作周 Java** 的方法。按照上述步骤，您可以以编程方式从任何 MS Project 日历中提取工作周定义，将数据集成到应用程序中，并实现进度相关工作流的自动化。欢迎尝试创建或更新工作周——Aspose.Tasks 让这一过程变得轻而易举。

---

**最后更新：** 2025-12-03  
**测试环境：** Aspose.Tasks for Java 24.12（撰写时的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}