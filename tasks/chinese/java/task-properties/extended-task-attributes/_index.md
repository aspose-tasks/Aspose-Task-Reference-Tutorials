---
date: 2026-01-28
description: 学习如何使用 Aspose.Tasks for Java 读取扩展任务属性，并高效切换自定义字段类型。
linktitle: Read Extended Task Attributes with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks for Java 读取扩展任务属性
url: /zh/java/task-properties/extended-task-attributes/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks for Java 读取扩展任务属性

## Introduction
在本综合教程中，您将学习如何使用 Aspose.Tasks for Java 库从 Microsoft Project 文件中**读取扩展任务属性**。无论您是构建报表工具、同步数据，还是仅仅需要深入了解自定义字段，掌握此功能都能帮助您提取项目中存储的每一条信息。我们将演示所需的设置步骤，展示在处理属性时如何切换自定义字段类型，并提供实用技巧以避免常见陷阱。

## Quick Answers
- **“读取扩展任务属性”是什么意思？** 它指的是提取超出 Project 文件默认任务属性的自定义字段值。  
- **哪个类提供对这些属性的访问？** Aspose.Tasks 中的 `ExtendedAttribute` 类。  
- **运行代码是否需要许可证？** 免费试用版可用于开发，生产环境需要商业许可证。  
- **我可以在运行时更改属性类型吗？** 可以——使用 `switch` 语句根据 `CustomFieldType` **切换自定义字段类型**。  
- **这是否兼容 Java 8 及以上版本？** 完全兼容，API 支持 JDK 8+。

## What is read extended task attributes?
扩展任务属性是用户自定义的字段（文本、日期、数字、标记等），用于补充 Microsoft Project 中的标准任务属性。Aspose.Tasks 通过附加在每个 `Task` 对象上的 `ExtendedAttribute` 集合公开这些属性，您可以以编程方式读取或修改其值。

## Why read extended task attributes?
- **完整可视化：** 了解利益相关者在进度表中添加的自定义数据。  
- **自动化：** 填充仪表盘、生成自定义报表，或在无需手动导出的情况下将数据迁移到其他系统。  
- **灵活性：** 通过适当处理每种情况，可使用任何自定义字段类型——文本、日期、持续时间、成本、标记等。

## Prerequisites
- 具备 Java 编程基础。  
- 机器上已安装 Java Development Kit（JDK）。  
- 使用 IntelliJ IDEA 或 Eclipse 等 IDE。  

## Import Packages
首先导入 Aspose.Tasks 项目所需的类：

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

## Step 1: Accessing Task and Extended Attributes
加载 Project 文件并遍历每个任务，以获取其扩展属性：

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "ReadTaskExtendedAttributes.mpp");
for (Task tsk : project.getRootTask().getChildren()) {
    for (ExtendedAttribute ea : tsk.getExtendedAttributes()) {
```

## Step 2: Retrieving Field ID and Value GUID
打印内部标识符，以帮助您了解正在处理的自定义字段：

```java
System.out.println(ea.getFieldId());
System.out.println(ea.getValueGuid());
```

## Step 3: How to switch custom field type when reading extended task attributes
使用针对 `CustomFieldType` 的 `switch` 语句，正确处理每种可能的数据类型：

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

对项目中的每个任务重复上述步骤，以探索并操作所有扩展任务属性。

## Common Issues and Solutions
| 问题 | 解决方案 |
|-------|----------|
| **返回空值** | 确认自定义字段在源 .mpp 文件中已实际填充。 |
| **显示的类型不正确** | 确保在 `switch` 语句中使用了正确的 `CustomFieldType`；类型不匹配会导致默认值。 |
| **大型项目性能下降** | 将任务分批处理，或使用 `project.getRootTask().getChildren().stream()` 并结合适当的谓词，仅过滤所需的任务。 |

## Frequently Asked Questions
### Can I modify extended task attributes programmatically?
是的，您可以使用 Aspose.Tasks for Java 编程修改扩展任务属性。请参阅文档获取详细说明。

### Is there a trial version available?
有，您可以在[此处](https://releases.aspose.com/)获取免费试用版。

### Where can I find support for Aspose.Tasks for Java?
请访问[Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15)获取支持。

### How can I obtain a temporary license?
您可以在[此处](https://purchase.aspose.com/temporary-license/)获取临时许可证。

### Where can I purchase the full version of Aspose.Tasks for Java?
您可以在[此处](https://purchase.aspose.com/buy)购买完整版本。

---

**最后更新：** 2026-01-28  
**测试环境：** Aspose.Tasks Java API（最新稳定版）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}