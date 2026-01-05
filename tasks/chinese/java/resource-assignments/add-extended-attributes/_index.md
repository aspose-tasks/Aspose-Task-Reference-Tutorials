---
date: 2026-01-05
description: 学习如何使用 Aspose.Tasks for Java 设置项目开始日期并保存 MS Project XML。面向 Java 开发者的逐步指南。
linktitle: Add Extended Attributes to Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks for Java 设置项目开始日期
url: /zh/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks for Java 设置项目开始日期

## 介绍
在本教程中，您将学习如何在 Microsoft Project 文件中 **设置项目开始日期**，然后使用 Aspose.Tasks for Java 库 **保存 MS Project XML**。无论是自动化报告管道还是构建自定义项目管理工具，掌握此任务都能为您节省时间并消除人工错误。

## 快速答案
- **设置开始日期的主要方法是什么？** 使用 `project.set(Prj.START_DATE, …)`。
- **我应该使用哪种格式导出文件？** 使用 `SaveFileFormat.Xml` 将其保存为 XML。
- **此操作是否需要许可证？** 试用版可用，但完整许可证可去除水印。
- **创建任务后我可以更改开始日期吗？** 可以，在添加任务之前更新项目属性。
- **这与所有 MS Project 版本兼容吗？** Aspose.Tasks 支持 XML、MPP 等多种格式。

## 什么是“设置项目开始日期”？
设置项目开始日期定义了所有任务调度计算的基准日历。这是以编程方式构建可靠项目计划的第一步。

## 为什么使用 Aspose.Tasks for Java？
Aspose.Tasks 提供纯 Java API，可在任何平台上运行，无需安装 Microsoft Project。它让您能够快速创建、修改和导出项目数据，非常适合服务器端自动化。

## 先决条件
1. **Java Development Kit (JDK)** – 任意近期的 JDK 版本。
2. **Aspose.Tasks for Java** – 从 [here](https://releases.aspose.com/tasks/java/) 下载。
3. **IDE** – IntelliJ IDEA、Eclipse 或您偏好的 Java IDE。

## 导入包
First, import the necessary classes:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### 步骤 1：设置数据目录
Define where the generated files will be stored.

```java
String dataDir = "Your Data Directory";
```

### 步骤 2：创建项目实例
Instantiate a new, empty project.

```java
Project project = new Project();
```

### 步骤 3：设置项目属性信息
Here we **set the project start date** and related schedule properties.

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### 步骤 4：保存 MS Project XML
Export the configured project to an XML file.

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## 常见问题及解决方案
- **日期格式不正确：** 确保使用 `java.util.Calendar` 并在赋值前调用 `getTime()`。
- **文件未保存：** 验证 `dataDir` 指向一个存在且可写的文件夹。
- **许可证警告：** 试用版会添加水印，使用有效许可证可将其移除。

## 常见问题解答

### Q: 我可以使用 Aspose.Tasks for Java 读取 MS Project 文件吗？  
**A:** 可以，Aspose.Tasks for Java 提供强大的功能，既可读取也可写入 MS Project 文件。

### Q: Aspose.Tasks for Java 是否兼容不同版本的 MS Project？  
**A:** 当然，Aspose.Tasks for Java 支持多种 MS Project 格式，确保广泛兼容性。

### Q: Aspose.Tasks for Java 的试用版有什么限制吗？  
**A:** 试用版允许您试用库，但会在输出文件中添加水印。

### Q: 我如何获取 Aspose.Tasks for Java 的支持？  
**A:** 您可以在 Aspose.Tasks 社区论坛 [here](https://forum.aspose.com/c/tasks/15) 寻求帮助。

### Q: 我可以购买 Aspose.Tasks for Java 的临时许可证吗？  
**A:** 可以，临时许可证可用于短期使用。可从 [here](https://purchase.aspose.com/temporary-license/) 获取。

### Q: 保存为 XML 是否保留自定义字段？  
**A:** 是的，使用 `SaveFileFormat.Xml` 保存时，所有自定义属性和扩展字段都会被保留。

### Q: 添加任务后我可以更改开始日期吗？  
**A:** 您可以在保存前随时更新开始日期，只需再次调用 `project.set(Prj.START_DATE, …)` 即可。

---

**最后更新：** 2026-01-05  
**测试环境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}