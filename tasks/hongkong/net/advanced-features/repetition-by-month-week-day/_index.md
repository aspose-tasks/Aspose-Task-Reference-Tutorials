---
title: Aspose.Tasks 中按月週日重複
linktitle: Aspose.Tasks 中按月週日重複
second_title: Aspose.Tasks .NET API
description: 了解如何在 Aspose.Tasks for .NET 中按月、週和日設定重複，以有效率地自動執行重複任務。
weight: 26
url: /zh-hant/net/advanced-features/repetition-by-month-week-day/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中按月週日重複

## 介紹

在軟體開發領域，特別是在專案管理應用程式中，有效處理重複任務的能力至關重要。 Aspose.Tasks for .NET 是一個功能強大的函式庫，旨在簡化專案任務（包括重複任務）的建立和管理。 Aspose.Tasks 提供的其中一項功能是能夠按月、週和日設定重複，確保任務按計畫執行，無需人工幹預。

## 先決條件

在深入研究使用 Aspose.Tasks for .NET 按月、週和日設定重複的複雜性之前，請確保滿足以下先決條件：

1. 對 C# 的基本了解：熟悉 C# 程式語言對於理解和實作所提供的程式碼範例至關重要。
   
2. 安裝 Aspose.Tasks for .NET：請確定您已下載並安裝 Aspose.Tasks for .NET 程式庫。您可以從以下位置取得該庫：[下載頁面](https://releases.aspose.com/tasks/net/).

3. 存取 .mpp 專案檔案：準備好 Microsoft Project 檔案 (.mpp)，因為我們將利用它來示範按月、週和日進行重複的實作。

## 導入命名空間

要開始在 C# 應用程式中使用 Aspose.Tasks for .NET，您需要匯入必要的命名空間。您可以這樣做：

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

讓我們將提供的程式碼片段分解為多個步驟，以徹底理解每個部分。

## 第 1 步：載入專案文件

```csharp
//文檔目錄的路徑。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

此步驟涉及建立一個新實例`Project`類別並載入現有的 Microsoft Project 檔案（`Project1.mpp`）從指定的目錄。

## 第 2 步：定義重複任務參數

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

在此步驟中，我們定義重複任務的參數。我們指定任務名稱、持續時間、重複模式（每月）和重複範圍（以特定日期結束）。

## 第 3 步：將重複任務新增至專案中

```csharp
project.RootTask.Children.Add(parameters);
```

在這裡，我們將定義的重複任務參數新增到專案的根任務中。

## 第 4 步：儲存專案文件

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

最後，我們保存修改後的項目文件以及新增的重複任務。

## 結論

總之，在 Aspose.Tasks for .NET 中按月、週和日設定重複是一個簡單的過程，使開發人員能夠有效地自動管理專案中的重複任務。透過遵循本教學中概述的步驟，您可以將此功能無縫整合到您的 C# 應用程式中，從而節省專案管理的時間和精力。

## 常見問題解答

###Q1：除了提供的範例之外，我還可以自訂重複模式嗎？

A1：是的，Aspose.Tasks for .NET 為重複模式提供了廣泛的自訂選項，可讓您根據您的特定要求進行自訂。

###Q2：Aspose.Tasks for .NET 有試用版嗎？

 A2：是的，您可以從 Aspose.Tasks for .NET 取得免費試用版[發布頁面](https://releases.aspose.com/).

###Q3：如何獲得對 Aspose.Tasks for .NET 的支援？

 A3：您可以尋求協助並與社群互動[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15).

###Q4：Aspose.Tasks for .NET 是否有臨時授權？

 A4：是的，您可以從[購買頁面](https://purchase.aspose.com/temporary-license/)用於測試和評估目的。

###Q5：在哪裡可以找到 Aspose.Tasks for .NET 的綜合文件？

 A5：您可以參考詳細的[文件](https://reference.aspose.com/tasks/net/)可在 Aspose 網站上取得有關使用該程式庫的深入指導。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
