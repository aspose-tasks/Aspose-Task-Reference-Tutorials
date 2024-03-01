---
title: 在 Aspose.Tasks 中更新和重新安排 MS 项目
linktitle: 在 Aspose.Tasks 中更新项目并重新安排未完成的工作
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 以编程方式更新和重新安排 MS Project 文件。
type: docs
weight: 23
url: /zh/java/project-file-operations/update-project-reschedule-work/
---
## 介绍
Microsoft Project 是一种广泛使用的项目管理软件，允许用户有效地管理任务、资源和时间表。 Aspose.Tasks for Java 提供了一组强大的 API 来以编程方式操作 Microsoft Project 文件。在本教程中，我们将学习如何使用 Aspose.Tasks for Java 更新 MS Project 文件并重新安排未完成的工作。
## 先决条件
在我们开始之前，请确保您具备以下条件：
1. 您的系统上安装了 Java 开发工具包 (JDK)。
2.  Java 库的 Aspose.Tasks。您可以从以下位置下载：[这里](https://releases.aspose.com/tasks/java/).
3. 对 Java 编程语言有基本的了解。

## 导入包
首先，在 Java 代码中导入必要的包：
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
## 第 1 步：设置项目
初始化一个新的 Project 对象并在其中定义任务及其持续时间和依赖性。
```java
String dataDir = "Your Data Directory";
Project project = new Project();
//定义任务及其持续时间
//...
//定义任务依赖关系
//...
//保存初始项目状态
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```
## 第 2 步：更新项目工作
更新项目工作以将其标记为在特定日期之前完成。
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
//保存更新的项目
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```
## 第 3 步：重新安排未完成的工作
重新安排任何未完成的工作在指定日期之后开始。
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
//保存重新安排的项目
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## 结论
在本教程中，我们学习了如何使用 Aspose.Tasks for Java 更新 MS Project 文件并重新安排未完成的工作。这在项目时间表需要根据进度或变化的优先级进行调整的情况下特别有用。

## 常见问题解答
### 问：Aspose.Tasks for Java 可以处理复杂的项目结构吗？
答：是的，Aspose.Tasks for Java 提供了强大的 API 来有效地管理任务、依赖项、资源和其他项目元素。
### 问：Aspose.Tasks for Java 有试用版吗？
答：是的，您可以从以下位置获得免费试用[这里](https://releases.aspose.com/).
### 问：如何获得 Aspose.Tasks for Java 的支持？
答：您可以访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)如有任何帮助或疑问。
### 问：我可以购买 Aspose.Tasks for Java 的临时许可证吗？
答：是的，可以购买临时许可证[这里](https://purchase.aspose.com/temporary-license/).
### 问：在哪里可以找到 Aspose.Tasks for Java 的详细文档？
答：可以参考文档[这里](https://reference.aspose.com/tasks/java/)获取全面的指南和 API 参考。