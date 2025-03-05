---
title: 掌握 Aspose.Tasks 中的時間分段資料收集
linktitle: Aspose.Tasks 中時間分段資料的收集
second_title: Aspose.Tasks .NET API
description: 探索 Aspose.Tasks for .NET 中的時間分段資料收集。逐步指南、常見問題等。立即增強您的專案管理能力！
type: docs
weight: 15
url: /zh-hant/net/text-view-configuration/timephased-data-collection/
---
## 介紹
您是否希望使用 Aspose.Tasks 在 .NET 應用程式中利用時間分段資料的強大功能？別再猶豫了！這個綜合指南將引導您完成使用 Aspose.Tasks for .NET 收集時間分段資料的過程，確保您充分利用這個強大的函式庫。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
1.  Aspose.Tasks for .NET Library：從以下位址下載並安裝此程式庫[Aspose.Tasks .NET 文檔](https://reference.aspose.com/tasks/net/).
2. .NET 開發環境：確保您已設定有效的 .NET 開發環境。
3. 您的文件目錄：將程式碼片段中的佔位符「您的文件目錄」替換為您的文件目錄的路徑。
## 導入命名空間
在您的 .NET 專案中，首先匯入必要的命名空間以利用 Aspose.Tasks 功能：
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. 建立專案和資源
```csharp
var project = new Project(DataDir + "Project1.mpp");
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
var resource2 = project.Resources.Add("Resource 2");
resource2.Set(Rsc.Type, ResourceType.Work);
```
## 2. 將任務加入項目中
```csharp
var task = project.RootTask.Children.Add("Task 1");
//設定任務屬性...
var task2 = project.RootTask.Children.Add("Task 2");
//設定任務2屬性...
```
## 3. 為任務分配資源
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
//設定分配屬性...
var assignment2 = project.ResourceAssignments.Add(task2, resource2);
//設定分配 2 屬性...
```
## 4. 使用時間分段數據
```csharp
//設定輪廓工作輪廓
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
//檢查時間分段資料收集是否為唯讀
Console.WriteLine("Is timephased data collection read-only?: " + assignment.TimephasedData.IsReadOnly);
//清除生成的時間分段數據
assignment.TimephasedData.Clear();
//建立並新增時間分段數據
var td = new TimephasedData
{
    //設定時間分段資料屬性...
};
assignment.TimephasedData.Add(td);
//新增時間分段資料列表
var list = new List<TimephasedData>();
//將更多時間分段資料項新增至清單...
assignment.TimephasedData.AddRange(list);
//按類型和日期範圍過濾時間分段數據
Console.WriteLine("Print filtered timephased data:");
IList<TimephasedData> filteredTds = assignment.TimephasedData.SelectBetweenStartAndFinish(
    TimephasedDataType.AssignmentRemainingWork,
    new DateTime(2019, 11, 11, 0, 0, 0),
    new DateTime(2019, 11, 13));
//列印過濾後的時間分段資料...
```
## 5. 操作時間分段數據
```csharp
//新增錯誤的時間分段資料項，然後將其刪除
var td4 = new TimephasedData
{
    //設定錯誤的時間分段資料屬性...
};
assignment.TimephasedData.Add(td4);
//刪除錯誤的時間分段資料項
if (assignment.TimephasedData.Contains(td4))
{
    assignment.TimephasedData.Remove(td4);
}
//迭代所有時間分段項目
Console.WriteLine("Print all timephased items:");
foreach (var item in assignment.TimephasedData)
{
    //列印按時間分段的項目詳細資料...
}
```
## 6. 將時間分段資料複製到另一個作業
```csharp
//將時間分段資料複製到另一個作業
var timephasedDatas = new TimephasedData[assignment.TimephasedData.Count];
assignment.TimephasedData.CopyTo(timephasedDatas, 0);
assignment2.TimephasedData.Clear();
foreach (var data in timephasedDatas)
{
    assignment2.TimephasedData.Add(data);
}
//將集合轉換為普通列表
List<TimephasedData> tds = assignment.TimephasedData.ToList();
//一項一項刪除時間分段資料項
foreach (var timephasedData in tds)
{
    assignment.TimephasedData.Remove(timephasedData);
}
```
## 結論
總之，本教學提供了使用 Aspose.Tasks for .NET 收集時間分段資料的詳細演練。透過執行這些步驟，您可以將此功能無縫整合到您的專案中，從而實現有效的時間追蹤和資源管理。
## 經常問的問題
### 我可以將 Aspose.Tasks for .NET 與其他專案管理工具一起使用嗎？
是的，Aspose.Tasks for .NET 旨在與流行的專案管理工具配合使用，並支援各種檔案格式。
### 我可以使用 Aspose.Tasks 管理的資源和任務數量是否有限制？
Aspose.Tasks可以處理不同規模的項目，並且對資源和任務的數量沒有嚴格的限制。
### 對於與 Aspose.Tasks for .NET 相關的任何問題或查詢，如何獲得支援？
如需支持，請訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)與社區聯繫並獲得協助。
### 我可以在購買之前試用 Aspose.Tasks for .NET 嗎？
是的，您可以透過造訪 Aspose.Tasks for .NET 來探索 Aspose.Tasks for .NET 的功能[免費試用](https://releases.aspose.com/).
### 在哪裡可以購買 Aspose.Tasks for .NET 的授權？
您可以購買 Aspose.Tasks for .NET 的許可證[這裡](https://purchase.aspose.com/buy).