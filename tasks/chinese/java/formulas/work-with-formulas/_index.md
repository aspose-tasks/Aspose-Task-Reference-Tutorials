---
title: MS Project 公式与 Aspose.Tasks for Java
linktitle: 在 Aspose.Tasks 中使用公式
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks 库在 Java 中操作 MS Project 文件。轻松创建、修改和计算属性。
weight: 11
url: /zh/java/formulas/work-with-formulas/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project 公式与 Aspose.Tasks for Java

## 介绍
在本教程中，我们将深入研究如何使用 Aspose.Tasks for Java 来处理 MS Project Formulas。 Aspose.Tasks 是一个功能强大的库，使开发人员能够以编程方式操作 Microsoft Project 文件。凭借其广泛的功能，您可以轻松地在 Java 应用程序中创建、读取、修改和转换项目文件。
## 先决条件
在我们开始之前，请确保您已设置以下先决条件：
### Java开发环境
确保您的系统上安装了 Java 开发工具包 (JDK)。您可以从 Oracle 网站下载并安装最新的 JDK。
### Aspose.Tasks库
您需要将 Aspose.Tasks 库添加到您的 Java 项目中。您可以从以下位置下载该库[Aspose.Tasks for Java 下载页面](https://releases.aspose.com/tasks/java/)并将其包含在您的项目的依赖项中。

## 导入包
在深入研究示例之前，请将必要的包导入到您的 Java 代码中：
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

让我们将提供的示例分解为多个步骤：
## 第 1 步：使用自定义字段创建测试项目
```java
Project project = CreateTestProjectWithCustomField();
```
首先，使用以下命令创建一个带有自定义字段的测试项目`CreateTestProjectWithCustomField()`方法。此方法将返回一个代表新创建的项目的 Project 对象。
## 步骤 2：定义扩展属性定义
```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```
从项目中检索扩展属性定义并设置其别名和公式。在此示例中，我们定义一个属性来计算从完成日期到截止日期的天数。
## 第 3 步：设置任务的截止日期
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```
创建一个 Calendar 对象并设置截止日期。然后，从项目中检索任务并使用 Calendar 对象设置其截止日期。
## 第 4 步：保存项目
```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```
最后，将项目保存到具有指定名称和格式的文件中。在本例中，我们将其另存为 MPP 文件。

## 结论
在本教程中，我们学习了如何使用 Aspose.Tasks for Java 来处理 MS Project Formulas。通过执行这些步骤，您可以以编程方式有效地操作项目文件，添加自定义字段并根据公式计算属性。

## 常见问题解答
### 问：我可以将 Aspose.Tasks 与其他编程语言一起使用吗？
答：是的，Aspose.Tasks 支持各种编程语言，包括 Java、.NET 等。
### 问：Aspose.Tasks 是否有免费试用版？
答：是的，您可以从以下位置下载 Aspose.Tasks 的免费试用版：[这里](https://releases.aspose.com/).
### 问：在哪里可以找到 Aspose.Tasks 的文档？
 A：你可以找到Aspose.Tasks的文档[这里](https://reference.aspose.com/tasks/java/).
### 问：如何获得 Aspose.Tasks 的支持？
答： 如需支持，您可以访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15).
### 问：使用 Aspose.Tasks 需要临时许可证吗？
答：如果您需要额外的功能，您可以从以下位置获取临时许可证：[这里](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
