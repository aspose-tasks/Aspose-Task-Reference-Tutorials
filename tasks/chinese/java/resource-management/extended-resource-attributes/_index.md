---
date: 2026-06-10
description: 了解如何在 Java 中创建 extended attribute，加载 Microsoft Project 文件，设置 numeric
  values，并使用 Aspose.Tasks for Java 将项目保存为 XML。
keywords:
- create extended attribute java
- custom attribute Aspose.Tasks
- Java project management
linktitle: 在 Aspose.Tasks 中处理 Extended Resource Attributes
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  headline: How to create extended attribute in Java with Aspose.Tasks
  type: TechArticle
- description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  name: How to create extended attribute in Java with Aspose.Tasks
  steps:
  - name: Define Data Directory
    text: '`Paths` is a utility class that provides methods to obtain a file system
      path in a platform‑independent way.'
  - name: Load Microsoft Project File
    text: '`Project` represents a Microsoft Project file in memory, allowing read
      and write access to its contents.'
  - name: Define the Custom Attribute
    text: '`ExtendedAttributeDefinition` defines the schema of a new custom field
      that can be attached to resources or tasks.'
  - name: Set Numeric Value in Java
    text: '`ExtendedAttributeResource` holds the value of a custom attribute for a
      specific resource instance.'
  - name: Add Resource and Attach the Custom Attribute
    text: '`Resource` models a project resource such as a person, equipment, or material.'
  - name: Save Project as XML
    text: '`SaveFileFormat` enumerates the supported output formats for saving a project,
      including XML.'
  - name: Display Result
    text: '`System.out.println` prints a line of text to the standard console output.'
  type: HowTo
- questions:
  - answer: Yes – use `ExtendedAttributeTask` instead of `ExtendedAttributeResource`
      when defining the attribute schema.
    question: Can I create custom attributes for tasks as well as resources?
  - answer: Absolutely. Create separate `ExtendedAttributeDefinition` objects for
      each attribute and attach them to the desired resources or tasks.
    question: Is it possible to add multiple custom attributes at once?
  - answer: Aspose.Tasks supports XML, MPP, PDF, HTML, and more than 30 additional
      formats. In this example we used `SaveFileFormat.Xml`.
    question: What formats can I save the project in?
  - answer: A temporary evaluation license is sufficient for testing. For any production
      deployment, a full commercial license is required.
    question: Do I need a license for development builds?
  - answer: Call `resource.getExtendedAttributes()` and iterate over the collection;
      retrieve the stored value with `getNumericValue()` or `getTextValue()`.
    question: How do I read back the custom attribute values later?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: 如何在 Java 中使用 Aspose.Tasks 创建 extended attribute
url: /zh/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中使用 Aspose.Tasks 创建扩展属性

## 介绍
在本实践指南中，您将 **在 Java 中创建扩展属性** 用于 Microsoft Project 文件，使用 Aspose.Tasks。我们将演示如何加载现有项目、定义新的数值属性、为资源分配值，最后将更改持久化为 XML 文件。完成后，您将拥有一个可复用的代码模式，可直接嵌入任何基于 Java 的项目管理解决方案。

## 快速答案
- **什么是扩展属性？**  
  用户自定义字段（例如，年龄、技能等级），用于存储资源或任务的额外数据。  
- **哪个 API 创建它？**  
  Aspose.Tasks for Java 提供 `ExtendedAttributeDefinition` 类，用于定义和管理自定义属性。  
- **我需要许可证吗？**  
  临时评估许可证可用于开发；生产部署需要完整许可证。  
- **我可以存储数字吗？**  
  可以——使用 `setNumericValue(BigDecimal)` 来分配精确的十进制值。  
- **我如何持久化更改？**  
  调用 `project.save("output.xml", SaveFileFormat.Xml)` 将更新后的项目写入 XML 格式。

## 什么是自定义属性？
**custom attribute**（也称为扩展属性）是您可以在 Microsoft Project 中添加到资源或任务的额外列。它允许您捕获内置字段未覆盖的数据，例如员工年龄、认证等级或任何业务特定指标。

## 为什么在 Java 中创建扩展属性？
在 Java 中创建 extended attribute 使您能够以编程方式丰富项目数据，确保文件之间的一致性并实现自动化报告。通过一次定义属性，即可将其应用于任意数量的资源或任务，无需手动输入，从而节省时间并降低错误。

