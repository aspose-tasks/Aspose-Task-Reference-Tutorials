---
date: 2026-06-10
description: 了解如何使用 Aspose.Tasks for Java 读取资源分配的费率以及写入费率比例。支持物料资源、多种格式和大型项目。
keywords:
- how to read rate
- how to write rate
- write rate scale
- Aspose.Tasks rate scale
- resource assignments Java
linktitle: 在 Aspose.Tasks 中读取和写入资源分配的费率比例
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to read rate and how to write rate scale for resource assignments
    using Aspose.Tasks for Java. Supports material resources, multiple formats, and
    large projects.
  headline: How to Read Rate Scale and Write Rate Scale for Resource Assignments in
    Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java is compatible with all major Java IDEs, including
      IntelliJ IDEA, Eclipse, and NetBeans.
    question: Can I use Aspose.Tasks for Java with any Java IDE?
  - answer: Yes, Aspose.Tasks supports various file formats, including MPP, XML, and
      HTML.
    question: Does Aspose.Tasks support other file formats besides MPP?
  - answer: Absolutely, Aspose.Tasks offers comprehensive features for managing projects
      of any scale, making it suitable for enterprise‑level project management.
    question: Is Aspose.Tasks suitable for enterprise‑level project management?
  - answer: Yes, Aspose.Tasks provides extensive capabilities for customizing resource
      assignments, including cost, work, and duration adjustments.
    question: Can I customize resource assignments further beyond rate scale?
  - answer: Yes, you can find support and interact with other users on the Aspose.Tasks
      forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is there a community forum for Aspose.Tasks support?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: 如何在 Aspose.Tasks 中读取和写入资源分配的费率比例
url: /zh/java/resource-assignments/read-write-rate-scale/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何读取和写入 Aspose.Tasks 中资源分配的费率比例

在本教程中，您将了解如何读取费率比例设置并使用 Aspose.Tasks for Java 对资源分配进行调整。无论您是在构建调度器、报告工具，还是仅需自动化项目更新，掌握费率比例的操作都能让您对材料和工作资源进行细粒度控制。

## 快速答案
`ResourceAssignment` 将任务与资源关联，并保存分配特定的数据。  
`Asn` 包含分配字段的常量，包括 `RATE_SCALE`。  
`RateScaleType` 枚举列出了费率比例可能的时间单位。  

- **处理费率的主要类是什么？** `ResourceAssignment` 与 `Asn.RATE_SCALE` 属性一起使用。  
- **哪个枚举定义了比例选项？** `RateScaleType`（Day、Week、Month 等）。  
- **运行示例是否需要许可证？** 免费评估许可证可用于测试；生产环境需要商业许可证。  
- **保存后可以更改比例吗？** 可以——重新加载项目并按示例修改 `Asn.RATE_SCALE`。  
- **支持的 IDE？** 任意 Java IDE（IntelliJ IDEA、Eclipse、NetBeans）均可编译代码。

## 如何读取资源分配的费率比例？

加载项目，定位所需的 `ResourceAssignment`，并调用 `getRateScale()` ——该方法返回一个 `RateScaleType` 值，指示费率是按天、周、月或其他单位应用。答案即时返回，仅需两次 API 调用，非常适合审计脚本或 UI 显示。

## 如何写入资源分配的费率比例？

创建或获取 `ResourceAssignment` 对象，将其 `Asn.RATE_SCALE` 属性设置为所需的 `RateScaleType`（例如 `RateScaleType.Week`），然后保存项目。此单一属性的更改会自动更新成本计算，并在所有受支持的文件格式中持久化。设置比例后，您可能还需要调整资源的标准费率或加班费率，以匹配新的时间单位，确保成本计算保持准确。

## 什么是费率比例？

费率比例决定资源成本费率所适用的时间单位（天、周、月等）。调整比例可让您准确地对材料消耗或人工工作量进行建模。例如，将比例设置为 Week 表示费用率被解释为每周费用，任务的总费用将根据资源分配的周数进行计算。

## 为什么要读取和写入费率比例？

读取当前比例有助于审计现有进度表，而写入新比例则可以使资源与项目的计费或消耗政策保持一致。这在**定义材料资源**成本或需要为非标准工作日历**设置比例**时尤为有用。

