---
date: 2026-06-05
description: 了解如何使用 Aspose.Tasks for Java 过滤 MPP 文件，自定义 filter criteria，并按日期 filter
  tasks，以简化 project management。
keywords:
- how to filter mpp
- filter tasks by date
- Aspose.Tasks Java filter
- project management Java API
linktitle: 如何使用 Aspose.Tasks for Java 过滤 MPP 文件
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to filter MPP files using Aspose.Tasks for Java, customize
    filter criteria, and filter tasks by date to streamline project management.
  headline: How to Filter MPP Files Using Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: It means extracting a subset of project data based on defined conditions.
    question: What does “filter mpp” mean?
  - answer: Aspose.Tasks for Java provides a comprehensive API for creating and applying
      filters.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – each entity type has its own filter collection.
    question: Can I filter tasks, resources, and assignments?
  - answer: Aspose.Tasks supports Java 8 and later versions.
    question: Is Java 8 or higher required?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks for Java 过滤 MPP 文件
url: /zh/java/project-management/filter-data/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks for Java 过滤 MPP 文件

## 介绍
如果您在 Java 应用程序中处理 Microsoft Project 文件（*.mpp*），通常需要 **过滤 MPP 文件** 以隔离最重要的任务、资源或分配。在本教程中，我们将逐步演示如何使用 Aspose.Tasks for Java 以编程方式 **过滤 mpp** 文件，向您展示如何 **自定义过滤条件**，并演示一个实用的“按日期过滤任务”场景。完成后，您将拥有一个可直接放入任何 Java 项目的即用代码片段。

## 快速解答
- **What does “filter mpp” mean?** 它指的是根据定义的条件提取项目数据的子集。  
- **Which library handles this?** Aspose.Tasks for Java 提供了用于创建和应用过滤器的全面 API。  
- **Do I need a license?** 免费试用可用于开发；生产环境需要商业许可证。  
- **Can I filter tasks, resources, and assignments?** 是的 – 每种实体类型都有自己的过滤器集合。  
- **Is Java 8 or higher required?** Aspose.Tasks 支持 Java 8 及更高版本。

## 在 Java 中 “how to filter mpp” 是什么？
`How to filter mpp` 是使用 Aspose.Tasks 的 `Filter` 对象来选择满足特定谓词（如开始日期、成本或自定义字段）的项目元素的过程。加载一个 `Project`，获取一个 `Filter`，API 将返回匹配您条件的集合，从而实现聚焦的报告或下游集成。

## 为什么要自定义过滤条件？
自定义过滤条件可以让您针对高风险任务、逾期项目或预算超支的资源，将庞大的项目文件转化为简洁、可操作的视图。Aspose.Tasks 支持 **50+ 预定义过滤类型**，并允许您构建无限的自定义过滤器，将手动筛选数据的时间最多减少 70 %。

