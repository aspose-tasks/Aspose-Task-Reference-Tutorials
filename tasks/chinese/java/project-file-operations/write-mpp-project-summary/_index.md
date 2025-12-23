---
date: 2025-12-23
description: 学习如何使用 Aspose.Tasks for Java 创建 MPP 汇总并更新项目作者。轻松设置和检索项目信息。
linktitle: Write MPP Project Summary in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks 创建 MPP 摘要并更新项目作者
url: /zh/java/project-file-operations/write-mpp-project-summary/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 编写 MPP 项目摘要

## 介绍
在本教程中，您将**create MPP summary**信息用于 Microsoft Project 文件，并学习如何使用 Aspose.Tasks for Java 库**update project author**详情。无论是构建项目管理工具还是自动化报告，程序化控制摘要属性都能节省时间并确保项目之间的一致性。

## 快速答案
- **What does “create MPP summary” mean?** 它指的是设置 Microsoft Project 中“项目摘要信息”对话框中显示的高级项目属性（作者、修订版、关键字等）。  
- **Which library handles this?** Aspose.Tasks for Java 提供了流式 API 来读取和写入这些属性。  
- **Do I need a license?** 提供免费试用版，但在生产环境中需要商业许可证。  
- **Can I also change the author after the file is saved?** 是的——您可以通过调用 `project.set(Prj.AUTHOR, "New Author")` 来**update project author**，然后重新保存文件。  
- **What file formats are supported?** 完全支持 MPP 和 XML（SaveFileFormat.Xml）两种文件格式。

## 什么是 create MPP summary？
创建 MPP 摘要涉及填充项目的元数据——作者、修订号、关键字、注释、创建日期和打印日期。这些元数据存储在 Project Summary Information 记录中，并显示在 Microsoft Project 的 **File → Info** 部分。

## 为什么要更新 project author？
保持 **project author** 信息的准确性对于审计追踪、协作和报告至关重要。当多个团队成员参与时，您可能需要**update project author**以反映最新更改或正确归属工作。

## 前提条件
1. 在机器上安装 Java Development Kit (JDK)。  
2. Aspose.Tasks for Java – 从 [here](https://releases.aspose.com/tasks/java/) 下载。  
3. 使用 IntelliJ IDEA、Eclipse 或 NetBeans 等 IDE。

## 导入包
首先，将必要的包导入到您的 Java 类中：
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.util.Calendar;
```

## 步骤 1：设置项目并定义摘要信息
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Initialize a new Project object with the path to your project file
Project project = new Project(dataDir + "project.mpp");
// Set summary information about the project
project.set(Prj.AUTHOR, "Author");
project.set(Prj.LAST_AUTHOR, "Last Author");
project.set(Prj.REVISION, 15);
project.set(Prj.KEYWORDS, "MSP Aspose");
project.set(Prj.COMMENTS, "Comments");
// Set creation date of the project
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.CREATION_DATE, cal.getTime());
// Set keywords for the project
project.set(Prj.KEYWORDS, "MPP Aspose");
// Set last printed date of the project
cal.set(2014, Calendar.MARCH, 16, 0, 0, 0);
project.set(Prj.LAST_PRINTED, cal.getTime());
```
在上述代码中，我们**create MPP summary**了作者、修订版和关键字等字段。您也可以稍后通过调用 `project.set(Prj.AUTHOR, "New Name")` 来**update project author**。

## 步骤 2：保存项目摘要信息
```java
// Save the Project back in MPP format
project.save(dataDir + "MppAspose.xml", SaveFileFormat.Xml);
// Display a success message
System.out.println("Process completed Successfully");
```
保存项目会持久化您刚才定义的所有摘要数据。

## 步骤 3：读取项目摘要信息
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
// Print keywords of the project (again)
System.out.println("Keywords: " + project.get(Prj.KEYWORDS));
// Print last printed date of the project
System.out.println("Last Printed: " + project.get(Prj.LAST_PRINTED).toString());
```
此代码片段演示了如何**read back**摘要信息，以确认**create MPP summary**操作已成功。

## 常见问题及解决方案
- **Null values after reading:** 确保在重新加载之前项目已成功保存。检查文件路径和权限。  
- **Date formatting differences:** `project.get(Prj.CREATION_DATE)` 返回 `java.util.Date`。如果需要自定义显示格式，请使用 `SimpleDateFormat`。  
- **License not set:** 未设置有效许可证时，Aspose.Tasks 以评估模式运行，可能会嵌入水印。请在代码中尽早注册许可证。

## 常见问答
**Q: 我可以将 Aspose.Tasks for Java 与其他 Java 库一起使用吗？**  
A: 可以，Aspose.Tasks for Java 可以无缝集成到其他 Java 库中，以增强您的项目管理能力。

**Q: 是否提供 Aspose.Tasks for Java 的试用版？**  
A: 是的，您可以从 [here](https://releases.aspose.com/) 下载免费试用版。

**Q: Aspose.Tasks for Java 更新频率如何？**  
A: Aspose.Tasks for Java 会定期更新，以确保与最新版本的 Java 和 Microsoft Project 文件兼容。

**Q: 我可以进一步自定义项目摘要信息吗？**  
A: 当然，Aspose.Tasks for Java 提供了丰富的选项，您可以根据具体需求自定义项目摘要信息。

**Q: 我在哪里可以获得 Aspose.Tasks for Java 的支持？**  
A: 您可以在 Aspose.Tasks 社区论坛 [here](https://forum.aspose.com/c/tasks/15) 获取支持。

## 结论
在本教程中，我们演示了如何使用 Aspose.Tasks for Java **create MPP summary** 数据、**update project author**，并验证这些更改。通过自动化这些步骤，您可以全面控制项目元数据，使应用程序更健壮，项目报告更准确。

---

**Last Updated:** 2025-12-23  
**Tested With:** Aspose.Tasks for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}