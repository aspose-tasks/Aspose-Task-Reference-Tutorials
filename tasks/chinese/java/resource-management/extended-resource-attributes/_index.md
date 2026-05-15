---
date: 2026-01-13
description: 学习如何使用 Aspose.Tasks for Java 创建自定义属性、加载 Microsoft Project 文件、在 Java 中设置数值，并将项目保存为
  XML。
linktitle: Handle Extended Resource Attributes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks 在 MS Project 中创建自定义属性
url: /zh/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks 在 MS Project 中创建自定义属性

## 介绍
在本教程中，**您将学习如何为 Microsoft Project 文件中的资源创建自定义属性**，使用 Aspose.Tasks for Java。我们将演示如何加载 Microsoft Project 文件、定义一个新的数值属性、为其赋值，最后将项目保存为 XML。完成后，您将拥有一个清晰、可操作的示例，能够在自己的项目管理解决方案中进行改造。

## 快速答案
- **“自定义属性”是什么意思？**  
  由用户自行定义的字段，用于存储资源或任务的额外信息（例如年龄、技能等级）。  
- **哪个库负责此功能？**  
  Aspose.Tasks for Java 提供了流式 API 来创建和管理自定义属性。  
- **是否需要许可证？**  
  评估期间可使用免费临时许可证；生产环境需要正式许可证。  
- **可以设置数值吗？**  
  可以——使用 `setNumericValue` 并传入 `BigDecimal`（例如 `30.5345`）。  
- **项目如何保存？**  
  可使用 `SaveFileFormat.Xml` 将修改后的文件保存为 XML。

## 什么是自定义属性？
**自定义属性**（亦称扩展属性）是您可以在 Microsoft Project 中为资源或任务添加的额外列。它用于捕获内置字段未覆盖的数据，例如员工年龄、认证等级或任何业务特定指标。

## 为什么要在 MS Project 中创建自定义属性？
- **根据组织需求定制项目数据**。  
- **通过存储可查询的值实现高级报表**。  
- **在多个项目之间保持一致性**，通过编程方式统一属性定义。

## 前置条件
在开始之前，请确保您已具备：

1. **Java 开发环境** – 已安装 JDK 8 或更高版本。  
2. **Aspose.Tasks for Java** – 从 [here](https://releases.aspose.com/tasks/java/) 下载最新版本。  
3. **IDE** – Eclipse、IntelliJ IDEA 或任意支持 Java 的 IDE。  

## 步骤指南

### 导入包
首先，导入处理项目、资源和扩展属性所需的 Aspose.Tasks 类。

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

### 第 1 步：定义数据目录
设置源项目文件所在的文件夹以及输出文件的写入位置。

```java
String dataDir = "Your Data Directory";
```

### 第 2 步：加载 Microsoft Project 文件
通过加载已有文件创建 `Project` 实例。这一步 **load Microsoft project file** 让您能够完整访问其内容。

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

### 第 3 步：定义自定义属性
我们将定义一个名为 **Age** 的数值属性。API 会检查该定义是否已存在；若不存在则创建它。

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

### 第 4 步：在 Java 中设置数值
为特定资源创建属性实例，并使用 `setNumericValue` 赋予数值。这演示了 **set numeric value java** 的实际用法。

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

### 第 5 步：添加资源并附加自定义属性
新增一个名为 **R1** 的资源，并将前面创建的自定义属性绑定到该资源上。

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

### 第 6 步：将项目保存为 XML
最后，通过保存项目来持久化更改。这是 **save project as xml** 步骤，会生成更新后文件的干净 XML 表示。

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

### 第 7 步：显示结果
打印友好的确认信息，以便您知道过程已顺利完成且没有错误。

```java
System.out.println("Process completed Successfully");
```

按照这些步骤，您已经成功 **创建了自定义属性**，加载了 Microsoft Project 文件，使用 Java 设置了数值，并将项目保存为 XML。

## 常见问题与技巧
- **属性 ID 冲突**：在创建新定义前务必使用 `getById` 检查，以避免重复 ID。  
- **精度处理**：`BigDecimal` 能保持小数精度；请避免使用 `float` 或 `double` 来存储精确值。  
- **文件路径**：使用绝对路径或配置 IDE 的工作目录，以防止出现 `FileNotFoundException`。  

## 常见问答

**问：我可以为任务而不仅是资源创建自定义属性吗？**  
答：可以——在定义属性时使用 `ExtendedAttributeTask` 而不是 `ExtendedAttributeResource`。

**问：是否可以一次性添加多个自定义属性？**  
答：完全可以。为每个属性创建单独的 `ExtendedAttributeDefinition` 对象，然后将其附加到相应的资源或任务上。

**问：项目可以保存为何种格式？**  
答：Aspose.Tasks 支持 XML、MPP 以及 PDF、HTML 等多种格式。本示例使用 `SaveFileFormat.Xml`。

**问：开发构建是否需要 Aspose.Tasks 许可证？**  
答：评估阶段使用临时许可证即可。正式生产部署需要完整许可证。

**问：以后如何读取自定义属性的值？**  
答：使用 `resource.getExtendedAttributes()` 遍历已附加的属性，并通过 `getNumericValue()` 或 `getTextValue()` 获取其值。

## 结论
使用 Aspose.Tasks for Java 在 Microsoft Project 中创建 **自定义属性** 的过程相当直接：加载项目、定义属性、设置值、附加到资源、保存文件。此方法让您能够以编程方式扩展项目数据模型，进而实现更丰富的报表和更紧密的业务流程集成。

---

**最后更新：** 2026-01-13  
**测试环境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}