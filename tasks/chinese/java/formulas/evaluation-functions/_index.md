---
date: 2026-02-13
description: 学习如何通过在 Java 中创建项目对象、添加扩展属性以及使用 Aspose.Tasks 的评估函数来生成项目报告。
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: 生成项目报告 – 创建项目对象（Java）
url: /zh/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 支持 Aspose.Tasks 公式中的评估函数

## 介绍
Aspose.Tasks for Java 让您通过在 Java 中创建 **project object** 并直接在代码中评估 Microsoft Project 函数来 **generate project report**。通过嵌入这些公式，您可以执行复杂的计算、生成自定义报告，并在不离开开发环境的情况下实现项目分析自动化。在本教程中，我们将演示如何创建 project object、添加扩展属性，以及使用评估函数来 **add custom field task** 数据。

## 快速答案
- **What does “create project object java” mean?** 它创建一个内存中的 `Project` 实例，您可以以编程方式操作它。  
- **Which library is required?** Aspose.Tasks for Java（从官方网站下载）。  
- **Do I need a license?** 生产环境需要临时或完整的 Aspose.Tasks 许可证；提供免费试用版。  
- **Can I use custom fields?** 是的——您可以 **add extended attribute** 到任务并将其视为自定义字段。  
- **Is this compatible with all Project file formats?** Aspose.Tasks 支持 MPP、MPT 和 XML 格式。

## 前提条件
在开始之前，请确保您具备以下条件：

1. **Java Development Environment** – JDK 8+ 和如 IntelliJ IDEA 或 Eclipse 的 IDE。  
2. **Aspose.Tasks for Java Library** – 从 [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/) 下载并引用该库。

## 导入包
将 Aspose.Tasks 命名空间添加到您的 Java 类中，以便能够使用项目、任务和扩展属性：

```java
import com.aspose.tasks.*;
```

## 生成项目报告 – Create Project Object Java
实例化一个新的 `Project` 对象。它将作为所有任务、资源和自定义数据的容器。

```java
Project project = new Project();
```

上述代码 **creates project object java**，初始为空，准备进行自定义。

## 如何添加扩展属性
定义一个扩展属性，用于为每个任务存储自定义数值数据（例如正弦值）。

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

这里我们 **add extended attribute** 类型为 `Number`，名称为 “Sine”，并将其关联到任务。

## 将扩展属性添加到项目中
将属性定义注册到项目，以便每个任务都可以引用它。

```java
project.getExtendedAttributes().add(attr);
```

## 创建新任务
在项目的根任务下添加一个名为 “Task” 的简单任务。

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## 将扩展属性关联到任务
将先前定义的扩展属性链接到新创建的任务。

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

现在任务拥有自定义的 “Sine” 字段，您可以在公式或计算中使用。这也是以编程方式 **add custom field task** 数据的方式。

## 为什么使用评估函数？
在 Aspose.Tasks 公式中嵌入 MS Project 函数，使您能够：

- 在不使用外部工具的情况下执行即时计算（例如 `Sin([Start])`）。  
- 将所有项目逻辑保存在单一且易于维护的代码库中。  
- 生成能够反映实时数据变化的动态报告，帮助您自动 **generate project report**。

## 常见问题及解决方案
| Issue | Solution |
|-------|----------|
| **Formula returns `NaN`** | 验证自定义字段类型是否匹配预期的数值类型。 |
| **Extended attribute not visible** | 确保在创建任务 **之前** 已将属性定义添加到项目中。 |
| **License exception** | 安装临时或完整的 **Aspose.Tasks license**；试用模式可能限制某些功能。 |
| **Missing temporary license** | 从 Aspose 网站获取 **temporary Aspose license**。 |

## 常见问答

**Q: Aspose.Tasks for Java 能处理复杂的 MS Project 公式吗？**  
A: 可以，Aspose.Tasks for Java 支持评估广泛的 MS Project 函数，允许在 Java 应用程序中进行复杂计算。

**Q: Aspose.Tasks for Java 是否兼容不同版本的 Microsoft Project 文件？**  
A: 可以，Aspose.Tasks for Java 支持多种版本的 Microsoft Project 文件，包括 MPP、MPT 和 XML 格式。

**Q: 我可以在购买前试用 Aspose.Tasks for Java 吗？**  
A: 可以，您可以从网站 [here](https://purchase.aspose.com/buy) 下载 Aspose.Tasks for Java 的免费试用版。

**Q: 如何获取 Aspose.Tasks for Java 的支持？**  
A: 您可以在 Aspose.Tasks 社区论坛 [here](https://forum.aspose.com/c/tasks/15) 获得支持。

**Q: 是否有 Aspose.Tasks for Java 的临时许可证？**  
A: 有，您可以从 Aspose 网站 [here](https://purchase.aspose.com/temporary-license/) 获取用于测试的临时许可证。

## 结论
通过遵循这些步骤，您已经学会了如何 **create project object**、**add extended attribute**，并利用评估函数自动 **generate project report**。现在，您可以在此基础上进一步构建更丰富的项目分析、定制仪表盘或自动化调度工具——全部由 Aspose.Tasks for Java 提供动力。

---

**最后更新：** 2026-02-13  
**测试环境：** Aspose.Tasks for Java 24.10  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}