---
date: 2026-01-10
description: 学习如何读取费率比例并在 Aspose.Tasks for Java 中管理资源分配。定义材料资源，如何设置比例，以及将资源分配给任务。
linktitle: Read and Write Rate Scale for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何在 Aspose.Tasks 中读取和写入资源分配的费率比例
url: /zh/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何读取和写入资源分配的费率比例（Rate Scale）在 Aspose.Tasks 中

在本教程中，您将了解 **如何读取费率** 比例设置并使用 Aspose.Tasks for Java 对资源分配进行调整。无论您是在构建调度器、报告工具，还是仅需自动化项目更新，掌握费率比例的操作都能让您对材料和工作资源进行细粒度控制。

## 快速答案
- **处理费率的主要类是什么？** `ResourceAssignment` 与 `Asn.RATE_SCALE` 属性。  
- **哪个枚举定义了比例选项？** `RateScaleType`（Day、Week、Month 等）。  
- **运行示例是否需要许可证？** 免费评估许可证可用于测试；生产环境需要商业许可证。  
- **保存后可以更改比例吗？** 可以——重新加载项目并按示例修改 `Asn.RATE_SCALE`。  
- **支持的 IDE？** 任意 Java IDE（IntelliJ IDEA、Eclipse、NetBeans）均可编译代码。

## 什么是费率比例？

费率比例决定资源成本费率所适用的时间单位（天、周、月等）。调整比例可让您准确地模拟材料消耗或人工工作量。

## 为什么要读取和写入费率比例？

读取当前比例有助于审计现有计划，而写入新比例则可使资源与项目的计费或消耗政策保持一致。这在 **定义材料资源** 成本或需要为非标准工作日历 **设置比例** 时尤为有用。

## 前提条件
1. **Java 开发环境** – 已安装 JDK 8 或更高版本。  
2. **Aspose.Tasks for Java 库** – 从 [here](https://releases.aspose.com/tasks/java/) 下载并安装库。

## 导入包
首先，导入必要的 Aspose.Tasks 类。

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.RateScaleType;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import java.io.IOException;
```

## 步骤 1：设置 Java 项目
创建 Maven 或 Gradle 项目，并将 Aspose.Tasks JAR 添加到类路径中。此步骤确保编译器能够找到导入的类。

## 步骤 2：加载项目文件
加载您要使用的现有 Microsoft Project 文件。

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## 步骤 3：添加任务
创建一个新任务，稍后将为其分配资源。

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## 步骤 4：定义资源
这里我们 **定义材料资源** 和常规工作资源。请注意对材料类型资源使用 `ResourceType.Material`。

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## 步骤 5：将资源分配给任务
现在我们 **将资源分配给任务**，并通过使用 `RateScaleType.Week` 指定 **如何设置比例**。这演示了读取和写入费率比例。

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## 步骤 6：保存项目
将更改持久化到新文件，以便稍后验证存储的费率比例。

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## 步骤 7：检索资源分配
重新加载已保存的项目，并 **读取费率** 比例以确认其已正确写入。

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## 常见陷阱与技巧
- **UID 不匹配** – 按 UID 检索分配时，确保 UID 值与创建时分配的相匹配。  
- **资源类型错误** – 对工作资源使用 `ResourceType.Material` 会导致费率计算异常。  
- **保存格式** – 始终使用 `SaveFileFormat.Mpp`（或其他受支持的格式）保存，以保留诸如费率比例的自定义字段。

## 结论
一旦了解相关类和属性，在 Aspose.Tasks for Java 中管理和检查资源分配的费率比例就非常简单。遵循本指南，您可以自信地 **读取费率** 信息、**定义材料资源** 对象、**设置比例**，以及 **将资源分配给任务**。

## 常见问题

**Q: 我可以在任何 Java IDE 中使用 Aspose.Tasks for Java 吗？**  
A: 是的，Aspose.Tasks for Java 与所有主流 Java IDE（包括 IntelliJ IDEA、Eclipse 和 NetBeans）兼容。

**Q: Aspose.Tasks 是否支持除 MPP 之外的其他文件格式？**  
A: 是的，Aspose.Tasks 支持多种文件格式，包括 MPP、XML 和 HTML。

**Q: Aspose.Tasks 适用于企业级项目管理吗？**  
A: 绝对适用，Aspose.Tasks 提供全面的功能，可管理任何规模的项目，适合企业级项目管理。

**Q: 我可以在费率比例之外进一步自定义资源分配吗？**  
A: 是的，Aspose.Tasks 提供广泛的功能来自定义资源分配，包括成本、工作量和持续时间的调整。

**Q: 是否有 Aspose.Tasks 社区论坛可获取支持？**  
A: 是的，您可以在 Aspose.Tasks 论坛 [here](https://forum.aspose.com/c/tasks/15) 找到支持并与其他用户互动。

---

**最后更新：** 2026-01-10  
**测试环境：** Aspose.Tasks for Java 24.12（撰写时的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}