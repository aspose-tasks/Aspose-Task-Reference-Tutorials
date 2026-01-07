---
date: 2026-01-07
description: 了解如何使用 Aspose.Tasks for Java 将资源添加到项目并处理资源分配的平衡延迟属性。
linktitle: Handle Leveling Delay Properties for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何在 Aspose.Tasks 中向项目添加资源并处理平衡延迟属性
url: /zh/java/resource-assignments/leveling-delay-properties/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中向项目添加资源并处理平衡延迟属性

## 介绍
在本教程中，您将学习 **如何向项目添加资源**，并使用 Aspose.Tasks for Java 管理资源分配的平衡延迟属性。无论您是构建调度引擎还是自动化项目更新，掌握这些步骤都能让您在无需安装 Microsoft Project 的情况下保持项目数据的准确性。

## 快速回答
- **“向项目添加资源”是什么意思？** 它会创建一个可以分配给任务的新资源条目。  
- **分配后我可以设置平衡延迟吗？** 可以，使用 `Asn.DELAY` 或 `Asn.LEVELING_DELAY` 字段。  
- **运行此代码是否需要许可证？** 免费试用可用于开发；生产环境需要付费许可证。  
- **支持哪个 Java 版本？** Java 8 或更高版本。  
- **这是否兼容所有 MS Project 文件格式？** Aspose.Tasks 支持 .MPP、.XML、.XER 等格式。

## 在 Aspose.Tasks 中“向项目添加资源”是什么？
向项目添加资源是指在 `Project` 模型中创建一个 `Resource` 对象。该对象随后可以通过 `ResourceAssignment` 与任务关联，从而帮助您跟踪工作、成本和水平设置。

## 为什么要处理平衡延迟属性？
平衡延迟帮助调度器在资源超额分配时分散工作。通过设置延迟，您可以指示引擎推迟分配的开始时间，从而避免冲突并保持项目的现实性。

## 前置条件
在开始之前，请确保您具备以下前置条件：

1. Java Development Kit (JDK)：确保您的系统已安装 Java JDK。您可以从[网站](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html)下载并安装。  
2. Aspose.Tasks for Java 库：从[下载页面](https://releases.aspose.com/tasks/java/)下载 Aspose.Tasks for Java 库。

## 导入包
首先，将必要的包导入您的 Java 项目，以使用 Aspose.Tasks 功能：
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

## 步骤 1：创建 Project 对象
实例化一个 `Project` 对象，它将作为所有任务、资源和分配的容器：
```java
Project prj = new Project();
```

## 步骤 2：创建任务
向项目添加任务。这演示了如何以编程方式 **添加任务**：
```java
Task task = prj.getRootTask().getChildren().add("Task 1");
```

## 步骤 3：设置任务开始日期和持续时间
定义任务的开始时间以及持续时长：
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2000, Calendar.JANUARY, 3, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.DURATION, prj.getDuration(8));
```

## 步骤 4：添加资源
现在我们通过创建新的 `Resource` 条目来 **向项目添加资源**：
```java
Resource resource = prj.getResources().add("Resource 1");
```

## 步骤 5：创建资源分配
将任务与新添加的资源关联起来：
```java
ResourceAssignment assignment = prj.getResourceAssignments().add(task, resource);
```

## 步骤 6：设置平衡延迟
为该分配配置平衡延迟。将其设为零表示没有额外延迟，但您可以根据需要调整该值：
```java
assignment.set(Asn.DELAY, prj.getDuration(0, TimeUnitType.Day));
```

## 步骤 7：显示结果
打印重要属性以验证所有设置是否正确：
```java
System.out.println("Delay: " + assignment.get(Asn.DELAY));
System.out.println("Leveling Delay: " + assignment.get(Asn.LEVELING_DELAY));
System.out.println("Process completed Successfully");
```

## 常见陷阱与技巧
- **陷阱：** 忘记设置任务开始日期可能导致分配默认使用项目开始时间。  
- **技巧：** 使用 `prj.getDuration(value, TimeUnitType.Day)` 来控制延迟的粒度。  
- **技巧：** 添加多个资源后，调用 `prj.updateResourceAssignments()` 让调度器重新计算平衡。

## 结论
通过遵循这些步骤，您现在了解了 **如何向项目添加资源**，将其分配给任务，并使用 Aspose.Tasks for Java 管理平衡延迟属性。此知识使您能够构建稳健的项目自动化解决方案，使其与真实的资源约束保持同步。

## 常见问题

### 问：我可以将 Aspose.Tasks 与其他 Java 库一起使用吗？
答：可以，Aspose.Tasks 可以与其他 Java 库集成，以增强项目管理功能。

### 问：Aspose.Tasks 是否兼容不同版本的 Microsoft Project 文件？
答：是的，Aspose.Tasks 支持各种版本的 Microsoft Project 文件，确保在不同环境中的兼容性。

### 问：我在哪里可以找到 Aspose.Tasks 的额外支持？
答：您可以在 [Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15) 上找到支持和资源。

### 问：我可以在购买前试用 Aspose.Tasks 吗？
答：可以，您可以从 [发布页面](https://releases.aspose.com/) 获取 Aspose.Tasks 的免费试用版。

### 问：我如何获取 Aspose.Tasks 的临时许可证？
答：您可以在 [临时许可证页面](https://purchase.aspose.com/temporary-license/) 请求临时许可证用于评估。

## 其他常见问题

**问：如果我设置非零的平衡延迟会怎样？**  
答：调度器会将分配的开始时间推迟指定的时长，帮助解决超额分配问题。

**问：保存项目后我能获取平衡延迟吗？**  
答：可以，您可以重新打开项目文件并从分配中读取 `Asn.DELAY` 属性。

**问：有没有办法一次性对所有分配应用平衡延迟？**  
答：您可以遍历 `prj.getResourceAssignments()`，在循环中为每个分配设置延迟。

---

**最后更新：** 2026-01-07  
**测试环境：** Aspose.Tasks for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}