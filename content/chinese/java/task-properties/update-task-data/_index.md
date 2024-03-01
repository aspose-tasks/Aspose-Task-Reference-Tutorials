---
title: 在 Aspose.Tasks 中将任务数据更新为 MPP 格式
linktitle: 在 Aspose.Tasks 中将任务数据更新为 MPP 格式
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 将任务数据更新为 MPP 格式。遵循我们的高效项目管理分步指南。
type: docs
weight: 35
url: /zh/java/task-properties/update-task-data/
---
## 介绍
欢迎阅读我们有关使用 Aspose.Tasks for Java 将任务数据更新为 MPP 格式的分步指南。在本教程中，我们将引导您完成整个过程，确保您清楚地掌握每个步骤。 Aspose.Tasks for Java 提供了一个用于处理 Microsoft Project 文件的强大解决方案，在本指南结束时，您将能够高效地更新 MPP 格式的任务数据。
## 先决条件
在我们深入学习本教程之前，请确保您具备以下先决条件：
-  Aspose.Tasks for Java：确保您已安装 Aspose.Tasks 库。您可以从[发布页面](https://releases.aspose.com/tasks/java/).
- Java 开发工具包 (JDK)：确保您的系统上安装了 Java。
- 集成开发环境 (IDE)：使用您选择的 IDE 进行 Java 开发。
## 导入包
首先将必要的包导入到您的 Java 项目中。以下代码片段演示了如何导入包：
```java
import com.aspose.tasks.ConstraintType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.examples.TaskLinks.UpdatedTaskLinkDataToMpp;
```
## 1. 创建并配置初始任务
```java
//文档目录的路径。
String dataDir = "Your Document Directory";
long OneSec = 1000;
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
Project project = new Project(dataDir + "project.xml");
Task task1 = project.getRootTask().getChildren().add("First task");
//...（继续其余代码）
```
## 2. 设置开始日期和持续时间
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 12, 10, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task1.set(Tsk.START, cal.getTime());
task1.set(Tsk.DURATION, project.getDuration(24, TimeUnitType.Hour));
//...（继续其余代码）
```
## 3. 创建摘要任务
```java
Task summary = project.getRootTask().getChildren().add("Summary task");
summary.getChildren().add(task1);
//...（继续其余代码）
```
## 4.设定截止日期和任务说明
```java
cal.setTime(task1.get(Tsk.START));
cal.add(java.util.Calendar.DATE, 10);
task1.set(Tsk.DEADLINE, cal.getTime());
task1.set(Tsk.NOTES_TEXT, "The first task.");
//...（继续其余代码）
```
## 5. 配置任务约束
```java
task1.set(Tsk.DURATION_FORMAT, TimeUnitType.DayEstimated);
task1.set(Tsk.CONSTRAINT_TYPE, ConstraintType.FinishNoLaterThan);
//...（继续其余代码）
```
## 6. 创建附加任务
```java
//创建 10 个新任务
for (int i = 0; i < 10; i++) {
    //...（继续其余代码）
}
//...（继续其余代码）
```
## 7. 保存项目
```java
//保存项目
project.save(dataDir + "WritingUpdatedTaskDataToMpp.mpp", SaveFileFormat.Mpp);
```
通过执行这些步骤，您已使用 Aspose.Tasks for Java 成功将任务数据更新为 MPP 格式。
## 结论
恭喜！您已经完成了有关使用 Aspose.Tasks for Java 更新 MPP 格式的任务数据的综合指南。这个功能强大的库简化了项目管理任务，使其成为 Java 开发人员的宝贵工具。
## 常见问题解答
### 问：在哪里可以找到 Aspose.Tasks for Java 文档？
答：文档已提供[这里](https://reference.aspose.com/tasks/java/).
### 问：如何下载 Aspose.Tasks for Java？
答：您可以从以下网址下载[发布页面](https://releases.aspose.com/tasks/java/).
### 问：有免费试用吗？
答：是的，您可以免费试用[这里](https://releases.aspose.com/).
### 问：在哪里可以获得 Aspose.Tasks for Java 的支持？
答：访问支持论坛[这里](https://forum.aspose.com/c/tasks/15).
### 问：你们是否提供用于测试目的的临时许可证？
答：是的，您可以获得临时许可证[这里](https://purchase.aspose.com/temporary-license/).