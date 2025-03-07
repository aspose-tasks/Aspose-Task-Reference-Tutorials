---
title: 在 Aspose.Tasks 中停止和恢复任务
linktitle: 在 Aspose.Tasks 中停止和恢复任务
second_title: Aspose.Tasks Java API
description: 通过我们有关停止和恢复任务的分步指南来探索 Aspose.Tasks for Java 的强大功能。无缝增强项目管理！
weight: 30
url: /zh/java/task-properties/stop-resume-task/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中停止和恢复任务

## 介绍
在 Java 开发领域，有效管理任务是项目执行的一个重要方面。 Aspose.Tasks for Java 以其强大的功能提供了处理任务的强大解决方案。在本教程中，我们将深入研究一项特定功能 - 停止和恢复任务。通过遵循此分步指南，您将能够将此功能无缝集成到您的 Java 项目中。
## 先决条件
在深入学习本教程之前，请确保您具备以下先决条件：
- 对 Java 编程有基本的了解。
- 在您的系统上安装了 Java 开发工具包 (JDK)。
- Aspose.Tasks for Java 库下载并添加到您的项目中。您可以从以下位置获取它：[这里](https://releases.aspose.com/tasks/java/).
## 导入包
要开始该过程，请确保将必要的包导入到您的 Java 项目中：
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
import java.util.GregorianCalendar;
```
## 第 1 步：初始化
首先初始化您的项目并创建一个`ChildTasksCollector`实例来收集所有任务。
```java
//文档目录的路径。
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "Software Development.mpp");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## 第 2 步：设置最短日期
定义最短日期来过滤需要停止或恢复的任务。
```java
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
```
## 第 3 步：停止和恢复任务
迭代任务，检查并打印停止和恢复日期。
```java
for (Task tsk : collector.getTasks()) {
    if (tsk.get(Tsk.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.STOP).toString());
    }
    if (tsk.get(Tsk.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.RESUME).toString());
    }
}
```
在您的 Java 项目中重复这些步骤，以使用 Aspose.Tasks for Java 无缝集成停止和恢复功能。
## 结论
在本教程中，我们探索了使用 Aspose.Tasks for Java 停止和恢复任务的过程。通过执行上述步骤，您可以增强项目管理能力并简化任务执行。
## 经常问的问题
### Aspose.Tasks for Java适合大型项目吗？
绝对地！ Aspose.Tasks for Java 旨在处理不同规模的项目，确保效率和可靠性。
### 我可以自定义停止和恢复任务的日期吗？
是的，所提供的示例允许根据您的项目要求灵活设置最短日期。
### 在哪里可以找到 Aspose.Tasks for Java 的其他支持？
参观[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)以获得社区支持和讨论。
### Aspose.Tasks for Java 是否有免费试用版？
是的，您可以访问[免费试用](https://releases.aspose.com/)在购买前探索功能。
### 如何获得 Aspose.Tasks for Java 的临时许可证？
您可以获得临时许可证[这里](https://purchase.aspose.com/temporary-license/)用于测试目的。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
