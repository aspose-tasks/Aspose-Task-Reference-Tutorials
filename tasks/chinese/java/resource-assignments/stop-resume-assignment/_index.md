---
date: 2026-01-10
description: 通过本分步教程，了解如何停止分配、管理资源分配以及查看 Aspose.Tasks for Java 中的资源分配示例。
linktitle: Stop and Resume Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何在 Aspose.Tasks 中停止分配并恢复资源分配
url: /zh/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中停止分配并恢复资源分配

## 介绍
在本教程中，**您将学习如何停止分配**并随后使用 Aspose.Tasks for Java 恢复它。Aspose.Tasks 是一个强大的 Java API，能够读取项目文件的 Java 格式，操作 Microsoft Project 数据，并在无需安装 Microsoft Project 的情况下管理资源分配。我们将逐步演示每一步，解释每行代码的意义，并提供可在实际项目中应用的实用技巧。

## 快速答案
- **“停止分配”是什么意思？** 它将资源分配标记为从特定停止日期起暂时不活动。  
- **我可以稍后恢复同一分配吗？** 可以，通过在同一分配上设置恢复日期。  
- **使用此 API 是否需要 Microsoft Project？** 不需要，Aspose.Tasks 独立于 Microsoft Project 工作。  
- **需要哪个版本的 Java？** 推荐使用 Java 8 或更高版本。  
- **在哪里可以下载该库？** 在官方 Aspose.Tasks Java 下载页面。

## 在 Aspose.Tasks 中“如何停止分配”是什么意思？
停止分配会指示调度器忽略资源在 **停止日期** 之后（直到 **恢复日期**，如果有的话）分配的工作。这对于处理假期、设备停机或任何资源不应被视为活动的期间非常有用。

## 为什么使用 Aspose.Tasks 来管理资源分配？
- **无需 Microsoft Project** – 直接处理 .mpp 文件。  
- **对日期的完整控制** – 您可以通过编程检查停止日期、恢复日期并进行调整。  
- **跨平台** – 在任何支持 Java 的操作系统上运行。  
- **丰富的 API** – 提供一个 *资源分配示例*，您可以将其扩展用于自定义报告。

## 前置条件
在开始之前，请确保您已具备以下条件：

- 已在系统上安装 Java Development Kit (JDK)。  
- 已下载 Aspose.Tasks for Java 库。您可以从 [此处](https://releases.aspose.com/tasks/java/) 下载。  
- 对 Java 编程有基本了解。

## 导入包
首先，让我们在 Java 项目中导入必要的包：

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## 步骤 1：加载项目文件
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

这里我们 **读取项目文件的 Java** 格式（`.mpp`），并创建一个 `Project` 对象，以便访问所有项目数据，包括资源分配。

## 步骤 2：遍历资源分配
```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

我们设置一个 **最小日期** 来过滤占位日期，然后遍历每个分配。这是常见的 *资源分配示例* 模式，用于检查或修改分配时使用。

## 步骤 3：检查停止和恢复日期
```java
    // Check stop date
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Check resume date
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```

在此代码块中，我们为每个分配 **检查停止日期** 和 **检查恢复日期**。如果日期早于我们的 `minDate`，则视为未设置（`"NA"`）；否则打印实际日期。此逻辑对于正确 **管理资源分配** 至关重要。

## 常见问题及解决方案
- **空日期** – `ra.get(Asn.STOP)` 可能返回 `null`。在调用 `.before(minDate)` 之前添加空值检查以防止错误。  
- **文件路径不正确** – 确保 `dataDir` 以适合您操作系统的路径分隔符（`/` 或 `\\`）结尾。  
- **版本不匹配** – 使用最新的 Aspose.Tasks for Java 版本，以避免缺少枚举值。

## 常见问题
### 我可以在未安装 Microsoft Project 的情况下使用 Aspose.Tasks 吗？
是的，Aspose.Tasks 允许您在系统上未安装 Microsoft Project 的情况下处理 Microsoft Project 文件。

### 在哪里可以找到更多文档？
您可以在 [此处](https://reference.aspose.com/tasks/java/) 找到详细文档。

### 是否提供免费试用？
是的，您可以在 [此处](https://releases.aspose.com/) 获取免费试用。

### 如果遇到问题，我该如何获取支持？
您可以在社区 [此处](https://forum.aspose.com/c/tasks/15) 获取支持。

### 我可以购买临时许可证吗？
是的，您可以在 [此处](https://purchase.aspose.com/temporary-license/) 购买临时许可证。

## 常见问答

**Q: 如何以编程方式为分配设置停止日期？**  
A: 使用 `ra.set(Asn.STOP, yourDateObject);`，其中 `yourDateObject` 为 `java.util.Date` 类型。

**Q: 如果恢复日期早于停止日期会怎样？**  
A: API 并不强制时间顺序；但调度器只会在两者中较晚的日期之后将分配视为活动状态，因此您需要自行验证日期。

**Q: 我可以仅过滤出已设置停止日期的分配吗？**  
A: 可以，遍历 `prj.getResourceAssignments()` 并检查 `ra.get(Asn.STOP) != null`。

**Q: 设置后是否可以移除停止日期？**  
A: 将停止日期设为 `null`，即 `ra.set(Asn.STOP, null);`，然后保存项目。

**Q: Aspose.Tasks 是否支持其他与日期相关的字段，如开始、完成或实际开始？**  
A: 当然。`Asn` 枚举提供了所有分配字段的常量，例如 `Asn.START`、`Asn.FINISH` 等。

## 结论
通过遵循这些步骤，您现在了解了 **如何停止分配**，检查停止/恢复日期，并在需要时恢复分配。此功能使您能够更精确地 **管理资源分配**，尤其适用于资源休假或设备停机等场景。欢迎扩展示例以更新日期、生成报告或与您自己的调度逻辑集成。

---

**最后更新：** 2026-01-10  
**测试环境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}