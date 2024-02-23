---
title: Aspose.Tasks 中的日常工作重複
linktitle: Aspose.Tasks 中的日常工作重複
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 在 Microsoft Project 檔案中建立每日重複任務。輕鬆提高生產力和組織能力。
type: docs
weight: 26
url: /zh-hant/net/calendar-scheduling/daily-work-repetition/
---
## 介紹

Aspose.Tasks for .NET 是一個功能強大的程式庫，可讓開發人員輕鬆操作 Microsoft Project 檔案。其眾多功能之一是能夠有效處理重複任務。在本教程中，我們將深入研究日常工作重複功能，該功能允許創建在專案中每天重複的任務。

## 先決條件

在深入學習本教學之前，請確保您具備以下條件：

- C# 和 .NET 架構的基礎知識。
- Visual Studio 安裝在您的系統上。
-  .NET 函式庫的 Aspose.Tasks。你可以下載它[這裡](https://releases.aspose.com/tasks/net/).
- 熟悉 Microsoft Project 檔案 (.mpp)。

## 導入命名空間

在開始之前，請確保導入必要的命名空間：

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

讓我們將提供的範例分解為多個步驟：

## 第 1 步：載入專案文件

首先，使用以下命令載入專案文件`Project`班級：

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## 第 2 步：定義重複任務參數

定義重複任務的參數：

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "New recurrent task",
    RecurrencePattern = new DailyRecurrencePattern
    {
        RecurrenceRange = new EndAfterRecurrenceRange
        {
            Start = new DateTime(2018, 1, 1, 8, 0, 0),
            OccurrenceNumber = 9
        },
        Repetition = new DailyWorkRepetition { RepetitionInterval = 1 }
    },
    Duration = project.GetDuration(1, TimeUnitType.Hour)
};
```

## 步驟 3：設定日曆和任務開始日期

設定任務的日曆和開始日期：

```csharp
parameters.SetCalendar(project, "Standard");
var task = project.RootTask.Children.Add(parameters);
task.Set(Tsk.Start, new DateTime(2020, 4, 27, 8, 0, 0));
```

## 結論

在本教程中，我們探討如何利用 Aspose.Tasks for .NET 建立具有日常重複工作的重複任務。透過執行這些步驟，您可以有效地管理專案中的任務，確保工作流程和組織順利進行。

## 常見問題解答

### Q1：我可以進一步自訂重複模式嗎？

A1：是的，您可以調整開始日期、發生次數和重複間隔等參數，以根據您的要求自訂重複模式。

### Q2：Aspose.Tasks 是否與不同版本的 Microsoft Project 相容？

A2：是的，Aspose.Tasks支援各種版本的Microsoft Project，確保相容性和無縫整合。

### Q3：如何處理重複任務的異常或修改？

A3：Aspose.Tasks 提供了強大的功能來管理重複任務中的異常和修改，從而實現靈活性和自訂。

### Q4: 我可以將項目匯出為不同的格式嗎？

A4：當然，Aspose.Tasks 支援將項目匯出為各種格式，包括 PDF、HTML、XML 等，方便共享和協作。

### Q5：Aspose.Tasks 提供技術支援嗎？

A5：是的，Aspose.Tasks 透過其論壇提供全面的技術支持，您可以在其中尋求幫助、分享經驗並與其他用戶互動。