---
date: 2026-04-06
description: 學習如何使用 Aspose.Tasks for .NET 為專案新增資源並設定資源可用期間。一步一步的資源日曆管理指南。
keywords:
- add resource to project
- set resource availability
- configure work schedule
linktitle: 在 Aspose.Tasks 中使用可用期間
second_title: Aspose.Tasks .NET API
title: 在 Aspose.Tasks 中新增資源至專案並設定可用性
url: /zh-hant/net/advanced-features/working-with-availability-periods/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中將資源加入專案並設定可用性

## 介紹

在本教學中，你將學習**如何將資源加入專案**，並使用 Aspose.Tasks .NET 函式庫定義其可用期間。管理資源行事曆對於制定實際的專案排程至關重要，以下步驟將帶領你完成整個流程——從建立專案實例到列印每個期間的詳細資訊。

## 快速解答
- **主要目標是什麼？** 將資源加入專案並設定其可用期間。  
- **需要哪個函式庫？** Aspose.Tasks for .NET。  
- **生產環境需要授權嗎？** 需要，必須取得商業授權。  
- **支援的 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **實作時間？** 基本情境通常在 15 分鐘以內。

## 「將資源加入專案」是什麼？

將資源加入專案會建立一個可指派給工作項目的人員、設備或材料的佔位符。資源建立後，你可以**設定資源可用性**、定義其工作行事曆，並讓排程器遵守這些限制。

## 為何要設定工作排程與可用期間？

- **精確規劃：** 工作項目僅在資源實際空閒時排程。  
- **成本控制：** 可用單位反映兼職工作量，協助正確計算人工成本。  
- **資源平衡：** 引擎在了解每個資源的行事曆後，可自動平衡過度分配。

## 前置條件

1. Visual Studio（或任何相容 .NET 的 IDE）。  
2. Aspose.Tasks for .NET – 從[此處](https://releases.aspose.com/tasks/net/)下載。  
3. 基本的 C# 知識。

## 匯入命名空間

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## 如何將資源加入專案？

### 步驟 1：建立新的 `Project` 實例

```csharp
var project = new Project();
```

此物件在記憶體中代表整個專案檔案。

### 步驟 2：將資源加入專案

```csharp
var resource = project.Resources.Add("Work Resource");
```

此呼叫會建立一個名為 *Work Resource* 的**資源**，之後可將其指派給工作項目。

### 步驟 3：定義可用期間

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

`GetPeriods()` 是一個輔助方法（未顯示實作），會回傳 `AvailabilityPeriod` 物件的集合。每個期間指定開始日期、結束日期，以及資源可用的單位（全職工作量的百分比）。

### 步驟 4：將期間加入資源

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

在此，我們透過迴圈遍歷集合，將每個期間加入資源的行事曆，以**設定資源可用性**。

### 步驟 5：顯示可用性詳細資訊

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

主控台輸出讓你驗證期間已正確儲存。

## 常見陷阱與技巧

- **日期精度：** `AvailableFrom` 與 `AvailableTo` 為 `DateTime` 值；若希望以整天為單位，請確保設定為午夜 00:00。  
- **單位範圍：** 有效值為 0‑100 %；超出此範圍會拋出例外。  
- **重疊期間：** 重疊的期間會自動合併，但保持分開較為清晰。

## 常見問答

### Q1：我可以在商業專案中使用 Aspose.Tasks for .NET 嗎？

A1：可以，Aspose.Tasks for .NET 可用於商業專案。你可以在[此處](https://purchase.aspose.com/buy)購買授權。

### Q2：Aspose.Tasks for .NET 有提供免費試用嗎？

A2：有，你可以在[此處](https://releases.aspose.com/)取得 Aspose.Tasks for .NET 的免費試用。

### Q3：在哪裡可以找到 Aspose.Tasks for .NET 的文件？

A3：文件可於[此處](https://reference.aspose.com/tasks/net/)取得。

### Q4：如何取得 Aspose.Tasks for .NET 的支援？

A4：可從社群論壇[此處](https://forum.aspose.com/c/tasks/15)取得支援。

### Q5：是否提供 Aspose.Tasks for .NET 的臨時授權？

A5：有，臨時授權可於[此處](https://purchase.aspose.com/temporary-license/)取得。

---

**最後更新：** 2026-04-06  
**測試環境：** Aspose.Tasks for .NET（最新穩定版）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}