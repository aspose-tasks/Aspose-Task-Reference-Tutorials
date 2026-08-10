---
date: 2026-07-14
description: 了解如何停止资源分配 Java、管理资源分配，并在本分步指南中查看使用 Aspose.Tasks for Java 的示例。
keywords:
- stop resource assignment java
- Aspose.Tasks Java
- resource assignment management
- project scheduling Java
lastmod: 2026-07-14
linktitle: 在 Aspose.Tasks 中停止和恢复资源分配
og_description: 使用 Aspose.Tasks 停止资源分配 Java。本教程展示了如何暂停和恢复分配、处理日期，以及在不使用 Microsoft
  Project 的情况下集成 API。
og_image_alt: Guide to stop and resume resource assignments in Aspose.Tasks for Java
og_title: 停止资源分配 Java – Aspose.Tasks 指南
schemas:
- author: Aspose
  dateModified: '2026-07-14'
  description: Learn how to stop resource assignment java, manage resource assignments,
    and view examples using Aspose.Tasks for Java in this step‑by‑step guide.
  headline: How to Stop Resource Assignment Java – Resume with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Use `ra.set(Asn.STOP, yourDateObject);` where `yourDateObject` is a `java.util.Date`.
    question: How do I programmatically set a stop date for an assignment?
  - answer: The API does not enforce chronological order; however, the scheduler will
      treat the assignment as active only after the later of the two dates, so you
      should validate dates yourself.
    question: What happens if the resume date is earlier than the stop date?
  - answer: Yes, iterate through `prj.getResourceAssignments()` and check `ra.get(Asn.STOP)
      != null`.
    question: Can I filter assignments to only those that have a stop date set?
  - answer: Set the stop date to `null` with `ra.set(Asn.STOP, null);` and then save
      the project.
    question: Is it possible to remove a stop date once set?
  - answer: Absolutely. The `Asn` enum provides constants for all assignment fields,
      such as `Asn.START`, `Asn.FINISH`, etc.
    question: Does Aspose.Tasks support other date‑related fields like start, finish,
      or actual start?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- stop resource assignment
- Aspose.Tasks
- Java project scheduling
- resource management
title: 如何停止资源分配 Java – 使用 Aspose.Tasks 恢复
url: /zh/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何停止资源分配 Java – 使用 Aspose.Tasks 恢复

## 介绍
在本教程中，您将学习**如何停止资源分配 Java**，并随后使用 Aspose.Tasks for Java 恢复它。Aspose.Tasks 是一个强大的 Java API，能够读取和写入 Microsoft Project 文件、操作进度表以及控制资源分配——无需安装 Microsoft Project。我们将逐步演示每一步，解释每行代码的意义，并分享可在实际项目计划中应用的实用技巧。

## 快速答案
- **“stop assignment” 是什么意思？** 它将资源分配标记为从特定停止日期起暂时不活动。  
- **我可以稍后恢复同一分配吗？** 可以，通过在同一分配上设置恢复日期。  
- **使用此 API 是否需要 Microsoft Project？** 不需要，Aspose.Tasks 独立于 Microsoft Project 工作。  
- **需要哪个 Java 版本？** 推荐使用 Java 8 或更高版本。  
- **在哪里可以下载该库？** 在官方的 Aspose.Tasks Java 下载页面。

## 如何停止资源分配 Java？
加载项目，定位目标 `ResourceAssignment`，设置 `STOP` 日期，可选地设置 `RESUME` 日期，然后保存文件。此过程会在指定期间暂停工作，并在恢复日期后自动重新激活，使您能够精确控制资源日历，而无需手动编辑文件。

## 在 Aspose.Tasks 中，“如何停止分配” 是什么意思？
停止分配会指示调度器忽略资源在 **stop date** 之后（直到 **resume date**，如果有的话）的工作分配。这对于处理假期、设备停机或任何资源不应被视为活动的期间非常有用。

