---
date: 2025-12-05
description: 学习如何使用 Aspose.Tasks for Java 高效处理 MS Project 货币位数。一步步指南，涵盖 Java 项目文件处理以及如何加载
  MPP 文件。
linktitle: Handle ms project currency Digits with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks 处理 MS Project 货币小数位
url: /zh/java/currency/currency-digits/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 处理 MS Project 货币位数

## 介绍
在本完整教程中，您将了解 **如何使用 Aspose.Tasks for Java 库处理 MS Project 货币** 值。无论您是构建报表工具、迁移实用程序，还是仅需读取 **java 项目文件** 中的货币设置，本指南都会一步步带您完成——从加载 *.mpp* 文件到提取货币位数。阅读完本教程后，您将能够在自己的应用程序中自如地处理 MS Project 货币数据。

## 快速答案
- **哪个库可以读取 MS Project 文件？** Aspose.Tasks for Java。  
- **获取货币位数需要多少行代码？** 项目加载后仅需三行简洁代码。  
- **开发阶段需要许可证吗？** 免费试用可用于测试，生产环境需商业许可证。  
- **支持哪个 Java 版本？** Java 8 或更高（任何能够运行 Aspose.Tasks 的 JDK）。  
- **可以获取其他 Project 属性吗？** 可以——Aspose.Tasks 提供完整的 Project 字段集合（如开始日期、费用率等）。

## 什么是 MS Project 货币？
`ms project currency` 指的是 Microsoft Project 在显示货币值时使用的数字精度（小数位数）。它在项目文件中以 **CURRENCY_DIGITS** 属性存储，决定金额是以整数、单小数位、双小数位等形式显示。

## 为什么使用 Aspose.Tasks 处理 MS Project 货币？
- **无需安装 Microsoft Project** ——直接在任何支持 Java 的平台上操作 *.mpp* 文件。  
- **强类型安全** ——API 返回强类型值，降低解析错误。  
- **性能优化** ——快速加载大型项目，仅提取所需字段。  
- **跨平台** ——在 Windows、Linux 或 macOS 上无需修改即可运行。

## 前置条件
在开始之前，请确保具备以下条件：

1. **Java 开发环境** ——已安装并配置 JDK 8 或更高版本。  
2. **Aspose.Tasks for Java** ——从官方站点下载最新 JAR：[Aspose.Tasks for Java](https://releases.aspose.com/tasks/java/)。  
3. **基础 Java 知识** ——能够创建 Java 项目、添加外部库并运行 `main` 方法。

## 导入包
首先，导入我们需要的类。  
```java
import java.io.IOException;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## 步骤 1：定义数据目录
指定包含 **java 项目文件**（`*.mpp`）的文件夹。  
```java
String dataDir = "Your Data Directory";
```
将 `"Your Data Directory"` 替换为 `project.mpp` 所在的绝对路径或相对路径。

## 步骤 2：加载 MPP 文件  
接下来演示 **如何使用 Aspose.Tasks 加载 mpp** 文件。  
```java
Project project = new Project(dataDir + "project.mpp");
```
确保文件名完全匹配，否则会抛出 `IOException`。

## 步骤 3：检索货币位数  
项目加载后，提取 **MS Project 货币** 位数只需一行代码：  
```java
System.out.println(project.get(Prj.CURRENCY_DIGITS));
```
该调用返回一个 `Integer`，表示小数位数（例如，`2` 表示分币）。值会打印到控制台，也可以存入变量以便后续处理。

## 常见问题与技巧
- **文件未找到** ——再次检查 `dataDir` 路径，确保文件名及 `.mpp` 扩展名正确。  
- **不支持的文件版本** ——Aspose.Tasks 支持 Project 2000‑2024 格式，较旧或损坏的文件可能需要转换。  
- **未设置许可证** ——开发阶段可使用试用版，生产环境必须应用有效许可证以去除评估水印。

## 常见问答

**问：Aspose.Tasks 能处理除货币位数之外的其他 Project 属性吗？**  
答：可以，Aspose.Tasks 提供广泛功能，可操作任务、资源、自定义字段等多种 Project 内容。

**问：Aspose.Tasks 适合企业级应用吗？**  
答：完全适合，Aspose.Tasks 旨在满足企业级项目的高性能和可扩展性需求。

**问：Aspose.Tasks 是否支持跨平台开发？**  
答：是的，只要支持 Java 运行时环境（Windows、Linux、macOS），均可使用 Aspose.Tasks for Java。

**问：我可以在购买前试用 Aspose.Tasks 吗？**  
答：可以，您可以从 [此处](https://releases.aspose.com/) 下载免费试用版。

**问：在哪里可以获得 Aspose.Tasks 的支持？**  
答：您可以在 [Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15) 获取帮助。

---

**最后更新：** 2025-12-05  
**测试环境：** Aspose.Tasks for Java 24.11（撰写时最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}