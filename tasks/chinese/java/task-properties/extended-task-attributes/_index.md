---
title: Aspose.Tasks 中的扩展任务属性
linktitle: Aspose.Tasks 中的扩展任务属性
second_title: Aspose.Tasks Java API
description: 探索 Aspose.Tasks for Java 中的扩展任务属性。分步指南、常见问题解答和支持。立即优化您的项目管理！
type: docs
weight: 16
url: /zh/java/task-properties/extended-task-attributes/
---
## 介绍
欢迎阅读我们关于在 Aspose.Tasks for Java 中利用扩展任务属性的综合指南。 Aspose.Tasks 是一个功能强大的 Java 库，可让您无缝地处理 Microsoft Project 文档。在本教程中，我们将深入研究扩展任务属性，并演示如何利用它们来增强项目管理能力。
## 先决条件
在我们开始之前，请确保您具备以下先决条件：
- Java 编程的基础知识。
- 在您的计算机上安装了 Java 开发工具包 (JDK)。
- 集成开发环境 (IDE)，例如 IntelliJ 或 Eclipse。
## 导入包
首先导入必要的包来启动您的 Aspose.Tasks 项目：
```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```
现在，让我们将该示例分解为多个步骤来指导您完成该过程：
## 第 1 步：访问任务和扩展属性
```java
//文档目录的路径。
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "ReadTaskExtendedAttributes.mpp");
for (Task tsk : project.getRootTask().getChildren()) {
    for (ExtendedAttribute ea : tsk.getExtendedAttributes()) {
```
## 步骤 2：检索字段 ID 和值 GUID
```java
System.out.println(ea.getFieldId());
System.out.println(ea.getValueGuid());
```
## 步骤 3：处理不同的属性类型
```java
switch (ea.getAttributeDefinition().getCfType()) {
    case CustomFieldType.Date:
    case CustomFieldType.Start:
    case CustomFieldType.Finish:
        System.out.println(ea.getDateValue());
        break;
    case CustomFieldType.Text:
        System.out.println(ea.getTextValue());
        break;
    case CustomFieldType.Duration:
        System.out.println(ea.getDurationValue().toString());
        break;
    case CustomFieldType.Cost:
    case CustomFieldType.Number:
        System.out.println(ea.getNumericValue());
        break;
    case CustomFieldType.Flag:
        System.out.println(ea.getFlagValue());
        break;
}
```
对项目中的每个任务重复这些步骤，以探索和操作扩展任务属性。
## 结论
总之，理解和利用 Aspose.Tasks for Java 中的扩展任务属性可以显着增强您的项目管理能力。本指南为您开始这一旅程奠定了坚实的基础。
## 经常问的问题
### 我可以通过编程方式修改扩展任务属性吗？
是的，您可以使用 Aspose.Tasks for Java 修改扩展任务属性。请参阅文档以获取详细说明。
### 有试用版吗？
是的，您可以免费试用[这里](https://releases.aspose.com/).
### 在哪里可以找到 Aspose.Tasks for Java 的支持？
如需支持，请访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15).
### 我怎样才能获得临时许可证？
您可以获得临时许可证[这里](https://purchase.aspose.com/temporary-license/).
### 在哪里可以购买完整版的 Aspose.Tasks for Java？
您可以购买完整版[这里](https://purchase.aspose.com/buy).