---
title: 在 Aspose.Tasks 中管理分配基線
linktitle: 在 Aspose.Tasks 中管理分配基線
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 高效管理分配基線，確保準確追蹤專案進度和績效。
weight: 14
url: /zh-hant/net/advanced-features/assignment-baseline/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中管理分配基線

## 介紹

在執行專案管理任務時，管理分配基準對於準確追蹤進度至關重要。 Aspose.Tasks for .NET 提供了一套全面的工具來有效地處理分配基準。在本教程中，我們將逐步深入研究管理分配基線的過程。

## 先決條件

在我們開始之前，請確保您符合以下先決條件：

- C# 程式語言的基礎知識。
- Visual Studio 安裝在您的系統上。
- Aspose.Tasks for .NET 函式庫已新增至您的專案中。您可以從以下位置下載：[這裡](https://releases.aspose.com/tasks/net/).
- 存取 MPP 格式的專案文件。

## 導入命名空間

要開始使用 Aspose.Tasks，您需要將必要的命名空間匯入到您的 C# 專案中。在 C# 檔案的開頭新增以下命名空間：

```csharp
using Aspose.Tasks;
using System;


```

## 第 1 步：載入項目並設定基線

首先，使用以下命令載入專案文件`Project`來自 Aspose.Tasks 的類別。然後，使用以下命令設定項目的基線類型`SetBaseline`方法。

```csharp
//文檔目錄的路徑。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## 第 2 步：讀取作業基線信息

迭代專案中的每個資源分配並檢索每個分配的基線資訊。

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

## 第 3 步：檢查基線相等性

使用 Aspose.Tasks 提供的各種比較方法來比較不同作業的基準資訊。

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

//檢查基線相等性
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

//檢查基線比較
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

//顯示基線哈希碼
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## 結論

管理分配基準是專案管理不可或缺的一部分，可以準確追蹤進度和績效。透過 Aspose.Tasks for .NET，處理分配基準變得簡化且高效，為開發人員提供了增強專案管理工作流程的強大工具。

## 常見問題解答

### Q1：Aspose.Tasks 可以處理單一作業的多個基準嗎？

A1：是的，Aspose.Tasks 支援每個任務的多個基線，允許隨著時間的推移全面追蹤專案進度。

### Q2：Aspose.Tasks 是否相容於 MPP 以外的各種專案文件格式？

A2：是的，Aspose.Tasks支援多種專案文件格式，包括XML、MPX和MPP，確保與各種專案管理工具的兼容性。

### Q3：我可以使用 Aspose.Tasks 以程式方式修改基線資訊嗎？

A3：當然，Aspose.Tasks 提供了廣泛的 API，可以根據專案要求動態修改基線信息，從而提供對專案管理流程的靈活性和控制。

### Q4：Aspose.Tasks 是否為開發人員提供文件和支援資源？

A4：是的，開發人員可以在 Aspose.Tasks 網站上存取全面的文件、教學和論壇，從而促進順利整合和故障排除。

### Q5：Aspose.Tasks for .NET 有試用版嗎？

 A5：是的，開發人員可以從以下位置取得 Aspose.Tasks for .NET 的免費試用版：[這裡](https://releases.aspose.com/)，使他們能夠在做出購買決定之前評估其特性和功能。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
