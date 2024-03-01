---
title: 在 Aspose.Tasks 中监控加班、剩余成本和工作
linktitle: 在 Aspose.Tasks 中监控加班、剩余成本和工作
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks 监控加班、剩余成本以及 Java 项目中的工作。有效项目管理的简单步骤。
type: docs
weight: 18
url: /zh/java/resource-assignments/overtime-remaining-costs-work/
---
## 介绍
在本教程中，我们将学习如何使用 Aspose.Tasks for Java 来监控项目中的加班、剩余成本和工作。这对于项目经理和团队领导来说非常宝贵，可以确保项目按计划进行并在预算之内。
## 先决条件
在我们开始之前，请确保您具备以下条件：
1. Java 开发工具包 (JDK)：Aspose.Tasks for Java 需要 Java SE 6 或更高版本。
2.  Aspose.Tasks for Java Library：从以下位置下载并安装该库[这里](https://releases.aspose.com/tasks/java/).
3. 集成开发环境 (IDE)：任何 Java IDE，例如 Eclipse、IntelliJ IDEA 或 NetBeans。

## 导入包
首先在 Java 文件中导入必要的包：
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
```

## 第 1 步：设置数据目录
定义项目文件所在的目录：
```java
String dataDir = "Your Data Directory";
```
代替`"Your Data Directory"`与您的项目文件的路径。
## 第 2 步：加载项目
实例化一个`Project`对象并加载项目文件：
```java
Project project = new Project(dataDir + "ResourceAssignmentOvertimes.mpp");
```
代替`"ResourceAssignmentOvertimes.mpp"`与您的项目文件的名称。
## 第 3 步：迭代资源分配
循环遍历项目中的每个资源分配：
```java
for (ResourceAssignment ra : project.getResourceAssignments()) {
```
## 第 4 步：打印加班费用和工时
检索并打印每个资源分配的加班成本和工时：
```java
    System.out.println(ra.get(Asn.OVERTIME_COST));
    System.out.println(ra.get(Asn.OVERTIME_WORK).toString());
```
## 第 5 步：打印剩余成本和工作
检索并打印每个资源分配的剩余成本和工时：
```java
    System.out.println(ra.get(Asn.REMAINING_COST));
    System.out.println(ra.get(Asn.REMAINING_WORK).toString());
```
## 步骤 6：打印剩余加班成本和工时
检索并打印每个资源分配的剩余加班成本和工时：
```java
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_COST));
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_WORK).toString());
}
```

## 结论
监控项目中的加班时间、剩余成本和工作量对于成功的项目管理至关重要。借助 Aspose.Tasks for Java，您可以轻松访问和跟踪这些信息，确保您的项目按计划进行并在预算之内。
## 常见问题解答
### 我可以将 Aspose.Tasks for Java 与其他 Java 库一起使用吗？
是的，Aspose.Tasks for Java 与其他 Java 库和框架兼容。
### Aspose.Tasks 支持不同的项目文件格式吗？
是的，Aspose.Tasks 支持各种项目文件格式，包括 MPP、XML 等。
### 有试用版吗？
是的，您可以从以下位置下载免费试用版[这里](https://releases.aspose.com/).
### 如果遇到问题，我可以在哪里找到支持？
您可以访问 Aspose.Tasks 论坛[这里](https://forum.aspose.com/c/tasks/15)为了支持。
### 如何购买 Aspose.Tasks 的许可证？
您可以从以下位置购买许可证[这里](https://purchase.aspose.com/buy).