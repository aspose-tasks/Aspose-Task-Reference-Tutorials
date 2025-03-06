---
title: 使用 Aspose.Tasks for Java 读取 Primavera 的 MS 项目
linktitle: 在 Aspose.Tasks 中读取 Primavera 的项目
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 从 Primavera XML 无缝读取 MS Project 文件。提高您的项目管理效率。
weight: 20
url: /zh/java/project-management/read-primavera/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks for Java 读取 Primavera 的 MS 项目

## 介绍
在项目管理中，不同软件平台之间的互操作性对于无缝工作流程至关重要。 Aspose.Tasks for Java 提供了从 Primavera XML 读取 Microsoft Project 文件的强大功能。本教程将指导您完成使用 Aspose.Tasks for Java 从 Primavera 读取 MS Project 文件的过程，从而使您能够有效地检查任务的 Primavera 特定属性。
## 先决条件
在继续之前，请确保您已安装并设置以下先决条件：
1. Java 开发工具包 (JDK)：确保您的系统上安装了 JDK。
2.  Aspose.Tasks for Java：从以下位置下载并安装 Aspose.Tasks for Java：[这里](https://releases.aspose.com/tasks/java/).

## 导入包
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```
## 第 1 步：设置数据目录
```java
String dataDir = "Your Data Directory";
```
确保更换`"Your Data Directory"`与数据目录的实际路径。
## 第 2 步：从 Primavera XML 读取项目
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
确保更换`"PrimaveraProject.xml"`与您的 Primavera XML 文件的实际名称。
## 第 3 步：迭代任务并检索 Primavera 特定属性
```java
for (Task task : project.enumerateAllChildTasks()) {
    System.out.println("Task '" + task.getName() + "'");
    
    if (task.isSummary()) {
        System.out.println("WBS Sequence number: " + task.getPrimaveraProperties().getSequenceNumber());
    } else {
        System.out.println("Task ActivityId: " + task.getPrimaveraProperties().getActivityId());
    }
    
    System.out.println("Activity Type: " + task.getPrimaveraProperties().getActivityType());
    System.out.println("Duration Type: " + task.getPrimaveraProperties().getDurationType());
    System.out.println("Percent Complete Type: " + task.getPrimaveraProperties().getPercentCompleteType());
    System.out.println("Original Duration: " + TimeDelta.fromMilliseconds(task.getDuration().getTimeSpan()).getTotalHours());
    System.out.println("At Complete Duration: " +
            (TimeDelta.fromMilliseconds(task.getActualDuration().getTimeSpan()).getTotalHours() + TimeDelta.fromMilliseconds(task.getRemainingDuration().getTimeSpan()).getTotalHours()));
    System.out.println("Duration % Complete: " + task.getPrimaveraProperties().getDurationPercentComplete());
    System.out.println("Physical % Complete: " + task.getPrimaveraProperties().getPhysicalPercentComplete());
    
    System.out.println("Task RemainingEarlyStart: " + task.getPrimaveraProperties().getRemainingEarlyStart());
    System.out.println("Task RemainingEarlyFinish: " + task.getPrimaveraProperties().getRemainingEarlyFinish());
    
    System.out.println("Actual costs:");
    System.out.println(task.getPrimaveraProperties().getActualExpenseCost() + ", "
                    + task.getPrimaveraProperties().getActualLaborCost() + ", "
                    + task.getPrimaveraProperties().getActualMaterialCost() + ", "
                    + task.getPrimaveraProperties().getActualNonlaborCost() + ", Total: "
                    + task.getPrimaveraProperties().getActualTotalCost());
    
    System.out.println("Labor Units:");
    System.out.println(task.getPrimaveraProperties().getActualLaborUnits() + ", " +
            task.getPrimaveraProperties().getActualNonLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingNonLaborUnits());
    
    System.out.println("Units % Complete: " + task.getPrimaveraProperties().getUnitsPercentComplete());
}
```
此代码循环访问项目中的每个任务，打印相关的 Primavera 特定属性。

## 结论
在本教程中，您学习了如何使用 Aspose.Tasks for Java 从 Primavera XML 读取 MS Project 文件。此功能可以跨不同平台无缝集成和分析项目数据，从而提高整体项目管理效率。
## 常见问题解答
### 问：我可以使用 Aspose.Tasks for Java 修改任务的 Primavera 特定属性吗？
答：是的，Aspose.Tasks for Java 提供 API 来根据需要修改任务的 Primavera 特定属性。
### 问：Aspose.Tasks for Java 支持读取其他项目文件格式吗？
答：是的，Aspose.Tasks for Java 支持读取各种项目文件格式，包括 MPP、XML 和 Primavera XML。
### 问：Aspose.Tasks for Java 适合企业级项目管理应用程序吗？
答：当然，Aspose.Tasks for Java 提供了强大的功能和可扩展性，使其适合企业级项目管理应用程序。
### 问：我可以使用 Aspose.Tasks for Java 从 Primavera 项目中提取资源信息吗？
答：是的，Aspose.Tasks for Java 允许您从 Primavera 项目中提取资源信息以及任务详细信息。
### 问：在哪里可以找到 Aspose.Tasks for Java 的其他支持或文档？
答：您可以找到全面的文档并访问论坛以获得有关[Aspose.Tasks for Java 文档](https://reference.aspose.com/tasks/java/)页。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
