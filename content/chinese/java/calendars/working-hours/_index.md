---
title: 使用 Aspose.Tasks 从日历获取工作时间
linktitle: 使用 Aspose.Tasks 从日历获取工作时间
second_title: Aspose.Tasks Java API
description: 使用 Aspose.Tasks for Java 轻松从 MS Project 日历中提取工作时间。简化项目管理任务。
type: docs
weight: 13
url: /zh/java/calendars/working-hours/
---
## 介绍
管理项目日历和提取工作时间对于有效的项目管理至关重要。 Aspose.Tasks for Java 提供了强大的功能，可以轻松地从 MS Project 日历中检索工作时间。在本教程中，我们将逐步指导您完成该过程。
## 先决条件
在深入学习本教程之前，请确保您具备以下先决条件：
1. 您的系统上安装了 Java 开发工具包 (JDK)。
2.  Aspose.Tasks for Java 库下载并添加到您的项目中。您可以从以下位置下载：[这里](https://releases.aspose.com/tasks/java/).
3. 对 Java 编程语言有基本的了解。
## 导入包
首先，导入使用 Aspose.Tasks for Java 所需的包：
```java
import com.aspose.tasks.*;
```
## 第 1 步：加载项目文件
首先加载您的 MS Project 文件：
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## 第 2 步：检索任务和日历信息
从项目中提取任务和日历详细信息：
```java
Task task = project.getRootTask().getChildren().getById(1);
Calendar taskCalendar = task.get(Tsk.CALENDAR);
```
## 第 3 步：定义开始和结束日期
设置任务的开始和结束日期：
```java
java.util.Calendar calStartDate = java.util.Calendar.getInstance();
calStartDate.setTime(task.get(Tsk.START));
java.util.Calendar calEndDate = java.util.Calendar.getInstance();
calEndDate.setTime(task.get(Tsk.FINISH));
```
## 第 4 步：迭代日期
迭代任务持续时间内的日期：
```java
java.util.Calendar tempDate = calStartDate;
```
## 第 5 步：计算持续时间
计算持续时间（以分钟、小时和天为单位）：
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
## 结论
在本教程中，我们介绍了如何使用 Aspose.Tasks for Java 从 MS Project 日历中检索工作时间。通过执行这些步骤，您可以有效地管理项目进度并轻松计算任务工期。
## 常见问题解答
### 问：Aspose.Tasks for Java 可以处理复杂的项目结构吗？
答：是的，Aspose.Tasks for Java 为处理复杂的项目结构（包括任务、资源和日历）提供了全面的支持。
### 问：Aspose.Tasks for Java 是否与不同版本的 MS Project 兼容？
答：当然，Aspose.Tasks for Java 支持各种版本的 MS Project，确保不同环境之间的兼容性。
### 问：我可以在项目日历中自定义工作时间和假期吗？
答：是的，您可以使用 Aspose.Tasks for Java API 根据您的项目要求轻松自定义工作时间和假期。
### 问：Aspose.Tasks for Java 是否提供支持和文档？
答：是的，Aspose.Tasks for Java 提供了广泛的文档和专门的支持论坛，以帮助开发人员有效地利用其功能。
### 问：Aspose.Tasks for Java 有试用版吗？
答：是的，您可以访问 Aspose.Tasks for Java 的免费试用版：[这里](https://releases.aspose.com/).