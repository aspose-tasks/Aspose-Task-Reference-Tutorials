---
title: 使用 Aspose.Tasks for .NET 掌握時間分段資料處理
linktitle: 在 Aspose.Tasks 中處理時間分段數據
second_title: Aspose.Tasks .NET API
description: 探索 Aspose.Tasks for .NET 輕鬆處理時間分段資料、增強專案規劃並最佳化資源管理。 #Aspose #Tasks #MS 項目
type: docs
weight: 14
url: /zh-hant/net/text-view-configuration/timephased-data/
---
## 介紹
在專案管理領域，有效處理時間分段資料對於資源分配、成本估算和整體專案規劃至關重要。 Aspose.Tasks for .NET 提供了一個強大的解決方案來無縫處理自訂時間分段資料。本教學將引導您完成使用 Aspose.Tasks 處理時間分段資料的流程，使您能夠最佳化專案中的資源管理。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
- 對專案管理概念的基本了解。
- 安裝了 .NET 的 Aspose.Tasks。你可以下載它[這裡](https://releases.aspose.com/tasks/net/).
- 程式碼編輯器，例如 Visual Studio，用於實作提供的範例。
## 導入命名空間
在您的 .NET 專案中，請確保匯入必要的命名空間以利用 Aspose.Tasks 功能。在程式碼檔案的開頭新增以下行：
```csharp
    using Aspose.Tasks;
    using System;
    
```
現在，讓我們將提供的範例分解為多個步驟，以指導您使用 Aspose.Tasks 處理時間分段資料：
## 第 1 步：設定項目
```csharp
//文檔目錄的路徑。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp") { CalculationMode = CalculationMode.None };
```
在這裡，我們初始化一個新項目並設定其計算模式。
## 第 2 步：定義資源和任務
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
var costResource = project.Resources.Add("Cost Resource");
costResource.Set(Rsc.Type, ResourceType.Cost);
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2018, 1, 1, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```
建立工作和成本資源以及任務來模擬專案結構。
## 步驟 3：為任務分配資源
```csharp
var workAssignment = project.ResourceAssignments.Add(task, workResource);
workAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
var costAssignment = project.ResourceAssignments.Add(task, costResource);
costAssignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
將工時和成本資源分配給任務。
## 步驟 4：新增自訂時間分段數據
```csharp
workAssignment.TimephasedData.Clear();
var td1 = TimephasedData.CreateWorkTimephased(
    workAssignment.Get(Asn.Uid),
    new DateTime(2018, 1, 2, 8, 0, 0),
    new DateTime(2018, 1, 5, 17, 0, 0),
    TimeSpan.FromHours(40),
    TimeUnitType.Hour,
    TimephasedDataType.AssignmentRemainingWork);
workAssignment.TimephasedData.Add(td1);
//costAssignment 的類似步驟
costAssignment.TimephasedData.Clear();
```
為工作和成本分配新增自訂時間分段資料。
## 第 5 步：顯示時間分段數據
```csharp
Console.WriteLine("Print assignment timephased data:");
foreach (var assignment in project.ResourceAssignments)
{
    Console.WriteLine("Assignment UID: " + assignment.Get(Asn.Uid));
    foreach (var tds in assignment.TimephasedData)
    {
        //顯示有關每個時間分段資料條目的相關信息
    }
}
```
最後，顯示每個作業的時間分段資料。
#
## 結論
在 Aspose.Tasks 中有效處理時間分段資料為詳細的專案規劃和資源管理開闢了新的可能性。透過遵循本逐步指南，您已了解如何操作時間分段資料以滿足專案的特定需求。
## 經常問的問題
### 我可以將 Aspose.Tasks for .NET 與其他專案管理工具一起使用嗎？
Aspose.Tasks 主要是為.NET 開發而設計的。然而，它的功能可以補充各種專案管理工具。
### Aspose.Tasks for .NET 有沒有免費試用版？
是的，您可以探索免費試用[這裡](https://releases.aspose.com/).
### 如何獲得 Aspose.Tasks for .NET 支援？
訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)以獲得社區支持。
### 什麼是臨時許可證？如何取得臨時許可證？
了解臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
### 在哪裡可以找到 Aspose.Tasks for .NET 的文檔？
參考綜合[文件](https://reference.aspose.com/tasks/net/)獲取詳細資訊。