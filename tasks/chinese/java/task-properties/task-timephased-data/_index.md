---
title: Aspose.Tasks 中的任务时间分段数据
linktitle: Aspose.Tasks 中的任务时间分段数据
second_title: Aspose.Tasks Java API
description: 探索 Aspose.Tasks for Java 和主任务时间分段数据管理。下载该库，享受免费试用，并简化您的项目跟踪。
weight: 34
url: /zh/java/task-properties/task-timephased-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中的任务时间分段数据

## 介绍
在项目管理领域，精确跟踪任务时间分段数据对于高效的项目执行至关重要。 Aspose.Tasks for Java 成为简化此过程的强大工具，提供强大的功能和灵活性。本教程将指导您利用 Aspose.Tasks for Java 有效管理任务时间分段数据。
## 先决条件
在深入学习本教程之前，请确保您具备以下先决条件：
- Java 开发环境：确保您的系统上安装了 Java。
-  Aspose.Tasks for Java Library：下载 Aspose.Tasks 库并将其包含在您的项目中。你可以找到图书馆[这里](https://releases.aspose.com/tasks/java/).
- 文档目录：为您的项目文档设置目录。
## 导入包
在您的 Java 项目中，导入 Aspose.Tasks 所需的包：
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
import java.math.BigDecimal;
import java.util.Date;
import java.util.List;
```
## 第 1 步：设置项目开始日期
```java
Project project = new Project(dataDir + "project.xml");
//包导入的附加代码
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
说明：初始化一个日历对象，设置开始日期，并将其应用到项目中。
## 第 2 步：定义任务和资源
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
说明：创建任务和资源，设置标准加班费率。
## 第 3 步：设置任务持续时间
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
说明：定义任务的持续时间（例如，6 天）。
## 步骤 4：将资源分配给任务
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
说明：将资源分配给任务。
## 步骤 5：配置资源分配
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
说明： 设置资源分配的停止、恢复、工作轮廓等参数。
## 第 6 步：设置基线
```java
project.setBaseline(BaselineType.Baseline);
```
说明： 为项目建立基线。
## 第7步：更新任务完成情况
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
说明：表示任务的完成百分比。
## 第 8 步：检索时间分段数据
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
说明：检索分配的剩余工时的时间分段数据。
## 第 9 步：显示时间分段数据
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
//用于显示其他值的附加代码
```
说明： 输出并显示时间分段数据。
## 结论
有效管理任务时间分段数据对于项目成功至关重要。 Aspose.Tasks for Java 简化了这个过程，提供了一套全面的功能。通过遵循本教程，您可以将 Aspose.Tasks 无缝集成到您的 Java 项目中，确保精确控制项目时间表和资源分配。
## 经常问的问题
### 问：我可以在任何 Java 项目中使用 Aspose.Tasks for Java 吗？
答：是的，Aspose.Tasks for Java 与任何基于 Java 的项目兼容。
### 问：在哪里可以找到 Aspose.Tasks for Java 的其他支持？
答：访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)以寻求支持和讨论。
### 问：Aspose.Tasks for Java 是否有免费试用版？
答：是的，您可以尝试免费试用[这里](https://releases.aspose.com/).
### 问：如何获得 Aspose.Tasks for Java 的临时许可证？
答：您可以获得临时许可证[这里](https://purchase.aspose.com/temporary-license/).
### 问：哪里可以购买 Aspose.Tasks for Java？
答：您可以购买 Aspose.Tasks for Java[这里](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
