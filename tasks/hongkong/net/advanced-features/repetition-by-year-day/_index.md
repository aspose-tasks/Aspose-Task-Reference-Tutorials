---
date: 2026-04-03
description: 學習專案管理任務排程，並了解如何使用 Aspose.Tasks for .NET 新增重複任務，包括將專案儲存為 MPP。
keywords:
- project management task scheduling
- how to add recurring task
- save project as mpp
linktitle: Aspose.Tasks 中的按年日重複
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks 中的專案管理任務排程與年度日重複
url: /zh-hant/net/advanced-features/repetition-by-year-day/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 專案管理任務排程與年度日期重複於 Aspose.Tasks

## 介紹

Effective **project management task scheduling** 是任何成功專案的基礎。當任務以年度方式重複——例如年度稽核、維護窗口或季節性檢視——若手動處理這些重複會容易出錯且耗時。Aspose.Tasks for .NET 透過讓您以程式方式定義年度日期模式，簡化此流程，讓您專注於最重要的事：交付價值。在本教學中，您將學習 **如何新增重複任務** 的邏輯，基於一年中的特定日期，並且了解 **如何將專案儲存為 MPP**，以便無縫整合 Microsoft Project。

## 快速解答
- **「year day repetition」是什麼意思？** 它會在每年的特定月份的特定日期排程任務。  
- **哪個 API 類別會建立此重複？** `YearlyRecurrencePattern` combined with `ByYearDayRepetition`.  
- **我可以設定開始與結束日期嗎？** 可以，使用 `EndByRecurrenceRange`。  
- **產生的檔案格式是什麼？** 專案會儲存為 MPP 檔案 (`SaveFileFormat.Mpp`)。  
- **正式環境需要授權嗎？** 非評估使用須購買商業授權。

## 前置條件

在開始本教學之前，請確保您已具備以下前置條件：

1. Aspose.Tasks for .NET 函式庫：從[網站](https://releases.aspose.com/tasks/net/)下載並安裝 Aspose.Tasks for .NET 函式庫。  
2. 開發環境：使用 Visual Studio 或其他您偏好的 .NET 開發 IDE，建立合適的開發環境。  
3. C# 基礎知識：熟悉 C# 程式語言的基本概念，以便跟隨程式碼範例。  
4. 專案管理概念：了解專案管理概念與任務排程，有助於有效掌握本教學內容。

## 匯入命名空間

在開始編寫程式碼之前，先匯入必要的命名空間，以便使用 Aspose.Tasks for .NET 進行任務操作。

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

現在，讓我們將提供的範例分解為多個步驟，並詳細說明每個步驟。

## 如何使用年度日期模式新增重複任務

### 步驟 1：載入專案檔案

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

此處，我們建立一個新的 `Project` 物件，並載入名為 **Project1.mpp** 的現有專案檔案。

### 步驟 2：定義重複任務參數

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new YearlyRecurrencePattern
    {
        Repetition = new ByYearDayRepetition { DayPosition = 1, Month = Month.July },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2019, 7, 1, 17, 0, 0)
        }
    }
};
```

在此步驟中，我們為重複任務定義參數。我們指定任務名稱、持續時間與重複模式。對於年度重複，我們使用 `YearlyRecurrencePattern`，並透過 `ByYearDayRepetition` 設定在 **7 月 1 日** 重複。此外，我們將重複範圍定義為 2018 年 7 月 1 日至 2019 年 7 月 1 日。

### 步驟 3：將任務加入專案

```csharp
project.RootTask.Children.Add(parameters);
```

此處，我們將已定義的重複任務參數加入專案的根任務中。

### 步驟 4：將專案儲存為 MPP

```csharp
project.Save(DataDir + "CanAddRecurringTask_Years_YearDay_EndByRecurrenceRange_Test.mpp", SaveFileFormat.Mpp);
```

最後，我們 **將專案儲存為 MPP 檔案**，使其可在 Microsoft Project 或任何相容的檢視器中開啟。

## 為何這很重要

- **Automation** – 消除年度任務的手動輸入，降低人為錯誤。  
- **Consistency** – 確保相同的日‑月模式在多個年份中一致套用。  
- **Integration** – 產生的 MPP 檔案可與依賴 Microsoft Project 的利害關係人共享。  

## 常見陷阱與技巧

- **DateTime precision** – 確保開始時間與專案行事曆對齊；否則任務可能會出現偏移。  
- **Time zones** – API 使用 `DateTime` 物件；若您的應用程式跨多個區域，請考慮轉換為 UTC。  
- **License enforcement** – 評估模式下，儲存的 MPP 可能會帶有浮水印；正式環境請使用有效授權。

## 常見問與答

**Q: Aspose.Tasks 能處理複雜的重複模式嗎？**  
**A:** 是的，Aspose.Tasks 提供對各種重複模式的完整支援，包括年度、月度、每週以及每日的重複。

**Q: Aspose.Tasks 是否相容於不同的專案檔案格式？**  
**A:** 當然，Aspose.Tasks 支援常見的專案檔案格式，如 MPP、XML 與 CSV，確保在不同的專案管理工具間具備相容性。

**Q: Aspose.Tasks 是否提供開發人員文件與支援？**  
**A:** 有，開發人員可取得完整的文件，並可在 Aspose.Tasks 社群論壇上尋求協助，解決任何疑問或問題。

**Q: 我可以使用 Aspose.Tasks 自訂任務屬性，例如持續時間與開始日期嗎？**  
**A:** 當然，Aspose.Tasks 提供強大的 API，讓您動態操作任務屬性，能自訂持續時間、開始日期、相依性等。

**Q: Aspose.Tasks 是否適用於小型與企業級專案？**  
**A:** 確實，Aspose.Tasks 設計上能滿足各種規模的開發需求，從單一任務到大型企業專案皆適用。

---

**最後更新：** 2026-04-03  
**測試環境：** Aspose.Tasks 24.12 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}