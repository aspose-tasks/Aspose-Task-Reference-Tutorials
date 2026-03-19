---
date: 2026-03-19
description: 學習如何使用 Aspose.Tasks for .NET 設定專案基準線並有效管理指派基準線，確保專案進度的精確追蹤。
linktitle: Managing Assignment Baseline in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: 設定專案基準 – 在 Aspose.Tasks 中管理指派基準
url: /zh-hant/net/advanced-features/assignment-baseline/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 設定專案基準 – 在 Aspose.Tasks 中管理指派基準

## 介紹

在處理專案管理工作時，**設定專案基準**是衡量實際進度與原始計畫之間差異的關鍵。Aspose.Tasks for .NET 不僅讓您**設定專案基準**，還提供完整的指派基準控制，讓您能精準追蹤績效。本教學將逐步說明整個流程——載入專案、設定基準、讀取指派基準資料，以及比較基準——讓您能自信地監控專案。

## 快速解答
- **「設定專案基準」是什麼意思？** 它會記錄原始的排程與成本資料，以便之後與實際執行情況比較。  
- **哪個 API 方法用於設定基準？** `Project.SetBaseline(BaselineType.Baseline)`。  
- **指派基準需要額外呼叫嗎？** 不需要，設定專案基準時會自動儲存指派基準。  
- **支援哪些格式？** MPP、XML、MPX 等，皆可透過 Aspose.Tasks 讀寫。  
- **正式環境需要授權嗎？** 需要，非試用版必須使用商業授權。

## 前置條件

在開始之前，請確保您已具備：

- 基本的 C# 程式設計知識。  
- Visual Studio（任一近期版本）。  
- 已將 Aspose.Tasks for .NET 套件加入專案。您可以從 [此處](https://releases.aspose.com/tasks/net/) 下載。  
- 一個 MPP 格式的專案檔（例如 `AssignmentBaseline2007.mpp`）。

## 匯入命名空間

在 C# 檔案的最上方加入必要的命名空間，讓編譯器能找到 Aspose.Tasks 類別。

```csharp
using Aspose.Tasks;
using System;
```

## 步驟 1：載入專案並設定專案基準

首先，載入既有的 MPP 檔，然後呼叫 `SetBaseline` 為整個專案**設定專案基準**。

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## 步驟 2：讀取指派基準資訊

基準設定完成後，每個資源指派都會有自己的基準紀錄。以下迴圈會擷取並列印這些細節，包括開始/結束日期、成本、工時，以及任何時間相位資料。

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var baseline in assignment.Baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
        Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
        Console.WriteLine("Bcwp: " + baseline.Bcwp);
        Console.WriteLine("Bcws: " + baseline.Bcws);
        Console.WriteLine("Cost: " + baseline.Cost);
        Console.WriteLine("Work: " + baseline.Work);
        if (baseline.TimephasedData != null)
        {
            foreach (var td in baseline.TimephasedData)
            {
                Console.WriteLine("TD Start: " + td.Start);
                Console.WriteLine("TD Finish: " + td.Finish);
                Console.WriteLine("TD Timephased Data Type: " + td.TimephasedDataType);
                Console.WriteLine();
            }
        }

        Console.WriteLine();
    }

    Console.WriteLine();
}
```

## 步驟 3：比較指派基準

您可以使用內建的相等與比較運算子，比對不同指派的基準。這在需要偵測排程變動或成本超支時非常實用。

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Check baseline equality
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Check baseline comparison
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Display baseline hashcodes
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## 常見問題與解決方案

| 問題 | 發生原因 | 解決方法 |
|------|----------|----------|
| **基準資料顯示為空** | 專案檔以唯讀模式開啟，或根本未設定基準。 | 在讀取指派基準前先呼叫 `project.SetBaseline(BaselineType.Baseline)`。 |
| **`NullReferenceException` 發生於 `TimephasedData`** | 並非所有基準都包含時間相位項目。 | 始終檢查 `baseline.TimephasedData != null`（如程式碼所示）。 |
| **UID 取得錯誤** | 不同檔案版本的 UID 可能不同。 | 使用正確的 UID 呼叫 `ResourceAssignments.GetByUid`，或遍歷以找到所需的指派。 |

## 常見問答

**Q:** Aspose.Tasks 能處理單一指派的多個基準嗎？  
**A:** 能，Aspose.Tasks 支援每個指派擁有多個基準，讓您能全面追蹤專案隨時間的進度變化。

**Q:** Aspose.Tasks 是否相容除 MPP 之外的其他專案檔格式？  
**A:** 能，Aspose.Tasks 支援多種專案檔格式，包括 XML、MPX 以及 MPP，確保與各種專案管理工具的相容性。

**Q:** 我可以使用 Aspose.Tasks 以程式方式修改基準資訊嗎？  
**A:** 當然可以，Aspose.Tasks 提供完整的 API，讓您依專案需求動態修改基準資訊，提供彈性與控制力。

**Q:** Aspose.Tasks 是否提供開發人員的文件與支援資源？  
**A:** 有，開發人員可在 Aspose.Tasks 官方網站取得完整文件、教學範例與論壇，協助順利整合與除錯。

**Q:** 有提供 Aspose.Tasks for .NET 的試用版嗎？  
**A:** 有，開發人員可從 [此處](https://releases.aspose.com/) 取得 Aspose.Tasks for .NET 的免費試用版，先行評估功能與效能再決定購買。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-03-19  
**測試環境：** Aspose.Tasks 24.12 for .NET  
**作者：** Aspose  

---