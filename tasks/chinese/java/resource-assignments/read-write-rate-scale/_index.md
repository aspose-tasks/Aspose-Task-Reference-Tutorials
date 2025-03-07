---
title: Aspose.Tasks 中资源分配的读写速率范围
linktitle: Aspose.Tasks 中资源分配的读写速率范围
second_title: Aspose.Tasks Java API
description: 通过这个综合教程，了解如何在 Aspose.Tasks for Java 中有效管理资源分配比例。
weight: 20
url: /zh/java/resource-assignments/read-write-rate-scale/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中资源分配的读写速率范围

## 介绍
在本教程中，我们将深入研究使用 Aspose.Tasks for Java 来管理资源分配率比例，Aspose.Tasks for Java 是一个用于以编程方式处理 Microsoft Project 文件的强大库。通过执行这些步骤，您将能够有效地操作 Java 应用程序中资源分配的速率比例设置。
## 先决条件
在我们开始之前，请确保您满足以下先决条件：
1. Java 开发环境：确保您的系统上安装了 Java 开发工具包 (JDK)。
2.  Aspose.Tasks for Java Library：下载并安装 Aspose.Tasks for Java 库[这里](https://releases.aspose.com/tasks/java/).

## 导入包
首先，您需要导入必要的包才能使用 Aspose.Tasks 功能。 
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```
## 第 1 步：设置您的项目
首先设置您的 Java 项目并将 Aspose.Tasks 库包含在您的依赖项中。
## 第 2 步：加载项目文件
将您想要使用的项目文件加载到您的 Java 应用程序中。
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```
## 第 3 步：添加任务
将新任务添加到您的项目中。
```java
Task task = project.getRootTask().getChildren().add("t1");
```
## 第 4 步：定义资源
定义物质和非物质资源并指定其类型。
```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```
## 步骤 5：为任务分配资源
将先前定义的资源及其费率等级类型分配给任务。
```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```
## 第 6 步：保存项目
保存具有修改后的资源分配的项目。
```java
project.save("output.mpp", SaveFileFormat.Mpp);
```
## 第 7 步：检索资源分配
重新加载已保存的项目并检索资源分配以验证费率比例设置。
```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## 结论
在 Aspose.Tasks for Java 中管理资源分配比例对于有效的项目管理至关重要。通过遵循此分步指南，您可以无缝地操作 Java 应用程序中资源分配的速率比例设置。
## 常见问题解答
### Q1：我可以在任何 Java IDE 中使用 Aspose.Tasks for Java 吗？
答：是的，Aspose.Tasks for Java 与所有主要 Java IDE 兼容，包括 IntelliJ IDEA、Eclipse 和 NetBeans。
### Q2：Aspose.Tasks 是否支持除 MPP 之外的其他文件格式？
答：是的，Aspose.Tasks 支持各种文件格式，包括 MPP、XML 和 HTML。
### Q3：Aspose.Tasks适合企业级项目管理吗？
答：当然，Aspose.Tasks 提供了管理任何规模项目的全面功能，使其适合企业级项目管理。
### 问题 4：我可以在费率范围之外进一步定制资源分配吗？
答：是的，Aspose.Tasks 提供了广泛的自定义资源分配功能，包括成本、工时和工期调整。
### Q5：有 Aspose.Tasks 支持的社区论坛吗？
答：是的，您可以在 Aspose.Tasks 论坛上找到支持并与其他用户互动[这里](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