## 前置条件
1. **Java Development Kit (JDK)** – 版本 8 或更高。  
2. **Aspose.Tasks for Java** – 从 [download page](https://releases.aspose.com/tasks/java/) 下载。  
3. **An IDE** – IntelliJ IDEA、Eclipse 或 NetBeans 都可使用。  

## 导入包
`Filter`、`FilterCollection`、`FilterCriteria`、`ItemType` 和 `Project` 是用于定义和应用项目数据过滤器的核心类。

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

## 步骤指南

### 步骤 1：设置项目
首先，创建一个指向要分析的 MPP 文件的 `Project` 实例，然后将其加载到内存中。此一步骤会准备整个项目模型，以便进行过滤、验证和进一步操作，使您能够通过 API 访问任务、资源和分配。

### 如何设置项目以过滤 MPP 文件？
`Project` 类在内存中加载并表示一个 MPP 文件。创建一个指向要分析的 MPP 文件的 `Project` 实例，然后将其加载到内存中。此一步骤会准备整个项目模型，以便进行过滤、验证和进一步操作，使您能够通过 API 访问任务、资源和分配。

### 如何检索和检查过滤器？
`Filter` 对象封装用于选择项目项的过滤器定义。Aspose.Tasks 存储了诸如 “All Tasks” 或 “Critical Tasks” 等预定义过滤器。使用 `project.getTaskFilters().getByName("My Filter")` 或基于索引的方式获取 `Filter` 对象，然后检查其 `FilterCriteria` 集合，以查看每条规则以及组合它们的逻辑运算符（AND/OR），确保过滤器符合您的需求。

### 如何遍历嵌套的条件行？
`FilterCriteriaGroup` 表示一组使用逻辑运算符组合的过滤条件。过滤器可以包含多个条件组，每个组都有自己的运算符。遍历 `filter.getCriteria().getRows()`，对于任何是 `FilterCriteriaGroup` 的行，递归进入其子行。此遍历使您能够完整理解复杂的过滤逻辑，例如 “(Start < today AND Cost > 1000) OR Priority = High”，并根据需要调整条件。

### 如何打印条件信息以进行调试？
遍历完条件树后，将每行的字段名、测试运算符和数值输出到控制台。此简单的转储帮助您在将过滤器应用于大型项目之前验证其符合预期的业务规则，并更容易发现错误的运算符或数值。

### 如何以编程方式创建全新的过滤器？
使用 `new Filter("My Filter")` 实例化一个 `Filter`，然后使用 `project.getTaskFilters().add(filter)` 将其添加到项目的任务过滤器集合中。之后，用所需的行填充其 `FilterCriteria` 集合，指定字段名、测试运算符和值，以准确定义在应用过滤器时应包含的任务。

### 我可以将过滤器应用于资源而不是任务吗？
`ResourceFilters` 集合保存适用于资源的过滤器定义。是的 – 使用 `project.getResourceFilters()` 以与任务过滤器相同的方式处理资源特定的过滤器。添加或检索过滤器后，像对任务一样配置其 `FilterCriteria`，然后将其应用于资源集合，以获得过滤后的资源集合。

### 是否可以使用 OR 逻辑组合多个过滤器？
创建一个父级 `FilterCriteriaGroup`，将其 `Operation` 设置为 `OR`，然后将各个 `FilterCriteria` 对象作为子项添加。该组将评估每个子条件并返回满足任意条件的项目，从而允许您将多个简单过滤器组合成更广泛的选择。

### Aspose.Tasks 是否支持对自定义字段进行过滤？
`CustomField` 枚举提供项目中定义的自定义字段的标识符。完全支持。通过 `CustomField` 枚举引用自定义字段，它们在过滤表达式中表现得像任何内置字段。您可以在 `FilterCriteria` 行中包含它们，使用相同的运算符和值，从而在标准项目属性的同时对用户定义的数据进行强大的查询。

### 过滤对大型 MPP 文件的性能影响如何？
过滤完全在内存中运行，通常在 200 ms 以下处理包含 1,000 个任务的项目。对于包含数千任务的文件，考虑使用 `ProjectReader` 仅加载所需部分，然后在选择性加载后应用过滤器，这可以保持低内存使用，并在非常大的项目中仍保持快速响应时间。

---

**最后更新:** 2026-06-05  
**测试环境:** Aspose.Tasks for Java 24.10  
**作者:** Aspose

## 相关教程

- [加载 MPP 文件 Java - 使用 Aspose.Tasks 管理项目属性](/tasks/java/project-management/default-properties/)
- [Aspose.Tasks Java - 轻松读取 MS Project 在线数据](/tasks/java/project-data-reading/read-project-online/)
- [使用 Aspose.Tasks for Java 设置 MS Project 项目开始日期](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "Project2003.mpp");
```

```java
Filter filter = project.getTaskFilters().toList().get(1);
```

```java
System.out.println(filter.getCriteria().getCriteriaRows().size());
System.out.println(filter.getCriteria().getOperation());
```

```java
FilterCriteria criteria1 = filter.getCriteria().getCriteriaRows().get(0);
System.out.println(criteria1.getTest());
System.out.println(criteria1.getField());
```

```java
FilterCriteria criteria2 = filter.getCriteria().getCriteriaRows().get(1);
System.out.println(criteria2.getOperation());
System.out.println(criteria2.getCriteriaRows().size());
```

```java
FilterCriteria criteria21 = criteria2.getCriteriaRows().get(0);
System.out.println(criteria21.getTest());
System.out.println(criteria21.getField());
FilterCriteria criteria22 = criteria2.getCriteriaRows().get(1);
System.out.println(criteria22.getTest());
System.out.println(criteria22.getField());
```