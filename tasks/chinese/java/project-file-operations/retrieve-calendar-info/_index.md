---
title: 在 Aspose.Tasks 中检索 MS 项目日历信息
linktitle: 在 Aspose.Tasks 中检索日历信息
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 检索 MS Project 日历信息。以编程方式访问日历详细信息的分步指南。
weight: 14
url: /zh/java/project-file-operations/retrieve-calendar-info/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中检索 MS 项目日历信息

## 介绍
在本教程中，我们将探讨如何使用 Aspose.Tasks for Java 库从 Microsoft Project 文件中检索日历信息。 Aspose.Tasks 提供了强大的功能来操作项目数据，包括访问日历详细信息，例如工作日和时间。
## 先决条件
在我们开始之前，请确保您具备以下条件：
- Java 编程的基础知识。
- 您的系统上安装了 Java 开发工具包 (JDK)。
-  Java 库的 Aspose.Tasks。您可以从以下位置下载：[这里](https://releases.aspose.com/tasks/java/).
## 导入包
首先，您需要在 Java 代码中导入必要的包才能使用 Aspose.Tasks 功能。
```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.CalendarCollection;
import com.aspose.tasks.Project;
import com.aspose.tasks.WeekDay;
import com.aspose.tasks.WeekDayCollection;
```
现在让我们将提供的示例分解为多个步骤以便更好地理解。
## 第1步：设置数据目录
```java
String dataDir = "Your Data Directory";
```
代替`"Your Data Directory"`以及项目文件目录的路径。
## 第 2 步：定义时间单位
```java
long OneSec = 10000000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```
这些常数表示以微秒为单位的时间单位。
## 第3步：创建项目实例
```java
Project project = new Project(dataDir + "project.mpp");
```
这一行创建了一个实例`Project`类，使用项目文件的路径对其进行初始化（`project.mpp`）。
## 第 4 步：检索日历信息
```java
CalendarCollection alCals = project.getCalendars();
```
在这里，我们检索项目文件中存在的日历集合。
## 第 5 步：迭代日历
```java
for (Calendar cal : alCals) {
    if (cal.getName() != null) {
        //日历信息
        System.out.println("Calendar UID : " + cal.getUid());
        System.out.println("Calendar Name : " + cal.getName());
        //迭代工作日
        WeekDayCollection alDays = cal.getWeekDays();
        for (WeekDay wd : alDays) {
            double ts = wd.getWorkingTime(); //时间（以毫秒为单位）
            double time = ts / (OneHour); //转换为小时
            if (wd.getDayWorking()) {
                //显示工作日和时间
                System.out.print(wd.getDayType() + ":");
                System.out.print("Working Time:" + time + " Hours");
                System.out.println(", Ticks = " + ts);
            }
        }
    }
}
```
此循环遍历每个日历并打印其 UID、名称、工作日以及相应的工作时间。
## 第 6 步：显示完成消息
```java
System.out.println("Process completed Successfully");
```
最后，将显示一条消息，指示该过程已完成。
## 结论
在本教程中，我们学习了如何使用 Aspose.Tasks for Java 从 MS Project 文件检索日历信息。通过执行这些步骤，您可以有效地访问和操作 Java 应用程序中的项目数据。

## 常见问题解答
### 问：我可以将 Aspose.Tasks 与其他编程语言一起使用吗？
答：是的，Aspose.Tasks支持多种平台和编程语言，包括.NET、C++、Python 和 Java。
### 问：Aspose.Tasks 是否有免费试用版？
答：是的，您可以从以下位置下载免费试用版：[这里](https://releases.aspose.com/).
### 问：如何获得 Aspose.Tasks 的支持？
答：您可以从 Aspose.Tasks 社区论坛获得支持[这里](https://forum.aspose.com/c/tasks/15).
### 问：我可以购买 Aspose.Tasks 的临时许可证吗？
答：是的，可以购买临时许可证[这里](https://purchase.aspose.com/temporary-license/).
### 问：在哪里可以找到 Aspose.Tasks 的详细文档？
答：可以参考文档[这里](https://reference.aspose.com/tasks/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
