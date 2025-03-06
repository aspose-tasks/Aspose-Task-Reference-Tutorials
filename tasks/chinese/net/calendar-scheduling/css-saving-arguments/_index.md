---
title: Aspose.Tasks 中的 CSS 保存参数
linktitle: Aspose.Tasks 中的 CSS 保存参数
second_title: Aspose.Tasks .NET API
description: 了解如何在 Aspose.Tasks for .NET 中保存 CSS 参数以自定义 HTML 输出。通过定制 CSS 设置增强演示效果。
weight: 20
url: /zh/net/calendar-scheduling/css-saving-arguments/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中的 CSS 保存参数

## 介绍

在本教程中，我们将深入研究使用 Aspose.Tasks for .NET 保存 CSS 参数的过程。层叠样式表 (CSS) 对于定义 HTML 元素的表示至关重要。 Aspose.Tasks允许我们有效地操作和保存这些CSS属性。

## 先决条件

在我们开始之前，请确保您具备以下先决条件：

1. 安装：确保您已经安装了 Aspose.Tasks for .NET。您可以从[网站](https://releases.aspose.com/tasks/net/).

2. 基础知识：建议熟悉C#和.NET开发环境。

## 导入命名空间

首先，导入必要的命名空间：

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```
## 第 1 步：定义 CSS 保存回调

首先，我们定义 CSS 保存回调方法来处理 CSS 文件的保存：

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        //在这里实现你的 CSS 保存逻辑
    }
}
```

## 第 2 步：实现字体和图像保存回调

接下来同样实现字体和图片保存回调方法：

```csharp
public void FontSaving(FontSavingArgs args)
{
    //在这里实现你的字体保存逻辑
}

public void ImageSaving(ImageSavingArgs args)
{
    //在这里实现您的图像保存逻辑
}
```

## 步骤 3：配置保存选项

现在，配置 HTML 保存选项以利用已实现的回调：

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        //配置 HTML 保存选项
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## 第 4 步：使用自定义 CSS 保存项目

最后，使用自定义的 CSS 设置保存您的项目：

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## 结论

在本教程中，我们探讨了如何使用 Aspose.Tasks for .NET 保存 CSS 参数。通过定义CSS保存回调和配置HTML保存选项，我们可以根据我们的要求有效地操作CSS属性。

## 常见问题解答

### Q1：什么是 Aspose.Tasks for .NET？

A1：Aspose.Tasks for .NET 是一个功能强大的 .NET API，使开发人员能够以编程方式使用 Microsoft Project 文件。

### Q2：使用Aspose.Tasks保存HTML文件时可以自定义CSS属性吗？

A2：是的，您可以根据需要定义 CSS 保存回调来自定义 CSS 属性。

### Q3：Aspose.Tasks for .NET 是否与所有版本的 Microsoft Project 文件兼容？

A3：Aspose.Tasks for .NET支持各种版本的Microsoft Project文件，确保不同环境下的兼容性。

### 问题 4：在哪里可以找到 Aspose.Tasks for .NET 的综合文档？

A4：您可以参考[文档](https://reference.aspose.com/tasks/net/)获取详细信息和示例。

### Q5：Aspose.Tasks for .NET 是否为开发人员提供支持？

 A5：是的，您可以通过 Aspose.Tasks 社区获得支持[论坛](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
