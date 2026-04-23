---
date: 2026-02-07
description: 了解如何在 Aspose.Tasks 项目中使用 Java 设置货币代码、更改货币符号，并为 Microsoft Project 文件应用自定义货币格式。
linktitle: Set Currency Properties in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: 货币代码 Java – 如何在 Aspose.Tasks 项目中设置
url: /zh/java/currency-properties/set-properties/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中设置货币代码 – Java 指南

## 介绍
在本教程中，您将学习 **如何在 Java 中设置货币代码**，以便使用 Aspose.Tasks Java API 操作 Microsoft Project 文件。无论是为国际团队 **更改货币**、调整 **货币符号**，还是应用 **自定义货币格式**，下面的步骤都将为您提供清晰的说明和可直接运行的代码示例。

## 快速答案
- **需要哪个库？** Aspose.Tasks for Java。  
- **可以更改货币符号吗？** 可以 – 使用 `CurrencySymbolPositionType` 和 `Prj.CURRENCY_SYMBOL`。  
- **支持哪些文件格式？** XML、MPP 等多种格式，均通过 `SaveFileFormat` 提供。  
- **开发阶段需要许可证吗？** 免费试用可用于测试；生产环境必须使用许可证。  
- **实现大约需要多长时间？** 基本设置约 5‑10 分钟即可完成。

## 在 Aspose.Tasks 中设置 Currency Code Java
项目的货币决定了费用值的显示方式——代码（例如 `AUD`）、小数位数、符号（`$`）以及符号的位置。设置这些属性可确保所有与费用相关的字段（资源费率、任务预算等）都以正确的货币格式呈现给受众。

## 为什么使用 Aspose.Tasks 更改货币？
- **无需安装 Microsoft Project** – 可在任何服务器上操作文件。  
- **完整的 API 覆盖** – 所有与货币相关的字段均通过 `Prj` 常量暴露。  
- **跨平台** – 在 Windows、Linux、macOS 上均可使用任意兼容 Java 的 IDE。  
- **高性能** – 能快速、可靠地处理大型项目文件。  
- **支持自定义货币格式** – 您可以定义符号、小数位数和位置，以符合地区标准。

## 前置条件
在开始之前，请确保您已具备以下条件：

1. **Java Development Kit (JDK)** – 版本 8 或更高。  
2. **Aspose.Tasks for Java** – 从 [Aspose.Tasks 下载页面](https://releases.aspose.com/tasks/java/) 获取最新 JAR 包。  
3. **IDE** – Eclipse、IntelliJ IDEA 或您喜欢的任何编辑器。  
4. **可写文件夹** – 用于保存生成的项目文件。

## 导入包
首先，导入提供项目属性和文件处理功能的类。

```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## 步骤指南

### 步骤 1：定义数据目录
指定包含源文件以及输出文件将写入的文件夹。

```java
String dataDir = "Your Data Directory";
```

### 步骤 2：创建新的 Project 实例
实例化一个全新的 `Project` 对象。该对象代表内存中的 Microsoft Project 文件。

```java
Project project = new Project();
```

### 步骤 3：设置货币属性
在这里 **设置货币** 的详细信息，包括代码、位数、符号以及符号位置。

```java
project.set(Prj.CURRENCY_CODE, "AUD");                         // Currency code (e.g., AUD, USD)
project.set(Prj.CURRENCY_DIGITS, 2);                          // Number of decimal places
project.set(Prj.CURRENCY_SYMBOL, "$");                        // Symbol to display
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After); // Position of the symbol
```

> **专业提示：** 如果需要 **更改现有文件的项目货币**，只需使用 `new Project("file.mpp")` 加载文件，然后再应用上述设置。

### 步骤 4：保存更新后的项目
将项目写回磁盘，使用所需的格式。示例中使用 XML 格式，您也可以选择 `SaveFileFormat.MPP`。

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### 步骤 5：确认成功
打印友好的提示信息，以确认操作已成功完成且没有错误。

```java
System.out.println("Process completed Successfully");
```

## 常见问题与解决方案
| 问题 | 原因 | 解决办法 |
|------|------|----------|
| **`NullPointerException` 在 `project.save` 时出现** | `dataDir` 路径无效或缺少写权限。 | 确认目录存在且 Java 进程拥有写入权限。 |
| **货币符号未显示** | 符号位置设置不符合本地区域。 | 若符号应位于金额前，请使用 `CurrencySymbolPositionType.Before`。 |
| **项目文件在 MS Project 中无法打开** | 使用了旧格式且设置不兼容。 | 使用 `SaveFileFormat.MPP` 保存，以获得与最新 MS Project 版本的完全兼容性。 |

## 常见问答

**问：可以在单个项目中使用 Aspose.Tasks 设置多种货币吗？**  
答：可以，Aspose.Tasks 允许在同一项目文件中对不同资源或任务分别设置货币属性，从而实现多币种管理。

**问：Aspose.Tasks 是否兼容不同版本的 Microsoft Project 文件？**  
答：完全兼容。该库支持从 Project 2000 到最新版本的 MPP 文件，以及 XML 等其他格式。

**问：Aspose.Tasks 是否支持自定义货币格式？**  
答：支持，您可以自定义符号、十进制位数以及位置，以满足任何地区需求。

**问：可以将 Aspose.Tasks 与其他 Java 库或框架集成吗？**  
答：可以。API 纯 Java 实现，能够无缝集成到 Spring、Hibernate、Maven、Gradle 等生态系统中。

**问：在哪里可以获取 Aspose.Tasks 的额外支持或帮助？**  
答：访问 [Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15) 获取社区帮助，或查阅官方文档获取详细的 API 参考。

## 结论
现在，您已经掌握了 **如何在 Java 中设置货币代码**、**如何更改货币** 值以及 **如何更改货币符号**，全部通过 Aspose.Tasks for Java 实现。这些功能帮助您为全球团队定制费用数据、生成地区特定的报告，并保持项目文件在跨境协作中的一致性。

---

**最后更新：** 2026-02-07  
**测试环境：** Aspose.Tasks for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}