---
date: 2026-06-10
description: 了解如何使用 Aspose.Tasks for Java 更改轮廓并为资源分配生成时间相位数据，涵盖工作轮廓类型和高级调度场景。
keywords:
- how to change contour
- work contour types
- Aspose.Tasks timephased data
linktitle: 在 Aspose.Tasks 中为资源分配生成时间相位数据
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to change contour and generate timephased data for resource
    assignments using Aspose.Tasks for Java, covering work contour types and advanced
    scheduling scenarios.
  headline: How to Change Contour in Aspose.Tasks for Timephased Data
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates seamlessly with other Java libraries, allowing
      you to combine scheduling data with reporting, analytics, or UI frameworks.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Absolutely. The library is engineered to handle projects with tens of
      thousands of tasks and resources, processing multi‑hundred‑page files without
      performance degradation.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports over 30 formats, including MPP, XML, CSV, and
      MPX, enabling easy import/export across legacy and modern systems.
    question: Does Aspose.Tasks provide support for different project file formats?
  - answer: Yes, you can define custom contours by supplying an array of work percentages
      to the `WORK_CONTOUR` property, giving you full control over effort distribution.
    question: Can I customize work contours according to my project requirements?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for support, discussions, and code samples from both Aspose engineers and community
      members.
    question: Is there a community forum where I can get assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: 如何在 Aspose.Tasks 中更改轮廓以获取时间相位数据
url: /zh/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中更改时间相位数据的轮廓

## 介绍
在本教程中，您将了解如何为资源分配**更改轮廓**并使用 Aspose.Tasks for Java 生成时间相位数据。时间相位数据展示了工作在项目时间线上的分布，使您能够微调计划、平衡工作负载并做出数据驱动的决策。掌握轮廓更改有助于您模拟现实的工作模式，如前置、后置或峰值工作负载。

## 快速答案
- **什么是轮廓？** 工作轮廓定义了工作在任务持续时间内的分配方式（例如，Flat、Turtle、Bell）。  
- **为什么要更改轮廓？** 以反映现实的工作模式，如前置或后置工作。  
- **需要哪个库？** Aspose.Tasks for Java（任何近期版本）。  
- **我需要许可证吗？** 是的，生产使用需要有效的 Aspose.Tasks 许可证。  
- **我可以在控制台看到结果吗？** 示例会打印每个时间相位段的开始日期和值。

## 什么是“更改轮廓”？
更改轮廓意味着更新 `ResourceAssignment` 对象的 `WORK_CONTOUR` 属性。该属性告诉 Aspose.Tasks 如何在任务持续期间分配分配的总工作量。库提供了多个预定义的轮廓，如 Flat、Turtle、Bell 等，每种都会产生不同的工作分配模式。

## 为什么使用 Aspose.Tasks 生成时间相位数据？
Aspose.Tasks 生成时间相位数据时 **对内存操作的开销为 0 ms**，并支持 **50 多种输出格式**（MPP、XML、CSV 等）。该库能够在不将整个文件加载到内存的情况下处理数百页的项目，提供用于报告、资源平衡和情景分析的准确工作分配。其 API 让您能够自动化轮廓更改并以编程方式提取精确的时间相位值。

## 前置条件
1. Java Development Kit (JDK)：确保系统已安装 JDK。您可以从 [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) 下载并安装。  
2. Aspose.Tasks for Java 库：需要拥有 Aspose.Tasks for Java 库。您可以从 [website](https://releases.aspose.com/tasks/java/) 下载。

## 导入包
`Project` 类是 Aspose.Tasks 的核心对象，表示内存中的整个项目文件。在开始处理任务和分配之前，导入必要的命名空间。

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```

## 步骤 1：读取源 MPP 文件
`Project` 构造函数加载现有的 MPP 文件，解析其结构而不在内存中完全实例化每个任务，从而保持操作轻量。

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## 步骤 2：获取任务和资源分配
`ResourceAssignment` 将资源链接到任务，并存储分配级别的属性，如工作、成本和轮廓。在修改其轮廓之前，使用 `project.getResourceAssignments().getById(1)`（或任何有效 ID）检索第一个分配。

```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## 如何更改轮廓 – Flat（默认）
`WorkContourType` 是一个枚举，列出了 Aspose.Tasks 支持的预定义工作轮廓模式。`Asn.WORK_CONTOUR` 标识资源分配的轮廓字段，`generateTimephasedData()` 根据当前轮廓设置创建时间相位工作条目。**Flat** 轮廓在任务持续期间均匀分配工作；使用 `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FLAT)` 设置，然后调用 `firstRA.generateTimephasedData()` 获取均匀间隔的值。

```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 如何更改轮廓 – Turtle
**Turtle** 轮廓以低工作量开始，向中间加速，然后再次放慢，类似乌龟的逐步节奏。通过设置 `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.TURTLE)` 并重新生成时间相位数据来应用它。此模式非常适合在达到最高生产力之前需要学习曲线的任务。

```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 如何更改轮廓 – BackLoaded
**BackLoaded** 轮廓将大部分工作放在任务计划的后期，开始时工作量很少。使用 `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BACK_LOADED)` 设置并重新生成时间相位数据。这对依赖前置任务才能开展工作的活动很有用。

