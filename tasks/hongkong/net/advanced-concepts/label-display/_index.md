---
date: 2026-03-08
description: 學習如何在專案管理中使用 Aspose.Tasks for .NET 設定標籤顯示與自訂天數標籤，以提升可讀性與清晰度。
linktitle: Displaying Labels in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: 如何在 Aspose.Tasks for .NET 中設定標籤顯示
url: /zh-hant/net/advanced-concepts/label-display/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks for .NET 中設定標籤顯示

## Introduction

當您使用 **Aspose.Tasks for .NET** 建置專案管理解決方案時，能夠 **設定標籤** 的選項對於讓排程易於閱讀至關重要。無論您需要逐分鐘的精確度，或是高層次的年度檢視，客製化標籤顯示讓您能以利害關係人期望的方式呈現時間軸。在本教學中，我們將逐步說明如何為分鐘、時、天、週、月、年設定標籤顯示，並示範如何 **自訂天標籤** 格式以達到最佳清晰度。

## Quick Answers
- **「如何設定標籤」是什麼意思？** 它指的是設定 `DisplayOptions` 屬性，以控制時間單位在專案檔中如何顯示。  
- **我可以變更哪種標籤？** 分鐘、時、天、週、月與年皆可設定。  
- **需要授權嗎？** 正式使用需具備有效的 Aspose.Tasks 授權；免費試用版可用於測試。  
- **在 .NET Core 上支援嗎？** 支援，API 可在 .NET Core、.NET 5/6 以及完整的 .NET Framework 上運作。  
- **可以在執行時變更標籤嗎？** 當然可以——您可以在儲存專案前隨時修改顯示選項。

## What is label display in Aspose.Tasks?

標籤顯示決定了時間單位（分鐘、時、天等）在甘特圖與時間尺度上的文字呈現方式。透過設定適當的 `DisplayOptions` 屬性，您告訴 Aspose.Tasks 如何繪製這些單位，從而大幅提升專案的可讀性。

## Why customize label displays?

- **提升可讀性：** 利害關係人能立即了解排程的粒度。  
- **一致的報告：** 使視覺輸出符合公司標準（例如，月份使用「Mo」）。  
- **彈性：** 可在詳細與高層次檢視間切換，且不需更改底層排程資料。

## Prerequisites

1. **C# 知識** – 基本熟悉 C# 語法與 .NET 專案結構。  
2. **Aspose.Tasks for .NET** – 從 [此處](https://releases.aspose.com/tasks/net/) 下載並安裝函式庫。  
3. **開發環境** – Visual Studio、VS Code，或任何支援 .NET 開發的 IDE。

## Import Namespaces

Before you begin, import the required namespaces:

```csharp
using Aspose.Tasks;
using Aspose.Tasks;
```

## How to set label display for minutes

### 1. Displaying Minute Labels

To set the minute label, use the `MinuteLabel` property:

```csharp
public void WorkWithMinuteLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the minute label is displayed
    project.DisplayOptions.MinuteLabel = MinuteLabelDisplay.M;
}
```

## How to set label display for hours

### 2. Displaying Hour Labels

```csharp
public void WorkWithHourLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the hour label is displayed
    project.DisplayOptions.HourLabel = HourLabelDisplay.H;
}
```

## Customize day label display

### 3. Displaying Day Labels

```csharp
public void WorkWithDayLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the day label is displayed
    project.DisplayOptions.DayLabel = DayLabelDisplay.D;
}
```

## How to set label display for weeks

### 4. Displaying Week Labels

```csharp
public void WorkWithWeekLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the week label is displayed
    project.DisplayOptions.WeekLabel = WeekLabelDisplay.W;
}
```

## How to set label display for months

### 5. Displaying Month Labels

```csharp
public void WorkWithMonthLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the month label is displayed
    project.DisplayOptions.MonthLabel = MonthLabelDisplay.Mo;
}
```

## How to set label display for years

### 6. Displaying Year Labels

```csharp
public void WorkWithYearLabelDisplay()
{
    var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");

    // Set how the year label is displayed
    project.DisplayOptions.YearLabel = YearLabelDisplay.Y;
}
```

## Common Pitfalls & Tips

- **提示：** 請務必在儲存專案之前設定標籤顯示；儲存後的變更不會反映在檔案中。  
- **陷阱：** 使用不支援的列舉值會拋出 `ArgumentException`。請使用提供的 `*LabelDisplay` 列舉。  
- **提示：** 若需為不同視圖使用不同的標籤樣式，可建立獨立的 `Project` 實例或複製 `DisplayOptions` 物件。

## Conclusion

透過精通 **設定標籤** 選項，您即可細緻掌控專案排程的視覺呈現。無論是為每日站會板自訂天標籤，或是為多年度路線圖調整年標籤，這些設定都有助於提供更清晰、專業的專案文件。

## 常見問題

### Q1: 我可以為專案的特定區段自訂標籤顯示嗎？

A1: 可以，Aspose.Tasks for .NET 提供對標籤顯示的細部控制，讓您依需求為專案的特定區段自訂標籤。

### Q2: Aspose.Tasks 是否相容於常見的 .NET 框架？

A2: 可以，Aspose.Tasks for .NET 相容於多種 .NET 框架，包括 .NET Core 與 .NET Framework。

### Q3: 我可以根據專案需求動態變更標籤顯示嗎？

A3: 當然可以，Aspose.Tasks for .NET 的彈性讓您能根據不斷變化的專案需求動態調整標籤顯示。

### Q4: 標籤顯示的自訂有什麼限制嗎？

A4: Aspose.Tasks for .NET 提供廣泛的標籤顯示自訂選項，限制極少，為使用者提供充足的彈性。

### Q5: Aspose.Tasks 是否支援與其他專案管理工具整合？

A5: 可以，Aspose.Tasks 提供無縫的整合功能，方便與其他專案管理工具與平台互通。

---

**最後更新：** 2026-03-08  
**測試環境：** Aspose.Tasks 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}