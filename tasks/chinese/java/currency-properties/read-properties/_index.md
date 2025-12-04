---
date: 2025-12-04
description: 了解如何使用 Aspose.Tasks for Java 从 MS Project 文件中读取货币属性。请按照本分步指南以编程方式提取货币代码、符号、位数和位置。
language: zh
linktitle: Read Currency Properties Java with Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks 项目在 Java 中读取货币属性
url: /java/currency-properties/read-properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 项目读取货币属性（Java）

## 介绍
在本教程中，您将使用 Aspose.Tasks for Java API **读取货币属性（Java）**，从 Microsoft Project 文件中提取相关信息。Aspose.Tasks 允许在未安装 Microsoft Project 的情况下操作 .mpp 文件，非常适合自动化报表、数据迁移或集成到基于 Java 的企业应用程序。阅读完本指南后，您将能够直接从项目文件中提取货币代码、符号、小数位数以及符号位置。

## 常见问题快速解答
- **“读取货币属性（Java）”是什么意思？** 它指的是使用 Java 代码从 MS Project 文件中获取与货币相关的元数据（代码、符号、位数、位置）。  
- **尝试此功能需要许可证吗？** Aspose.Tasks 提供免费试用版；在生产环境中需要商业许可证。  
- **需要哪个 JDK 版本？** Java 8 或更高版本。  
- **读取后可以修改货币设置吗？** 可以，Aspose.Tasks 支持对货币属性的读取和写入操作。  
- **是否兼容所有 .mpp 版本？** 该 API 支持 Microsoft Project 2003‑2021 创建的文件。

## 什么是读取货币属性（Java）？
在 Java 中读取货币属性是指访问 Microsoft Project 文件中定义货币显示方式的项目级设置。这些设置包括 ISO 货币代码（例如 **USD**）、符号（**$**）、小数位数以及符号是位于金额前还是后。

## 为什么使用 Aspose.Tasks 读取货币属性（Java）？
- **无需安装 Microsoft Project** – API 可在任何支持 Java 的平台上运行。  
- **快速、进程内提取** – 适合批量处理大量项目文件。  
- **完全控制** – 可将获取的值与自定义报表结合，或集成到 ERP 系统中。  
- **跨版本支持** – 兼容 Project 2003 到最新 2021 版本的 .mpp 文件。

## 前提条件
在开始之前，请确保您已具备以下条件：

1. **Java Development Kit (JDK)** – 已安装 Java 8 或更高版本，并在 `PATH` 中配置。  
2. **Aspose.Tasks for Java JAR** – 从 [here](https://releases.aspose.com/tasks/java/) 下载最新库，并将其添加到项目的类路径中。  

## 导入包
首先导入操作项目所需的 Aspose.Tasks 命名空间：

```java
import com.aspose.tasks.*;
```

## 步骤 1：设置项目目录
定义包含要分析的 `.mpp` 文件的文件夹。将路径存入变量可以提高代码复用性：

```java
String dataDir = "Your Data Directory";
```

*将 `"Your Data Directory"` 替换为 `project.mpp` 所在文件夹的绝对或相对路径。*

## 步骤 2：创建项目读取实例
将 Microsoft Project 文件加载到 `Project` 对象中。该对象提供对所有项目属性的访问，包括货币设置：

```java
Project project = new Project(dataDir + "project.mpp");
```

*如果文件名不同，请相应修改 `"project.mpp"`。*

## 步骤 3：显示货币属性
使用 `Prj` 枚举检索每个货币属性，并将结果打印到控制台。API 返回的对象可以转换为字符串进行显示：

```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position : " + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```

**您将看到的内容：**  
- **Currency Code** – ISO‑4217 代码，例如 `USD`、`EUR`、`JPY`。  
- **Currency Digits** – 大多数货币为 `2` 位，小数位为 `0` 的如日元。  
- **Currency Symbol** – 报表中显示的字符（`$`、`€`、`¥`）。  
- **Currency Symbol Position** – `0` 表示 **在金额前**，`1` 表示 **在金额后**。

## 步骤 4：处理完成
在提取成功完成后输出提示信息。当代码作为更大批处理作业的一部分运行时，此信息非常有用：

```java
System.out.println("Process completed Successfully");
```

## 常见问题及解决方案
| 问题 | 原因 | 解决方案 |
|------|------|----------|
| **FileNotFoundException** | `dataDir` 路径不正确或文件名拼写错误。 | 检查目录字符串，确保 `.mpp` 文件存在于指定位置。 |
| **NullPointerException on `project.get(...)`** | 项目文件未包含货币信息（极少见）或属性键错误。 | 在读取前使用 `project.contains(Prj.CURRENCY_CODE)` 检查是否存在。 |
| **LicenseException** | 在生产环境中未使用有效的 Aspose.Tasks 许可证运行。 | 在创建 `Project` 对象前使用 `License license = new License(); license.setLicense("Aspose.Tasks.lic");` 加载许可证文件。 |

## 常见问答

**Q: Aspose.Tasks 是否兼容所有版本的 Microsoft Project？**  
A: Aspose.Tasks 支持 Microsoft Project 2003‑2021 生成的 .mpp 文件，覆盖旧版和最新格式。

**Q: 可以使用 Aspose.Tasks 修改货币属性吗？**  
A: 可以，既可以读取也可以写入货币设置。使用 `project.set(Prj.CURRENCY_CODE, "EUR");` 后保存项目即可。

**Q: Aspose.Tasks 适合商业使用吗？**  
A: 完全适合。它是商业库，您可以在 [here](https://purchase.aspose.com/buy) 购买许可证。

**Q: Aspose.Tasks 提供免费试用吗？**  
A: 是的，可从 [here](https://releases.aspose.com/) 获取功能完整的试用版。

**Q: 在哪里可以获取 Aspose.Tasks 的帮助或支持？**  
A: 官方 Aspose.Tasks 论坛是获取帮助的最佳渠道——请访问 [here](https://forum.aspose.com/c/tasks/15)。

## 结论
现在，您已经学会如何使用 Aspose.Tasks for Java **读取货币属性（Java）**，从 MS Project 文件中提取货币元数据。这一功能使您能够在不依赖 Microsoft Project 的情况下，将货币信息整合到自定义报表、财务分析或集成流水线中。欢迎尝试修改属性或将此数据与其他项目属性结合，构建更丰富的解决方案。

---

**最后更新：** 2025-12-04  
**测试环境：** Aspose.Tasks for Java 24.12（撰写时的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}