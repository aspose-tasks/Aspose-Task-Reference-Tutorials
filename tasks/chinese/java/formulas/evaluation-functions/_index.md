---
date: 2026-10-10
description: 了解如何在 Aspose.Tasks 中添加扩展属性，使用评估函数，并使用此 Java 项目管理库生成项目报告。
keywords:
- how to add extended attribute
- add custom field task
- java project management library
lastmod: 2026-10-10
linktitle: 在 Aspose.Tasks 公式中支持评估函数
og_description: 了解如何在 Aspose.Tasks 中添加扩展属性，使用评估函数，并使用此 Java 项目管理库生成项目报告。
og_image_alt: Aspose.Tasks Java tutorial showing how to add extended attribute and
  use evaluation functions
og_title: 如何在 Aspose.Tasks 公式中添加扩展属性
schemas:
- author: Aspose
  dateModified: '2026-10-10'
  description: Learn how to add extended attribute in Aspose.Tasks, use evaluation
    functions, and generate project reports with this Java project management library.
  headline: How to add extended attribute in Aspose.Tasks formulas
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java supports evaluation of a wide range of MS Project
      functions, allowing for complex calculations within Java applications.
    question: Can Aspose.Tasks for Java handle complex MS Project formulas?
  - answer: Yes, Aspose.Tasks for Java supports various versions of Microsoft Project
      files, including MPP, MPT, and XML formats.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project files?
  - answer: Yes, you can download a free trial version of Aspose.Tasks for Java from
      the website [Aspose.Tasks for Java purchase page](https://purchase.aspose.com/buy).
    question: Can I try Aspose.Tasks for Java before purchasing?
  - answer: You can get support from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, you can obtain a temporary license for testing purposes from the
      Aspose website [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Is there a temporary license available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add extended attribute
- java project management library
- Aspose.Tasks
- evaluation functions
- custom field task
title: 如何在 Aspose.Tasks 公式中添加扩展属性
url: /zh/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 公式中添加扩展属性

## 简介
Aspose.Tasks for Java 是一个 **Java 项目管理库**，它允许您通过在 Java 中创建 `Project` 对象并直接在代码中评估 Microsoft Project 函数来生成项目报告。通过嵌入这些公式，您可以执行复杂的计算、生成自定义报告，并在不离开开发环境的情况下实现项目分析。在本教程中，我们将演示如何创建项目对象、添加扩展属性，以及使用评估函数来 **add custom field task** 数据。

## 快速答案
- **What does “create project object java” mean?** 它创建了一个内存中的 `Project` 实例，您可以以编程方式操作它。  
- **Which library is required?** Aspose.Tasks for Java（从官方网站下载）。  
- **Do I need a license?** 生产环境使用需要临时或完整的 Aspose.Tasks 许可证；提供免费试用版。  
- **Can I use custom fields?** 是的——您可以 **add extended attribute** 到任务并将其视为自定义字段。  
- **Is this compatible with all Project file formats?** Aspose.Tasks 支持 3 种主要格式（MPP、MPT、XML）以及超过 50 种其他输入/输出格式。

## 先决条件
在开始之前，请确保您已具备以下条件：

1. **Java Development Environment** – JDK 8+ 和诸如 IntelliJ IDEA 或 Eclipse 的 IDE。  
2. **Aspose.Tasks for Java Library** – 从 [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/) 下载并引入库。

## 导入包
将 Aspose.Tasks 命名空间添加到您的 Java 类中，以便能够处理项目、任务和扩展属性：

```java
import com.aspose.tasks.*;
```

## 生成项目报告 – create project object java
`Project` 类表示内存中的 Microsoft Project 文件，公开任务、资源和自定义数据。实例化此类为您提供一个容器，用于定义所有项目元素。

```java
Project project = new Project();
```

上述代码 **creates project object java**，它从空开始，准备进行自定义。

## 如何添加扩展属性
`ExtendedAttributeDefinition` 类定义了可以附加到任务的自定义字段。要添加扩展属性，请创建该类的实例，类型为 `Number`，为其分配别名，例如 “Sine”，将其添加到项目的 `ExtendedAttributes` 集合中，然后链接到每个需要该自定义字段的任务。

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

这里我们 **add extended attribute** 类型为 `Number`，名称为 “Sine”，并将其关联到任务。

## 将扩展属性添加到项目
在项目中注册属性定义，以便每个任务都可以引用它。

```java
project.getExtendedAttributes().add(attr);
```

## 创建新任务
`Task` 代表项目中的工作项，并且可以包含自定义字段。

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## 将自定义字段任务添加到项目
将先前定义的扩展属性链接到新创建的任务，为任务提供一个自定义的 “Sine” 字段，您可以在公式或计算中使用它。

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

现在任务拥有一个自定义的 “Sine” 字段，您可以在公式或计算中使用。这也是以编程方式 **add custom field task** 数据的方式。

## 为什么使用评估函数？
评估函数允许您在 Aspose.Tasks 中直接嵌入原生 Microsoft Project 公式（例如 `Sin([Start])`），实现即时计算，无需外部处理。这使得所有项目逻辑集中在一处，减少数据同步错误，并加快报告生成。Aspose.Tasks 支持评估超过 100 种 MS Project 函数，提供了 Java 中的完整计算引擎。

## 常见问题及解决方案
| 问题 | 解决方案 |
|-------|----------|
| **Formula returns `NaN`** | 验证自定义字段类型是否匹配预期的数值类型。 |
| **Extended attribute not visible** | 确保在创建任务 **before** 将属性定义添加到项目。 |
| **License exception** | 安装临时或完整的 **Aspose.Tasks license**；试用模式可能限制某些功能。 |
| **Missing temporary license** | 从 Aspose 网站获取 **temporary Aspose license**。 |

## 常见问题

**Q: Aspose.Tasks for Java 能处理复杂的 MS Project 公式吗？**  
A: 是的，Aspose.Tasks for Java 支持评估广泛的 MS Project 函数，允许在 Java 应用程序中进行复杂计算。

**Q: Aspose.Tasks for Java 与不同版本的 Microsoft Project 文件兼容吗？**  
A: 是的，Aspose.Tasks for Java 支持各种版本的 Microsoft Project 文件，包括 MPP、MPT 和 XML 格式。

**Q: 我可以在购买前试用 Aspose.Tasks for Java 吗？**  
A: 是的，您可以从网站 [Aspose.Tasks for Java purchase page](https://purchase.aspose.com/buy) 下载 Aspose.Tasks for Java 的免费试用版。

**Q: 我如何获取 Aspose.Tasks for Java 的支持？**  
A: 您可以在 Aspose.Tasks 社区论坛 [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15) 获得支持。

**Q: Aspose.Tasks for Java 是否提供临时许可证？**  
A: 是的，您可以从 Aspose 网站的 [Aspose temporary license page](https://purchase.aspose.com/temporary-license/) 获取用于测试的临时许可证。

## 结论
通过遵循这些步骤，您已经学习了如何 **create project object**、**add extended attribute**，以及利用评估函数自动 **generate project report**。现在，您可以在此基础上构建更丰富的项目分析、定制仪表板或自动化调度工具——全部由 Aspose.Tasks for Java 提供支持。

---

**最后更新：** 2026-10-10  
**测试环境：** Aspose.Tasks for Java 24.10  
**作者：** Aspose

## 相关教程

- [Java 项目管理中的自定义列和扩展属性](/tasks/java/project-management/extended-attributes/)
- [使用 Aspose.Tasks for Java 读取扩展任务属性](/tasks/java/task-properties/extended-task-attributes/)
- [如何使用 Aspose.Tasks for Java – 为资源分配添加扩展属性](/tasks/java/resource-assignments/add-extended-attributes/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}