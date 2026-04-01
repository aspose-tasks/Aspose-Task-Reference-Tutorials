---
date: 2026-04-01
description: 了解如何在 Aspose.Tasks for .NET 中設定重複、加入重複任務，並按月、按週、按日自動化重複任務。
keywords:
- how to set recurrence
- add recurring task
- automate recurring tasks
linktitle: 在 Aspose.Tasks 中按月、週、日重複
second_title: Aspose.Tasks .NET API
title: 如何在 Aspose.Tasks 中設定重複（月份、星期、天）
url: /zh-hant/net/advanced-features/repetition-by-month-week-day/
weight: 26
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中設定重複 (月份、星期、天)

## 介紹

如果您需要 **設定任務的重複**，Aspose.Tasks for .NET 提供了一個簡潔的程式化方式，讓您可以新增以月份、星期或天為單位執行的重複任務定義。在本教學中，我們將透過一個實務範例說明如何 **新增重複任務**、**自動化重複任務**，以及如何直接從 C# 程式碼管理它們。完成後，您即可將此功能整合至任何排程或專案管理解決方案中。

## 快速解答
- **在 Aspose.Tasks 中「重複」是什麼意思？** 它定義了一個模式（每日、每週、每月），會在指定的日期範圍內自動產生任務實例。  
- **哪個主要方法會建立重複？** `RecurringTaskParameters` 搭配特定的 `RecurrencePattern`。  
- **執行此程式碼需要授權嗎？** 試用版可用於評估；正式環境需購買商業授權。  
- **可以改為排程每週任務而不是每月嗎？** 可以 – 將 `MonthlyRecurrencePattern` 換成 `WeeklyRecurrencePattern`。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 及更高版本。

## Aspose.Tasks 中的重複是什麼？

重複是一組規則，告訴 Aspose.Tasks 在固定間隔（每日、每週或每月）自動產生任務實例，無需手動複製。此功能對於包含例行活動（如狀態會議、檢查或維護工作）的專案尤為重要。

## 為什麼要使用重複功能？

- **節省時間：** 不必手動複製貼上任務。  
- **減少錯誤：** 函式庫保證日期與工期的一致性。  
- **彈性高：** 可組合模式（例如「每兩個月的第一個星期日」）。  
- **自動化：** 非常適合在 CI 管線或報表工具中產生排程。

## 前置條件

在開始之前，請確保您已具備：

1. **基本的 C# 知識** – 您將撰寫少量 C# 程式碼。  
2. **已安裝 Aspose.Tasks for .NET** – 從[下載頁面](https://releases.aspose.com/tasks/net/)取得。  
3. **.mpp 專案檔** – 本教學使用 `Project1.mpp` 作為來源檔案。

## 匯入命名空間

首先，匯入所需的 Aspose.Tasks 命名空間：

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### 步驟 1：載入專案檔

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

我們建立一個指向既有 Microsoft Project 檔案的 `Project` 實例。

### 步驟 2：定義重複任務參數

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthWeekDayRepetition
        {
            Position = OrdinalNumber.First,
            WeekDay = DayOfWeek.Sunday,
            RepetitionInterval = 2
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 2, 17, 0, 0)
        }
    }
};
```

此處 **建立重複任務** 參數：

- **TaskName** – 產生的任務名稱。  
- **Duration** – 每次出現的持續時間。  
- **RecurrencePattern** – 每兩個月的第一個星期日的月份模式。  
- **RecurrenceRange** – 限定排程的開始與結束日期。

### 步驟 3：將重複任務加入專案

```csharp
project.RootTask.Children.Add(parameters);
```

此行 **將重複任務** 加入專案層級的根節點。

### 步驟 4：儲存更新後的專案

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

專案會另存為新的 `.mpp` 檔，內含自動化排程。

## 常見問題與解決方案

| 問題 | 原因 | 解決方式 |
|------|------|----------|
| **任務未顯示** | 重複範圍超出專案日期。 | 確認 `Start` 與 `Finish` 值在專案行事曆內。 |
| **星期錯誤** | `WeekDay` 列舉不匹配。 | 依需求使用 `DayOfWeek.Monday` … `DayOfWeek.Sunday`。 |
| **授權例外** | 生產環境未使用有效授權。 | 在儲存前套用臨時或正式授權。 |

## 常見問答

### Q1: 我可以自訂重複模式，超出範例提供的設定嗎？

A1: 可以，Aspose.Tasks for .NET 提供廣泛的自訂選項，讓您依需求調整重複模式。

### Q2: 是否有 Aspose.Tasks for .NET 的試用版？

A2: 有，您可從[發行頁面](https://releases.aspose.com/)取得免費試用版。

### Q3: 如何取得 Aspose.Tasks for .NET 的支援？

A3: 您可在[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)上尋求協助並與社群互動。

### Q4: 是否提供臨時授權給 Aspose.Tasks for .NET？

A4: 有，您可於[購買頁面](https://purchase.aspose.com/temporary-license/)取得臨時授權，用於測試與評估。

### Q5: 哪裡可以找到 Aspose.Tasks for .NET 的完整文件？

A5: 請參考 Aspose 官方網站上的詳細[文件說明](https://reference.aspose.com/tasks/net/)，獲取深入的使用指南。

---

**最後更新：** 2026-04-01  
**測試環境：** Aspose.Tasks 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}