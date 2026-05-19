---
date: 2026-01-15
description: 了解如何使用 Aspose.Tasks for Java 处理 Microsoft Project 文件中已排程的预算成本工作。请按照我们的分步指南进行操作。
linktitle: Handle Resource Cost in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks for Java 调度预算成本工作
url: /zh/java/resource-management/resource-cost/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks for Java 的预算成本工作计划

## 介绍

管理 **预算成本工作计划** (BCWS) 对于保持项目进度并确保财务预测与计划工作保持一致至关重要。在 Microsoft Project 中，BCWS 表示截至特定日期应为已安排的工作支出的金额。Aspose.Tasks for Java 为您提供对这些值的完整编程控制，让您能够读取、修改和报告资源成本，而无需手动打开 .mpp 文件。在本教程中，我们将通过完整示例演示如何加载项目、遍历其资源，并显示预算成本工作计划以及其他关键成本指标。

## 快速答案
- **BCWS 是什么？** 预算成本工作计划 – 截至目前已安排工作的计划成本。  
- **哪个 API 属性检索 BCWS？** `Resource` 对象上的 `Rsc.BCWS`。  
- **运行示例是否需要许可证？** 免费评估许可证可用于测试；生产环境需要完整许可证。  
- **我可以修改 BCWS 值吗？** 可以，您可以像设置其他数值字段一样设置 `Rsc.BCWS`。  
- **支持的 Project 版本？** 所有从 2000 到最新 .mpp 格式的 Microsoft Project 版本。

## 什么是预算成本工作计划？

**预算成本工作计划 (BCWS)** 是一种绩效衡量指标，反映截至某一时间点应为已计划工作产生的成本。它是挣值管理 (EVM) 的基石，帮助项目经理比较计划支出与实际支出。

## 前提条件

1. 扎实的 Java 基础。  
2. 将 Aspose.Tasks for Java 添加到项目中（Maven/Gradle 或 JAR）。  
3. 包含资源成本数据的 Microsoft Project 文件（`.mpp`），例如 *ResourceCosts.mpp*。

## 导入包

First, import the Aspose.Tasks classes required for handling projects and resources:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## 步骤 1：定义数据目录

将 `"Your Data Directory"` 替换为 *ResourceCosts.mpp* 所在的绝对或相对路径。

```java
String dataDir = "Your Data Directory";
```

## 步骤 2：加载 MS Project 文件

`Project` 构造函数读取 .mpp 文件并构建可查询的内存表示。

```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```

## 步骤 3：遍历资源

此循环遍历项目中定义的每个资源，提供对其成本字段的访问。

```java
for (Resource res : prj.getResources()) {
```

## 步骤 4：检查资源名称和成本

Inside the `if` block we:

* 打印 **总成本** (`Rsc.COST`)。  
* 打印 **实际已完成工作成本** (`Rsc.ACWP`)。  
* 打印 **预算成本工作计划** (`Rsc.BCWS`) —— 我们关注的主要指标。  
* 打印 **预算成本已完成工作** (`Rsc.BCWP`)。

这些四个值可快速概览项目的财务状态。

```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.COST));
    System.out.println(res.get(Rsc.ACWP));
    System.out.println(res.get(Rsc.BCWS));
    System.out.println(res.get(Rsc.BCWP));
}
```

## 为什么监控预算成本工作计划很重要

* **早期预警：** 如果 BCWS 明显高于实际成本，可能意味着资源分配过度。  
* **挣值分析：** BCWS 是计算成本偏差 (CV) 和进度偏差 (SV) 的关键输入。  
* **预测：** 准确的 BCWS 数据有助于预测未来现金流需求，并为利益相关者报告提供依据。

## 常见问题与故障排除

| 症状 | 可能原因 | 解决办法 |
|---------|--------------|-----|
| `null` 打印为 BCWS | 资源未定义成本费率表 | 在 Microsoft Project 中为资源定义成本费率表，或通过 `Rsc.COST_RATE_TABLE` 编程设置 |
| 遍历资源时出现 `ArrayIndexOutOfBoundsException` | 项目文件损坏或包含空资源条目 | 在 Microsoft Project 中验证 .mpp 文件并删除空资源 |
| 出现异常值（例如负数 BCWS） | 自定义字段覆盖了标准成本字段 | 确保访问的是标准的 `Rsc.BCWS`，而不是同名的自定义字段 |

## 常见问答

**问：我可以以编程方式更新 BCWS 值吗？**  
答：可以。使用 `res.set(Rsc.BCWS, newValue)`，然后使用 `prj.save("Updated.mpp")` 保存项目。

**问：Aspose.Tasks 是否支持多币种项目？**  
答：当然。成本字段遵循项目文件中定义的货币设置。

**问：有没有办法将这些成本指标导出为 CSV？**  
答：可以遍历资源并将值写入 `StringBuilder`，或使用 CSV 库生成文件。

**问：BCWS 与 BCWP 有何区别？**  
答：BCWS 是已安排工作计划的成本，而 BCWP（已完成工作预算成本）反映已实际完成工作的计划成本。

**问：读取成本数据是否需要特殊许可证？**  
答：评估许可证提供完整的读写权限；生产部署需要商业许可证。

## 结论

通过使用 Aspose.Tasks for Java，您可以精确、以编程方式访问 **预算成本工作计划** 以及其他关键成本指标。这使您能够构建自定义仪表板、自动化挣值报告，并保持项目的财务进度——全部无需手动操作 Microsoft Project。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-01-15  
**Tested With:** Aspose.Tasks for Java 24.12 (latest)  
**Author:** Aspose