## 为什么使用 Aspose.Tasks 管理资源分配？
Aspose.Tasks 让您能够以编程方式控制分配日期，消除手动编辑并降低错误风险。它支持 **50 多种输入和输出格式**，并且能够处理包含 **多达 10,000 个任务** 的项目，同时内存使用保持在 200 MB 以下，因为它采用流式处理而不是一次性加载整个文件。该 API 可在任何支持 Java 的操作系统上运行，为您提供跨平台的灵活性。

## 前置条件
- 已安装 Java Development Kit (JDK) 8 或更高版本。  
- 已下载 Aspose.Tasks for Java 库。您可以从 [here](https://releases.aspose.com/tasks/java/) 下载。  
- 对 Java 编程有基本了解。  

## 导入包
`Project`、`ResourceAssignment` 和 `Asn` 类位于 `com.aspose.tasks` 命名空间。请在源文件顶部导入它们：

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## 步骤 1：加载项目文件
`Project` 类是 Aspose.Tasks 的顶层对象，表示内存中的单个 Microsoft Project 文件。创建实例会加载文件，并让您访问任务、资源和分配。

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

## 步骤 2：遍历资源分配
`ResourceAssignment` 对象公开所有与分配相关的字段。我们设置一个 **minimum date** 来过滤占位日期，然后遍历每个分配。此模式是检查或修改的标准 *resource assignment example*。

```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

## 步骤 3：检查停止和恢复日期
在此代码块中，我们检查每个分配的 `STOP` 和 `RESUME` 字段。如果日期早于我们的 `minDate`，则视为未设置（`"NA"`）；否则打印实际日期。此逻辑对于正确 **manage resource assignments** 至关重要。

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

## 常见问题及解决方案
- **空日期** – `ra.get(Asn.STOP)` 可能返回 `null`。在调用 `.before(minDate)` 之前添加空检查以防止此情况。  
- **文件路径不正确** – 确保 `dataDir` 以适合您操作系统的路径分隔符（`/` 或 `\\`）结尾。  
- **版本不匹配** – 使用最新的 Aspose.Tasks for Java 版本，以避免缺少枚举值。  

## 常见问题

**Q: 如何以编程方式为分配设置停止日期？**  
A: 使用 `ra.set(Asn.STOP, yourDateObject);`，其中 `yourDateObject` 为 `java.util.Date` 类型的对象。

**Q: 如果恢复日期早于停止日期会怎样？**  
A: API 不会强制时间顺序；然而，调度器只会在两者中较晚的日期之后将分配视为活动，因此您应自行验证日期。

**Q: 我能否仅筛选出已设置停止日期的分配？**  
A: 可以，遍历 `prj.getResourceAssignments()` 并检查 `ra.get(Asn.STOP) != null`。

**Q: 设置后是否可以删除停止日期？**  
A: 使用 `ra.set(Asn.STOP, null);` 将停止日期设为 `null`，然后保存项目。

**Q: Aspose.Tasks 是否支持其他与日期相关的字段，如 start、finish 或 actual start？**  
A: 当然。`Asn` 枚举为所有分配字段提供常量，例如 `Asn.START`、`Asn.FINISH` 等。

## 结论
通过遵循这些步骤，您现在了解 **how to stop resource assignment java**，能够检查停止/恢复日期，并在需要时恢复分配。此功能使您能够更精确地 **manage resource assignments**，尤其在资源休假或设备停机等场景中。欢迎扩展示例以更新日期、生成报告或与您自己的调度逻辑集成。

---

**最后更新:** 2026-07-14  
**已测试:** Aspose.Tasks for Java 24.12  
**作者:** Aspose

## 相关教程

- [在 Aspose.Tasks 中创建资源分配](/tasks/java/resource-assignments/create-resource-assignments/)
- [如何计算成本差异并使用 Aspose.Tasks 管理分配成本](/tasks/java/resource-assignments/assignment-cost/)
- [如何向 Aspose.Tasks 中的资源分配添加备注](/tasks/java/resource-assignments/resource-assignment-notes/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}