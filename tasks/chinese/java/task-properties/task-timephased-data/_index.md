---
date: 2026-02-28
description: 了解如何使用 Aspose.Tasks for Java 来管理任务分阶段数据，下载库，免费试用，并简化项目跟踪。
linktitle: Task Timephased Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks 管理任务时间分段数据（Java）
url: /zh/java/task-properties/task-timephased-data/
weight: 34
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks 进行任务分阶段数据处理

## 介绍
如果您正在寻找 **how to use Aspose** 来紧密掌控项目进度，那么您来对地方了。对任务分阶段数据的精确跟踪是成功项目管理的基石，Aspose.Tasks for Java 为您提供了自动化该过程所需的工具。在本教程中，我们将演示一个完整的端到端示例，展示如何使用 Aspose.Tasks 创建项目、分配资源、设置基线，最后检索并显示分阶段数据。

## 快速答案
- **What does “timephased data” mean?** 它是按时间间隔（天、周、月）划分的数据，显示项目时间线上的工作、成本或剩余工作。  
- **Which library provides this capability?** Aspose.Tasks for Java。  
- **Do I need a license to run the sample?** 免费试用可用于开发；生产环境需要许可证。  
- **What Java version is required?** Java 8 或更高版本。  
- **Can I export the results to Excel?** 可以 — 您可以遍历 `TimephasedData` 集合并将值写入任何所需格式。

## 什么是任务分阶段数据？
任务分阶段数据表示在项目日历的每个时间片段中为任务安排的工作（或成本）量。它使您能够查看工作分配情况，发现资源超额分配，并比较计划进度与实际进度。

## 为什么使用 Aspose.Tasks 来管理分阶段数据？
- **Full control** – 在不打开 Microsoft Project 的情况下，以编程方式创建、修改和查询分阶段信息。  
- **Cross‑platform** – 可在任何支持 Java 的操作系统上运行。  
- **No COM dependencies** – 适用于服务器端自动化。  
- **Rich API** – 开箱即支持基线、工作轮廓和自定义字段。

## 前提条件
在深入代码之前，请确保您已具备：

- **Java Development Environment** – 已安装 JDK 8+ 并配置 `JAVA_HOME`。  
- **Aspose.Tasks for Java Library** – 下载并在项目中引用 Aspose.Tasks 库。您可以在[此处](https://releases.aspose.com/tasks/java/)找到该库。  
- **Document Directory** – 您机器上的一个文件夹，用于读取和写入示例项目文件（`project.xml`）。

## 导入包
在您的 Java 项目中，导入必要的 Aspose.Tasks 类：

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
import java.math.BigDecimal;
import java.util.Date;
import java.util.List;
```

## 步骤 1：设置项目开始日期
```java
Project project = new Project(dataDir + "project.xml");
// Additional code for package imports
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
*Explanation:* 我们创建一个 `Project` 实例，初始化一个 `Calendar` 为所需的开始日期，并将其分配给项目的 `START_DATE` 属性。

## 步骤 2：定义任务和资源
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
*Explanation:* 在根任务下添加了一个名为 **Task** 的新任务。我们还创建了一个名为 **Rsc** 的资源，并设置其标准费率和加班费率。

## 步骤 3：设置任务持续时间
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
*Explanation:* 该任务的计划持续时间为 **6 天**。

## 步骤 4：将资源分配给任务
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
*Explanation:* 通过 `ResourceAssignment` 将先前定义的资源链接到任务。

## 步骤 5：配置资源分配
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
*Explanation:* 我们设置分配的停止和恢复日期（使用占位值），并应用 **Back‑Loaded** 工作轮廓，使更多工作向分配的后期倾斜。

## 步骤 6：设置基线
```java
project.setBaseline(BaselineType.Baseline);
```
*Explanation:* 捕获基线后，您可以在以后比较计划值与实际值。

## 步骤 7：更新任务完成情况
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
*Explanation:* 任务被标记为 **50 % 完成**，这将影响剩余工作量的计算。

## 步骤 8：检索分阶段数据
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
*Explanation:* 此调用获取分配的 **remaining work**，并按项目的时间间隔进行拆分。

## 步骤 9：显示分阶段数据
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Additional code for displaying other values
```
*Explanation:* 我们仅打印分阶段条目的数量以及第一个条目的值。在实际场景中，您会遍历列表并将数据导出到报告或 UI。

## 常见问题及解决方案
- **NullPointerException on `getTimephasedData`** – 在调用该方法之前，请确保已设置分配的 `START` 和 `FINISH` 日期。  
- **Incorrect work contour** – 验证您选择的 `WorkContourType` 与您的调度策略匹配；`BackLoaded` 只是多种选项之一。  
- **Baseline not reflecting changes** – 请记得在定义任务、资源和分配后再调用 `project.setBaseline`。

## 常见问题
### Q: 我可以在任何 Java 项目中使用 Aspose.Tasks for Java 吗？
A: 可以，Aspose.Tasks for Java 与任何基于 Java 的项目兼容。

### Q: 我在哪里可以找到 Aspose.Tasks for Java 的额外支持？
A: 请访问 [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) 获取支持和讨论。

### Q: 是否有 Aspose.Tasks for Java 的免费试用？
A: 有，您可以在[此处](https://releases.aspose.com/)体验免费试用。

### Q: 我如何获取 Aspose.Tasks for Java 的临时许可证？
A: 您可以在[此处](https://purchase.aspose.com/temporary-license/)获取临时许可证。

### Q: 我在哪里可以购买 Aspose.Tasks for Java？
A: 您可以在[此处](https://purchase.aspose.com/buy)购买 Aspose.Tasks for Java。

---

**Last Updated:** 2026-02-28  
**Tested With:** Aspose.Tasks for Java 24.12（撰写时的最新版本）  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}