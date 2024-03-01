---
title: 在 Aspose.Tasks 中設定重複任務參數
linktitle: 在 Aspose.Tasks 中設定重複任務參數
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 在 Microsoft Project 中設定重複任務參數。帶有逐步指南的綜合教程。
type: docs
weight: 14
url: /zh-hant/net/rate-recurring-tasks/recurring-task-parameters/
---
## 介紹
在本教學中，我們將引導您完成使用 Aspose.Tasks for .NET 設定 Microsoft Project 重複任務參數的過程。
## 先決條件
在開始之前，請確保您具備以下條件：
1. 對 C# 程式語言有基本了解。
2. 安裝了 Visual Studio 或任何其他 C# IDE。
3. Aspose.Tasks for .NET 程式庫已安裝並在您的專案中引用。

## 導入命名空間
首先，您需要在 C# 程式碼中匯入必要的命名空間：
```csharp
using Aspose.Tasks;
using System;

```
## 第 1 步：定義文檔目錄
```csharp
String DataDir = "Your Document Directory";
```
代替`"Your Document Directory"`與您的文檔目錄的路徑。
## 第 2 步：載入專案文件
```csharp
var project = new Project(DataDir + "Blank2010.mpp");
```
這行程式碼將 Microsoft Project 檔案載入到`project`多變的。
## 步驟 3：定義重複任務參數
```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "Recurring task",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new WeeklyRecurrencePattern
    {
        Repetition = new WeeklyRepetition
        {
            RepetitionInterval = 2,
            WeekDays = WeekdayType.Sunday | WeekdayType.Monday | WeekdayType.Friday
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 7, 20, 17, 0, 0)
        }
    },
    IgnoreResourceCalendar = false
};
```
在此，您可以定義重複任務的參數，例如任務名稱、持續時間、重複模式、重複範圍以及是否忽略資源行事曆。
## 步驟 4：為重複任務設定日曆
```csharp
parameters.SetCalendar(project, "Standard");
```
此步驟設定重複任務的日曆。在此範例中，它將日曆設定為“標準”。
## 第5步：為項目新增參數
```csharp
project.RootTask.Children.Add(parameters);
```
最後，將參數新增至專案的根任務。

## 結論
在本教學中，我們示範如何使用 Aspose.Tasks for .NET 設定 Microsoft Project 重複任務參數。透過執行這些步驟，您可以有效地管理專案中的重複任務。
## 常見問題解答
### 我可以進一步自訂重複模式嗎？
是的，Aspose.Tasks 提供了各種重複模式和選項，可根據您的專案要求進行自訂。
### 購買前是否有試用版？
是的，您可以從 Aspose.Tasks 下載免費試用版[網站](https://purchase.aspose.com/buy)評估圖書館的功能。
### Aspose.Tasks 是否支援其他專案文件格式？
是的，Aspose.Tasks 支援各種專案檔案格式，包括 MPP、XML、XLSX 等。
### 如果在實施過程中遇到任何問題，我可以獲得支援嗎？
是的，您可以造訪 Aspose.Tasks 論壇尋求社群的協助，或聯絡支援人員以獲得直接協助。
### 我如何獲得 Aspose.Tasks 的臨時許可證？
您可以從以下機構獲得臨時許可證[網站](https://purchase.aspose.com/temporary-license/)用於測試目的。