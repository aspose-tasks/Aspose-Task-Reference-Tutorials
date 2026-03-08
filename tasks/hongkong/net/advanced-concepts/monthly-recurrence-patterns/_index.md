---
date: 2026-03-08
description: 透過此一步一步的教學，學習如何在 Aspose.Tasks for .NET 中建立每月重複任務。
linktitle: How to Create Monthly Recurring Task in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: 如何在 Aspose.Tasks 中建立每月重複任務
url: /zh-hant/net/advanced-concepts/monthly-recurrence-patterns/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 建立每月重複任務

## 介紹

Aspose.Tasks for .NET 讓您能以程式方式操作 Microsoft Project 檔案，而最常見的實務需求之一就是 **建立每月重複任務** 排程。無論您是建立專案追蹤工具、自動化資源分配，或產生定期維護工作項目，本教學都會一步步說明如何為任務加入每月重複模式。

在接下來的章節中，您將看到如何設定專案、定義重複參數，最後儲存更新後的檔案——全部提供清晰說明與實用技巧。

## 快速解答
- **「每月重複任務」是什麼意思？** 每月依照指定的日或週模式重複的任務。  
- **哪個 API 類別負責處理重複？** `RecurringTaskParameters` 搭配 `MonthlyRecurrencePattern`。  
- **執行範例是否需要授權？** 免費試用可用於評估；正式環境需購買授權。  
- **可以更改間隔嗎？** 可以——將 `RepetitionInterval` 設為兩次發生之間的月份數。  
- **支援哪些檔案格式？** `.mpp` 與 `.xml` 兩種 Project 檔案皆可載入與儲存。

## 什麼是每月重複模式？

每月重複模式告訴 Microsoft Project（以及 Aspose.Tasks）任務每個月應重複的頻率。您可以指定月份的固定日期（例如第 1 天）或相對位置（例如最後一個星期五）。API 會將這些規則轉換為底層的 Project 檔案結構。

## 為什麼使用 Aspose.Tasks？

- **完整控制** – 無 UI 限制；您可以在程式碼中定義模式的每個細節。  
- **跨平台** – 可在 .NET Framework、.NET Core 以及 .NET 5/6+ 上執行。  
- **不需 Microsoft Project** – 可在伺服器或 CI 流程中產生或修改檔案。  

## 前置條件

在開始之前，請確保您已具備以下條件：

- 已安裝 .NET 6（或 .NET 5 / Framework 4.7+）。  
- 已在專案中加入 Aspose.Tasks for .NET NuGet 套件。  
- 一個範例 Project 檔案 (`Project1.mpp`) 放置於已知資料夾 (`DataDir`)。  

## 匯入命名空間

首先，匯入處理任務與儲存專案所需的命名空間：

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

## 步驟 1：初始化專案

建立指向現有 `.mpp` 檔案的 `Project` 實例。此操作會將檔案載入記憶體，以便進行修改。

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

> **小技巧：** 若檔案不存在，Aspose.Tasks 會自動建立一個全新的空白專案。

## 步驟 2：設定重複任務參數

定義重複任務的詳細資訊，包括名稱、持續時間以及您想套用的每月模式。

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthDayRepetition { DayPosition = 1, RepetitionInterval = 2 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 30, 17, 0, 0)
        }
    }
};
```

- `DayPosition = 1` 表示任務發生於每月的 **第一天**。  
- `RepetitionInterval = 2` 使任務每 **兩個月** 重複一次。  
- `Start` 與 `Finish` 定義重複模式生效的整體時間範圍。  

## 步驟 3：將參數加入專案

將 `RecurringTaskParameters` 物件附加至根任務的子集合中。這樣即可在專案層級中實際建立重複任務。

```csharp
project.RootTask.Children.Add(parameters);
```

## 步驟 4：儲存專案

將變更寫入新檔案以永久保存。您可以選擇任何支援的格式；此處使用原生的 `.mpp` 格式。

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

執行程式碼後，於 Microsoft Project 開啟產生的檔案，即可看到剛剛建立的每月重複任務。

## 常見問題與解決方案

| 問題 | 原因 | 解決方案 |
|------|------|----------|
| 任務儲存後未顯示 | UI 未重新整理專案 | 重新開啟檔案或在儲存前呼叫 `project.UpdateTaskLinks()`。 |
| 開始日期錯誤 | `Start` 設為週末 | 使用落在工作日的 `DateTime`，或調整行事曆。 |
| 重複間隔被忽略 | 使用 `ByMonthDayRepetition` 且 `DayPosition` = 0 | 確保 `DayPosition` 為 1‑31。 |

## 結論

透過上述步驟，您現在已了解如何使用 Aspose.Tasks for .NET **建立每月重複任務** 排程。API 提供對重複間隔、開始/結束範圍以及特定日期模式的精細控制，讓您能自動化複雜的專案規劃情境。

## 常見問答

### Q1：Aspose.Tasks 是否相容所有版本的 Microsoft Project 檔案？

A1：Aspose.Tasks 支援多種版本的 Microsoft Project 檔案，包括 MPP、MPT、XML 與 MPX。

### Q2：我可以進一步自訂重複模式嗎？

A2：可以，Aspose.Tasks 提供廣泛的選項來自訂重複模式，包含每日、每週、每月與每年。

### Q3：是否提供 Aspose.Tasks 的免費試用？

A3：有，您可從網站 [here](https://releases.aspose.com/) 取得 Aspose.Tasks 的免費試用版。

### Q4：如何取得 Aspose.Tasks 的支援？

A4：您可在 [Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15) 尋求協助並參與討論。

### Q5：在哪裡可以購買 Aspose.Tasks 的授權？

A5：您可從網站 [here](https://purchase.aspose.com/buy) 購買 Aspose.Tasks 授權。

## 常見問題

**Q：我可以在 .NET Core 應用程式中使用此程式碼嗎？**  
A：當然可以。Aspose.Tasks for .NET 完全支援 .NET Core 3.1 及之後的版本。

**Q：如何將重複設定為「每月最後一個工作日」？**  
A：使用 `ByMonthDayRepetition` 並將 `DayPosition = -1`（負值表示從月末倒算），同時依需求設定 `WeekDay`。

**Q：若重複範圍超出專案行事曆會發生什麼情況？**  
A：API 會遵循專案行事曆；落在非工作日的發生會根據行事曆設定被跳過或移動。

**Q：能否刪除特定的重複任務發生嗎？**  
A：可以。加入重複任務後，您可透過 `Task.GetOccurrences()` 取得個別發生，並刪除不需要的項目。

**Q：Aspose.Tasks 會自動處理時區差異嗎？**  
A：此函式庫以 UTC 儲存日期；如有需要，可使用標準 .NET `DateTime` 方法轉換為本地時間。

**最後更新：** 2026-03-08  
**測試版本：** Aspose.Tasks 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}