---
title: 在 Aspose.Tasks 中高效管理 MS 项目属性
linktitle: 管理 Aspose.Tasks 中的默认项目属性
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 管理默认的 MS Project 属性。轻松简化您的项目管理工作流程。
type: docs
weight: 11
url: /zh/java/project-management/default-properties/
---
## 介绍
您是否希望使用 Aspose.Tasks for Java 简化您的项目管理流程？管理 Microsoft Project 文件中的默认属性可以显着提高效率。在本教程中，我们将逐步说明如何使用 Aspose.Tasks 管理默认的 MS Project 属性。
## 先决条件
在我们深入研究本教程之前，请确保您具备以下先决条件：
### 1.Java开发工具包（JDK）
   - 确保您的系统上安装了 JDK。
   - 您可以从以下位置下载：[这里](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
### 2. Java 库的 Aspose.Tasks
   - 下载 Aspose.Tasks for Java 库并将其包含在您的项目中。
   - 您可以从[网站](https://releases.aspose.com/tasks/java/).
## 导入包
首先，在 Java 文件中导入必要的包：
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```
让我们将这个过程分解为可管理的步骤：
## 第 1 步：加载项目文件
```java
//文档目录的路径。
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## 第 2 步：显示默认属性
```java
//显示默认属性
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("New Task Default Start: " + project.get(Prj.DEFAULT_START_TIME));
System.out.println("New Task Default Type: " + project.get(Prj.DEFAULT_TASK_TYPE));
System.out.println("Resource Default Standard Rate: " + project.get(Prj.DEFAULT_STANDARD_RATE));
System.out.println("Resource Default Overtime Rate: " + project.get(Prj.DEFAULT_OVERTIME_RATE));
System.out.println("Default Task EV Method: " + project.get(Prj.DEFAULT_TASK_EV_METHOD));
System.out.println("Default Cost Accrual: " + project.get(Prj.DEFAULT_FIXED_COST_ACCRUAL));
```
## 步骤 3：设置默认属性
```java
//设置默认属性
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.DEFAULT_START_TIME, project.get(Prj.START_DATE));
project.set(Prj.DEFAULT_TASK_TYPE, TaskType.FixedDuration);
project.set(Prj.DEFAULT_STANDARD_RATE, 15d);
project.set(Prj.DEFAULT_OVERTIME_RATE, 12d);
project.set(Prj.DEFAULT_TASK_EV_METHOD, EarnedValueMethodType.PercentComplete);
project.set(Prj.DEFAULT_FIXED_COST_ACCRUAL, CostAccrualType.Prorated);
```
## 第 4 步：将项目保存为 XML 格式
```java
//将项目保存为 XML 格式
project.save(dataDir + "project4.xml", SaveFileFormat.Xml);
```
## 第5步：显示结果
```java
//显示转换结果。
System.out.println("Process completed Successfully");
```
通过执行这些步骤，您可以使用 Aspose.Tasks for Java 有效管理默认的 MS Project 属性。
## 结论
在本教程中，我们学习了如何使用 Aspose.Tasks for Java 管理默认的 MS Project 属性。通过利用这些技术，您可以优化项目管理工作流程，提高生产力和组织能力。
## 常见问题解答
### Q1：我可以将 Aspose.Tasks 与其他编程语言一起使用吗？
A1：是的，Aspose.Tasks 支持各种编程语言，例如.NET、Python 和 Java。
### Q2：Aspose.Tasks 适合个人和企业使用吗？
A2：当然！无论您是管理小型个人项目还是大型企业计划，Aspose.Tasks 都能满足您的需求。
### Q3：Aspose.Tasks 提供客户支持吗？
A3：是的，您可以在[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15).
### Q4：我可以在购买前试用 Aspose.Tasks 吗？
 A4：当然！您可以从以下网站获得免费试用[网站](https://releases.aspose.com/).
### Q5：如何获得Aspose.Tasks的临时许可证？
 A5：您可以从以下机构获得临时许可证：[购买页面](https://purchase.aspose.com/temporary-license/)用于测试和评估目的。