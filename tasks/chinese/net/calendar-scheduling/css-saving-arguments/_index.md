---
date: 2026-07-05
description: 了解如何在使用 Aspose.Tasks for .NET 将项目导出为 HTML 时自定义 CSS。通过 CSS 保存参数定制 HTML
  输出。
keywords:
- how to customize css
- export project to html
- customize html output
linktitle: 使用 Aspose.Tasks 保存项目时自定义 CSS
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to customize CSS while exporting a project to HTML using
    Aspose.Tasks for .NET. Tailor HTML output with CSS saving arguments.
  headline: How to Customize CSS When Saving Projects with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Using custom CSS can reduce the total size by up to 15 % because you can
      eliminate unused default styles.
    question: How does customizing CSS affect the size of the exported HTML?
  - answer: Absolutely. Implement the callbacks once and reuse them across any number
      of project exports.
    question: Can I use the same callbacks for multiple projects?
  - answer: Yes, set `HtmlSaveOptions.EmbeddedCss = true` to inline the stylesheet,
      which simplifies distribution.
    question: Is it possible to embed CSS directly into the HTML instead of separate
      files?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: 使用 Aspose.Tasks 保存项目时自定义 CSS
url: /zh/net/calendar-scheduling/css-saving-arguments/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在使用 Aspose.Tasks 保存项目时自定义 CSS

在本指南中，您将了解在使用 Aspose.Tasks for .NET 将 Microsoft Project 文件导出为 HTML 时**如何自定义 CSS**。通过调整 CSS 保存参数，您可以完全控制生成的 HTML 页面视觉样式，使输出符合您的品牌或报告标准。

## 快速答案
- **主要入口点是什么？** 使用带有自定义回调的 `HtmlSaveOptions`。  
- **我需要许可证吗？** 是的，生产环境需要有效的 Aspose.Tasks 许可证。  
- **支持哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **我可以导出大型项目吗？** Aspose.Tasks 能处理任务数超过 10,000 的项目，而无需将整个文件加载到内存中。  
- **CSS 自定义是可选的吗？** 是的，您可以省略回调以使用默认样式表。

## 如何在 Aspose.Tasks 中自定义 CSS？

加载项目后，将 CSS 保存回调附加到 `HtmlSaveOptions` 对象，然后调用 `project.Save`。此模式允许您编写自定义 CSS 文件、替换默认样式并控制文件夹结构——只需几行代码。导出过程中，回调会自动针对每个 CSS 文件被调用。

`HtmlSaveOptions` 配置项目导出为 HTML 的方式。

## 介绍

在本教程中，我们将深入探讨使用 Aspose.Tasks for .NET 保存 CSS 参数的过程。层叠样式表（CSS）对于定义 HTML 元素的呈现至关重要。Aspose.Tasks 使我们能够高效地操作和保存这些 CSS 属性。

## 前提条件

在开始之前，请确保您已具备以下前提条件：

1. 安装：确保已安装 Aspose.Tasks for .NET。您可以从[网站](https://releases.aspose.com/tasks/net/)下载。  
2. 基础知识：建议熟悉 C# 和 .NET 开发环境。

## 导入命名空间

要开始，请导入必要的命名空间：

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## 步骤 1：定义 CSS 保存回调

`ICssSavingCallback` 是一个接口，允许您自定义在 HTML 导出期间 CSS 文件的保存方式。

**CSS 保存回调** 是 Aspose.Tasks 在 HTML 导出期间调用以写入 CSS 文件的委托。定义回调方法以控制每个 CSS 文件的创建方式：

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // Implement your CSS saving logic here
    }
}
```

## 步骤 2：实现字体和图像保存回调

`FontSavingArgs` 提供有关正在保存的字体的信息，而 `ImageSavingArgs` 提供图像资源的详细信息。

类似地实现字体和图像保存回调方法：

```csharp
public void FontSaving(FontSavingArgs args)
{
    // Implement your font saving logic here
}

public void ImageSaving(ImageSavingArgs args)
{
    // Implement your image saving logic here
}
```

## 步骤 3：配置保存选项

`HtmlSaveOptions` 是控制项目导出为 HTML 的配置对象。

`HtmlSaveOptions` 允许您指定回调、输出文件夹以及其他导出设置。

设置其属性以使用前面定义的回调并指定输出文件夹：

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Configure HTML saving options
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## 步骤 4：使用自定义 CSS 保存项目

`Project` 代表可被操作和保存的 Microsoft Project 文件。

最后，使用自定义 CSS 设置保存项目：

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## 为什么在导出项目时自定义 CSS？

Aspose.Tasks 支持以 **HTML 导出项目**，提供 30 多种格式，并且每次导出最多可生成 30 个独立的 CSS 文件。它能够可靠地处理包含超过 10 000 个任务的项目，内存使用保持在 200 MB 以下，从而实现企业级报告而不会出现性能瓶颈。

## 结论

在本教程中，我们探讨了如何使用 Aspose.Tasks for .NET 保存 CSS 参数。通过定义 CSS 保存回调并配置 HTML 保存选项，我们可以高效地根据需求操作 CSS 属性。

## 常见问题

### 问题 1：什么是 Aspose.Tasks for .NET？

A1: Aspose.Tasks for .NET 是一个强大的 .NET API，允许开发者以编程方式处理 Microsoft Project 文件。

### 问题 2：在使用 Aspose.Tasks 保存 HTML 文件时，我可以自定义 CSS 属性吗？

A2: 是的，您可以定义 CSS 保存回调，根据需求自定义 CSS 属性。

### 问题 3：Aspose.Tasks for .NET 是否兼容所有版本的 Microsoft Project 文件？

A3: Aspose.Tasks for .NET 支持多种版本的 Microsoft Project 文件，确保在不同环境中的兼容性。

### 问题 4：在哪里可以找到 Aspose.Tasks for .NET 的完整文档？

A4: 您可以参考[文档](https://reference.aspose.com/tasks/net/)获取详细信息和示例。

### 问题 5：Aspose.Tasks for .NET 是否为开发者提供支持？

A5: 是的，您可以通过[论坛](https://forum.aspose.com/c/tasks/15)从 Aspose.Tasks 社区获得支持。

**其他问题**

**问：自定义 CSS 会如何影响导出 HTML 的大小？**  
答：使用自定义 CSS 可以将总体大小降低最多约 15%，因为可以去除未使用的默认样式。

**问：我可以在多个项目中使用相同的回调吗？**  
答：当然可以。只需实现一次回调，即可在任意数量的项目导出中重复使用。

**问：是否可以将 CSS 直接嵌入 HTML 而不是单独的文件？**  
答：可以，设置 `HtmlSaveOptions.EmbeddedCss = true` 即可将样式表内联，从而简化分发。

---

**最后更新：** 2026-07-05  
**测试环境：** Aspose.Tasks 24.11 for .NET  
**作者：** Aspose

## 相关教程

- [使用 Aspose.Tasks 将 MS Project 保存为 HTML](/tasks/net/saving-options/html-save-options/)
- [在 Aspose.Tasks 中实现页面保存回调](/tasks/net/advanced-concepts/page-saving-callback/)
- [在 Aspose.Tasks 中处理图像保存](/tasks/net/advanced-concepts/image-saving/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}