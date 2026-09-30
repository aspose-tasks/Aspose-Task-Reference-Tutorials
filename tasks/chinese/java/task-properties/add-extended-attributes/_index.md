---
date: 2026-09-30
description: 了解如何使用 Aspose.Tasks for Java 创建任务扩展属性，该库是领先的 Java 项目管理库，可用于添加自定义任务字段。
keywords:
- create task extended attribute
- java project management library
- add custom task field
lastmod: 2026-09-30
linktitle: 如何使用 Aspose.Tasks Java 创建任务扩展属性
og_description: 了解如何使用 Aspose.Tasks for Java 创建任务扩展属性，该库是领先的 Java 项目管理库，可用于添加自定义任务字段。
og_image_alt: 'Developer guide: create task extended attribute in Aspose.Tasks Java'
og_title: 如何使用 Aspose.Tasks Java 创建任务扩展属性
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Learn how to create task extended attribute using Aspose.Tasks for
    Java, the leading java project management library for adding custom task fields.
  headline: How to create task extended attribute with Aspose.Tasks Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates smoothly with any Java ecosystem,
      including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library is engineered to handle multi‑thousand‑task projects
      and supports streaming to keep memory usage low.
    question: Is Aspose.Tasks for Java suitable for large‑scale project management
      applications?
  - answer: Yes, you need a valid commercial license. You can review the details on
      the [Aspose.Tasks website](https://purchase.aspose.com/buy).
    question: Are there any licensing considerations for using Aspose.Tasks for Java
      in a commercial project?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community help, or open a support ticket through your Aspose account.
    question: How can I get support or assistance with Aspose.Tasks for Java?
  - answer: Yes, you can access a free trial version on the [Aspose.Tasks free trial](https://releases.aspose.com/)
      page.
    question: Can I try Aspose.Tasks for Java before purchasing?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project management
- extended attributes
- task customization
title: 如何使用 Aspose.Tasks Java 创建任务扩展属性
url: /zh/java/task-properties/add-extended-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks Java 创建任务扩展属性

## 介绍
在本教程中，您将学习如何使用 Aspose.Tasks for Java 在 Microsoft Project 文件中**创建任务扩展属性**。添加自定义字段可让您捕获项目特定的数据，这些数据不在内置列中，从而对报告和资源规划进行更细粒度的控制。完成本指南后，您将能够为任何任务添加纯文本、带查找功能和持续时间属性。

## 快速回答
- **“扩展属性”是什么意思？** 它是您定义并附加到任务、资源或分配的自定义字段。  
- **哪个库提供此功能？** Aspose.Tasks for Java，一个 Java 项目管理库。  
- **我需要许可证才能试用吗？** 是的 – 可以从 Aspose 网站获取免费 30 天试用。  
- **我可以添加查找值吗？** 当然；您可以为文本或持续时间字段提供允许值列表。  
- **API 是否兼容 Java 8 及更高版本？** 是的，它支持 Java 8+，并可在所有主流操作系统上运行。

## 任务扩展属性是什么？
任务扩展属性是用户定义的列，用于在项目文件中为每个任务存储额外信息。它的行为类似于内置字段，但可以保存您需要的任何数据类型，例如文本、数字、日期或持续时间。

## 为什么使用 Aspose.Tasks for Java？
Aspose.Tasks 支持 **50+ 文件格式**，并且能够处理包含 **10,000+ 任务** 的项目，而无需安装 Microsoft Project。该库完全离线工作，确保数据隐私并为企业级解决方案提供确定性的性能。

## 先决条件
- 基本的 Java 编程知识。  
- 已安装 Aspose.Tasks for Java 库。您可以从[website](https://releases.aspose.com/tasks/java/)下载。  
- 在您的机器上已设置 Java IDE（IntelliJ IDEA、Eclipse 或 VS Code）。

## 导入包
`import` 语句为您提供访问所需核心类的权限，例如 `Project`、`ExtendedAttributeDefinition` 和 `ExtendedAttribute`。  

`Project` 表示一个 Microsoft Project 文件，并提供读取、修改和保存的方法。  
`ExtendedAttributeDefinition` 定义一个可以附加到任务、资源或分配的自定义字段。  
`ExtendedAttribute` 是定义的实例，保存特定实体的实际值。

## 如何向任务添加纯文本扩展属性？
要添加纯文本扩展属性，首先加载项目，然后创建 Text 类型的定义，将其添加到项目的集合中，创建任务，从定义实例化属性，设置其文本值，将其附加到任务，最后保存项目。

### 1. 设置文档目录路径
指定源文件和输出文件所在的位置。

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

### 2. 创建新项目
实例化一个 `Project` 对象，可选择加载现有的 .mpp 文件。

```java
String dataDir = "Your Document Directory";
```

### 3. 创建 Text1 类型的扩展属性定义
将自定义字段定义为名为 “Text1” 的纯文本列。

```java
Project project = new Project(dataDir + "project.mpp");
```

### 4. 将定义添加到项目的扩展属性集合中
注册新定义，使项目能够识别它。

```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```

### 5. 向项目添加任务
创建一个将接收自定义字段的任务。

```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```

### 6. 根据属性定义创建扩展属性
生成一个实例，可绑定到特定任务。

```java
Task task = project.getRootTask().getChildren().add("Task 1");
```

### 7. 为生成的扩展属性赋值
设置您想存储的实际文本，例如 “Design Review”。

```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```

### 8. 将扩展属性添加到任务
将属性实例附加到任务的 `ExtendedAttributes` 集合中。

```java
taskExtendedAttributeText1.setTextValue("London");
```

### 9. 保存项目
将更新后的项目以所需格式写回磁盘。

```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```

## 如何添加带查找选项的文本属性？
在添加带查找的文本属性时，您遵循与纯文本属性相同的步骤，但在添加定义之前，需要用允许的字符串填充其 `LookupValues` 集合。这些值会在 Microsoft Project 中显示为下拉列表，确保数据一致性。

## 如何添加带查找选项的持续时间属性？
要添加带查找的持续时间属性，在创建定义时将 `Text1` 类型替换为 `Duration2`，然后用诸如 “1 day”、 “2 days” 等持续时间字符串填充 `LookupValues` 集合。将定义添加到项目后，创建属性实例，设置持续时间值，将其附加到任务，并保存文件。

## 常见问题与故障排除
- **查找值未显示** – 确保在调用 `project.getExtendedAttributes().add(definition)` 之前，将每个查找条目添加到 `LookupValues` 集合中。  
- **属性值未保存** – 验证在设置属性值后，将 `ExtendedAttribute` 实例添加到任务中。  
- **文件大小意外增长** – 在处理非常大的项目时，考虑调用 `project.setSaveOptions(new ProjectSaveOptions())` 以启用增量保存。

## 常见问题

**Q: 我可以将 Aspose.Tasks for Java 与其他 Java 库一起使用吗？**  
A: 是的，Aspose.Tasks for Java 能够平稳地与任何 Java 生态系统集成，包括 Spring、Hibernate 和 Apache POI。

**Q: Aspose.Tasks for Java 适用于大规模项目管理应用吗？**  
A: 当然。该库专为处理数千任务的项目而设计，并支持流式处理以保持低内存使用。

**Q: 在商业项目中使用 Aspose.Tasks for Java 有哪些许可考虑？**  
A: 是的，您需要有效的商业许可证。您可以在 [Aspose.Tasks website](https://purchase.aspose.com/buy) 查看详情。

**Q: 我如何获得 Aspose.Tasks for Java 的支持或帮助？**  
A: 访问 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 获取社区帮助，或通过您的 Aspose 帐户提交支持工单。

**Q: 我可以在购买前试用 Aspose.Tasks for Java 吗？**  
A: 是的，您可以在 [Aspose.Tasks free trial](https://releases.aspose.com/) 页面获取免费试用版。

---

**最后更新：** 2026-09-30  
**测试环境：** Aspose.Tasks for Java 24.10  
**作者：** Aspose  

```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```

## 相关教程

- [Java 项目管理中的自定义列和扩展属性](/tasks/java/project-management/extended-attributes/)
- [使用 Aspose.Tasks for Java 读取扩展任务属性](/tasks/java/task-properties/extended-task-attributes/)
- [如何创建项目 aspose.tasks – 设置新任务属性](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}