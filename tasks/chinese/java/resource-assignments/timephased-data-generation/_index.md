---
date: 2026-01-10
description: 学习如何使用 Aspose.Tasks for Java 更改资源分配的轮廓并生成时间相位数据，从而提升项目管理效率。
linktitle: Generate Timephased Data for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何在 Aspose.Tasks 中更改时间相位数据的轮廓
url: /zh/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中更改时相数据的轮廓

## 介绍
在本教程中，您将学习 **如何更改资源分配的轮廓** 并使用 Aspose.Tasks for Java 生成时相数据。时相数据展示了工作在项目时间线上的分布，帮助您微调进度、平衡工作负荷，并做出数据驱动的决策。

## 快速答案
- **什么是轮廓？** 工作轮廓定义了工作在任务持续期间的分布方式（例如，Flat、Turtle、Bell）。  
- **为什么要更改轮廓？** 为了反映真实的工作模式，如前置或后置工作负荷。  
- **需要哪个库？** Aspose.Tasks for Java（任意近期版本）。  
- **需要许可证吗？** 是的，生产环境必须使用有效的 Aspose.Tasks 许可证。  
- **可以在控制台看到结果吗？** 示例会打印每个时相段的开始日期和数值。

## 什么是“更改轮廓”？
更改轮廓即更新 `ResourceAssignment` 的 `WORK_CONTOUR` 属性。Aspose.Tasks 支持多种预定义轮廓（Flat、Turtle、Bell 等），这些轮廓会影响工作随时间的分配方式。

## 为什么使用 Aspose.Tasks 生成时相数据？
- **准确的报告：** 导出精确的工作分布供报表工具使用。  
- **情景规划：** 在不修改原始进度的情况下测试不同的轮廓。  
- **自动化：** 集成到 CI 流水线中，自动验证项目健康状况。

## 前置条件
在开始之前，请确保具备以下前置条件：
1. Java Development Kit (JDK)：确保系统已安装 JDK。您可以从 [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) 下载并安装。  
2. Aspose.Tasks for Java 库：需要拥有 Aspose.Tasks for Java 库。您可以从 [website](https://releases.aspose.com/tasks/java/) 下载。

## 导入包
首先，导入使用 Aspose.Tasks 所需的包：
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
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## 步骤 2：获取任务和资源分配
```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## 如何更改轮廓 – Flat (Default)
```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 如何更改轮廓 – Turtle
```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 如何更改轮廓 – BackLoaded
```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 如何更改轮廓 – FrontLoaded
```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 如何更改轮廓 – Bell
```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 如何更改轮廓 – EarlyPeak
```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 如何更改轮廓 – LatePeak
```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 如何更改轮廓 – DoublePeak
```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 常见问题与技巧
- **轮廓未更新？** 确保在获取时相数据 *之前* 调用 `firstRA.set(Asn.WORK_CONTOUR, …)`。  
- **数值异常？** 验证任务的开始和结束日期在源 MPP 中是否正确设置。  
- **性能提示：** 在遍历多个轮廓时复用同一个 `Project` 实例，以避免不必要的文件 I/O。

## 常见问题
### 我可以将 Aspose.Tasks 与其他 Java 库一起使用吗？
可以，Aspose.Tasks 可与其他 Java 库集成，以增强项目管理功能。

### Aspose.Tasks 适用于大规模企业项目吗？
当然，Aspose.Tasks 旨在处理各种规模的项目，包括大型企业级项目。

### Aspose.Tasks 是否支持不同的项目文件格式？
是的，Aspose.Tasks 支持多种格式，如 MPP、XML 和 MPX。

### 我可以根据项目需求自定义工作轮廓吗？
可以，您可以定义自定义工作轮廓以满足特定的排程需求。

### 是否有社区论坛可以获取 Aspose.Tasks 的帮助？
有，您可以访问 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 获取支持和讨论。

---

**最后更新：** 2026-01-10  
**测试环境：** Aspose.Tasks for Java（最新发布）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}