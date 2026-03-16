---
date: 2026-03-16
description: 学习如何在 Aspose.Tasks for .NET 中实现页面保存回调，以实现对多页文档输出流的自定义处理。
linktitle: Implement page saving callback in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: 在 Aspose.Tasks 中实现页面保存回调
url: /zh/net/advanced-concepts/page-saving-callback/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中实现页面保存回调

## 介绍

在本教程中，您将学习如何在 Aspose.Tasks for .NET 中**实现页面保存回调**。此强大功能允许您将多页文档的每一页定向到您选择的流，从而完全控制输出的存储方式或后续处理。

## 快速答案
- **页面保存回调的作用是什么？** 它将每个渲染的页面捕获到单独的流中，以便您可以单独处理它们。  
- **我可以导出哪些格式？** 任意 `ImageSaveOptions` 支持的格式，例如 PNG、JPEG、PDF。  
- **我需要许可证吗？** 生产环境使用需要有效的 Aspose.Tasks 许可证。  
- **我可以在 .NET Core 中使用吗？** 可以，Aspose.Tasks 完全支持 .NET Core 以及 .NET 5/6+。  
- **回调是线程安全的吗？** 回调在执行渲染的同一线程上运行，因此遵循常规的线程安全规则。

## 什么是 **实现页面保存回调**？

**实现页面保存回调** 模式让您可以将自定义逻辑插入 Aspose.Tasks 的保存管道。与直接写入文件不同，您会为每一页收到一个 `Stream` 对象，从而可以将其存储在内存中、上传到云存储，或进行其他处理。

## 为什么使用回调将项目导出为 PNG？

将项目导出为 PNG 可为每个甘特图页面生成光栅图像，适用于报告、电子邮件或嵌入网页。使用回调意味着您可以将每页保存在单独的 `MemoryStream` 中，而无需在磁盘上创建临时文件。

## 前提条件

1. **C# 知识** – 对类、接口和流有基本了解。  
2. **Aspose.Tasks for .NET** – 从 [here](https://releases.aspose.com/tasks/net/) 下载并安装。  
3. **IDE** – Visual Studio、Rider 或任何兼容 .NET 的编辑器。

## 导入命名空间

要开始，请导入所需的命名空间：

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
```

## 步骤 1：创建 Project 对象

将现有的 MPP 文件加载到 `Project` 实例中：

```csharp
var project = new Project(DataDir + "Homemoveplan.mpp");
```

## 步骤 2：配置 Image Save Options

为 PNG 输出设置 `ImageSaveOptions` 并附加自定义回调：

```csharp
var imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
var callback = new CustomPageSavingCallback();
imageSaveOptions.PageSavingCallback = callback;
imageSaveOptions.RenderToSinglePage = false;
```

> **技巧提示：** 将 `RenderToSinglePage = false` 设置为确保每个甘特图页面单独渲染，这对于回调接收独立流至关重要。

## 步骤 3：使用回调保存项目

调用 `Save` 方法，传入 `Stream.Null`，因为实际的流由回调提供：

```csharp
project.Save(Stream.Null, imageSaveOptions);
```

## 步骤 4：处理已保存的页面流

保存操作完成后，回调持有一个 `MemoryStream` 对象集合——每页一个。现在您可以遍历它们：

```csharp
foreach (var stream in callback.PageStreams)
{
    // Process each page stream, e.g., upload to Azure Blob, write to a database, etc.
}
```

## 步骤 5：实现自定义页面保存回调

创建一个 sealed 类实现 `IPageSavingCallback`。该类捕获每页的流并将其存入列表以供后续使用。

```csharp
private sealed class CustomPageSavingCallback : IPageSavingCallback
{
    public List<MemoryStream> PageStreams { get; } = new List<MemoryStream>();

    public void PageSaving(PageSavingArgs args)
    {
        var memoryStream = new MemoryStream();
        args.Stream = memoryStream;
        args.KeepStreamOpen = false;
        PageStreams.Add(memoryStream);
    }

    public void OnFinish()
    {
        // Perform any cleanup or finalization
    }
}
```

## 常见问题与故障排除

| 问题 | 原因 | 解决方案 |
|-------|--------|----------|
| **未返回页面** | `RenderToSinglePage` 保持为 `true`。 | 将 `RenderToSinglePage = false` 设置为生成单独的页面。 |
| **流为空** | `KeepStreamOpen` 设置为 `true` 且未在后续处置。 | 保持为 `false`（默认），让回调自动关闭流。 |
| **内存不足错误** | 非常大的项目会生成许多高分辨率 PNG。 | 一次处理一个流或增加虚拟机内存限制。 |

## 常见问题解答

**Q1: 什么是 Aspose.Tasks 中的页面保存回调？**  
A: 页面保存回调允许您拦截多页文档的保存过程，为每一页提供自定义的 `Stream`。

**Q2: 我可以使用不同的格式通过此回调保存页面吗？**  
A: 可以。通过更改 `SaveFileFormat`，您可以导出为 PNG、JPEG、PDF、SVG 等格式。

**Q3: Aspose.Tasks 与 .NET Core 兼容吗？**  
A: 完全兼容。Aspose.Tasks 支持 .NET Core、.NET 5 和 .NET 6。

**Q4: 如何在页面保存过程中处理错误？**  
A: 将回调逻辑包装在 try/catch 块中并记录异常。`OnFinish` 方法是进行最终清理的好位置。

**Q5: 在哪里可以找到更多 Aspose.Tasks 的资源和支持？**  
A: 您可以访问 [Aspose.Tasks 论坛](https://forum.aspose.com/c/tasks/15) 获取帮助，查阅文档 [here](https://reference.aspose.com/tasks/net/)，或在 [Aspose.Tasks 网站](https://purchase.aspose.com/buy) 上了解更多功能和授权选项。

---

**最后更新：** 2026-03-16  
**测试环境：** Aspose.Tasks 24.12 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}