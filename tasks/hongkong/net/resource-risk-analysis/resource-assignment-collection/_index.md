---
title: Aspose.Tasks 中資源分配的集合
linktitle: Aspose.Tasks 中資源分配的集合
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 管理 Microsoft Project 中的資源分配。帶有程式碼範例的分步教程。
weight: 12
url: /zh-hant/net/resource-risk-analysis/resource-assignment-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中資源分配的集合

## 介紹
歡迎閱讀這個關於使用 Aspose.Tasks for .NET 在 Microsoft Project 中管理資源分配的綜合教學。在本教程中，我們將逐步深入研究該過程，確保您充分了解如何有效地操縱資源分配。無論您是經驗豐富的開發人員還是剛入門，本指南都將引導您完成您需要了解的所有內容。
## 先決條件
在我們深入研究程式碼之前，請確保您已進行以下設定：
1. 已安裝 Aspose.Tasks for .NET：請確定您的開發環境中安裝了 Aspose.Tasks for .NET。如果沒有，您可以從以下位置下載[這裡](https://releases.aspose.com/tasks/net/).
2. C# 基礎知識：本教學假設您對 C# 程式語言有基本了解。
3. Microsoft Project 檔案：準備好 Microsoft Project 檔案以用於測試目的。如果沒有，您可以建立一個範例文件。

## 導入命名空間
首先，讓我們導入必要的名稱空間：
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 第 1 步：載入專案文件
首先載入 Microsoft Project 檔案：
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TemplateResource2010.mpp");
```
## 步驟 2：新增任務和資源
現在，讓我們為專案新增任務和資源：
```csharp
var task = project.RootTask.Children.Add("Task 1");
var resource = project.Resources.Add("Resource 1");
```
## 步驟 3：將資源分配給任務
接下來，我們將資源分配給任務：
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
assignment.Set(Asn.Start, new DateTime(2019, 9, 23, 9, 0, 0));
assignment.Set(Asn.Work, project.GetWork(40));
assignment.Set(Asn.Finish, new DateTime(2019, 9, 27, 18, 0, 0));
```
## 步驟 4：處理不同的作業類型
您也可以處理涉及單位或成本的作業：
```csharp
var assignmentWithUnits = project.ResourceAssignments.Add(task, resource, 1d);
var assignmentWithCost = project.ResourceAssignments.Add(task, resource);
//設定單位和成本分配的屬性，與步驟 3 所示類似
```
## 第 5 步：列印作業
列印專案的作業：
```csharp
Console.WriteLine("Print assignments for the project: " + project.ResourceAssignments.ParentProject.Get(Prj.Name));
Console.WriteLine("Resource assignment count: " + project.ResourceAssignments.Count);
foreach (var resourceAssignment in project.ResourceAssignments)
{
    //列印作業詳細信息
}
```
## 第 6 步：透過 UID 檢索分配
您可以透過 UID 檢索分配：
```csharp
var assignmentByUid = project.ResourceAssignments.GetByUid(2);
Console.WriteLine("Assignment By Uid Start: " + assignmentByUid.Get(Asn.Start));
```
## 第7步：檢查唯讀狀態
驗證資源分配集合是否是唯讀的：
```csharp
Console.WriteLine("Is resource assignment collection read-only?: " + project.ResourceAssignments.IsReadOnly);
```
## 第 8 步：將集合轉換為列表並迭代
將集合轉換為列表並對其進行迭代：
```csharp
List<ResourceAssignment> resourceAssignments = project.ResourceAssignments.ToList();
foreach (var ra in resourceAssignments)
{
    Console.WriteLine(ra.ToString());
}
```

## 結論
恭喜！您已經了解如何使用 Aspose.Tasks for .NET 管理 Microsoft Project 中的資源分配。透過執行這些步驟，您可以有效地操縱任務和資源，使專案管理變得輕而易舉。
## 常見問題解答
### Q：我可以將 Aspose.Tasks for .NET 與不同版本的 Microsoft Project 檔案一起使用嗎？
答：是的，Aspose.Tasks for .NET 支援各種版本的 Microsoft Project 文件，包括 MPP、MPT 和 XML 格式。
### Q：購買 Aspose.Tasks for .NET 之前是否有試用版？
答：是的，您可以從以下位置獲得 Aspose.Tasks for .NET 的免費試用版：[這裡](https://releases.aspose.com/).
### Q：如果在使用 Aspose.Tasks for .NET 時遇到任何問題，如何獲得支援？
答：您可以從Aspose.Tasks論壇尋求支持[這裡](https://forum.aspose.com/c/tasks/15).
### Q：我可以使用 Aspose.Tasks for .NET 的臨時授權嗎？
答：是的，臨時許可證可用於評估目的。您可以從以下位置取得一個[這裡](https://purchase.aspose.com/temporary-license/).
### Q：在哪裡可以購買 Aspose.Tasks for .NET 的完整授權？
答：您可以從 Aspose 線上商店購買完整許可證[這裡](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
