---
date: 2026-03-03
description: 学习如何在 Aspose.Tasks for Java 中重新编号 WBS，管理工作分解并通过一步步示例高效自定义 WBS 代码。
linktitle: WBS Associated with Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何在 Aspose.Tasks for Java 中重新编号 WBS
url: /zh/java/task-properties/wbs-associated-with-task/
weight: 36
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks for Java 中重新编号 WBS

## 介绍
如果您需要在 Microsoft Project 文件中使用 Aspose.Tasks for Java **重新编号 WBS**，这里就是您要找的地方。本教程将手把手教您读取已有的 WBS 编码、进行自定义，然后重新编号层级，使您的项目保持有序。无论是清理遗留的计划还是从头构建新计划，掌握这些步骤都能帮助您 **自信地管理工作分解结构**。

## 快速答案
- **重新编号 WBS 的作用是什么？** 它会重新计算任务的层级编号，以反映任何结构性变更。  
- **哪个类执行重新编号？** `Project.renumberWBSCode`。  
- **运行代码是否需要许可证？** 生产环境下需要有效的 Aspose.Tasks 许可证。  
- **我可以自定义 WBS 格式吗？** 可以——使用 `Task.set(Tsk.WBS, "...")` 为任务分配任意字符串。  
- **主要前置条件有哪些？** Java JDK、Aspose.Tasks for Java 库以及有效的项目文件（.mpp）。

## 什么是工作分解结构（WBS）？
工作分解结构（WBS）是项目交付物和任务的层级表示。每个任务都有一个代码（例如 1.2.3），反映其在层级中的位置。当任务被添加、删除或重新排序时，重新编号变得至关重要，以确保代码保持逻辑且易于阅读。

## 为什么要管理工作分解并自定义 WBS 编码？
- **清晰度：** 明确的 WBS 编码让利益相关者能够轻松定位任务。  
- **报告：** 许多报表工具依赖一致的编号。  
- **灵活性：** 自定义编码可以让项目结构与内部标准保持一致。  

## 前置条件
在深入代码之前，请确认您已具备以下条件：

- 在机器上安装了 Java Development Kit（JDK）。  
- 已将 Aspose.Tasks for Java 库添加到项目中。您可以从[此处](https://releases.aspose.com/tasks/java/)获取。

## 导入包
确保导入必要的包以启动项目：

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```

## 读取 WBS 编码
首先，我们读取已有的 WBS 编码，以便您了解当前情况。

### 步骤 1：加载项目
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```

### 步骤 2：收集任务
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

### 步骤 3：解析并自定义
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```

上面的代码片段会打印每个任务的当前 WBS 和层级，并演示通过分配新字符串来 **自定义 WBS 编码**。

## 重新编号任务 WBS 编码
接下来我们实际进行 WBS 层级的重新编号。

### 步骤 1：加载项目（重新编号示例）
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```

### 步骤 2：选择所有任务
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```

### 步骤 3：输出初始 WBS 编码
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

### 步骤 4：重新编号 WBS 编码
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```

### 步骤 5：输出更新后的 WBS 编码
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

按照这些步骤，您即可对项目文件中的任意任务集合 **重新编号 WBS**。

## 常见问题及解决方案
- **`set` 调用后 WBS 未变化：** 确认您操作的是正确的任务实例，并在修改后保存项目。  
- **`renumberWBSCode` 抛出异常：** 检查 ID 列表是否与顶层任务数量匹配，否则方法无法正确映射新编号。  
- **缺少 WBS 值：** 某些任务可能因导入的文件未定义而为 `null`，在打印前使用默认值进行兜底。

## 常见问答

**问：在哪里可以找到 Aspose.Tasks for Java 的文档？**  
答：文档可在[此处](https://reference.aspose.com/tasks/java/)查看。

**问：如何下载 Aspose.Tasks for Java？**  
答：您可以在[此处](https://releases.aspose.com/tasks/java/)下载。

**问：Aspose.Tasks for Java 是否提供免费试用？**  
答：是的，免费试用可在[此处](https://releases.aspose.com/)获取。

**问：在哪里可以获得 Aspose.Tasks for Java 的支持？**  
答：请访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)获取支持。

**问：我可以为 Aspose.Tasks for Java 获取临时许可证吗？**  
答：可以，临时许可证请前往[此处](https://purchase.aspose.com/temporary-license/)。

**问：重新编号后我可以重新命名 WBS 格式吗？**  
答：当然可以。在调用 `renumberWBSCode` 后，您可以遍历任务并使用 `task.set(Tsk.WBS, "NewFormat-" + task.get(Tsk.WBS))` 来符合您的命名约定。

**问：重新编号会影响任务依赖关系吗？**  
答：不会。该方法仅更新 WBS 字符串，任务链接和约束保持不变。

---

**最后更新：** 2026-03-03  
**测试环境：** Aspose.Tasks for Java 24.12（最新）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}