## 前置条件
在开始之前，请确保具备以下前提条件：
1. **Java Development Environment** – JDK 8 或更高版本已安装。  
2. **Aspose.Tasks for Java Library** – 从 [here](https://releases.aspose.com/tasks/java/) 下载并安装库。

## 导入包
`ResourceAssignment` 类表示任务与资源之间的关联，而 `RateScaleType` 则枚举了费率可能的时间单位。在开始编码之前，请导入必要的 Aspose.Tasks 类。

`Project` 是用于加载和保存 Microsoft Project 文件的主要对象。  
`Resource` 定义项目资源，如工作或材料。  
`ResourceType` 枚举指定资源是工作还是材料。  
`Task` 表示项目进度表中的工作项。  
`SaveFileFormat` 枚举定义保存项目的输出格式。

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
创建一个 Maven 或 Gradle 项目，并将 Aspose.Tasks JAR 添加到类路径中。此步骤可确保编译器能够找到导入的类。

## 步骤 2：加载项目文件
加载您要处理的现有 Microsoft Project 文件。

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "New project 2013.mpp");
```

## 步骤 3：添加任务
创建一个新任务，以便后续接收资源分配。

```java
Task task = project.getRootTask().getChildren().add("t1");
```

## 步骤 4：定义资源
这里我们**定义材料资源**和常规工作资源。请注意对材料类型资源使用 `ResourceType.Material`。

```java
Resource materialResource = project.getResources().add("materialResource");
materialResource.set(Rsc.TYPE, ResourceType.Material);
Resource nonMaterialResource = project.getResources().add("nonMaterialResource");
nonMaterialResource.set(Rsc.TYPE, ResourceType.Work);
```

## 步骤 5：为任务分配资源
现在我们**为任务分配资源**，并通过使用 `RateScaleType.Week` 指定**如何设置比例**。这演示了读取和写入费率比例的过程。

```java
ResourceAssignment materialResourceAssignment = project.getResourceAssignments().add(task, materialResource);
materialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
ResourceAssignment nonMaterialResourceAssignment = project.getResourceAssignments().add(task, nonMaterialResource);
nonMaterialResourceAssignment.set(Asn.RATE_SCALE, RateScaleType.Week);
```

## 步骤 6：保存项目
将更改持久化到新文件，以便稍后验证已存储的费率比例。

```java
project.save("output.mpp", SaveFileFormat.Mpp);
```

## 步骤 7：检索资源分配
重新加载已保存的项目，并**读取费率比例**以确认其已正确写入。

```java
Project resavedProject = new Project("output.mpp");
ResourceAssignment resavedMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(1);
System.out.println(resavedMaterialResourceAssignment.get(Asn.RATE_SCALE));
ResourceAssignment resavedNonMaterialResourceAssignment = resavedProject.getResourceAssignments().getByUid(2);
```

## 常见陷阱与技巧
- **UID 不匹配** – 按 UID 检索分配时，确保 UID 值与创建时分配的相匹配。  
- **资源类型错误** – 对工作资源使用 `ResourceType.Material` 会导致费率计算出现异常。  
- **保存格式** – 始终使用 `SaveFileFormat.Mpp`（或其他受支持的格式）保存，以保留诸如费率比例的自定义字段。  
- **大型项目** – 由于流式架构，Aspose.Tasks 能够处理超过 **500 页** 的文件，而无需将整个文档加载到内存中。

## 常见问题解答

**Q: 我可以在任何 Java IDE 中使用 Aspose.Tasks for Java 吗？**  
A: 是的，Aspose.Tasks for Java 与所有主流 Java IDE 兼容，包括 IntelliJ IDEA、Eclipse 和 NetBeans。

**Q: Aspose.Tasks 是否支持除 MPP 之外的其他文件格式？**  
A: 是的，Aspose.Tasks 支持多种文件格式，包括 MPP、XML 和 HTML。

**Q: Aspose.Tasks 适合企业级项目管理吗？**  
A: 当然，Aspose.Tasks 提供全面的功能，可管理任何规模的项目，适用于企业级项目管理。

**Q: 我可以在费率比例之外进一步自定义资源分配吗？**  
A: 可以，Aspose.Tasks 提供广泛的功能来自定义资源分配，包括成本、工作量和工期的调整。

**Q: 是否有 Aspose.Tasks 的社区论坛可供支持？**  
A: 有，您可以在 Aspose.Tasks 论坛 [here](https://forum.aspose.com/c/tasks/15) 上获取支持并与其他用户互动。

---

**最后更新：** 2026-06-10  
**测试环境：** Aspose.Tasks for Java 24.12（撰写时的最新版本）  
**作者：** Aspose

## 相关教程

- [在 Aspose.Tasks 中创建资源分配](/tasks/java/resource-assignments/create-resource-assignments/)
- [如何修改分配 – 使用 Aspose 读取共享资源](/tasks/java/resource-assignments/read-shared-resource-assignments/)
- [在 Aspose.Tasks 中向资源分配添加备注](/tasks/java/resource-assignments/resource-assignment-notes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}