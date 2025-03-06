---
title: 在 Aspose.Tasks 中配置 MS Project 顯示選項
linktitle: 在 Aspose.Tasks 中配置項目顯示選項
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 以程式設計 MS Project 顯示選項。輕鬆自訂您的項目外觀。
type: docs
weight: 17
url: /zh-hant/net/project-management-integration/project-display-options/
---
## 介紹
Microsoft Project 提供了大量的顯示選項來自訂項目的外觀。 Aspose.Tasks for .NET 提供了一個強大的框架來以程式設計方式操作這些選項。在本教學中，我們將探討如何使用 Aspose.Tasks 設定 MS Project 顯示選項。
## 先決條件
在深入學習本教學之前，請確保您具備以下條件：
1.  Aspose.Tasks for .NET：從下列位置下載並安裝程式庫[這裡](https://releases.aspose.com/tasks/net/).
2. Microsoft Project 檔案：準備好有效的 MS Project 檔案 (.mpp) 以套用顯示選項。
3. C# 基礎知識：需要熟悉 C# 程式語言。

## 導入命名空間
首先，確保將必要的命名空間匯入到您的 C# 程式碼：
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## 第 1 步：載入專案文件
使用以下命令載入 MS Project 文件`Project`Aspose.Tasks 提供的類別：
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "YourProjectFile.mpp");
```
## 第 2 步：配置顯示選項
現在，讓我們來配置 MS Project 中可用的各種顯示選項：
### 停用任務計劃警告
若要停用與手動排程任務的計畫衝突的警告（適用於 Project 2010 及更高版本）：
```csharp
project.DisplayOptions.ShowTaskScheduleWarnings = false;
```
### 在標籤前加入空格
設定在數值和時間縮寫前加入空格：
```csharp
project.DisplayOptions.AddSpaceBeforeLabel = true;
```
### 配置時間單位的標籤顯示
自訂不同時間單位的顯示方式：
```csharp
project.DisplayOptions.MinuteLabel = MinuteLabelDisplay.Min;
project.DisplayOptions.HourLabel = HourLabelDisplay.Hr;
project.DisplayOptions.DayLabel = DayLabelDisplay.Dy;
project.DisplayOptions.WeekLabel = WeekLabelDisplay.Week;
project.DisplayOptions.MonthLabel = MonthLabelDisplay.Mon;
project.DisplayOptions.YearLabel = YearLabelDisplay.Year;
```
### 顯示項目摘要任務
在一行上顯示有關整個項目的摘要資訊：
```csharp
project.DisplayOptions.ShowProjectSummaryTask = true;
```
### 啟用任務規劃建議
允許顯示與手動規劃任務衝突的建議：
```csharp
project.DisplayOptions.ShowTaskScheduleSuggestions = true;
```
### 超連結底線
設定為項目內的超連結新增底線：
```csharp
project.DisplayOptions.UnderlineHyperlinks = true;
```
## 第 3 步：保存項目
最後，使用應用程式的顯示選項儲存項目：
```csharp
project.Save(DataDir + "ModifiedProjectFile.mpp", SaveFileFormat.Mpp);
```

## 結論
在本教學中，我們學習如何使用 Aspose.Tasks for .NET 設定 MS Project 顯示選項。借助這些功能，您可以以程式設計方式有效地自訂專案文件的外觀。
## 常見問題解答
### Q：我可以將這些顯示選項僅套用至特定任務嗎？
答：是的，您可以使用 Aspose.Tasks API 選擇性地將顯示選項套用到各個任務。
### Q：這些顯示選項會影響底層項目資料嗎？
答：不，這些選項僅修改項目的視覺表示，不會更改底層資料。
### Q：這些顯示選項是否與所有版本的 Microsoft Project 相容？
答：不可以，某些選項可能特定於 MS Project 的某些版本。有關相容性詳細信息，請參閱文件。
### Q：我可以將顯示選項恢復為預設設定嗎？
答：是的，您可以使用 Aspose.Tasks API 將顯示選項重設為其預設值。
### Q：以程式設計方式自訂顯示選項有任何限制嗎？
答：雖然 Aspose.Tasks 提供了廣泛的自訂功能，但由於 MS Project 檔案格式的限制，某些顯示選項可能無法透過程式存取。