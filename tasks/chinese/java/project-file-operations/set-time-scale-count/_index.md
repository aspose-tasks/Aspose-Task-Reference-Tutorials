---
date: 2026-03-29
description: 学习如何使用 Aspose.Tasks for Java 创建项目 PDF 文件，同时自定义甘特图时间尺度计数。本指南将一步步演示如何在完全控制下将甘特图导出为
  PDF。
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 创建项目 PDF – 自定义甘特图时间尺度
url: /zh/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 创建项目 PDF – 自定义甘特图时间刻度

## 介绍
如果您需要 **创建项目 PDF** 文件，以呈现完美调校的甘特图，则控制时间刻度计数是关键。使用 Aspose.Tasks for Java，您可以以编程方式设置底部和中部时间刻度层级，隐藏刻度线，然后 **将项目保存为 PDF**，便于分发。在本教程中，我们将逐步介绍所需的一切——从搭建开发环境到生成展示您自定义甘特视图的精美 PDF。

## 快速答案
- **“customize Gantt chart” 是什么意思？** 调整时间刻度层级、颜色和布局，以匹配您的报告需求。  
- **哪个 API 方法设置底部层级计数？** `view.getBottomTimescaleTier().setCount(int)`。  
- **我可以直接从项目生成 PDF 吗？** 是的——使用 `project.save(..., SaveFileFormat.Pdf)`。  
- **生产使用是否需要许可证？** 需要商业许可证；提供免费试用版。  
- **支持哪个 Java 版本？** Java 8 或更高版本可与最新的 Aspose.Tasks 库一起使用。

## 在 Aspose.Tasks 中，“customize Gantt chart” 是什么？
自定义甘特图是指以编程方式修改其视觉组件——例如时间刻度间隔、刻度线和任务条——使图表符合您希望 **管理项目可视化** 的方式。通过更改时间刻度计数，您可以控制每个段落代表多少天、周或月，从而使图表对不同受众更清晰。

## 为什么要使用自定义甘特图创建项目 PDF？
- **面向利益相关者的输出：** PDF 可在任何平台查看，确保所有人看到相同的进度布局。  
- **适合打印：** 精确控制时间刻度层级，可防止打印输出拥挤或模糊。  
- **自动化：** 将 PDF 生成集成到 CI 流水线或报告服务中，实现零手动工作。

## 前置条件
在开始之前，请确保您已具备以下条件：

1. **Java 开发环境** – 已安装 JDK 8 或更高版本。  
2. **Aspose.Tasks for Java 库** – 从 [此处](https://releases.aspose.com/tasks/java/) 下载。  
3. **基本的 Java 知识** – 熟悉 Java 语法和面向对象概念。

## 导入包
将必要的类导入您的 Java 项目：

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
创建一个 `GanttChartView` 对象——在这里您将 **生成 Gantt view Java** 代码以控制图表外观：

```java
GanttChartView view = new GanttChartView();
```

### 步骤 4：设置底部层级的时间刻度计数
将底部层级调整为显示两个间隔并隐藏刻度线：

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### 步骤 5：设置中部层级的时间刻度计数
对中部层级应用相同的配置：

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### 步骤 6：将自定义视图添加到项目中
将您刚配置的视图附加到 `Project` 实例中：

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
最后，将项目（包括您的 **自定义甘特图**）导出为 PDF 文件：

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

生成的 PDF 展示了底部和中部时间刻度层级已被 **自定义**，为利益相关者提供了清晰、可打印的进度视图。

## 常见问题与故障排除
- **PDF 空白** – 确保 `dataDir` 路径以文件分隔符（`/` 或 `\`）结尾，并且目录存在。  
- **刻度仍然出现** – 验证在两个层级上都调用了 `setShowTicks(false)`。  
- **持续时间未应用** – 确认在创建持续时间时使用了 `TimeUnitType.Hour`（或相应的单位）。

## 常见问答

**Q: Aspose.Tasks for Java 能处理大规模项目文件吗？**  
A: 是的，该库针对大规模项目数据的高性能处理进行了优化。

**Q: Aspose.Tasks for Java 与不同的 Java IDE 兼容吗？**  
A: 当然——它可无缝配合 Eclipse、IntelliJ IDEA、NetBeans 以及其他流行的 IDE 使用。

**Q: 我可以在时间刻度设置之外自定义甘特图的外观吗？**  
A: 可以，Aspose.Tasks 提供了丰富的样式选项，如条形颜色、字体和网格线等。

**Q: 是否有 Aspose.Tasks for Java 的试用版？**  
A: 有，您可以从 [此处](https://releases.aspose.com/) 获取免费试用版。

**Q: 在哪里可以获得 Aspose.Tasks for Java 的支持？**  
A: 您可以在 Aspose.Tasks 论坛的 [此处](https://forum.aspose.com/c/tasks/15) 获取支持和帮助。

**Q: 如何以编程方式更改甘特图的背景颜色？**  
A: 在导入 `java.awt.Color` 后，使用 `view.getGanttChartProperties().setBackgroundColor(Color)` 方法。

## 结论
通过遵循这些步骤，您已经学会了如何使用 Aspose.Tasks for Java **创建项目 PDF** 文件，并实现完全自定义的甘特图时间刻度，提升 **项目可视化**，以及 **将项目保存为 PDF**。此方法让您对视觉输出拥有完整控制，便于向团队或客户共享清晰、专业的进度安排。

---

**最后更新：** 2026-03-29  
**测试环境：** Aspose.Tasks for Java (latest)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}