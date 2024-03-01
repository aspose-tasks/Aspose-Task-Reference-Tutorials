---
title: 与 Aspose.Tasks 中的任务关联的 WBS
linktitle: 与 Aspose.Tasks 中的任务关联的 WBS
second_title: Aspose.Tasks Java API
description: 使用 Aspose.Tasks for Java 掌握 WBS - 学习读取和重新编号任务 WBS 代码。提升项目管理效率！
type: docs
weight: 36
url: /zh/java/task-properties/wbs-associated-with-task/
---
## 介绍
欢迎来到 Aspose.Tasks for Java 的项目管理世界！在本教程中，我们将深入研究与使用 Aspose.Tasks for Java 的任务相关的工作分解结构 (WBS) 的复杂性。无论您是经验丰富的开发人员还是新手，本指南都将帮助您了解有效管理 WBS 代码的要点。
## 先决条件
在我们深入学习本教程之前，请确保您具备以下先决条件：
- 您的计算机上安装了 Java 开发工具包 (JDK)。
-  Aspose.Tasks for Java 库下载并添加到您的项目中。你可以从[这里](https://releases.aspose.com/tasks/java/).
## 导入包
确保导入必要的包来启动您的项目：
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```
## 读取 WBS 代码
让我们首先阅读与任务相关的 WBS 代码。按着这些次序：
## 第 1 步：加载项目
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```
## 第二步：收集任务
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## 第 3 步：解析和定制
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```
此代码片段读取并自定义与项目中的任务关联的 WBS 代码。
## 重新编号任务 WBS 代码
现在，让我们探讨如何对任务的 WBS 代码重新编号：
## 第 1 步：加载项目
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```
## 第 2 步：选择所有任务
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```
## 步骤3：输出初始WBS代码
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
## 步骤 4：重新编号 WBS 代码
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```
## 步骤 5：输出更新的 WBS 代码
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
通过执行这些步骤，您将有效地为项目中的任务重新编号 WBS 代码。
## 结论
恭喜！您已经成功学习了如何使用 Aspose.Tasks for Java 来处理 WBS 代码。这些知识将使您能够有效地管理和定制项目的任务层次结构。
## 常见问题解答
### 问：在哪里可以找到 Aspose.Tasks for Java 的文档？
答：文档已提供[这里](https://reference.aspose.com/tasks/java/).
### 问：如何下载 Aspose.Tasks for Java？
答： 你可以下载[这里](https://releases.aspose.com/tasks/java/).
### 问：Aspose.Tasks for Java 是否有免费试用版？
答：是的，您可以免费试用[这里](https://releases.aspose.com/).
### 问：在哪里可以获得 Aspose.Tasks for Java 的支持？
答：访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)为了支持。
### 问：我可以获得 Aspose.Tasks for Java 的临时许可证吗？
答：是的，获得临时许可证[这里](https://purchase.aspose.com/temporary-license/).