- **针对组织定制数据** – 存储任何对您重要的指标，无需手动 Excel 处理。  
- **实现更丰富的报告** – 稍后查询自定义字段以用于仪表板或分析。  
- **保持一致性** – 以编程方式在数十个项目中应用相同的定义，消除人为错误。  
- **性能已验证** – 根据产品基准，Aspose.Tasks 可在不将整个文件加载到内存的情况下处理多达 10,000 个任务和 5,000 个资源的项目。

## 前提条件
在开始之前，请确保您具备：

1. **Java Development Kit** – 已安装 JDK 8 或更高版本。  
2. **Aspose.Tasks for Java** – 从 [here](https://releases.aspose.com/tasks/java/) 下载最新发布。  
3. **IDE** – Eclipse、IntelliJ IDEA 或任何兼容 Java 的开发环境。  

## 如何在 Java 中创建扩展属性？
加载项目，定义属性，将其附加到资源，并保存文件——只需几个简明步骤。以下各节将每一步拆分为简要说明，随后是实际代码所在的占位符。

### 步骤指南

#### 导入包
`Project`、`ExtendedAttributeDefinition`、`ExtendedAttributeResource` 以及相关类位于 `com.aspose.tasks` 命名空间。请在 Java 文件的顶部导入它们。

```java
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.SaveFileFormat;
import java.math.BigDecimal;
```

#### 步骤 1：定义数据目录
`Paths` 是一个实用类，提供以平台无关方式获取文件系统路径的方法。

```java
String dataDir = "Your Data Directory";
```

#### 步骤 2：加载 Microsoft Project 文件
`Project` 表示内存中的 Microsoft Project 文件，允许读取和写入其内容。

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

#### 步骤 3：定义自定义属性
`ExtendedAttributeDefinition` 定义了可附加到资源或任务的新自定义字段的模式。

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

#### 步骤 4：在 Java 中设置数值
`ExtendedAttributeResource` 保存特定资源实例的自定义属性值。

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

#### 步骤 5：添加资源并附加自定义属性
`Resource` 表示项目资源，例如人员、设备或材料。

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

#### 步骤 6：将项目保存为 XML
`SaveFileFormat` 列举了保存项目时支持的输出格式，包括 XML。

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

#### 步骤 7：显示结果
`System.out.println` 将一行文本打印到标准控制台输出。

```java
System.out.println("Process completed Successfully");
```

## 常见陷阱与技巧
- **属性 ID 冲突**：在创建新定义之前，始终调用 `project.getExtendedAttributes().getById(id)` 以防止标识符重复。  
- **精度处理**：在精确数值上，优先使用 `BigDecimal` 而非 `float`/`double`；这可避免报告中的四舍五入错误。  
- **文件路径可靠性**：使用 `Paths.get(...).toAbsolutePath()` 或配置 IDE 的工作目录，以消除 `FileNotFoundException`。  

## 常见问题解答

**Q: 我可以为任务以及资源创建自定义属性吗？**  
A: 可以——在定义属性模式时使用 `ExtendedAttributeTask` 替代 `ExtendedAttributeResource`。

**Q: 是否可以一次添加多个自定义属性？**  
A: 当然。为每个属性创建单独的 `ExtendedAttributeDefinition` 对象，并将其附加到所需的资源或任务上。

**Q: 我可以将项目保存为何种格式？**  
A: Aspose.Tasks 支持 XML、MPP、PDF、HTML 等超过 30 种其他格式。在本示例中我们使用了 `SaveFileFormat.Xml`。

**Q: 开发构建是否需要许可证？**  
A: 临时评估许可证足以用于测试。任何生产部署都需要完整的商业许可证。

**Q: 我如何在以后读取自定义属性值？**  
A: 调用 `resource.getExtendedAttributes()` 并遍历集合；使用 `getNumericValue()` 或 `getTextValue()` 获取存储的值。

---

**最后更新：** 2026-06-10  
**测试环境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose

## 相关教程

- [如何创建资源 – 使用 Aspose.Tasks for Java 的资源管理](/tasks/java/resource-management/)
- [创建自定义字段 Aspose - 处理扩展属性](/tasks/java/project-management/extended-attributes/)
- [如何创建项目 – 使用 Aspose.Tasks 设置新任务属性](/tasks/java/project-file-operations/set-attributes-new-tasks/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}