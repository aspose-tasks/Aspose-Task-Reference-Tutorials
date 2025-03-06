---
title: Aspose.Tasks 中的任务基线持续时间管理
linktitle: Aspose.Tasks 中的任务基线持续时间管理
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 在 MS Project 中高效管理任务基线。本教程将指导您逐步完成该过程。
type: docs
weight: 12
url: /zh/java/task-baselines/task-baseline-duration/
---
## 介绍
在 MS Project 中管理任务基线对于项目规划和跟踪至关重要。在本教程中，我们将探讨如何使用 Aspose.Tasks for Java 有效管理任务基线持续时间。
## 先决条件
在我们开始之前，请确保您具备以下条件：
1. Java 开发环境：确保您的系统上安装了 Java 开发工具包 (JDK)。
2.  Aspose.Tasks 库：下载并安装 Aspose.Tasks for Java 库[这里](https://releases.aspose.com/tasks/java/).

## 导入包
首先，导入 Java 项目所需的包：
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```
## 第1步：创建项目实例
使用以下代码初始化一个新的项目实例：
```java
Project project = new Project();
```
## 第 2 步：创建任务基线
创建一个新任务并使用以下代码设置其基线：
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```
## 步骤 3：显示任务基线信息
检索并显示任务基线信息，例如持续时间、开始日期、完成日期等：
```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```
## 第 4 步：检查中期基准和固定成本
检查基线是否是临时基线并检索与其相关的任何固定成本：
```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```
## 第 5 步：打印时间分段数据
打印与任务基线关联的时间分段数据：
```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```
通过执行以下步骤，您可以使用 Aspose.Tasks for Java 有效管理 MS Project 中的任务基线持续时间。

## 结论
管理任务基线对于项目管理至关重要，它使您能够跟踪与计划进度的偏差。借助 Aspose.Tasks for Java，该流程变得精简且高效，从而实现更好的项目控制和交付。
## 常见问题解答
### MS Project 中的任务基线是什么？
MS Project 中的任务基线是任务的初始计划时间表的快照，包括其开始日期、完成日期和持续时间。
### 为什么管理任务基线很重要？
管理任务基线有助于将计划进度与项目的实际进度进行比较，从而促进更好的跟踪和决策。
### 任务基线设置后我可以修改吗？
是的，您可以在 MS Project 中修改任务基线以反映项目计划中的更改。但是，必须记录与原始基线的任何偏差。
### Aspose.Tasks 是否支持其他项目管理功能？
是的，Aspose.Tasks 为项目管理提供了广泛的功能，包括任务调度、资源分配和甘特图生成。
### 在哪里可以找到对 Aspose.Tasks 的支持？
您可以在以下位置找到对 Aspose.Tasks 的支持[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)，您可以在其中提出问题并与其他用户互动。