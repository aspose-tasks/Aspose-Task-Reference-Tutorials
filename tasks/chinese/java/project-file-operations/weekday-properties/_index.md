---
date: 2026-03-29
description: 了解如何在 Aspose.Tasks for Java 中更改每月天数并管理其他工作日属性。自定义周起始日期，修改项目日历，并将项目保存为
  XML。
linktitle: Weekday Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks 的 Weekday 属性更改每月天数
url: /zh/java/project-file-operations/weekday-properties/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 工作日属性更改每月天数

## 介绍
Aspose.Tasks for Java 允许您 **更改每月天数** 并微调其他工作日设置，无需安装 Microsoft Project。无论是将项目日历对齐到非标准财务月份，还是仅需调整一周的起始日，本教程都将带您了解最常见的场景——获取当前的周起始日、定制周起始日期、修改项目日历以及将项目保存为 XML。

## 快速回答
- **我可以更改每月的天数吗？** 可以，在 `Project` 对象上使用 `Prj.DAYS_PER_MONTH`。  
- **如何定制周起始日期？** 将 `Prj.WEEK_START_DAY` 设置为 `DayType` 值（例如 `DayType.Monday`）。  
- **导出项目可以使用什么格式？** 示例使用 `SaveFileFormat.Xml` 将文件保存为 XML。  
- **生产环境是否需要许可证？** 非评估部署需要有效的 Aspose.Tasks 许可证。  
- **支持哪些 IDE？** 任何 Java IDE，如 IntelliJ IDEA、Eclipse 或 NetBeans 都可使用。

## 什么是 Aspose.Tasks 中的 “更改每月天数”？
更改每月天数是指更新 `Project` 实例的 `Prj.DAYS_PER_MONTH` 属性。该属性告诉引擎每个月应视为多少工作日，直接影响任务调度和成本计算。

## 为什么要修改项目日历属性？
定制项目日历——例如设置不同的周起始日或更改每天/每周的分钟数——可以帮助您：

- 与地区工作周保持一致。  
- 建模非标准工作模式（例如 4 天工作制）。  
- 为使用自定义日历的合同提供准确的报告。

## 前置条件
- **Java Development Kit (JDK)** – 从 Oracle 下载并安装最新的 JDK。  
- **Aspose.Tasks for Java 库** – 从官方站点[此处](https://releases.aspose.com/tasks/java/)下载。  
- **您选择的 IDE** – IntelliJ IDEA、Eclipse 或 NetBeans。

## 导入包
首先，导入 Aspose.Tasks 的核心类：

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

## 步骤 1：加载项目文件
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
此代码从您指定的文件夹加载现有的 Microsoft Project 文件 (`project.mpp`)。

## 步骤 2：显示工作日属性
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
在这里我们检索并打印当前的工作日设置，包括 **周起始日** 和 **每月天数**。

## 步骤 3：设置工作日属性
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
本步骤将 **每月天数** 更改为 24，设置周起始日为 Monday，并调整每天/每周的分钟数。这演示了如何以编程方式 **修改项目日历** 的数值。

## 步骤 4：保存项目
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
修改后的项目使用 **保存为 XML** 格式持久化，便于与其他工具集成或进行版本控制存储。

## 步骤 5：显示结果
```java
System.out.println("Process completed Successfully");
```
一个简单的确认，表明操作已成功完成且没有错误。

## 如何定制周起始日期
如果贵组织采用星期日为首日的日历，只需将 `DayType.Monday` 替换为 `DayType.Sunday`。同样使用 `Prj.WEEK_START_DAY` 属性，修改非常直接。

## 如何获取周起始日
您可以在任何时候调用 `project.get(Prj.WEEK_START_DAY)` 来 **获取周起始日** 信息，如步骤 2 所示。

## 如何修改项目日历
除了周起始日，您还可以调整 `Prj.MINUTES_PER_DAY` 和 `Prj.MINUTES_PER_WEEK`，以反映自定义工作时间或班次模式。

## 常见问题及解决方案
- **DayType 值不正确** – 确保使用 `DayType` 枚举（例如 `DayType.Monday`）。  
- **文件路径错误** – 验证 `dataDir` 以正确的文件分隔符（`/` 或 `\`）结尾。  
- **许可证未设置** – 若出现许可证警告，请在创建 `Project` 对象之前注册 Aspose.Tasks 许可证。

## 常见问答

**问：Aspose.Tasks for Java 能处理复杂的项目结构吗？**  
答：可以，Aspose.Tasks for Java 提供全面支持，能够轻松处理复杂的项目结构。

**问：Aspose.Tasks for Java 是否兼容不同版本的 Microsoft Project 文件？**  
答：完全兼容，Aspose.Tasks for Java 支持多种 Microsoft Project 文件版本，确保跨平台兼容性。

**问：我可以将 Aspose.Tasks for Java 集成到现有的 Java 应用程序中吗？**  
答：可以，Aspose.Tasks for Java 提供无缝集成能力，帮助您在 Java 应用中加入强大的项目管理功能。

**问：Aspose.Tasks for Java 是否提供文档和支持？**  
答：是的，您可以在其[官方网站](https://releases.aspose.com/)上获取丰富的文档和社区支持。

**问：Aspose.Tasks for Java 有免费试用吗？**  
答：有，您可以从其[官方网站](https://reference.aspose.com/tasks/java/)下载免费试用版，先行体验功能后再决定购买。

---

**最后更新：** 2026-03-29  
**测试环境：** Aspose.Tasks for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}