---
title: Aspose.Tasks 中按月日重複
linktitle: Aspose.Tasks 中按月日重複
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks 管理 .NET 專案中的重複任務。按月日處理重複的分步指南。
weight: 25
url: /zh-hant/net/advanced-features/repetition-by-month-day/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中按月日重複

## 介紹

在.NET 開發領域，Aspose.Tasks 是管理專案任務和進度的強大工具。它提供了大量的功能來簡化專案管理工作流程，包括處理重複任務。按月日重複是專案調度中的常見要求，Aspose.Tasks 為這種情況提供了強大的支援。

## 先決條件

在深入學習本教程之前，請確保您具備以下先決條件：

1. 對 C# 的基本了解：要掌握本教程中討論的概念，需要熟悉 C# 程式語言。
2. 安裝Aspose.Tasks for .NET：確保您已經安裝了Aspose.Tasks for .NET。您可以從以下位置下載：[這裡](https://releases.aspose.com/tasks/net/).
3. 整合開發環境 (IDE)：在系統上安裝 Visual Studio 等 IDE，以方便編碼。

## 導入命名空間

在您的 C# 專案中，匯入必要的命名空間以存取 Aspose.Tasks 功能：

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

讓我們將提供的程式碼範例分解為逐步指南格式：

## 第 1 步：載入專案文件

```csharp
//文檔目錄的路徑。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

這行程式碼初始化了一個新的實例`Project`類，載入名為“Project1.mpp”的專案檔。

## 第 2 步：定義重複任務參數

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

此部分定義重複任務的參數，包括其名稱、持續時間、重複模式和重複範圍。

## 第 3 步：將任務新增至專案中

```csharp
project.RootTask.Children.Add(parameters);
```

在這裡，我們將重複任務參數新增到專案中。

## 第 4 步：儲存專案文件

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

最後，修改後的項目與新增的重複任務一起儲存。

## 結論

在本教程中，我們探討如何在 Aspose.Tasks for .NET 中按月處理重複。透過遵循提供的步驟，您可以有效地管理專案計劃中的重複任務。

## 常見問題解答

### Q1：Aspose.Tasks 是否與所有版本的.NET 相容？

A1：Aspose.Tasks支援各種版本的.NET框架，確保不同環境下的相容性。

### Q2：我可以進一步自訂重複模式嗎？

A2：是的，Aspose.Tasks 提供了廣泛的自訂選項，用於根據特定項目要求定義重複模式。

### Q3：Aspose.Tasks 是否提供其他專案管理功能的支援？

A3：當然，Aspose.Tasks 為專案管理提供了廣泛的功能，包括任務追蹤、資源分配和甘特圖生成。

### Q4：Aspose.Tasks 有試用版嗎？

 A4：是的，您可以免費試用[這裡](https://releases.aspose.com/)在做出購買決定之前探索 Aspose.Tasks 的功能。

### Q5：如果我遇到問題或有疑問，可以到哪裡尋求協助？

 A5：您可以訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)尋求社區或 Aspose 團隊的支持。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
