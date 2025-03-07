---
title: MS Project Outline 程式碼處理 Aspose.Tasks 中的定義
linktitle: 在 Aspose.Tasks 中處理大綱程式碼定義
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 處理 MS Project 大綱程式碼定義，從而增強您的專案管理應用程式的能力。
weight: 12
url: /zh-hant/net/outline-code-page-settings/outline-code-definitions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project Outline 程式碼處理 Aspose.Tasks 中的定義

## 介紹
Microsoft Project 是管理專案的強大工具，Aspose.Tasks for .NET 為以程式設計方式操作專案檔案提供全面支援。專案管理的一個重要面向是使用大綱程式碼組織任務。在本教程中，我們將探討如何使用 Aspose.Tasks for .NET 處理 MS Project 大綱程式碼定義。
## 先決條件
在我們深入實施之前，請確保您符合以下先決條件：
### 1.安裝Aspose.Tasks for .NET
確保您已在開發環境中安裝 Aspose.Tasks for .NET。您可以從以下位置下載：[這裡](https://releases.aspose.com/tasks/net/).
### 2. 對 C# 和 .NET Framework 的基本了解
請熟悉 C# 程式語言和 .NET 框架，因為本教學需要中級 C# 知識。
### 3.整合開發環境（IDE）
在系統上安裝 Visual Studio 等 IDE，用於編碼和偵錯。
## 導入命名空間
在開始編碼之前，讓我們導入必要的命名空間以使用 Aspose.Tasks for .NET。
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
現在，讓我們將提供的範例分解為多個步驟，以便清楚地理解。
## 第 1 步：載入專案文件
首先，我們需要將 MS Project 檔案載入到我們的應用程式中。
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## 第 2 步：建立大綱程式碼定義
現在，讓我們建立一個新的大綱程式碼定義。
```csharp
var outline = new OutlineCodeDefinition();
```
## 第3步：設定欄位編號和名稱
設定大綱代碼的欄位編號和名稱。
```csharp
outline.FieldId = ExtendedAttributeTask.OutlineCode7.ToString("D");
outline.FieldName = "Outline Code1";
```
## 步驟 4：設定 GUID 和其他屬性
設定大綱程式碼的 GUID 和其他屬性。
```csharp
outline.Guid = "e6afac06-0d86-4359-a96c-db705e3d2ca8";
outline.LeafOnly = false;
outline.Alias = "My Outline Code";
outline.PhoneticAlias = "Outline Code";
outline.AllLevelsRequired = true;
outline.Enterprise = false;
outline.EnterpriseOutlineCodeAlias = 0;
```
## 第5步：新增輪廓蒙版
將輪廓蒙版加入輪廓程式碼。
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
outline.Masks.Add(mask);
```
## 第6步：設定其他屬性
設定大綱程式碼的附加屬性。
```csharp
outline.OnlyTableValuesAllowed = false;
outline.ResourceSubstitutionEnabled = false;
outline.ShowIndent = false;
```
## 第7步：新增輪廓值
最後，讓我們在大綱程式碼中加入一個大綱值。
```csharp
var value = new OutlineValue();
value.Value = "Text value 1";
value.ValueId = 1;
value.Type = OutlineValueType.Text;
value.Description = "Text value descr 1";
outline.Values.Add(value);
```
## 結論
在本教程中，我們學習如何使用 Aspose.Tasks for .NET 處理 MS Project 大綱程式碼定義。透過遵循逐步指南，您可以以程式設計方式有效地操作專案文件中的大綱程式碼。
## 常見問題解答
### Q1：我可以將 Aspose.Tasks for .NET 與不同版本的 MS Project 檔案一起使用嗎？
答：是的，Aspose.Tasks for .NET 支援各種版本的 MS Project 文件，包括 MPP 和 XML 格式。
### Q2：Aspose.Tasks for .NET 與 .NET Core 相容嗎？
答：是的，Aspose.Tasks for .NET 與 .NET Core 相容，讓您可以開發跨平台應用程式。
### Q3：我可以使用 Aspose.Tasks for .NET 操作資源分配嗎？
答：是的，Aspose.Tasks for .NET 提供了豐富的功能來操作資源分配，包括新增、更新和刪除分配。
### Q4：Aspose.Tasks for .NET 支援從 MS Project 檔案讀取自訂欄位嗎？
答：當然，Aspose.Tasks for .NET 支援從 MS Project 檔案讀取和寫入自訂字段，包括大綱程式碼。
### Q5：Aspose.Tasks for .NET 有社群論壇嗎？
答：是的，您可以加入 Aspose.Tasks for .NET 社群論壇[這裡](https://forum.aspose.com/c/tasks/15)提出問題、分享知識並與其他開發人員合作。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
