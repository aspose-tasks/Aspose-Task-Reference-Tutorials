---
date: 2026-02-23
description: 学习如何使用 Aspose.Tasks for Java 在项目任务中管理加班，包括如何计算加班费用以及简化资源跟踪。
linktitle: Overtimes in Tasks with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks 管理任务中的加班
url: /zh/java/task-properties/overtimes-in-tasks/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks 管理任务中的加班

## Introduction
如果您正在寻找 **如何在 Microsoft Project 文件中管理加班**，您来对地方了。在本教程中，我们将展示 Aspose.Tasks for Java 如何读取、修改和报告每个任务的加班相关属性，从而保持您的进度表和预算的准确性。  

## Quick Answers
- **在项目中，“加班”是什么意思？** 超出资源常规容量的额外工作时间。  
- **哪个 API 类提供加班数据？** `Task` 与 `Tsk` 字段集合（例如 `Tsk.OVERTIME_COST`）。  
- **运行示例是否需要许可证？** 是的，生产使用需要临时或完整的 Aspose.Tasks 许可证。  
- **我可以自动计算加班费用吗？** 当然——检索 `Tsk.OVERTIME_COST` 并应用您的费用率逻辑。  
- **这与 Java 17 兼容吗？** 是的，Aspose.Tasks for Java 支持 Java 8 及以上版本。

## What is Overtime Management in Project Tasks?
加班管理是指在资源超出正常工作时间时跟踪额外的工作和费用。准确捕获这些数据有助于预测预算、调整进度并报告真实的项目健康状况。

## Why Use Aspose.Tasks for Overtime?
* **无需 Microsoft Project** – 直接操作 .MPP 文件。  
* **完整访问加班字段** – 成本、工作量和完成百分比值通过 `Tsk` 枚举公开。  
* **编程控制** – 您可以读取、修改或计算加班费用，而无需手动 UI 步骤。

## Prerequisites
在开始教程之前，请确保具备以下前置条件：
- Java 开发环境：确保您的机器上已设置 Java 开发环境。  
- Aspose.Tasks for Java：下载并安装 Aspose.Tasks 库。您可以在[此处](https://reference.aspose.com/tasks/java/)找到库及其文档。  
- 项目文件：准备一个项目文件（例如 TaskOvertimes.mpp），在教程中使用。

## Import Packages
在您的 Java 项目中，导入必要的 Aspose.Tasks 包以利用其功能。添加以下导入语句：

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## Step 1: Create a New Project
创建新项目（或加载现有项目）是任何分析的第一步。这也满足了次要关键词 **create new project**。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create a new project
Project project = new Project(dataDir + "TaskOvertimes.mpp");
```

## Step 2: Iterate Through Tasks and Print Overtime Details
现在我们将遍历每个顶层任务，显示其加班信息，并演示如何通过读取 `OVERTIME_COST` 字段来 **计算加班费用**。

```java
for (Task tsk : project.getRootTask().getChildren()) {
    System.out.println("Overtime Cost: " + tsk.get(Tsk.OVERTIME_COST));
    System.out.println("Overtime Work: " + tsk.get(Tsk.OVERTIME_WORK).toString());
    System.out.println("Percent Complete: " + tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println("Percent Work Complete: " + tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println("Physical Percent Complete: " + tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
    // Set percent complete
    tsk.set(Tsk.PERCENT_COMPLETE, 100);
}
```

> **提示：** `OVERTIME_COST` 值已由 Aspose.Tasks 根据资源的加班费率自动计算。如果需要自定义计算，可将 `OVERTIME_WORK` 乘以您自己的费率，并使用 `tsk.set(Tsk.OVERTIME_COST, yourValue);` 更新该字段。

## Common Issues and Solutions
| 问题 | 解决方案 |
|-------|----------|
| **加班字段为空值** | 确保源 .MPP 文件实际包含加班数据；否则字段返回 `null`。 |
| **修改后费用不正确** | 更改加班工作量或费用后，调用 `project.save()` 以持久化更改。 |
| **未找到许可证** | 将您的 `Aspose.Tasks.lic` 文件放在项目根目录，或在加载项目之前以编程方式设置许可证。 |

## Frequently Asked Questions

**Q: Aspose.Tasks 适用于大规模项目管理吗？**  
A: 是的，Aspose.Tasks 旨在处理各种规模的项目，从小型计划到大型复杂项目。

**Q: 我可以将 Aspose.Tasks 与其他 Java 框架集成吗？**  
A: 当然！Aspose.Tasks 可无缝集成 Spring、Jakarta EE 等 Java 生态系统，提升其多样性。

**Q: 使用 Aspose.Tasks 有哪些许可证注意事项？**  
A: 有的，您可以在[此处](https://purchase.aspose.com/temporary-license/)查看许可证详情并获取临时许可证。

**Q: 我可以在哪里寻求帮助或讨论 Aspose.Tasks 相关问题？**  
A: 访问 [Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15) 与社区交流并获取支持。

**Q: 是否有 Aspose.Tasks 的免费试用版？**  
A: 有，您可以在[此处](https://releases.aspose.com/)获取免费试用版。

**Q: 如何计算特定资源的加班费用？**  
A: 获取该资源的加班费率，将其乘以 `OVERTIME_WORK`（小时），如果需要自定义计算，则将结果设置回 `OVERTIME_COST`。

## Conclusion
Aspose.Tasks for Java 简化了 **如何在项目任务中管理加班**，为开发者提供对加班费用、工作量和进度指标的直接编程访问。通过本指南，您可以加载项目、读取加班详情、调整百分比，甚至计算自定义加班费用——全部无需打开 Microsoft Project。

---

**最后更新：** 2026-02-23  
**测试环境：** Aspose.Tasks for Java（最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}