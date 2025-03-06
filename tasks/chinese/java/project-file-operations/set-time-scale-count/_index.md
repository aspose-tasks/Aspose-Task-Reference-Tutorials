---
title: 在 Aspose.Tasks 中掌握 MS 项目时间尺度计数
linktitle: 在 Aspose.Tasks 中设置时间刻度计数
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 有效管理 MS Project 中的时间刻度计数。轻松优化项目可视化和管理。
weight: 22
url: /zh/java/project-file-operations/set-time-scale-count/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中掌握 MS 项目时间尺度计数

## 介绍
在 MS Project 中管理时间尺度计数可以显着影响项目可视化和管理。借助 Aspose.Tasks for Java（一种用于以编程方式处理项目管理任务的强大 API），您可以有效地操作时间刻度计数，以根据您的特定需求定制项目视图。
## 先决条件
在开始之前，请确保您已具备以下条件：
1. Java 开发环境：确保您的系统上安装了 Java 开发工具包 (JDK)。
2.  Aspose.Tasks for Java 库：下载并安装 Aspose.Tasks for Java 库。你可以从[这里](https://releases.aspose.com/tasks/java/).
3. Java 编程基础知识：熟悉 Java 编程语言将会很有帮助。

## 导入包
将必要的包导入到您的 Java 项目中：
```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## 第1步：设置数据目录
定义将存储项目文件的数据目录的路径：
```java
String dataDir = "Your Data Directory";
```
代替`"Your Data Directory"`与您的数据目录的路径。
## 第2步：创建项目实例
实例化一个新的`Project`目的：
```java
Project project = new Project();
```
这将创建一个新的项目对象。
## 步骤 3：配置甘特图视图
创建一个`GanttChartView`对象来配置甘特图视图：
```java
GanttChartView view = new GanttChartView();
```
## 步骤 4：设置底层的时间刻度计数
设置底部时间刻度层的计数和刻度可见性：
```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```
这指定间隔计数以及是否显示底层的刻度。
## 步骤 5：设置中间层的时间刻度计数
同样，配置中间时间刻度层：
```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```
## 第 6 步：将视图添加到项目中
将配置好的视图添加到项目中：
```java
project.getViews().add(view);
```
这会将自定义视图添加到项目中。
## 第7步：将测试数据添加到项目中
项目中添加一些测试数据进行演示：
```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```
这将创建两个具有指定持续时间的任务。
## 第 8 步：将项目另存为 PDF
将项目另存为 PDF 文件：
```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```
这会将应用了配置的项目保存到 PDF 文件中。

## 结论
使用 Aspose.Tasks for Java 有效管理 MS Project 中的时间刻度计数，使您能够自定义项目视图，以实现更好的可视化和管理。
## 常见问题解答
### 问：Aspose.Tasks for Java 可以处理大型项目文件吗？
答：是的，Aspose.Tasks for Java 能够有效地处理大型项目文件。
### 问：Aspose.Tasks for Java 是否与不同的 Java IDE 兼容？
答：是的，Aspose.Tasks for Java 可以与流行的 Java 集成开发环境 (IDE) 无缝协作，例如 Eclipse 和 IntelliJ IDEA。
### 问：我可以使用 Aspose.Tasks for Java 自定义甘特图的外观吗？
答：当然，Aspose.Tasks for Java 提供了广泛的功能，可以根据您的要求自定义甘特图的外观。
### 问：Aspose.Tasks for Java 有试用版吗？
答：是的，您可以从以下位置获取免费试用版[这里](https://releases.aspose.com/).
### 问：在哪里可以获得 Aspose.Tasks for Java 的支持？
答：您可以在 Aspose.Tasks 论坛上找到支持和帮助[这里](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
