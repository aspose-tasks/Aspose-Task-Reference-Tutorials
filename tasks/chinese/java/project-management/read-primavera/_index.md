---
date: 2025-12-28
description: 学习如何使用 Aspose.Tasks for Java 将 Primavera XML 文件读取到 MS Project 中，实现无缝的数据交换和改进的项目管理。
linktitle: Read Project from Primavera in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks for Java 将 Primavera XML 读取到 MS Project 中
url: /zh/java/project-management/read-primavera/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks for Java 从 Primavera 读取 MS Project

## 介绍
在现代项目管理中，在工具之间无损迁移数据至关重要。本教程向您展示 **如何读取 primavera xml** 文件并使用 Aspose.Tasks for Java 将其导入 Microsoft Project。完成后，您将能够提取 Primavera 特有的任务属性，使跨平台分析变得直接且高效。

## 快速答案
- **Aspose.Tasks for Java 能做什么？** 它可以读取和写入多种项目文件格式，包括 Primavera XML 和 Microsoft Project (MPP)。  
- **需要许可证吗？** 免费试用可用于评估；生产环境需要许可证。  
- **支持哪个 Java 版本？** 需要 Java 8 或更高版本。  
- **除了 Primavera XML，还能读取其他格式吗？** 可以，Aspose.Tasks 支持 MPP、XML 等多种格式。  
- **此方法适用于大型企业项目吗？** 绝对适用——Aspose.Tasks 为高性能、企业级场景而设计。

## 什么是 read primavera xml？
读取 Primavera XML 指解析 Oracle Primavera P6 导出的 XML，以获取项目进度数据——任务、工期、资源以及 Primavera 特有的属性——从而能够被 Microsoft Project 等其他工具使用。

## 为什么使用 Aspose.Tasks for Java 来读取 primavera xml？
- **完整保真度：** 所有 Primavera 特有属性均得以保留。  
- **无外部依赖：** 纯 Java 库，无需安装 Primavera 或 MS Project。  
- **可扩展性：** 能高效处理包含数千任务的大型项目。  
- **跨平台：** 支持 Windows、Linux 和 macOS。

## 前置条件
在开始之前，请确保您具备以下条件：
1. **Java Development Kit (JDK)** – 已安装 Java 8 或更高版本。  
2. **Aspose.Tasks for Java** – 从 [here](https://releases.aspose.com/tasks/java/) 下载。  
3. 一个 Primavera XML 文件（例如 `PrimaveraProject.xml`），即您想要读取的文件。

## 如何使用 Aspose.Tasks 读取 Java 项目文件？
下面是一份逐步指南，带您完成整个过程。

### 导入包
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```

### 步骤 1：设置数据目录
```java
String dataDir = "Your Data Directory";
```
将 `"Your Data Directory"` 替换为存放 Primavera XML 文件的绝对路径。

### 步骤 2：从 Primavera XML 读取项目
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
将 `"PrimaveraProject.xml"` 替换为您实际的 Primavera 导出文件名。

### 步骤 3：遍历任务并获取 Primavera 特有属性
```java
for (Task task : project.enumerateAllChildTasks()) {
    System.out.println("Task '" + task.getName() + "'");
    
    if (task.isSummary()) {
        System.out.println("WBS Sequence number: " + task.getPrimaveraProperties().getSequenceNumber());
    } else {
        System.out.println("Task ActivityId: " + task.getPrimaveraProperties().getActivityId());
    }
    
    System.out.println("Activity Type: " + task.getPrimaveraProperties().getActivityType());
    System.out.println("Duration Type: " + task.getPrimaveraProperties().getDurationType());
    System.out.println("Percent Complete Type: " + task.getPrimaveraProperties().getPercentCompleteType());
    System.out.println("Original Duration: " + TimeDelta.fromMilliseconds(task.getDuration().getTimeSpan()).getTotalHours());
    System.out.println("At Complete Duration: " +
            (TimeDelta.fromMilliseconds(task.getActualDuration().getTimeSpan()).getTotalHours() + TimeDelta.fromMilliseconds(task.getRemainingDuration().getTimeSpan()).getTotalHours()));
    System.out.println("Duration % Complete: " + task.getPrimaveraProperties().getDurationPercentComplete());
    System.out.println("Physical % Complete: " + task.getPrimaveraProperties().getPhysicalPercentComplete());
    
    System.out.println("Task RemainingEarlyStart: " + task.getPrimaveraProperties().getRemainingEarlyStart());
    System.out.println("Task RemainingEarlyFinish: " + task.getPrimaveraProperties().getRemainingEarlyFinish());
    
    System.out.println("Actual costs:");
    System.out.println(task.getPrimaveraProperties().getActualExpenseCost() + ", "
                    + task.getPrimaveraProperties().getActualLaborCost() + ", "
                    + task.getPrimaveraProperties().getActualMaterialCost() + ", "
                    + task.getPrimaveraProperties().getActualNonlaborCost() + ", Total: "
                    + task.getPrimaveraProperties().getActualTotalCost());
    
    System.out.println("Labor Units:");
    System.out.println(task.getPrimaveraProperties().getActualLaborUnits() + ", " +
            task.getPrimaveraProperties().getActualNonLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingNonLaborUnits());
    
    System.out.println("Units % Complete: " + task.getPrimaveraProperties().getUnitsPercentComplete());
}
```
此循环会打印每个任务的 Primavera 特有细节，如 Activity ID、WBS 序列、工期类型、成本细分等。

## 常见问题及解决方案
- **文件未找到错误：** 确认 `dataDir` 以路径分隔符（`/` 或 `\\`）结尾，并且 XML 文件名正确。  
- **缺少 Primavera 属性：** 确保 XML 已导出所有必需字段；较旧的 Primavera 版本可能会遗漏某些属性。  
- **大文件性能问题：** 对于包含数万任务的项目，可考虑增大 JVM 堆大小（如 `-Xmx2g` 或更高）。

## 常见问答
### 问：我可以使用 Aspose.Tasks for Java 修改任务的 Primavera 特有属性吗？
答：可以，Aspose.Tasks for Java 提供了相应的 API 来根据需要修改这些属性。

### 问：Aspose.Tasks for Java 支持读取其他项目文件格式吗？
答：支持，Aspose.Tasks for Java 可读取包括 MPP、XML 和 Primavera XML 在内的多种项目文件格式。

### 问：Aspose.Tasks for Java 适用于企业级项目管理应用吗？
答：完全适用，Aspose.Tasks for Java 具备强大的功能和可扩展性，适合企业级项目管理应用。

### 问：我能否使用 Aspose.Tasks for Java 提取 Primavera 项目的资源信息？
答：可以，Aspose.Tasks for Java 允许您在提取任务详情的同时获取资源信息。

### 问：在哪里可以找到 Aspose.Tasks for Java 的更多支持或文档？
答：您可以在 [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/) 页面找到完整的文档并访问论坛获取支持。

## 结论
您现在已经学会 **如何读取 primavera xml** 文件，并使用 Aspose.Tasks 将详细的任务信息导入 Java 应用程序。此功能弥合了 Primavera 与 Microsoft Project 之间的鸿沟，为您提供跨平台的完整可视化，并提升整体项目管理效率。

---

**最后更新：** 2025-12-28  
**测试环境：** Aspose.Tasks for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}