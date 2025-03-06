---
title: 在 Aspose.Tasks 中管理关键任务和工作驱动任务
linktitle: 在 Aspose.Tasks 中管理关键任务和工作驱动任务
second_title: Aspose.Tasks Java API
description: 使用 Aspose.Tasks 轻松管理 Java 项目中的关键和需要大量精力的任务。下载该库并增强您的项目管理能力。
type: docs
weight: 14
url: /zh/java/task-properties/critical-effort-driven-tasks/
---
在快节奏的项目管理世界中，有效处理关键和需要付出努力的任务对于成功完成项目至关重要。 Aspose.Tasks for Java 提供了一个强大的解决方案来无缝管理这些任务。在本教程中，我们将指导您完成使用 Aspose.Tasks for Java 处理项目中的关键任务和工作驱动型任务的过程。
## 先决条件
在我们深入学习本教程之前，请确保您具备以下先决条件：
- Aspose.Tasks for Java Library：从以下位置下载并安装该库：[Aspose.Tasks for Java 文档](https://reference.aspose.com/tasks/java/).
- Java 开发工具包 (JDK)：确保您的系统上安装了 Java。
- 集成开发环境 (IDE)：使用您首选的 IDE 进行 Java 开发。
- 项目文件：准备一个 XML 格式的项目文件，用于演示。
## 导入包
在您的 Java 项目中，导入必要的包以利用 Aspose.Tasks for Java 的功能：
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
```
现在，让我们将每个步骤分解为一个综合指南：
## 第 1 步：使用 ChildTasksCollector 收集任务
创建一个`ChildTasksCollector`使用实例从根任务收集所有任务`TaskUtils.apply`。这确保您可以访问项目内的所有任务。
```java
//文档目录的路径。
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "project.xml");
//创建一个 ChildTasksCollector 实例
ChildTasksCollector collector = new ChildTasksCollector();
//使用 TaskUtils 从 RootTask 收集所有任务
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## 第 2 步：迭代收集的任务
使用 a 解析所有收集到的任务`for`环形。对于每项任务，确定它是否是努力驱动的和关键的，并打印相应的状态。
```java
//解析所有收集的任务
for (Task tsk : collector.getTasks()) {
    String strED = tsk.get(Tsk.IS_EFFORT_DRIVEN) != null ? "EffortDriven" : "Non-EffortDriven";
    String strCrit = tsk.get(Tsk.IS_CRITICAL) != null ? "Critical" : "Non-Critical";
    System.out.println(strED);
    System.out.println(strCrit);
}
```
通过执行这些步骤，您可以使用 Aspose.Tasks for Java 有效管理项目中的关键任务和工作驱动型任务。
## 结论
总之，Aspose.Tasks for Java 使 Java 开发人员能够有效地管理项目管理中的关键任务和工作驱动型任务。凭借其易于使用的特性和强大的功能，处理复杂的项目场景变得轻而易举。
## 经常问的问题
### 问：我可以在 Windows 和 Linux 环境中使用 Aspose.Tasks for Java 吗？
是的，Aspose.Tasks for Java 是独立于平台的，可以在 Windows 和 Linux 环境中使用。
### 问：Aspose.Tasks for Java 是否有免费试用版？
是的，您可以免费试用 Aspose.Tasks for Java[这里](https://releases.aspose.com/).
### 问：在哪里可以找到 Aspose.Tasks for Java 的支持？
参观[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)以获得社区支持和讨论。
### 问：如何获得 Aspose.Tasks for Java 的临时许可证？
您可以获得临时许可证[这里](https://purchase.aspose.com/temporary-license/).
### 问：哪里可以购买 Aspose.Tasks for Java？
您可以从以下位置购买 Aspose.Tasks for Java[购买页面](https://purchase.aspose.com/buy).