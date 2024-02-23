---
title: 使用 Aspose.Tasks 掌握 MS 專案大綱值
linktitle: 在Aspose.Tasks中管理大綱值
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 高效管理 MS Project 大綱值。輕鬆客製化專案大綱。
type: docs
weight: 16
url: /zh-hant/net/outline-code-page-settings/outline-values/
---
## 介紹
在本教學中，我們將探索如何使用 .NET 的 Aspose.Tasks 函式庫管理 Microsoft Project 大綱值。使用Aspose.Tasks，您可以輕鬆操作大綱程式碼，建立新的大綱值，並根據您的要求自訂專案大綱。
## 先決條件
在開始之前，請確保您具備以下條件：
1. 安裝 Aspose.Tasks for .NET：從下列位置下載並安裝 Aspose.Tasks for .NET 函式庫[這裡](https://releases.aspose.com/tasks/net/).
2. 開發環境：確保您設定了具有 .NET 框架相容性的開發環境，例如 Visual Studio。
3. 對 C# 程式設計的基本了解：熟悉 C# 程式語言基礎知識，因為我們將使用 C# 來處理 Aspose.Tasks 函式庫。

## 導入命名空間
首先將必要的命名空間匯入到您的 C# 程式碼：
```csharp
    using Aspose.Tasks;
    using System;
    
```
## 第 1 步：載入專案文件
```csharp
//文檔目錄的路徑。
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
此步驟初始化一個新的 Project 物件並從指定目錄載入 Microsoft Project 檔案。
## 第 2 步：定義大綱程式碼定義
```csharp
var outline = new OutlineCodeDefinition();
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.Alias = "My Outline Code";
var outline2 = new OutlineCodeDefinition();
outline2.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline2.Alias = "My Outline Code 2";
project.OutlineCodes.Add(outline);
```
在這裡，我們定義了兩個 OutlineCodeDefinition 物件並將它們新增至專案的 OutlineCodes 集合中。
## 第 3 步：定義輪廓蒙版
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
此步驟為大綱程式碼定義設定 OutlineMask。
## 第 4 步：建立輪廓值
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
value.IsCollapsed = false;
outline.Values.Add(value);
var value2 = new OutlineValue();
value2.DurationValue = project.GetDuration(1, TimeUnitType.Hour);
value2.ValueId = 2;
outline2.Values.Add(value2);
```
在此步驟中，我們建立兩個 OutlineValue 物件並設定它們的屬性，例如值、值 ID、類型、描述和折疊狀態。

## 結論
透過提供的功能，使用 Aspose.Tasks for .NET 管理 MS Project 大綱值非常簡單。透過遵循本教學中概述的步驟，您可以有效地操作大綱程式碼和值，以根據您的需求自訂專案大綱。
## 常見問題解答
### Q：我可以將 Aspose.Tasks 與其他 .NET 框架一起使用嗎？
答：是的，Aspose.Tasks 與各種.NET 框架相容，確保您的開發環境的靈活性。
### Q：Aspose.Tasks 有試用版嗎？
答：是的，您可以從以下位置存取 Aspose.Tasks 的免費試用版：[這裡](https://releases.aspose.com/).
### Q：如何獲得 Aspose.Tasks 的支援？
答：如需支援和協助，您可以造訪 Aspose.Tasks 論壇。[這裡](https://forum.aspose.com/c/tasks/15).
### Q：我可以購買 Aspose.Tasks 的臨時授權嗎？
答：是的，您可以從以下位置購買 Aspose.Tasks 的臨時許可證：[這裡](https://purchase.aspose.com/temporary-license/).
### Q：在哪裡可以找到 Aspose.Tasks 的詳細文件？
答：您可以參考可用的綜合文檔[這裡](https://reference.aspose.com/tasks/net/).