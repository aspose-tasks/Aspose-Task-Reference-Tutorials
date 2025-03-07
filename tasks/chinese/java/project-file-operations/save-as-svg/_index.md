---
title: 在 Java 中将 MS Project 转换为 SVG
linktitle: 在 Aspose.Tasks 中另存为 SVG
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks 库将 Microsoft Project 文件保存为 Java 中的 SVG。带有代码示例的分步指南。
weight: 18
url: /zh/java/project-file-operations/save-as-svg/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 中将 MS Project 转换为 SVG

## 介绍
Aspose.Tasks for Java 是一个功能强大的库，用于处理项目管理文件，允许开发人员操纵项目数据、执行各种操作并高效生成报告。在本教程中，我们将探讨如何使用 Aspose.Tasks for Java 将项目另存为 SVG。 SVG（可扩展矢量图形）是一种广泛用于在 Web 上显示矢量图形的格式，提供可扩展性和高质量渲染。
## 先决条件
在我们开始之前，请确保您具备以下条件：
### Java开发环境
确保您的系统上安装了 Java 开发工具包 (JDK)。您可以从 Oracle 网站下载并安装 JDK。
### Java 库的 Aspose.Tasks
从网站下载并安装 Aspose.Tasks for Java 库。您可以在提供的文档中找到下载链接[这里](https://releases.aspose.com/tasks/java/).

## 导入包
首先，您需要在 Java 程序中导入必要的包才能使用 Aspose.Tasks 功能。

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

现在让我们将提供的示例分解为多个步骤：
## 第2步：定义数据目录
```java
String dataDir = "Your Data Directory";
```
代替`"Your Data Directory"`以及项目文件所在目录的路径。
## 第 3 步：加载项目文件
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
此步骤从指定的数据目录加载名为“HomeMovePlan.mpp”的项目文件。
## 第 4 步：另存为 SVG
```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```
此步骤将加载的项目以 SVG 格式保存在指定的数据目录中，名称为“project5.svg”。

## 结论
在本教程中，我们学习了如何使用 Aspose.Tasks for Java 将项目另存为 SVG。通过遵循提供的步骤，您可以有效地将项目文件转换为 SVG 格式，从而实现与基于 Web 的应用程序或可视化工具的无缝集成。
## 常见问题解答
### Aspose.Tasks for Java 是否与所有版本的 Microsoft Project 文件兼容？
是的，Aspose.Tasks for Java 支持各种版本的 Microsoft Project 文件，包括 MPP、MPT 和 XML 格式。
### 我可以自定义 SVG 输出的外观吗？
是的，您可以通过调整字体、颜色和布局配置等参数来自定义 SVG 输出的外观。
### Aspose.Tasks for Java 是否需要商业用途许可证？
是的，Aspose.Tasks for Java 的商业用途需要有效的许可证。您可以从网站获取许可证[这里](https://purchase.aspose.com/temporary-license/).
### 我可以在购买前试用 Aspose.Tasks for Java 吗？
是的，您可以从网站请求免费试用 Aspose.Tasks for Java[这里](https://purchase.aspose.com/buy)评估其特性和功能。
### 在哪里可以获得 Aspose.Tasks for Java 的支持？
您可以通过访问论坛获得 Aspose.Tasks for Java 的支持[这里](https://forum.aspose.com/c/tasks/15)，您可以在其中提出问题并与社区互动。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