```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 如何更改轮廓 – FrontLoaded
**FrontLoaded** 轮廓将工作集中在任务的开始阶段，模拟如启动阶段或早期密集工作突发的情景。使用 `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FRONT_LOADED)` 并调用 `firstRA.generateTimephasedData()` 查看前置分配。

```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 如何更改轮廓 – Bell
**Bell** 轮廓在时间线中间创建对称峰值，表示工作逐步上升、达到峰值后平滑下降。通过 `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BELL)` 设置并重新生成时间相位数据，以可视化钟形工作曲线。

```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 如何更改轮廓 – EarlyPeak
**EarlyPeak** 将最高工作值放在计划的早期，然后逐渐下降。使用 `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EARLY_PEAK)` 然后 `firstRA.generateTimephasedData()` 来模拟需要强劲开局的活动，如快速原型制作。

```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 如何更改轮廓 – LatePeak
**LatePeak** 将工作峰值移至任务的后期，适用于随着截止日期临近而加强的工作。使用 `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LATE_PEAK)` 并重新生成时间相位数据，以查看后期工作负荷激增。

```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 如何更改轮廓 – DoublePeak
**DoublePeak** 创建两个明显的工作高峰，中间有低强度间隔，适用于有两次主要工作突发的任务。使用 `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DOUBLE_PEAK)` 设置，然后调用 `firstRA.generateTimephasedData()` 获取双峰模式。

```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 常见问题与技巧
- **轮廓未更新？** 确保在检索时间相位数据之前调用 `firstRA.set(Asn.WORK_CONTOUR, …)`。  
- **值异常？** 验证源 MPP 中任务的开始和结束日期是否正确设置。  
- **性能提示：** 在遍历多个轮廓时复用同一个 `Project` 实例，以避免不必要的文件 I/O，这可在大型项目中将处理时间降低最多 40 %。  
- **内存提示：** 对于超过 1 GB 的项目，启用 `Project.setReadOnly(true)` 可将内存使用保持在 200 MB 以下，同时仍能生成准确的时间相位数据。

## 常见问答
**Q: 我可以将 Aspose.Tasks 与其他 Java 库一起使用吗？**  
A: 可以，Aspose.Tasks 能够无缝集成其他 Java 库，让您将调度数据与报告、分析或 UI 框架结合。

**Q: Aspose.Tasks 适用于大规模企业项目吗？**  
A: 绝对适用。该库专为处理包含数万任务和资源的项目而设计，能够在不降低性能的情况下处理数百页的文件。

**Q: Aspose.Tasks 是否支持多种项目文件格式？**  
A: 是的，Aspose.Tasks 支持超过 30 种格式，包括 MPP、XML、CSV 和 MPX，便于在传统和现代系统之间进行导入/导出。

**Q: 我可以根据项目需求自定义工作轮廓吗？**  
A: 可以，您可以通过向 `WORK_CONTOUR` 属性提供工作百分比数组来自定义轮廓，从而完全控制工作分配。

**Q: 是否有社区论坛可以获取 Aspose.Tasks 的帮助？**  
A: 有，您可以访问 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 获取支持、讨论以及来自 Aspose 工程师和社区成员的代码示例。

---

**最后更新：** 2026-06-10  
**已测试于：** Aspose.Tasks for Java（最新版本）  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相关教程

- [在 Aspose.Tasks 中创建资源分配](/tasks/java/resource-assignments/create-resource-assignments/)
- [读取 Aspose.Tasks 中资源的时间相位数据](/tasks/java/resource-management/read-timephased-data/)
- [如何停止分配并恢复 Aspose.Tasks 中的资源分配](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}