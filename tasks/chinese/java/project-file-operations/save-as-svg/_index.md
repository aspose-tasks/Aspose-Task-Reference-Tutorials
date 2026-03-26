---
date: 2025-12-21
description: 学习如何在 Java 中使用 Aspose.Tasks 库从 MPP 文件创建 SVG 并将项目保存为 SVG。一步一步的指南，附有代码示例。
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何在 Java 中使用 Aspose.Tasks 从 MPP 创建 SVG
url: /zh/java/project-file-operations/save-as-svg/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中从 MPP 创建 SVG

## 介绍
在本教程中，您将学习如何使用 **Aspose.Tasks for Java** **从 MPP 文件创建 SVG**。将 Microsoft Project（MPP）文件转换为可伸缩矢量图形（SVG），可以将高质量、分辨率无关的图表直接嵌入网页、报告或仪表板。我们将逐步演示所需的设置，展示完整代码，并解释每一步，让您能够自信地在自己的应用程序中 **将项目保存为 SVG**。

## 快速回答
- **“从 MPP 创建 SVG”是什么意思？**  
  它将 Microsoft Project 文件（.mpp）转换为 SVG 图像，可在任何浏览器中无损显示。  
- **哪个库负责转换？**  
  Aspose.Tasks for Java 提供一行 `save` 方法即可完成转换。  
- **我需要许可证吗？**  
  商业使用需要临时许可证；提供免费试用。  
- **前置条件是什么？**  
  Java JDK 8+ 和 Aspose.Tasks for Java JAR。  
- **转换需要多长时间？**  
  对于标准项目文件，通常不到一秒。

## 什么是 “从 MPP 创建 SVG”？
从 MPP 文件创建 SVG 意味着将项目进度的可视化表示——任务、时间线和资源——导出为可伸缩矢量图形格式。SVG 基于 XML，轻量且在高分辨率显示器上能够完美缩放。

## 为什么使用 Aspose.Tasks 将项目保存为 SVG？
- **无需安装 Microsoft Project** —— 库可独立工作。  
- **完整保真度** —— 图表、甘特条和里程碑保持原有样式。  
- **跨平台** —— 可在 Windows、Linux 或 macOS 上运行。  
- **易于集成** —— 一行 API 调用自然融入现有 Java 流程。

## 前置条件
- **Java Development Kit (JDK)** —— 版本 8 或更高。请从 Oracle 官网下载。  
- **Aspose.Tasks for Java** —— 从官方下载页面 **[here](https://releases.aspose.com/tasks/java/)** 获取库。  

## 导入包
首先，导入所需的类。导入块保持不变。

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## 步骤 1：定义数据目录
指定源 MPP 文件所在位置以及 SVG 将写入的目录。

```java
String dataDir = "Your Data Directory";
```

> **小技巧：** 使用绝对路径或相对于项目资源文件夹的路径，以避免 `FileNotFoundException`。

## 步骤 2：加载 MPP 文件
通过加载已有的 Microsoft Project 文件来创建 `Project` 实例。

```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

此行代码从前面定义的文件夹读取 *HomeMovePlan.mpp*。

## 步骤 3：将项目保存为 SVG
现在，您可以使用一条命令 **将项目保存为 SVG**。

```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```

该方法将 `project5.svg` 写入同一目录。生成的 SVG 可在任何现代浏览器中打开，或直接嵌入 HTML。

## 常见问题及解决方案
| 问题 | 原因 | 解决方案 |
|------|------|----------|
| **文件未找到** | `dataDir` 路径不正确 | 确认目录字符串以分隔符（`/` 或 `\\`）结尾。 |
| **SVG 输出为空白** | 项目加载时未包含视图 | 确保 MPP 文件中包含甘特图视图后再保存。 |
| **许可证异常** | 未应用有效许可证 | 在调用 `save` 前使用 `License.setLicense("path/to/license.xml")` 应用临时许可证。 |

## 常见问答

**Q: Aspose.Tasks for Java 是否兼容所有版本的 Microsoft Project 文件？**  
A: 是的，支持从旧版到最新版本的 MPP、MPT 和 XML 格式。

**Q: 我可以自定义 SVG 输出的外观吗？**  
A: 完全可以。使用 `SvgOptions` 在调用 `save` 前设置字体、颜色和布局选项。

**Q: Aspose.Tasks for Java 商业使用是否需要许可证？**  
A: 需要。生产环境必须使用有效许可证。您可以在 **[here](https://purchase.aspose.com/temporary-license/)** 获取临时许可证。

**Q: 我可以在购买前试用 Aspose.Tasks for Java 吗？**  
A: 可以，免费试用请访问 **[here](https://purchase.aspose.com/buy)**。

**Q: 哪里可以获得 Aspose.Tasks for Java 的支持？**  
A: 请前往社区论坛 **[here](https://forum.aspose.com/c/tasks/15)** 提问并分享反馈。

## 结论
现在您已经掌握了在 Java 中使用 Aspose.Tasks **从 MPP 创建 SVG** 并高效 **将项目保存为 SVG** 的方法。此功能让您能够将丰富的项目可视化集成到 Web 门户、报表仪表板或任何需要可伸缩图形的场景中。尝试使用 `SvgOptions` 微调输出，您将拥有一把强大的开发利器。

---

**最后更新：** 2025-12-21  
**测试环境：** Aspose.Tasks for Java 24.10  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}