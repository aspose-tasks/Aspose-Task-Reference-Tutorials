---
title: Aspose.Tasks .NET 中大綱程式碼定義的集合
linktitle: Aspose.Tasks 中大綱程式碼定義的集合
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 操作 Microsoft Project 文件中的大綱程式碼定義。輕鬆將項目資料分類。
weight: 13
url: /zh-hant/net/outline-code-page-settings/outline-code-definition-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks .NET 中大綱程式碼定義的集合

## 介紹
Aspose.Tasks 是一個功能強大的.NET 程式庫，旨在輕鬆有效率地操作 Microsoft Project 文件。其主要功能之一是能夠使用大綱程式碼定義，允許使用者有效地組織和分類項目資料。在本教程中，我們將探索如何使用 Aspose.Tasks for .NET 處理大綱程式碼定義。
## 先決條件
在我們深入學習本教學之前，請確保您具備以下條件：
1. 對 C# 的基本了解：熟悉 C# 程式語言將會很有幫助。
2. Visual Studio：安裝 Visual Studio 或任何其他首選的 C# 開發環境。
3.  Aspose.Tasks for .NET：下載並安裝 Aspose.Tasks for .NET 函式庫[這裡](https://releases.aspose.com/tasks/net/).

## 導入命名空間
首先，請確保導入必要的命名空間：
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## 第 1 步：載入 Microsoft Project 文檔
首先，載入 Microsoft Project 文件以開始使用大綱程式碼定義：
```csharp
//文檔目錄的路徑。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes.mpp");
```
## 第 2 步：存取大綱程式碼定義
現在，讓我們存取專案中的大綱程式碼定義：
```csharp
Console.WriteLine("Count of outline code definitions: " + project.OutlineCodes.Count);
foreach (var outlineCode in project.OutlineCodes)
{
	Console.WriteLine("Field Name: " + outlineCode.FieldName);
	Console.WriteLine("Alias: " + outlineCode.Alias);
	Console.WriteLine();
}
```
## 步驟 3：新增自訂大綱程式碼定義
您可以新增自訂大綱程式碼定義，如下所示：
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
if (!project.OutlineCodes.IsReadOnly)
{
    project.OutlineCodes.Add(outlineCodeDefinition);
}
```
## 步驟 4：修改大綱程式碼定義
輕鬆修改現有大綱程式碼定義：
```csharp
var index = project.OutlineCodes.IndexOf(outlineCodeDefinition);
project.OutlineCodes[index].Alias = "New Alias";
```
## 步驟 5：刪除大綱程式碼定義
不再需要時刪除大綱程式碼定義：
```csharp
if (project.OutlineCodes.Contains(outlineCodeDefinition))
{
    project.OutlineCodes.Remove(outlineCodeDefinition);
}
```
## 第 6 步：儲存更改
最後，儲存專案文件的變更：
```csharp
project.Save(DataDir + "ModifiedOutlineCodes.mpp", SaveFileFormat.MPP);
```

## 結論
總之，Aspose.Tasks for .NET 提供了管理 Microsoft Project 文件中大綱程式碼定義的全面功能。透過遵循本教學中概述的步驟，您可以有效地操作大綱程式碼定義，以有效地組織和分類項目資料。
## 常見問題解答
### Q：我可以在一個專案中新增多個大綱程式碼定義嗎？
答：是的，您可以根據需要在專案中新增多個大綱程式碼定義。只需使用`Add`您想要包含的每個定義的方法。
### Q：是否可以一次從專案中刪除所有大綱程式碼定義？
答：是的，您可以使用以下命令清除專案中的所有大綱程式碼定義：`Clear`方法。
### Q：如果我嘗試修改只讀大綱程式碼定義，會發生什麼事？
答：如果大綱程式碼定義是唯讀的，您將無法直接修改它。在嘗試任何修改之前，您需要檢查其唯讀狀態。
### Q：我可以新增到專案中的大綱程式碼定義數量有限制嗎？
答：Aspose.Tasks for .NET 不會對您可以新增至專案中的大綱程式碼定義的數量施加任何特定限制。但是，在使用大量定義時，請考慮效能影響。
### Q：我可以使用大綱程式碼定義根據自訂標準對任務進行分組嗎？
答：是的，大綱程式碼定義可讓您根據自訂標準對任務進行分類，從而提供組織專案資料的靈活性。## 完整原始程式碼
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
