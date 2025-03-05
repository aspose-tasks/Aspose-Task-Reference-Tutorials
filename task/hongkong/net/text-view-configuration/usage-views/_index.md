---
title: 在 Aspose.Tasks 中配置使用情況視圖
linktitle: 在 Aspose.Tasks 中配置使用情況視圖
second_title: Aspose.Tasks .NET API
description: 了解在 Aspose.Tasks for .NET 中配置任務使用視圖。透過詳細步驟增強項目視覺化。立即下載庫！
type: docs
weight: 17
url: /zh-hant/net/text-view-configuration/usage-views/
---
## 介紹
如果您是希望增強專案管理能力的 .NET 開發人員，Aspose.Tasks 是一款功能強大的工具，可讓您輕鬆操作 Microsoft Project 檔案。在本教程中，我們將重點放在使用 Aspose.Tasks for .NET 配置使用視圖。請繼續深入了解渲染任務使用情況視圖以及更好的專案視覺化的詳細資訊。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
-  Aspose.Tasks 函式庫：確保您已將 Aspose.Tasks 函式庫整合到您的 .NET 專案中。如果沒有的話可以下載[這裡](https://releases.aspose.com/tasks/net/)並按照安裝說明進行操作。
- 文檔目錄：設定儲存項目文檔的目錄。將程式碼片段中的「您的文檔目錄」替換為文檔目錄的實際路徑。
## 導入命名空間
在提供的程式碼片段中，您會注意到某些命名空間的使用。確保將這些包含在您的專案中以實現無縫整合：
```csharp
using Aspose.Tasks;
using Aspose.Tasks.Visualization;
using Aspose.Tasks.Saving;
```
## 第 1 步：渲染任務使用情況視圖及詳細信息
讓我們先渲染包含詳細資訊的任務使用量視圖。按著這些次序：
## 步驟1.1：載入項目
```csharp
//文檔目錄的路徑。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TaskUsageViewWithDetails.mpp");
```
## 步驟1.2：取得視圖
```csharp
UsageView view = (TaskUsageView)project.DefaultView;
```
## 步驟1.3：自訂視圖設置
```csharp
view.DisplayDetailsHeaderColumn = false;
view.RepeatDetailsHeaderOnAllRows = false;
view.DisplayShortDetailHeaderNames = false;
view.AlignDetailsData = HorizontalStringAlignment.Near;
```
## 步驟 1.4：將項目另存為 PDF
```csharp
project.Save(DataDir + "task_usage1_out.pdf", SaveFileFormat.Pdf);
```
## 步驟2：顯示詳細資料標題列
在此步驟中，我們將修改視圖設定以顯示詳細資料標題列並將項目儲存為 PDF：
## 步驟2.1：顯示詳細資料標題列
```csharp
view.DisplayDetailsHeaderColumn = true;
```
## 步驟 2.2：在所有行上重複詳細資訊標題
```csharp
view.RepeatDetailsHeaderOnAllRows = true;
view.AlignDetailsData = HorizontalStringAlignment.Far;
```
## 步驟 2.3：將項目另存為 PDF
```csharp
project.Save(DataDir + "task_usage2_out.pdf", SaveFileFormat.Pdf);
```
## 結論
恭喜！您已成功在 Aspose.Tasks 中配置使用視圖。本教程為使用 Aspose.Tasks 函式庫進行高效專案管理和視覺化奠定了基礎。

### 常見問題解答
### Q：在哪裡可以找到 Aspose.Tasks 文件？
提供全面的文檔[這裡](https://reference.aspose.com/tasks/net/).
### Q：如何下載 Aspose.Tasks for .NET？
下載庫[這裡](https://releases.aspose.com/tasks/net/).
### Q：哪裡可以購買 Aspose.Tasks？
你可以購買Aspose.Tasks[這裡](https://purchase.aspose.com/buy).
### Q：有免費試用嗎？
是的，探索免費試用版[這裡](https://releases.aspose.com/).
### Q：需要支援或有疑問嗎？
造訪支援論壇[這裡](https://forum.aspose.com/c/tasks/15).