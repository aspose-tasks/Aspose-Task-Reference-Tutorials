---
title: 在 Aspose.Tasks 中處理每月重複模式
linktitle: 在 Aspose.Tasks 中處理每月重複模式
second_title: Aspose.Tasks .NET API
description: 透過此逐步教程，了解如何在 Aspose.Tasks for .NET 中處理每月重複模式。
weight: 18
url: /zh-hant/net/advanced-concepts/monthly-recurrence-patterns/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中處理每月重複模式

## 介紹

Aspose.Tasks for .NET 是一個功能強大的 API，可讓開發人員以程式設計方式操作 Microsoft Project 檔案。它提供的基本功能之一是能夠有效處理重複任務。在本教程中，我們將逐步深入研究如何使用 Aspose.Tasks 處理每月重複模式。

## 先決條件

在開始之前，請確保您已安裝以下先決條件：

## 導入命名空間

首先，請確保您已在 .NET 專案中匯入了必要的命名空間：

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

現在，讓我們將處理每月重複模式的過程分解為多個步驟：

## 第 1 步：初始化項目

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## 步驟 2：設定重複任務參數

定義重複任務的參數，包括任務名稱、持續時間和重複模式：

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

## 第3步：為項目新增參數

```csharp
project.RootTask.Children.Add(parameters);
```

## 第 4 步：儲存項目

使用重複任務儲存修改後的項目：

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

## 結論

在 Aspose.Tasks for .NET 中處理每月重複模式既簡單又有效率。透過遵循本教學中概述的步驟，您可以輕鬆建立具有特定每月間隔和重複範圍的重複任務。

## 常見問題解答

### Q1：Aspose.Tasks 是否與所有版本的 Microsoft Project 檔案相容？

A1：Aspose.Tasks支援各種版本的Microsoft Project文件，包括MPP、MPT、XML和MPX。

### Q2：我可以進一步自訂重複模式嗎？

A2：是的，Aspose.Tasks 提供了廣泛的選項用於自訂重複模式，包括每日、每週、每月和每年。

### Q3：Aspose.Tasks 有免費試用版嗎？

 A3：是的，您可以從網站獲得Aspose.Tasks的免費試用版[這裡](https://releases.aspose.com/).

### Q4：如何獲得 Aspose.Tasks 的支援？

 A4：您可以尋求協助並參與討論[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15).

### Q5：在哪裡可以購買 Aspose.Tasks 的授權？

 A5：您可以從網站購買Aspose.Tasks的許可證[這裡](https://purchase.aspose.com/buy)
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
