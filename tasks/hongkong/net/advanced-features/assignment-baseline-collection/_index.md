---
date: 2026-03-19
description: 學習如何讀取基準線，並使用 Aspose.Tasks for .NET 高效管理專案管理基準線。
linktitle: Project Management Baselines using Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: 使用 Aspose.Tasks 的項目管理基準線
url: /zh-hant/net/advanced-features/assignment-baseline-collection/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 的專案管理基準線

## 介紹

在專案管理中，基準線是用來比較計畫與實際執行情況的參考點。管理 **專案管理基準線**——尤其是指派基準線——有助於讓排程保持在正軌並確保問責。Aspose.Tasks for .NET 提供強大的 API，可程式化地建立、讀取、更新與刪除這些基準線。在本教學中，我們將示範如何使用 Aspose.Tasks for .NET 操作 Assignment Baseline Collections。

## 快速回答
- **指派基準線的主要目的為何？** 用於捕捉每個資源指派的計畫開始/結束日期。  
- **哪個 API 方法讀取基準線？** `Assignment.Baselines` 集合。  
- **是否可以以程式方式刪除基準線？** 可以，透過從 `Assignment.Baselines` 集合中移除項目。  
- **使用這些功能是否需要授權？** 生產環境必須擁有有效的 Aspose.Tasks 授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。

## 什麼是專案管理基準線？

專案管理基準線是於特定時間點所拍攝的排程、成本與範圍資料快照。它們作為衡量專案績效的基準，並用於在整個專案生命週期中識別差異。

## 為什麼要使用 Aspose.Tasks 來處理專案管理基準線？

- **完整控制權：** 可在不開啟 Microsoft Project 的情況下存取與操作基準線資料。  
- **自動化就緒：** 可將基準線處理整合至 CI/CD 管線或報表工具。  
- **跨格式支援：** 支援 MPP、XML 與 MPX 檔案，確保在不同專案檔案格式間具彈性。

## 前置條件

在開始本教學之前，請確保已具備以下前置條件：

1. 具備 C# 程式語言的基本知識。  
2. 系統已安裝 Visual Studio。  
3. 已安裝 Aspose.Tasks for .NET 程式庫。可從 [此處](https://releases.aspose.com/tasks/net/) 下載。

## 匯入命名空間

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using Aspose.Tasks;
```

## 步驟 1：載入專案檔案

首先，我們需要載入包含指派基準線的專案檔案。

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
```

## 如何讀取基準線？

接著，我們遍歷專案中的每個資源指派，以取得其各自的基準線。

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    var baselines = assignment.Baselines;
    Console.WriteLine("Count of assignment baselines: " + baselines.Count);
    Console.WriteLine("Parent Assignment: " + baselines.ParentAssignment);
    foreach (var baseline in baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
    }

    Console.WriteLine();
}
```

## 步驟 3：刪除指派基準線

在此步驟中，我們示範如何從專案中刪除所有指派基準線。

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    List<AssignmentBaseline> baselines = assignment.Baselines.ToList();
    foreach (var baseline in baselines)
    {
        assignment.Baselines.Remove(baseline);
    }
}
```

## 常見問題與解決方案

| 問題 | 解決方案 |
|-------|----------|
| **基準線顯示為空** | 確保專案檔實際包含已儲存的基準線；基準線不會自動產生。 |
| **存取 `baselines.ParentAssignment` 時發生 `NullReferenceException`** | 確認指派物件不為 null，且基準線已初始化。 |
| **大型專案的效能下降** | 將指派分批處理或使用 `Assignment.Id` 進行篩選，以限制範圍。 |

## 結論

有效管理指派基準線對於專案管理至關重要，可確保排程遵循並精確追蹤專案進度。使用 Aspose.Tasks for .NET，處理指派基準線變得輕鬆，為開發人員提供了簡化專案管理流程所需的工具。

## 常見問答

### Q1：Aspose.Tasks 能否處理不同專案檔案格式的指派基準線？

A1：是的，Aspose.Tasks 支援多種專案檔案格式，包括 MPP、XML 與 MPX，讓您能輕鬆在不同檔案類型間管理指派基準線。

### Q2：Aspose.Tasks 相容於所有 .NET Framework 版本嗎？

A2：Aspose.Tasks for .NET 相容於多個 .NET Framework 版本，確保開發人員在不同環境下皆能使用。

### Q3：我可以使用 Aspose.Tasks 以程式方式操作指派基準線嗎？

A3：當然可以，Aspose.Tasks 提供完整的 API，讓開發人員依專案需求以程式方式建立、讀取、更新與刪除指派基準線。

### Q4：Aspose.Tasks 是否提供開發人員的技術支援？

A4：是的，Aspose.Tasks 透過其社群論壇提供強大的技術支援，開發人員可在此尋求協助、分享知識並與同儕合作。

### Q5：我可以在購買前試用 Aspose.Tasks 嗎？

A5：可以，Aspose.Tasks 提供免費試用版，讓開發人員在決定購買前先行探索其功能與特性。

## 常見問題

**Q：如何讀取特定指派的基準線？**  
A：存取該指派的 `Assignment.Baselines` 集合，並如「如何讀取基準線？」章節所示遍歷即可。

**Q：是否可以為已存在的指派新增基準線？**  
A：可以，您可以建立 `AssignmentBaseline` 物件，設定其 `Start` 與 `Finish` 值，然後加入 `Assignment.Baselines` 集合。

**Q：刪除基準線會影響原始排程嗎？**  
A：刪除基準線僅會移除已儲存的快照，當前排程（實際日期）不會受到影響。

**Q：我可以將基準線資料匯出為 CSV 嗎？**  
A：雖然 Aspose.Tasks 未直接提供基準線的 CSV 匯出功能，但您可以遍歷集合，使用標準 .NET I/O 類別將資料寫入 CSV 檔案。

**Q：Aspose.Tasks 支援基準線比較報表嗎？**  
A：是的，您可以程式化比較基準線日期與實際日期，並使用任意報表庫產生自訂報表。

---

**最後更新：** 2026-03-19  
**測試環境：** Aspose.Tasks for .NET (latest)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}