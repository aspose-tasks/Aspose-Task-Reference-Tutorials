---
date: 2026-03-29
description: 学习如何在使用 Aspose.Tasks for Java 的 MPP 项目中设置关键字和创建日期（Java）。提供带代码示例的逐步指南。
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks 在 MPP 项目摘要中设置关键字
url: /zh/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 MPP 项目摘要中使用 Aspose.Tasks 设置关键字

## 介绍
在本教程中，您将学习 **如何设置关键字** 和其他摘要信息，以使用 Aspose.Tasks for Java 操作 MPP 项目文件。无论您需要嵌入作者详情、修订号，还是自定义创建日期，本指南都会逐步演示完整的操作步骤，并提供可直接运行的代码示例。完成后，您将能够设置关键字、设置 Java 创建日期，并从文件中检索这些数据。

## 快速答案
- **使用的库是什么？** Aspose.Tasks for Java  
- **主要目的？** 在 MPP 文件中设置关键字、作者信息和创建日期  
- **代码步骤有多少？** 三个简单的代码块（初始化、保存、读取）  
- **需要许可证吗？** 免费试用可用于开发；生产环境需要商业许可证  
- **支持的 Java 版本？** Java 8 及以上  

## 什么是 MPP 文件中的“设置关键字”？
关键字是存储在 Microsoft Project（MPP）文件中的元数据字段。它们有助于对项目进行分类、实现快速搜索，并为下游工具提供上下文信息。Aspose.Tasks 提供了 `Prj.KEYWORDS` 属性，使得以编程方式写入或更新该值变得非常简单。

## 为什么使用 Aspose.Tasks for Java 来设置关键字和创建日期？
* **完整的 .MPP 兼容性** – 支持所有 Project 2007‑2023 格式。  
* **无需 COM 或 Office 安装** – 纯 Java，适用于服务器端环境。  
* **丰富的 API** – 除了关键字，还可以在一次调用中设置作者、修订、注释和日期。  
* **性能优化** – 即使是大型项目文件也能快速读写。  

## 前置条件
1. **Java Development Kit (JDK)** – 已安装 JDK 8 或更高版本。  
2. **Aspose.Tasks for Java** – 从 [here](https://releases.aspose.com/tasks/java/) 下载最新的 JAR。  
3. **IDE** – IntelliJ IDEA、Eclipse、NetBeans 或您喜欢的任何编辑器。  

## 导入包
首先，导入所需的类。这些导入让您能够访问 `Project` 对象、用于摘要字段的 `Prj` 枚举以及用于保存的 `SaveFileFormat` 枚举。

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## 步骤 1：设置项目并定义摘要信息
创建一个 `Project` 实例，然后使用 `set` 方法写入所需的元数据。请注意我们如何使用 `Calendar` 对象 **设置关键字** 和 **设置 Java 创建日期**。

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");          // <-- set keywords
project.set(Prj.COMMENTS, "Comments");

// Set creation date of the project (set creation date java)
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());

// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```

## 步骤 2：保存项目摘要信息
在填充完字段后，持久化更改。这里我们将项目保存为 XML，便于检查，但您也可以保存回 MPP 格式。

```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```

## 步骤 3：读取项目摘要信息
为了验证元数据是否正确写入，重新加载文件并读取每个属性。此步骤展示了 **如何设置关键字** 的端到端完整实现。

```java
// Reading Project Summary Information
project = new Project(dataDir + "MppAspose.xml");
// Print author of the project
System.out.println("Author: " + project.get(Prj.AUTHOR));
// Print last author of the project
System.out.println("Last Author: " + project.get(Prj.LAST_AUTHOR));
// Print revision number of the project
System.out.println("Revision: " + project.get(Prj.REVISION));
// Print keywords of the project
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print comments of the project
System.out.println("Comments: " + project.get(Prj.COMMENTS));
// Print creation date of the project
System.out.println("Creation Date: " + project.get(Prj.CREATION_DATE).toString());
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```

## 常见问题及解决方案
| 问题 | 原因 | 解决方案 |
|-------|----------------|-----|
| **在 `project.get(Prj.CREATION_DATE)` 上的 NullPointerException** | 在保存之前未设置日历。 | 确保在 `save()` 之前调用 `project.set(Prj.CREATION_DATE, cal.getTime())`。 |
| **关键字未在 Microsoft Project UI 中显示** | 文件以 XML 格式保存并直接在 Project 中打开。 | 保存回 MPP（`SaveFileFormat.MPP`）或通过 Project 的 *Import* 打开 XML。 |
| **日期值因时区偏移** | Java `Date` 包含时区信息。 | 如果需要 UTC 日期，请使用 `Calendar.setTimeZone(TimeZone.getTimeZone("UTC"))`。 |

## 常见问题

**Q: 我可以将 Aspose.Tasks for Java 与其他 Java 库一起使用吗？**  
A: 可以，Aspose.Tasks for Java 可以无缝集成其他 Java 库，以增强您的项目管理能力。

**Q: 是否提供 Aspose.Tasks for Java 的试用版？**  
A: 可以，您可以从 [here](https://releases.aspose.com/) 下载免费试用版。

**Q: Aspose.Tasks for Java 更新频率如何？**  
A: Aspose.Tasks for Java 会定期更新，以确保与最新的 Java 版本和 Microsoft Project 文件兼容。

**Q: 我可以进一步自定义项目摘要信息吗？**  
A: 当然，Aspose.Tasks for Java 提供了丰富的选项，可根据您的具体需求自定义项目摘要信息。

**Q: 我可以在哪里获得 Aspose.Tasks for Java 的支持？**  
A: 您可以在 Aspose.Tasks 社区论坛 [here](https://forum.aspose.com/c/tasks/15) 获取支持。

---

**最后更新：** 2026-03-29  
**测试环境：** Aspose.Tasks for Java 24.11（撰写时的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}