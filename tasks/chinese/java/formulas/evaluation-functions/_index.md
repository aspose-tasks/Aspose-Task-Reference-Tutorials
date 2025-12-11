---
date: 2025-12-09
description: 学习如何使用 Java 创建项目对象并在 Aspose.Tasks 公式中支持评估函数。了解如何为任务创建扩展属性。
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: 创建项目对象 Java – 在 Aspose.Tasks 中支持评估函数
url: /zh/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 支持 Aspose.Tasks 公式中的评估函数

## 介绍
Aspose.Tasks for Java 让您 **create project object java** 实例并直接在 Java 代码中评估 Microsoft Project 函数。通过嵌入这些公式，您可以执行复杂计算、生成自定义报告，并在不离开开发环境的情况下实现项目分析自动化。本教程将带您完成整个过程——从设置项目对象到添加可保存自定义数据的扩展属性。

## 快速答案
- **“create project object java” 是什么意思？** 它会创建一个内存中的 `Project` 实例，您可以以编程方式对其进行操作。  
- **需要哪个库？** Aspose.Tasks for Java（从官方网站下载）。  
- **需要许可证吗？** 生产环境需要临时或正式许可证；提供免费试用版。  
- **可以使用自定义字段吗？** 可以——您可以定义并将扩展属性附加到任务上。  
- **是否兼容所有 Project 文件格式？** Aspose.Tasks 支持 MPP、MPT 和 XML 格式。

## 前置条件
在开始之前，请确保您具备以下条件：

1. **Java 开发环境** – JDK 8 及以上，配合 IntelliJ IDEA 或 Eclipse 等 IDE。  
2. **Aspose.Tasks for Java 库** – 从 [Aspose.Tasks for Java 下载页面](https://releases.aspose.com/tasks/java/) 下载并引用该库。

## 导入包
将 Aspose.Tasks 命名空间添加到您的 Java 类中，以便能够操作项目、任务和扩展属性：

```java
import com.aspose.tasks.*;
```

## 步骤 1：创建 Project 对象 Java
实例化一个新的 `Project` 对象。它将作为所有任务、资源和自定义数据的容器。

```java
Project project = new Project();
```

上述代码 **creates project object java**，创建了一个空的、可供定制的项目对象。

## 步骤 2：如何创建扩展属性
定义一个扩展属性，用于为每个任务存储自定义数值数据（例如正弦值）。

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

这里我们 **create extended attribute**，类型为 `Number`，名称为 “Sine”，并将其关联到任务。

## 步骤 3：将扩展属性添加到项目中
将属性定义注册到项目，以便每个任务都可以引用它。

```java
project.getExtendedAttributes().add(attr);
```

## 步骤 4：创建新任务
在项目的根任务下添加一个名为 “Task” 的简单任务。

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## 步骤 5：将扩展属性关联到任务
将前面定义的扩展属性链接到新创建的任务。

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

现在任务拥有一个自定义的 “Sine” 字段，您可以在公式或计算中使用它。

## 为什么使用评估函数？
在 Aspose.Tasks 公式中嵌入 MS Project 函数可让您：

- 在不使用外部工具的情况下执行即时计算（例如 `Sin([Start])`）。  
- 将所有项目逻辑集中在单一、易于维护的代码库中。  
- 生成能够实时反映数据变化的动态报告。

## 常见问题及解决方案
| 问题 | 解决方案 |
|-------|----------|
| **公式返回 `NaN`** | 确认自定义字段类型与预期的数值类型匹配。 |
| **扩展属性不可见** | 确保在创建任务 **之前** 将属性定义添加到项目中。 |
| **许可证异常** | 安装临时或正式许可证；试用模式可能限制某些功能。 |

## 常见问题

**Q: Aspose.Tasks for Java 能处理复杂的 MS Project 公式吗？**  
A: 能，Aspose.Tasks for Java 支持评估大量 MS Project 函数，能够在 Java 应用中进行复杂计算。

**Q: Aspose.Tasks for Java 是否兼容不同版本的 Microsoft Project 文件？**  
A: 能，Aspose.Tasks for Java 支持多种版本的 Microsoft Project 文件，包括 MPP、MPT 和 XML 格式。

**Q: 我可以在购买前试用 Aspose.Tasks for Java 吗？**  
A: 可以，您可以从网站 [here](https://purchase.aspose.com/buy) 下载 Aspose.Tasks for Java 的免费试用版。

**Q: 如何获取 Aspose.Tasks for Java 的支持？**  
A: 您可以在 Aspose.Tasks 社区论坛 [here](https://forum.aspose.com/c/tasks/15) 获得支持。

**Q: 是否有 Aspose.Tasks for Java 的临时许可证？**  
A: 有，您可以从 Aspose 网站 [here](https://purchase.aspose.com/temporary-license/) 获取用于测试的临时许可证。

---

**最后更新：** 2025-12-09  
**测试环境：** Aspose.Tasks for Java 24.10  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}