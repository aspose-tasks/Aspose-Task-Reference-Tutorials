---
title: 掌握Aspose.Tasks中的任务属性
linktitle: 在 Aspose.Tasks 中读取和写入任务的常规属性
second_title: Aspose.Tasks Java API
description: 探索 Aspose.Tasks for Java 在轻松管理任务属性方面的强大功能。使用我们的分步指南轻松阅读和写作。
weight: 26
url: /zh/java/task-properties/read-write-general-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 掌握Aspose.Tasks中的任务属性

## 介绍
使用 Aspose.Tasks 释放 Java 任务管理的全部潜力。在本综合指南中，我们将深入研究使用 Aspose.Tasks for Java 读取和写入任务的一般属性。无论您是经验丰富的开发人员还是初学者，本教程都将为您提供轻松操作任务属性的技能。
## 先决条件
在我们深入学习本教程之前，请确保您具备以下先决条件：
- 您的系统上安装了 Java 开发工具包 (JDK)。
- 下载并设置了 Aspose.Tasks for Java 库。你可以找到下载链接[这里](https://releases.aspose.com/tasks/java/).
- 代码编辑器，例如 IntelliJ IDEA 或 Eclipse。
## 导入包
首先，在您的 Java 项目中导入必要的包。此步骤确保您可以访问 Aspose.Tasks 功能。这是一个指导您的片段：
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
## 读取任务的一般属性
## 第 1 步：创建任务
首先在您的项目中创建一个任务。这涉及设置任务名称、开始日期和其他相关详细信息。这是一个例子：
```java
//文档目录的路径。
String dataDir = "Your Document Directory";
Project project = new Project();
Task task = project.getRootTask().getChildren().add("Task1");
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, Calendar.JULY, 17, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.NAME, "new name");
```
## 第 2 步：读取任务属性
现在您已经创建了一个任务，让我们检索并显示其常规属性。下面的代码片段完成了这个任务：
```java
//读取任务的一般属性
Project prj = new Project(dataDir + "project.xml");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(prj.getRootTask(), collector, 0);
for (Task tsk : collector.getTasks()) {
    System.out.println("Task Id:" + tsk.get(Tsk.ID));
    System.out.println("Task Uid: " + tsk.get(Tsk.UID));
    System.out.println("Task Name: " + tsk.get(Tsk.NAME));
    System.out.println("Task Start: " + tsk.get(Tsk.START));
    System.out.println("Task Finish: " + tsk.get(Tsk.FINISH));
}
```
## 编写任务的一般属性
## 第 3 步：加载项目并创建收集器
要写入常规属性，请加载现有项目并设置`ChildTasksCollector`：
```java
Project prj = new Project(dataDir + "project.xml");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(prj.getRootTask(), collector, 0);
```
## 第4步：解析并显示属性
最后，解析收集到的任务并显示它们的属性：
```java
for (Task tsk : collector.getTasks()) {
    System.out.println("Task Id:" + tsk.get(Tsk.ID));
    System.out.println("Task Uid: " + tsk.get(Tsk.UID));
    System.out.println("Task Name: " + tsk.get(Tsk.NAME));
    System.out.println("Task Start: " + tsk.get(Tsk.START));
    System.out.println("Task Finish: " + tsk.get(Tsk.FINISH));
}
```
恭喜！您已使用 Aspose.Tasks for Java 成功读取和写入任务的常规属性。
## 结论
在本教程中，我们探索了使用 Aspose.Tasks for Java 无缝操作任务属性的基本步骤。通过掌握这些技术，您可以提高 Java 开发技能并简化项目中的任务管理。
## 常见问题解答
### Aspose.Tasks 与 Java 11 兼容吗？
是的，Aspose.Tasks 与 Java 11 及更高版本兼容。
### 我可以将 Aspose.Tasks 用于商业项目吗？
绝对地！ Aspose.Tasks 是个人和商业项目的强大工具。访问[这里](https://purchase.aspose.com/buy)探索许可选项。
### 我如何获得用于测试目的的临时许可证？
获得临时许可证[这里](https://purchase.aspose.com/temporary-license/)用于测试和评估。
### 在哪里可以找到 Aspose.Tasks 的社区支持？
加入社区讨论：[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)寻求帮助和合作。
### 有没有示例项目可供参考？
浏览文档的示例部分[这里](https://reference.aspose.com/tasks/java/)用于示例项目和代码片段。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
