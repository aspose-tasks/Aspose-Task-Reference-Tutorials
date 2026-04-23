---
date: 2026-01-23
description: 了解如何使用 Aspose.Tasks for Java 设置基准持续时间并创建项目实例。本分步指南帮助您高效管理任务基准。
linktitle: How to Set Baseline Duration in Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: 如何在 Aspose.Tasks for Java 中设置基准持续时间
url: /zh/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks for Java 中设置基线持续时间

## 介绍
设置基线是跟踪项目进度相对于原始计划的基础步骤。在本教程中，您将学习 **如何为 Microsoft Project 中的任务设置基线持续时间**，使用 Aspose.Tasks for Java 库，并了解为何尽早建立基线可以为您后续节省时间和避免麻烦。

## 快速答案
- **“设置基线”是什么意思？** 它记录任务的原始开始、完成和持续时间，以便您比较后续的更改。  
- **哪个 Aspose.Tasks 类用于创建项目？** `Project` 类——您还将学习如何 **正确创建项目实例**。  
- **运行代码是否需要许可证？** 免费评估许可证可用于测试；生产环境需要商业许可证。  
- **我可以检索临时基线吗？** 可以，Aspose.Tasks 允许您查询临时基线及其固定成本。  
- **需要哪个 Java 版本？** 推荐使用 Java 8 或更高版本。

## 什么是任务基线，为什么要设置它？
任务基线捕获特定时间点的计划进度（开始日期、完成日期和持续时间）。通过设置基线，您创建了一个参考点，能够在项目演进过程中轻松发现进度漂移、成本超支和资源整体超额分配。

## 为什么使用 Aspose.Tasks 进行基线管理？
- **完整的 .mpp 兼容性** – 在未安装 Office 的情况下读取和写入原生 Microsoft Project 文件。  
- **丰富的 API** – 以编程方式访问基线数据、临时基线和时间相位信息。  
- **跨平台** – 在 Windows、Linux 和 macOS 上均可使用任何标准 JDK。

## 前置条件
1. **Java 开发环境** – 已安装并配置 JDK 8+。  
2. **Aspose.Tasks for Java** – 从[此处](https://releases.aspose.com/tasks/java/)下载库。  
3. **IDE 或构建工具** – Maven、Gradle 或您偏好的任何 IDE。

## 导入包
首先，将必要的类导入到您的 Java 项目中：

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## 步骤 1：创建项目实例
创建项目实例是进行任何后续操作的基础。本步骤展示如何使用 Aspose.Tasks **创建项目实例**：

```java
Project project = new Project();
```

## 步骤 2：创建任务基线
向项目根目录添加新任务并设置其基线。这会记录任务的原始计划进度：

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## 步骤 3：显示任务基线信息
检索刚刚创建的基线并打印其关键属性。这有助于您验证基线是否已正确设置：

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## 步骤 4：检查临时基线和固定成本
如果您使用临时基线，可以查询当前基线是否为临时基线以及任何关联的固定成本：

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## 步骤 5：打印时间相位数据
时间相位数据展示基线在时间轴上的分布。遍历集合以检查每个条目：

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

通过遵循这些步骤，您可以 **如何设置基线** 持续时间，针对任何任务并使用 Aspose.Tasks for Java 检索详细的基线信息。

## 常见问题及解决方案
- **基线在 MS Project 中未显示：** 确保在添加任务 **之后** 调用了 `project.setBaseline(BaselineType.Baseline)`。  
- **`getBaselines()` 抛出 NullPointerException：** 验证任务已在设置基线前添加到项目中。  
- **时间单位不匹配：** 使用 `TimeUnitType` 正确格式化持续时间，尤其在使用自定义日历时。

## 常见问答
### 在 MS Project 中什么是任务基线？
任务基线是对任务初始计划进度的快照，包括开始日期、完成日期和持续时间。

### 为什么管理任务基线很重要？
管理任务基线有助于将计划进度与项目实际进展进行比较，从而实现更好的跟踪和决策。

### 设置基线后可以修改任务基线吗？
可以，在 MS Project 中可以修改任务基线以反映计划的更改。但必须记录任何偏离原始基线的情况。

### Aspose.Tasks 是否支持其他项目管理功能？
是的，Aspose.Tasks 提供广泛的项目管理功能，包括任务调度、资源分配和甘特图生成。

### 在哪里可以获得 Aspose.Tasks 的支持？
您可以在 [Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15) 上提问并与其他用户互动，获取支持。

## 其他常见问题
**问：是否需要为每个任务单独调用 `setBaseline`？**  
答：不需要。调用 `project.setBaseline(BaselineType.Baseline)` 即可一次性为项目中的所有任务记录基线。

**问：如何为特定任务设置临时基线？**  
答：在更新任务进度后，使用 `project.setBaseline(BaselineType.Baseline1)`（或 Baseline2‑Baseline10）即可。

**问：是否可以将基线数据导出为 CSV？**  
答：可以。遍历 `task.getBaselines()`，使用标准 Java I/O 将所需字段写入 CSV 文件。

**问：我能读取已经包含基线的现有 .mpp 文件吗？**  
答：完全可以。使用 `new Project("myproject.mpp")` 加载文件，然后按上述方式访问每个任务的基线。

**问：Aspose.Tasks 能处理多项目文件吗？**  
答：Aspose.Tasks 仅支持单项目 .mpp 文件。对于多项目场景，需要通过编程方式合并项目。

---

**最后更新：** 2026-01-23  
**测试版本：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}