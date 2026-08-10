---
date: 2026-03-21
description: 學習如何管理資源的可用性期間，並使用 Aspose.Tasks for .NET 實現有效的專案資源可用性。本分步指南說明如何新增、更新與移除可用性期間。
linktitle: Collection of Availability Periods in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: 項目資源可用性 – 在 Aspose.Tasks 中管理可用期間
url: /zh-hant/net/advanced-features/availability-period-collection/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 項目資源可用性：Aspose.Tasks 中可用期間的集合

管理 **項目資源可用性** 是成功專案規劃的核心部分。在本教學中，您將學習如何使用 Aspose.Tasks for .NET API 逐步 **管理資源的可用性**，從載入專案到在資源之間複製期間。

## 快速解答
- **可用期間的主要類別是什麼？** `AvailabilityPeriod` 位於 `Aspose.Tasks` 命名空間。  
- **可以清除現有的期間嗎？** 可以，呼叫 `resource.AvailabilityPeriods.Clear()`。  
- **如何新增期間？** 建立 `AvailabilityPeriod` 物件，然後使用 `Add` 或 `Insert`。  
- **能否將期間複製到其他資源？** 當然可以 – 使用 `CopyTo`，再將每個項目加入目標資源。  
- **正式環境需要授權嗎？** 需要，非試用部署必須購買 Aspose.Tasks 商業授權。

## 什麼是項目資源可用性？
項目資源可用性定義了資源可以指派至工作項目的日期與單位（容量百分比）。透過控制這些期間，可避免資源過度分配，提升排程精確度。

## 為什麼使用 Aspose.Tasks 來管理可用期間？
- **完整的 .NET 整合** – 無需 COM interop，純受管代碼。  
- **細緻的控制** – 可設定精確的開始/結束日期與分數單位。  
- **輕鬆複製** – 在資源之間搬移可用性資料，無需手動解析。  
- **效能最佳化** – 能高效處理大型 MPP 檔案。

## 前置條件
1. **Visual Studio** – 任一近期版本（2019、2022 或更新）。  
2. **Aspose.Tasks for .NET** – 從 [here](https://releases.aspose.com/tasks/net/) 下載。  
3. **基本的 C# 知識** – 需熟悉類別、集合與 LINQ。

## 匯入命名空間

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

我們同時匯入 Aspose.Tasks 的核心命名空間以及稍後會用到的 .NET 標準集合。

## 第一步：初始化專案與資源

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

此程式碼載入既有的 MPP 檔案，並取得要編輯可用性的資源（ID = 1）。

## 第二步：清除現有的可用期間

```csharp
resource.AvailabilityPeriods.Clear();
```

呼叫 Clear 會移除先前定義的所有期間，讓我們從空白開始。

## 第三步：新增可用期間

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

取得 `AvailabilityPeriod` 物件集合（假設已在其他地方定義 `GetPeriods` 輔助方法），並在集合可寫入時逐一加入。

## 第四步：插入新可用期間

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

若尚未存在，會在位置 1（第二個槽位）插入一個自訂的 2013 年期間。

## 第五步：顯示可用期間

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

簡易的 Console 輸出會顯示總筆數與每筆期間的詳細資訊，方便除錯或驗證。

## 第六步：將可用期間複製到其他資源

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

我們先將整個集合複製到陣列，清除目標資源的期間，然後重新填入。此範例示範如何在資源間複製可用性資料。

## 第七步：更新與移除可用期間

```csharp
// Update available units for a specific period
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Remove a specific period
otherResource.AvailabilityPeriods.Remove(period2013);
```

此段程式碼調整倒數第二筆期間的 `AvailableUnits`，並移除先前新增的 2013 年期間。

## 常見問題與解決方案
- **只讀集合錯誤** – 確認專案未以唯讀模式開啟，或在加入新項目前已呼叫 `resource.AvailabilityPeriods.Clear()`。  
- **期間重疊** – Aspose.Tasks 不會自動合併重疊區段，需自行撰寫邏輯偵測並處理。  
- **日期格式不正確** – 請始終使用 `DateTime` 物件；字串解析可能因地區設定產生錯誤。

## 常見問答

**Q: 可以為可用期間加入自訂欄位嗎？**  
A: 不行，Aspose.Tasks for .NET 的可用期間不支援自訂欄位。

**Q: 可用期間會與特定工作項目連結嗎？**  
A: 不會，它們僅與資源相關，定義資源一般可用於工作項目的時間。

**Q: 能否從外部來源匯入可用期間？**  
A: 可以，您可以從 CSV、XML 或資料庫讀取資料，建立 `AvailabilityPeriod` 物件後加入集合。

**Q: 如何處理重疊的可用期間？**  
A: 重疊不會自動解決，必須自行實作驗證邏輯以合併或拒絕衝突的期間。

**Q: 資源的可用期間數量有限制嗎？**  
A: 沒有硬性上限，但極大量的集合可能影響效能，建議盡可能合併期間。

## 結論

本指南涵蓋了使用 Aspose.Tasks for .NET 管理 **項目資源可用性** 所需的全部步驟——從初始化專案與清除舊資料，到新增、插入、複製、更新與移除可用期間。熟練這些操作可確保資源行事曆的準確性，讓專案排程更貼近現實。

---

**最後更新：** 2026-03-21  
**測試環境：** Aspose.Tasks for .NET（最新發行版）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}