---
title: 处理 Aspose.Tasks 中的调平延迟属性
linktitle: 处理 Aspose.Tasks 中资源分配的调配延迟属性
second_title: Aspose.Tasks Java API
description: 通过这个综合教程，了解如何在 Aspose.Tasks for Java 中处理资源分配的调平延迟属性。
weight: 17
url: /zh/java/resource-assignments/leveling-delay-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 处理 Aspose.Tasks 中的调平延迟属性

## 介绍
在本教程中，我们将逐步介绍在 Aspose.Tasks for Java 中处理资源分配的均衡延迟属性的过程。 Aspose.Tasks 是一个功能强大的 Java 库，允许您使用 Microsoft Project 文件，而无需在系统上安装 Microsoft Project。
## 先决条件
在我们开始之前，请确保您具备以下先决条件：
1.  Java 开发工具包 (JDK)：确保您的系统上安装了 Java JDK。您可以从以下位置下载并安装它[网站](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Aspose.Tasks for Java 库：从以下位置下载 Aspose.Tasks for Java 库：[下载页面](https://releases.aspose.com/tasks/java/).

## 导入包
首先，将必要的包导入到您的 Java 项目中以使用 Aspose.Tasks 功能：
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## 第 1 步：创建项目对象
实例化一个`Project`目的：
```java
Project prj = new Project();
```
## 第 2 步：创建任务
向项目添加任务：
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```
## 步骤 3：设置任务开始日期和持续时间
设置任务的开始日期和持续时间：
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```
## 第 4 步：添加资源
向项目添加资源：
```java
Resource resource = prj.getResources().add("Resource 1");
```
## 步骤 5：创建资源分配
为任务和资源创建资源分配：
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```
## 第6步：设置调平延迟
设置分配的调平延迟：
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```
## 第 7 步：显示结果
打印平层延迟及其他相关信息：
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## 结论
在本教程中，我们学习了如何处理 Aspose.Tasks for Java 中资源分配的均衡延迟属性。通过执行以下步骤，您可以有效地管理 Java 项目中的资源分配。
## 常见问题解答
### 问：我可以将 Aspose.Tasks 与其他 Java 库一起使用吗？

答：是的，Aspose.Tasks 可以与其他 Java 库集成，以增强项目管理能力。

### 问：Aspose.Tasks 是否与不同版本的 Microsoft Project 文件兼容？

答：是的，Aspose.Tasks 支持各种版本的 Microsoft Project 文件，确保不同环境之间的兼容性。

### 问：在哪里可以找到对 Aspose.Tasks 的额外支持？

答：您可以在以下位置找到支持和资源：[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15).

### 问：我可以在购买前试用 Aspose.Tasks 吗？

答：是的，您可以从 Aspose.Tasks 获取免费试用版[发布页面](https://releases.aspose.com/).

### 问：如何获得 Aspose.Tasks 的临时许可证？

答：您可以向以下机构申请临时许可证[临时许可证页面](https://purchase.aspose.com/temporary-license/)出于评估目的。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
