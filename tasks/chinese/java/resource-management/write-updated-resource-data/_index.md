---
title: 在 Aspose.Tasks 中写入更新的资源数据
linktitle: 在 Aspose.Tasks 中写入更新的资源数据
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 轻松更新 MS Project 文件中的资源数据。
weight: 21
url: /zh/java/resource-management/write-updated-resource-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中写入更新的资源数据

## 介绍
在本教程中，我们将指导您使用 Aspose.Tasks for Java 更新 Microsoft Project 资源数据。 Aspose.Tasks 是一个功能强大的 Java API，允许您操作 Microsoft Project 文件，而无需在系统上安装 Microsoft Project。

## 先决条件

在我们开始之前，请确保您具备以下条件：

1. 您的系统上安装了 Java 开发工具包 (JDK)。
2.  Java 库的 Aspose.Tasks。您可以从以下位置下载：[这里](https://releases.aspose.com/tasks/java/).
3. Java 编程的基础知识。

## 导入包

首先，您需要导入必要的包以便在 Java 代码中使用 Aspose.Tasks。将以下导入语句添加到您的 Java 文件中：

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## 第 1 步：设置您的数据目录

定义数据文件所在的目录：

```java
String dataDir = "Your Data Directory";
```

## 第 2 步：指定输入和输出文件

定义输入 MS Project 文件和生成的更新文件的路径：

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; //使用一个 rsc 来更新测试文件
String resultFile = dataDir + "OutputMPP.mpp"; //编写测试项目的文件
```

## 第 3 步：加载项目

将 MS Project 文件加载到`Project`目的：

```java
Project project = new Project(file);
```

## 步骤 4：添加资源并设置属性

向项目添加新资源并设置其属性，例如标准费率、加班费率和组：

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## 第 5 步：保存项目

使用修改后的资源数据保存更新的项目：

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## 结论

在本教程中，我们演示了如何使用 Aspose.Tasks for Java 更新 MS Project 资源数据。通过执行这些步骤，您可以以编程方式有效地操作 MS Project 文件中的资源信息。

## 常见问题解答

### Q1：我可以使用 Aspose.Tasks for Java 更新同一项目中的多个资源吗？

A1：是的，您可以通过迭代多个资源并相应地设置它们的属性来更新它们。

### Q2：Aspose.Tasks 是否支持除 MS Project 之外的其他文件格式？

A2：是的，Aspose.Tasks 支持各种文件格式，包括 XML、MPP 等。

### Q3：Aspose.Tasks 是否兼容不同版本的 Java？

A3：Aspose.Tasks 与 Java 版本 6 及更高版本兼容。

### Q4：我可以使用 Aspose.Tasks 对 MS Project 文件执行其他操作吗？

A4：是的，您可以执行多种操作，例如读取、写入和操作任务、资源和日历。

### Q5：我在哪里可以找到有关 Aspose.Tasks 的其他帮助或支持？

 A5：您可以访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)如有任何帮助或疑问。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
