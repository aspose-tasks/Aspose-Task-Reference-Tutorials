---
date: 2025-12-21
description: 了解如何使用 Aspose.Tasks for Java 自定义甘特图视图、管理项目可视化，并将项目保存为 PDF。轻松调整时间刻度计数。
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 自定义甘特图 – 掌握 Aspose.Tasks 中的 MS Project 时间尺度计数
url: /zh/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 自定义甘特图 – 精通 Aspose.Tasks 中的 MS Project 时间尺度计数

## 介绍
如果您需要在 Microsoft Project 中 **自定义甘特图** 的视觉效果，控制时间尺度计数是一项关键技术。使用 Aspose.Tasks for Java，您可以以编程方式设置底部和中间时间尺度层级，微调刻度线的可见性，然后 **将项目保存为 PDF** 以便与利益相关者共享。本教程将带您完成整个过程——从环境搭建到生成反映您自定义甘特视图的精美 PDF。

## 快速答案
- **“自定义甘特图” 是什么意思？** 调整时间尺度层级、颜色和布局，以满足您的报告需求。  
- **哪个 API 方法设置底部层级计数？** `view.getBottomTimescaleTier().setCount(int)`。  
- **我可以直接从项目生成 PDF 吗？** 可以——使用 `project.save(..., SaveFileFormat.Pdf)`。  
- **生产环境需要许可证吗？** 需要商业许可证；提供免费试用版。  
- **支持哪个 Java 版本？** Java 8 或更高版本可与最新的 Aspose.Tasks 库配合使用。

## Aspose.Tasks 中的 “自定义甘特图” 是什么？
自定义甘特图是指以编程方式修改其视觉组件——例如时间尺度间隔、刻度线和任务条——使图表符合您 **管理项目可视化** 的方式。通过更改时间尺度计数，您可以控制每个段落代表的天数、周数或月数，从而为不同受众提供更清晰的图表。

## 前置条件
在开始之前，请确保您已具备以下条件：

1. **Java 开发环境** – 已安装 JDK 8 或更高版本。  
2. **Aspose.Tasks for Java 库** – 从 [here](https://releases.aspose.com/tasks/java/) 下载。  
3. **基础 Java 知识** – 熟悉 Java 语法和面向对象概念。

## 导入包
将必要的类导入到您的 Java 项目中：

```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## 步骤指南

### 步骤 1：设置数据目录
定义项目文件的读取和写入位置：

```java
String dataDir = "Your Data Directory";
```

将 `"Your Data Directory"` 替换为您机器上的绝对路径。

### 步骤 2：创建新的 Project 实例
实例化一个全新的 `Project` 对象，用于保存所有任务和视图设置：

```java
Project project = new Project();
```

### 步骤 3：配置甘特图视图
创建 `GanttChartView` 对象——在这里您将 **生成 Gantt view Java** 代码以控制图表外观：

```java
GanttChartView view = new GanttChartView();
```

### 步骤 4：设置底部层级的时间尺度计数
将底部层级调整为显示两个间隔并隐藏刻度线：

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### 步骤 5：设置中间层级的时间尺度计数
对中间层级应用相同的配置：

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### 步骤 6：将自定义视图添加到项目中
将刚才配置好的视图附加到 `Project` 实例：

```java
project.getViews().add(view);
```

### 步骤 7：添加示例任务（测试数据）
创建几个具有特定持续时间的任务，以演示自定义甘特图：

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### 步骤 8：将项目保存为 PDF
最后，将项目——包括您 **自定义的甘特图**——导出为 PDF 文件：

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

生成的 PDF 展示了底部和中间时间尺度层级已被 **自定义**，为利益相关者提供了清晰、可打印的进度视图。

## 常见问题与故障排除
- **PDF 为白页** – 确认 `dataDir` 路径以文件分隔符（`/` 或 `\`）结尾，并且目录已存在。  
- **刻度线仍然显示** – 验证已在两个层级上调用 `setShowTicks(false)`。  
- **持续时间未生效** – 确认在创建持续时间时使用了 `TimeUnitType.Hour`（或相应的单位）。

## 常见问答

**问：Aspose.Tasks for Java 能处理大规模项目文件吗？**  
答：可以，库已针对大量项目数据的高性能处理进行优化。

**问：Aspose.Tasks for Java 是否兼容不同的 Java IDE？**  
答：完全兼容——可无缝在 Eclipse、IntelliJ IDEA、NetBeans 等主流 IDE 中使用。

**问：我可以在时间尺度设置之外自定义甘特图的外观吗？**  
答：可以，Aspose.Tasks 提供丰富的样式选项，如条形颜色、字体和网格线。

**问：是否有 Aspose.Tasks for Java 的试用版？**  
答：有，您可以从 [here](https://releases.aspose.com/) 获取免费试用版。

**问：在哪里可以获得 Aspose.Tasks for Java 的支持？**  
答：您可以在 Aspose.Tasks 论坛 [here](https://forum.aspose.com/c/tasks/15) 获取支持与帮助。

**问：如何以编程方式更改甘特图的背景颜色？**  
答：在导入 `java.awt.Color` 后，使用 `view.getGanttChartProperties().setBackgroundColor(Color)` 方法。

## 结论
通过本教程的步骤，您已经学会了如何 **自定义甘特图** 的时间尺度层级，提升 **项目可视化** 效果，并使用 Aspose.Tasks for Java **将项目保存为 PDF**。此方法让您完全掌控视觉输出，便于向团队或客户分享清晰、专业的进度表。

---

**最后更新：** 2025-12-21  
**测试环境：** Aspose.Tasks for Java 24.12（撰写时的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}