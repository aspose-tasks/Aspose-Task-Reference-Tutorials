---
title: 在 Aspose.Tasks 中定義 WBS 代碼定義
linktitle: 在 Aspose.Tasks 中定義 WBS 代碼定義
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET 能夠實現高效率的專案管理。透過我們的綜合教學輕鬆掌握 WBS 程式碼。立即簡化工作流程！
weight: 13
url: /zh-hant/net/view-wbs-code-configuration/wbs-code-definitions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中定義 WBS 代碼定義

## 介紹
隨著專案管理的發展，對簡化流程的強大工具的需求也不斷增長。在 .NET 開發領域，Aspose.Tasks 作為處理專案管理任務的強大函式庫脫穎而出。在本教程中，我們將深入研究使用 Aspose.Tasks for .NET 定義工作分解結構 (WBS) 程式碼的過程。 WBS 程式碼使專案層次結構井然有序，從而實現高效的追蹤和組織。
## 先決條件
在我們深入學習本教程之前，請確保您具備以下先決條件：
- .NET 開發的實用知識。
- 安裝了 .NET 函式庫的 Aspose.Tasks。你可以下載它[這裡](https://releases.aspose.com/tasks/net/).
- 程式碼編輯器（建議使用 Visual Studio）。
## 導入命名空間
在您的 .NET 專案中，首先匯入必要的命名空間：
```csharp
    
    using Aspose.Tasks.Saving;
```
現在，讓我們將定義 WBS 程式碼的流程分解為可管理的步驟。

## 步驟1：設定文檔目錄
```csharp
String DataDir = "Your Document Directory";
```
將“您的文檔目錄”替換為文檔目錄的實際路徑。
## 第 2 步：初始化項目
```csharp
var project = new Project();
```
使用 Aspose.Tasks 建立一個新的專案實例。
## 步驟 3：設定 WBS 代碼定義
```csharp
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
設定 WBS 代碼定義參數，例如代碼產生、唯一性驗證和代碼前綴。
## 步驟 4：定義 WBS 代碼掩碼
```csharp
var mask = new WBSCodeMask();
mask.Length = 2;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
mask = new WBSCodeMask();
mask.Length = 1;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
```
指定 WBS 程式碼遮罩以根據長度、分隔符號和序列建立程式碼。
## 步驟5：建立任務並重新計算
```csharp
var tsk = project.RootTask.Children.Add("Task 1");
tsk.Children.Add("Task 2");
project.Recalculate();
```
將任務新增至專案層次結構並重新計算以更新 WBS 程式碼。
## 第 6 步：儲存項目
```csharp
project.Save(DataDir + @"AddWBSCodes_out.xml", SaveFileFormat.Xml);
```
使用新定義的 WBS 代碼儲存項目。
## 結論
在本教程中，我們探索了 Aspose.Tasks for .NET 在定義 WBS 程式碼方面的強大功能。透過執行這些步驟，您可以增強專案管理能力，為您的工作流程帶來結構和效率。
## 經常問的問題
### Aspose.Tasks 與所有 .NET 版本相容嗎？
是的，Aspose.Tasks 支援各種 .NET 版本，確保與各種開發環境相容。
### 我可以進一步自訂 WBS 程式碼格式嗎？
絕對地。 Aspose.Tasks 提供了廣泛的靈活性，可讓您自訂 WBS 程式碼以滿足特定的專案要求。
### 我可以定義的 WBS 代碼數量有限制嗎？
Aspose.Tasks提供了可擴充性，您可以根據專案的複雜性定義相當數量的WBS程式碼。
### 如何解決專案中與 WBS 程式碼相關的問題？
 Aspose.Tasks 論壇（連結到[支援](https://forum.aspose.com/c/tasks/15)）是尋求幫助和解決問題的寶貴資源。
### 購買 Aspose.Tasks 之前是否有試用版？
是的，您可以透過造訪來探索 Aspose.Tasks 的特性和功能[免費試用](https://releases.aspose.com/)版本。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
