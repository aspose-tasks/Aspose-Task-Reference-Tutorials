---
title: Aspose.Tasks 中的渲染资源使用情况和工作表视图
linktitle: Aspose.Tasks 中的渲染资源使用情况和工作表视图
second_title: Aspose.Tasks Java API
description: 了解如何在 Aspose.Tasks for Java 中渲染 MS Project 资源使用情况和工作表视图。按照我们的分步指南轻松生成详细的 PDF 报告。
weight: 16
url: /zh/java/resource-management/render-resource-usage-sheet-view/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中的渲染资源使用情况和工作表视图

## 介绍
在本教程中，我们将学习如何使用 Aspose.Tasks for Java 渲染 MS Project 资源使用情况和工作表视图。 Aspose.Tasks 是一个功能强大的 Java 库，允许开发人员使用 Microsoft Project 文件，而无需安装 Microsoft Project。
## 先决条件
在开始之前，请确保您已安装并设置以下先决条件：
1. Java 开发工具包 (JDK)：确保您的系统上安装了 Java 开发工具包。您可以从 Oracle 网站下载并安装最新版本的 JDK。
2.  Aspose.Tasks for Java：从以下位置下载并安装 Aspose.Tasks for Java 库[下载页面](https://releases.aspose.com/tasks/java/).

## 导入包
首先，您需要将必要的包导入到您的 Java 项目中：
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```
## 第 1 步：阅读源项目
```java
//文档目录的路径。
String dataDir = "Your Data Directory";
//阅读源项目
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```
在此步骤中，我们指定源项目文件的路径（`ResourceUsageView.mpp` ）并使用`Project`类来阅读它。
## 步骤 2：使用所需的时间刻度设置定义 SaveOptions
```java
//将所需的 TimeScale 设置定义为 Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```
在这里，我们定义`SaveOptions`与所需的`TimeScale`设置。在这个例子中，我们设置`TimeScale`至天。
## 步骤 3：将演示格式设置为 ResourceUsage
```java
//将演示文稿格式设置为 ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```
我们将演示格式设置为`ResourceUsage`，表明我们要渲染资源使用情况视图。
## 第 4 步：保存项目
```java
//保存项目
project.save(dataDir + days, options);
```
最后，我们使用指定的选项保存项目。在此示例中，输出文件将另存为`result_days.pdf`.
## 第 5 步：渲染其他时间刻度设置的视图
重复步骤 2 到 4 以使用不同的时间刻度设置（ThirdsOfMonths 和 Months）渲染视图。
```java
//将时间刻度设置设置为 ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
//保存项目
project.save(thirds, options);
//将时间刻度设置设置为月
options.setTimescale(Timescale.Months);
//保存项目
project.save(dataDir + months, options);
```
确保更改`Timescale`为每个视图进行相应的设置。

## 结论
在本教程中，我们探索了如何使用 Aspose.Tasks for Java 来渲染 MS Project 资源使用情况和工作表视图。通过执行上述步骤，您可以高效地生成 PDF 格式的视图，从而更好地可视化和分析项目数据。
## 常见问题解答
### 除了资源使用情况和工作表之外，Aspose.Tasks 还可以渲染其他视图吗？
Aspose.Tasks 支持渲染各种视图，例如甘特图、任务使用情况和日历视图等。
### Aspose.Tasks 是否与不同版本的 Microsoft Project 文件兼容？
是的，Aspose.Tasks 支持多种 Microsoft Project 文件格式，包括 MPP、MPT 和 XML 格式。
### 我可以使用 Aspose.Tasks 自定义渲染视图的外观吗？
绝对地！ Aspose.Tasks 提供了广泛的选项来自定义渲染视图的外观和布局以满足您的特定要求。
### Aspose.Tasks 是否需要在系统上安装 Microsoft Project？
不需要，Aspose.Tasks 是一个独立的库，不需要安装 Microsoft Project 即可运行。
### Aspose.Tasks 用户可以获得技术支持吗？
是的，Aspose.Tasks 用户可以通过以下方式获得技术支持：[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
