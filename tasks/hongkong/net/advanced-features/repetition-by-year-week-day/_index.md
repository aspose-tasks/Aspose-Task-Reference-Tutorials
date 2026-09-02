---
date: 2026-04-03
description: 學習如何使用 Aspose.Tasks 新增重複任務專案並將專案儲存為 MPP。本指南逐步說明「按年、週、日」的重複功能。
keywords:
- how to use aspose.tasks
- add recurring task project
- save project as mpp
linktitle: Aspose.Tasks 中的按年、週、日重複
second_title: Aspose.Tasks .NET API
title: 如何使用 Aspose.Tasks – 按年、週、日重複
url: /zh-hant/net/advanced-features/repetition-by-year-week-day/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中的「按年週日」重複

## 介紹

當您需要 **how to use Aspose.Tasks** 來處理複雜的重複排程時，該函式庫提供了對年度模式的精細控制。在本教學中，我們將示範如何建立一個在特定月份的特定星期幾重複的任務，跨越多個年份。完成後，您將能夠以幾行 C# 程式碼 **add recurring task project** 並 **save project as MPP**。

## 快速解答
- **什麼是「Repetition by Year Week Day」？** 它會在每年指定月份的特定星期幾（例如第一個星期日）重複任務。  
- **支援哪些 .NET 版本？** 所有現代的 .NET Framework 以及 .NET Core/5/6 版本。  
- **執行程式碼是否需要授權？** 開發時可使用免費試用版；正式環境需購買商業授權。  
- **可以變更重複範圍嗎？** 可以——您可以設定開始日期、結束日期，或固定的發生次數。  
- **輸出會是 MPP 檔案嗎？** 當然——專案會儲存為可直接在 Microsoft Project 開啟的 MPP 檔案。

## 「Repetition by Year Week Day」功能是什麼？

此功能讓您定義每年的重複排程，針對特定的**星期幾**（例如星期日）以及該月份中的**位置**（第一、第二、最後等）。非常適合季檢、年度稽核或任何依照日曆節奏的事件。

## 為何在重複任務上使用 Aspose.Tasks？

- **精確度** – 完全掌控月份、星期幾與序數位置。  
- **相容性** – 產生原生 MPP 檔案，可在 Microsoft Project 中無縫開啟。  
- **無 COM 互操作** – 純 .NET API，無需安裝 Office。  
- **可擴充性** – 無論小型專案或企業級排程皆適用。

## 前置條件

在深入程式碼之前，請確保您已具備：

1. **基本 .NET 知識** – 熟悉 C# 與物件導向概念。  
2. **Aspose.Tasks for .NET** – 從[下載連結](https://releases.aspose.com/tasks/net/)下載，並將 DLL 加入專案。  
3. **取得官方文件** – [文件說明](https://reference.aspose.com/tasks/net/)提供所有類別的完整細節。  
4. **開發 IDE** – Visual Studio、Rider 或任何相容的 .NET 編輯器。

現在您已準備就緒，讓我們來看看實作方式。

## 如何使用 Aspose.Tasks 進行重複任務

### 匯入必要的命名空間

首先，將所需的命名空間匯入範圍，以便操作專案、任務與儲存選項。

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### 步驟 1：初始化專案與任務參數

建立新的 `Project` 實例，然後定義描述重複模式的 `RecurringTaskParameters` 物件。

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Blank2010.mpp");
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearWeekDayRepetition
        {
            Month = Month.July, WeekDay = DayOfWeek.Sunday, Position = OrdinalNumber.First
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 31, 17, 0, 0)
        }
    }
};
```

> **專業提示：** 調整 `Month`、`WeekDay` 與 `Position` 以符合實際排程。

### 步驟 2：將參數加入專案

將重複任務定義插入專案的根節點。

```csharp
project.RootTask.Children.Add(parameters);
```

### 步驟 3：將專案儲存為 MPP

最後，將專案持久化為 MPP 檔案，以便在 Microsoft Project 或任何相容檢視器中開啟。

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearWeekDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

> 這示範了如何以單行程式碼 **save project as mpp**。

## 常見問題與解決方案

| 症狀 | 可能原因 | 解決方法 |
|------|----------|----------|
| 開啟 MPP 檔案後未顯示任何任務 | 重複範圍日期超出專案行事曆 | 確認 `Start` 與 `Finish` 日期位於專案的工作時間內 |
| `Add` 時發生 `ArgumentNullException` 例外 | `parameters` 為 null 或未完整初始化 | 確保已設定所有必要屬性（TaskName、Duration、RecurrencePattern） |
| 選擇了錯誤的星期幾 | `WeekDay` 列舉值不匹配 | 根據需要使用 `DayOfWeek.Monday` … `DayOfWeek.Sunday` |

## 常見問答

**Q: 我可以自訂重複模式，超出範例所示嗎？**  
A: 可以，Aspose.Tasks 允許您結合 `MonthlyRecurrencePattern`、`WeeklyRecurrencePattern`，甚至自訂的 `RecurrenceRange` 物件，以符合任何排程。

**Q: Aspose.Tasks for .NET 是否相容其他專案管理軟體？**  
A: 當然——此函式庫可讀寫 MPP、XML 與 Primavera 格式，實現順暢的資料交換。

**Q: 我要如何處理例外或修改重複任務？**  
A: 使用 `ExceptionTask` 類別為特定發生建立例外，或編輯 `RecurringTaskParameters` 後重新儲存專案。

**Q: Aspose.Tasks 是否支援雲端解決方案？**  
A: 支援，您可以在 Azure Functions、AWS Lambda 或任何相容 .NET 的雲端服務中執行此 API。

**Q: 是否提供 Aspose.Tasks for .NET 的試用版？**  
A: 有，您可從[網站](https://releases.aspose.com/)取得 Aspose.Tasks for .NET 的免費試用版，以在購買前體驗其功能。

**Q: 如何在不覆寫其他資料的情況下，將重複任務加入現有專案？**  
A: 使用 `new Project("Existing.mpp")` 載入現有專案，將 `RecurringTaskParameters` 加入 `RootTask.Children`，最後 `Save` 檔案。

## 結論

透過精通 **how to use Aspose.Tasks** 於 **Repetition by Year Week Day** 情境，您即可 **add recurring task project** 條目，完美契合實際行事曆，並 **save project as MPP** 以實現無縫協作。將這些程式碼片段整合至您的解決方案，可提升排程精準度並減少手動工作。

---

**Last Updated:** 2026-04-03  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}