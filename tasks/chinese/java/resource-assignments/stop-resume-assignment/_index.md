---
title: 停止和恢复 Aspose.Tasks 中的资源分配
linktitle: 停止和恢复 Aspose.Tasks 中的资源分配
second_title: Aspose.Tasks Java API
description: 通过此分步教程，了解如何在 Aspose.Tasks for Java 中有效管理资源分配。
weight: 23
url: /zh/java/resource-assignments/stop-resume-assignment/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 停止和恢复 Aspose.Tasks 中的资源分配

## 介绍
在本教程中，我们将学习如何使用 Aspose.Tasks for Java 停止和恢复资源分配。 Aspose.Tasks 是一个功能强大的 Java API，允许开发人员使用 Microsoft Project 文件，而无需在其系统上安装 Microsoft Project。我们将把这个过程分解为可管理的步骤，以便于遵循。
## 先决条件
在我们开始之前，请确保您满足以下先决条件：
- 您的系统上安装了 Java 开发工具包 (JDK)。
- 下载了 Java 库的 Aspose.Tasks。您可以从以下位置下载：[这里](https://releases.aspose.com/tasks/java/).
- 对 Java 编程有基本的了解。
## 导入包
首先，让我们将必要的包导入到我们的 Java 项目中：
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```
## 第 1 步：加载项目文件
```java
//文档目录的路径。
String dataDir = "Your Data Directory";
//加载项目文件
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```
在此步骤中，我们将项目文件加载到`Project`使用文件路径的对象。
## 第 2 步：迭代资源分配
```java
//定义最短日期
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
//迭代资源分配
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```
在这里，我们定义一个最短日期并开始迭代项目中的每个资源分配。
## 第 3 步：检查停止和恢复日期
```java
    //检查停止日期
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    //检查简历日期
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```
在此步骤中，我们检查每个资源分配的停止日期和恢复日期是否早于最短日期。如果是，我们打印“NA”，否则，我们打印相应的日期。
## 结论
在本教程中，我们学习了如何在 Aspose.Tasks for Java 中停止和恢复资源分配。通过遵循提供的步骤，您可以在 Java 项目中轻松实现此功能。

## 常见问题解答
### 我可以在未安装 Microsoft Project 的情况下使用 Aspose.Tasks 吗？
是的，Aspose.Tasks 允许您使用 Microsoft Project 文件，而无需在系统上安装 Microsoft Project。
### 在哪里可以找到更多文档？
你可以找到详细的文档[这里](https://reference.aspose.com/tasks/java/).
### 有免费试用吗？
是的，您可以获得免费试用[这里](https://releases.aspose.com/).
### 如果遇到任何问题，我如何获得支持？
您可以获得社区的支持[这里](https://forum.aspose.com/c/tasks/15).
### 我可以购买临时许可证吗？
是的，您可以购买临时许可证[这里](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
