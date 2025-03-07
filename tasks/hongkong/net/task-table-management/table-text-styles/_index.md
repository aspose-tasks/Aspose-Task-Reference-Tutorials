---
title: Aspose.Tasks 中自訂表格文字樣式指南
linktitle: 在 Aspose.Tasks 中配置表格文字樣式
second_title: Aspose.Tasks .NET API
description: 使用 Aspose.Tasks for .NET 增強專案視覺化。了解逐步配置表格文字樣式。提高效率和演示。
weight: 14
url: /zh-hant/net/task-table-management/table-text-styles/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中自訂表格文字樣式指南

## 介紹
在專案管理領域，任務的有效視覺化對於成功至關重要。 Aspose.Tasks for .NET 提供了一個強大的解決方案來自訂表格文字樣式，讓您可以自訂專案中文字項目的外觀。在本逐步指南中，我們將引導您完成使用 Aspose.Tasks for .NET 設定表格文字樣式的過程。
## 先決條件
在深入學習本教學之前，請確保您具備以下條件：
- Aspose.Tasks for .NET：請確定您已安裝了最新版本的 Aspose.Tasks for .NET。你可以下載它[這裡](https://releases.aspose.com/tasks/net/).
- 文檔目錄：為您的文件設定目錄。將程式碼中的「您的文件目錄」替換為實際路徑。
- 有效的 Aspose 許可證：此範例需要有效的 Aspose 許可證。您可以購買完整許可證[這裡](https://purchase.aspose.com/buy)或取得 30 天的臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
## 導入命名空間
在開始編碼之前，導入必要的命名空間以利用 Aspose.Tasks 的功能：
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
現在，讓我們將範例分解為多個步驟：
## 第 1 步：載入項目並設定項目屬性
```csharp
var project = new Project(DataDir + "Project2.mpp");
project.Set(Prj.NewTasksAreManual, false);
```
## 第 2 步：訪問甘特圖視圖
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
## 第 3 步：自訂任務名稱文字樣式
```csharp
var style1 = new TableTextStyle(1);
style1.Field = Field.TaskName;
style1.Font = new FontDescriptor("Impact", 12F, FontStyles.Bold | FontStyles.Italic);
view.TableTextStyles.Add(style1);
```
## 第 4 步：自訂任務持續時間文字樣式
```csharp
var style2 = new TableTextStyle(2);
style2.Field = Field.TaskDurationText;
style2.Font = new FontDescriptor("Impact", 16F, FontStyles.Underline);
view.TableTextStyles.Add(style2);
```
## 第 5 步：使用自訂樣式儲存項目
```csharp
SimpleSaveOptions options = new MPPSaveOptions
{
    WriteViewData = true
};
project.Save(DataDir + "WorkWithTableTextStyle_out.mpp", options);
```
## 步驟6：處理許可異常
```csharp
catch (NotSupportedException ex)
{
    Console.WriteLine(
        ex.Message
        + "\nThis example will only work if you apply a valid Aspose License. You can purchase a full license or get a 30-day temporary license from [Aspose](http://www.aspose.com/purchase/default.aspx).");
}
```
## 結論
在 Aspose.Tasks for .NET 中自訂表格文字樣式提供了一種靈活有效的方法來增強項目的視覺表示。只需幾個簡單的步驟，您就可以創建更量身定制、更具影響力的專案管理體驗。
## 經常問的問題
### 我可以在沒有許可證的情況下使用 Aspose.Tasks for .NET 嗎？
不可以，此功能需要有效的 Aspose 許可證。您可以獲得許可證[這裡](https://purchase.aspose.com/buy)或取得 30 天的臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
### 如何更新其他任務屬性的字體樣式？
只需創建額外的`TableTextStyle`實例，指定所需的欄位和字型設定。
### Aspose.Tasks for .NET 有沒有試用版？
是的，您可以下載試用版[這裡](https://releases.aspose.com/).
### Aspose.Tasks 是否提供其他視覺化選項？
是的，Aspose.Tasks提供了各種視覺化功能來滿足不同的專案管理需求。
### 我可以為特定任務類型自訂樣式嗎？
當然，您可以透過相應地調整欄位和字體設定來將自訂擴展到不同的任務類型。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
