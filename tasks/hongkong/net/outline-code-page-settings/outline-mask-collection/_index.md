---
title: 使用 Aspose.Tasks 掌握 MS 專案大綱掩模
linktitle: Aspose.Tasks 中輪廓遮罩的集合
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 操作 MS Project 集合大綱遮罩。透過這個綜合教程提高工作效率。
weight: 15
url: /zh-hant/net/outline-code-page-settings/outline-mask-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 掌握 MS 專案大綱掩模

## 介紹
您是否希望使用 Aspose.Tasks for .NET 來利用 Microsoft Project 輪廓遮罩的強大功能？您來對地方了！在這個綜合教程中，我們將逐步引導您完成整個過程，確保您充分了解如何在專案中有效地操作輪廓遮罩。無論您是經驗豐富的開發人員還是剛入門，本指南都將為您提供優化工作流程所需的知識和技能。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
### 1.安裝Aspose.Tasks for .NET
確保您的開發環境中安裝了 Aspose.Tasks for .NET。您可以從 Aspose 網站下載該庫[這裡](https://releases.aspose.com/tasks/net/).
### 2. C#和.NET Framework基礎知識
熟悉 C# 程式語言和 .NET Framework，因為本教學將同時使用這兩種語言。
### 3.微軟專案文件
準備好 Microsoft Project 檔案 (MPP) 以用於測試目的。您可以使用現有文件或建立新文件進行實驗。
## 導入命名空間
首先，我們將必要的命名空間匯入到您的 C# 專案中。此步驟可確保您可以存取 Aspose.Tasks for .NET 提供的所需類別和功能。

在程式碼檔案的開頭新增以下命名空間：
```csharp
    using Aspose.Tasks;
    using System;
    
```
現在，讓我們將提供的範例分解為多個步驟並詳細解釋每個步驟：
## 第 1 步：初始化項目對象
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
在這裡，我們建立一個新的實例`Project`類別並載入名為「OutlineValues2010.mpp」的現有 Microsoft Project 檔案。
## 第 2 步：存取大綱程式碼
```csharp
var outline = project.OutlineCodes[0];
```
我們從專案中存取大綱程式碼。大綱程式碼是 Microsoft Project 中的自訂字段，可讓您對任務進行分類和組織。
## 第 3 步：清除輪廓蒙版
```csharp
if (outline.Masks.Count > 0)
{
    if (!outline.Masks.IsReadOnly)
    {
        outline.Masks.Clear();
    }
}
```
此步驟可確保在繼續操作之前清除任何現有的輪廓蒙版。
## 第 4 步：建立輪廓蒙版
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
var maskWrong = new OutlineMask();
maskWrong.Type = MaskType.Null;
outline.Masks.Add(mask);
```
我們建立新的輪廓蒙版並指定它們的類型。在此範例中，我們建立了一個有效的輪廓蒙版和一個錯誤的輪廓蒙版。
## 第 5 步：插入和編輯蒙版
```csharp
outline.Masks.Insert(0, maskWrong);
var idx = outline.Masks.IndexOf(mask);
outline.Masks[idx].Length = 2;
```
在這裡，我們將錯誤的遮罩插入集合中，並使用其索引編輯遮罩的長度。
## 第六步：摘下面具
```csharp
var idxOfWrong = outline.Masks.IndexOf(maskWrong);
outline.Masks.RemoveAt(idxOfWrong);
```
我們根據索引從集合中刪除錯誤的遮罩。
## 第 7 步：迭代掩模
```csharp
foreach (var outlineMask in outline.Masks)
{
    Console.WriteLine("Length: " + outlineMask.Length);
    Console.WriteLine("Level: " + outlineMask.Level);
    Console.WriteLine("Separator: " + outlineMask.Separator);
    Console.WriteLine("Type: " + outlineMask.Type);
}
```
此循環迭代集合中的每個輪廓蒙版，並列印出其屬性，例如長度、等級、分隔符號和類型。
## 第 8 步：將蒙版複製到另一個項目
```csharp
var otherProject = new Project(DataDir + "OutlineValues2010.mpp");
var otherOutline = otherProject.OutlineCodes[0];
var masks = new OutlineMask[outline.Masks.Count];
outline.Masks.CopyTo(masks, 0);
foreach (var maskToAdd in masks)
{
    if (!otherOutline.Masks.Contains(maskToAdd))
    {
        otherOutline.Masks.Add(maskToAdd);
    }
}
```
最後，我們將輪廓蒙版從一個項目複製到另一個項目，確保不同項目之間的一致性。
## 結論
恭喜！您已經成功學習如何使用 Aspose.Tasks for .NET 操作 MS Project 集合大綱遮罩。透過學習本教程，您現在已經具備了有效管理專案中的輪廓蒙版的技能，最終提高了您的工作效率和工作流程。
## 常見問題解答
### Q1：我可以將 Aspose.Tasks for .NET 與不同版本的 Microsoft Project 檔案一起使用嗎？
答：是的，Aspose.Tasks for .NET 支援各種版本的 Microsoft Project 文件，包括 MPP、MPT 和 XML 格式。
### Q2：Aspose.Tasks for .NET 與 .NET Core 相容嗎？
答：是的，Aspose.Tasks for .NET 與 .NET Core 相容，讓您在跨平台應用程式中使用它。
### Q3：我可以根據專案需求自訂輪廓蒙版的屬性嗎？
答：當然！您可以透過調整輪廓蒙版的長度、等級、分隔符號和類型來自訂輪廓蒙版，以滿足您的特定專案需求。
### Q4：Aspose.Tasks for .NET 是否提供文件和支援？
答：是的，Aspose.Tasks for .NET 透過其網站和[論壇](https://forum.aspose.com/c/tasks/15).
### Q5：Aspose.Tasks for .NET 有免費試用版嗎？
答：是的，您可以從他們的網站訪問 Aspose.Tasks for .NET 的免費試用版[網站](https://releases.aspose.com/tasks/net/)。在購買之前探索其特性和功能。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
