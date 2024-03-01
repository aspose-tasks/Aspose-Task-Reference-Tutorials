---
title: 在 Aspose.Tasks 中另存为 PDF
linktitle: 在 Aspose.Tasks 中另存为 PDF
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 将项目文件转换为 PDF。简单的步骤即可实现高效转换。
type: docs
weight: 17
url: /zh/java/project-file-operations/save-as-pdf/
---
## 介绍
在本教程中，我们将指导您完成使用 Aspose.Tasks for Java 将项目另存为 PDF 的过程。使用Aspose.Tasks，您可以有效地将项目文件转换为PDF格式，确保兼容性和易于共享。让我们深入了解步骤：
## 先决条件
开始之前，请确保您具备以下条件：
1. Java 开发工具包 (JDK)：确保您的系统上安装了 JDK。
2.  Aspose.Tasks for Java Library：下载并安装 Aspose.Tasks 库。你可以找到下载链接[这里](https://releases.aspose.com/tasks/java/).
3. 项目文件：准备好要转换为 PDF 的项目文件（例如 HomeMovePlan.mpp）。

## 导入包
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
```
## 第 1 步：读取输入项目文件
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```
确保更换`"Your Data Directory"`包含项目文件的数据目录的路径。
## 第 2 步：将项目另存为 PDF
```java
project.save(dataDir + "Project5.pdf", SaveFileFormat.Pdf);
```
此代码片段将项目另存为 PDF 文件，名称为“Project5.pdf”。
## 第 3 步：使内容适合单元格大小
```java
Project project1 = new Project(dataDir + "project6.mpp");
SaveOptions o = new PdfSaveOptions();
o.setFitContent(true);
o.setTimescale(Timescale.Months);
o.setPresentationFormat(PresentationFormat.TaskUsage);
```
在这里，我们设置保存 PDF 的选项，包括适合的内容、时间刻度和演示格式。
## 第 4 步：隐藏图例
```java
o.setLegendOnEachPage(false);
```
此步骤隐藏 PDF 每页上的图例。
## 第 5 步：使用应用的选项保存项目
```java
project1.save(dataDir + "result_months_WithoutLegend.pdf", o);
```
最后，此代码将应用了选项的项目保存到 PDF 文件中。

## 结论
在本教程中，我们学习了如何使用 Aspose.Tasks for Java 将项目另存为 PDF。通过执行这些简单的步骤，您可以有效地转换项目文件，以便于共享和分发。
## 常见问题解答
### 问：Aspose.Tasks 是否与所有版本的 Java 兼容？
答：是的，Aspose.Tasks 支持从 JDK 6 及更高版本开始的 Java 版本。
### 问：我可以自定义 PDF 输出的外观吗？
答：当然！ Aspose.Tasks 提供了各种选项来根据您的要求自定义 PDF 输出。
### 问：Aspose.Tasks 是否支持其他文件格式转换？
答：是的，Aspose.Tasks 支持多种文件格式，包括 MPP、XML、XLSX 等。
### 问：Aspose.Tasks 有试用版吗？
答：是的，您可以从以下位置获得 Aspose.Tasks 的免费试用版：[这里](https://releases.aspose.com/).
### 问：我在哪里可以获得 Aspose.Tasks 的支持？
答： 如需支持和帮助，您可以访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15).