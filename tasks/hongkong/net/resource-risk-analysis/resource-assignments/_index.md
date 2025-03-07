---
title: 在 Aspose.Tasks 中處理 MS Project 資源分配
linktitle: 在 Aspose.Tasks 中處理資源分配
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 有效地處理 MS Project 資源分配。此綜合指南為開發人員提供了逐步指導。
weight: 11
url: /zh-hant/net/resource-risk-analysis/resource-assignments/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中處理 MS Project 資源分配

## 介紹
在本教程中，我們將深入研究如何使用 Aspose.Tasks for .NET 有效地處理 Microsoft Project 資源分配。 Aspose.Tasks 是一個功能強大的 API，允許開發人員以程式設計方式操作 Microsoft Project 檔案。透過執行這些步驟，您將了解如何在 .NET 應用程式中有效管理資源分配。
## 先決條件
在我們開始之前，請確保您符合以下先決條件：

## 導入命名空間
首先，您需要匯入必要的命名空間以在 .NET 專案中使用 Aspose.Tasks 功能。這包括：

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;
```
現在讓我們將提供的範例分解為多個步驟，以便全面了解如何使用 Aspose.Tasks 處理 MS Project 資源分配。
## 第 1 步：設定項目和日曆設置
首先，建立一個新的專案實例並設定專案的日曆設定：
```csharp
var project = new Project();
var calendar = project.Get(Prj.Calendar);
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 4, 21, 17, 0, 0));
```
## 第 2 步：為專案新增任務
接下來，將新任務加入專案的根任務：
```csharp
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Duration, project.GetDuration(3));
```
## 步驟 3：建立資源分配並產生時間分段數據
現在，為任務建立新的資源分配並產生時間分段資料：
```csharp
var assignment = project.ResourceAssignments.Add(task, null);
assignment.TimephasedDataFromTaskDuration(calendar);
```
## 第 4 步：拆分任務
透過提供開始日期和完成日期將任務分成多個部分：
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 16, 17, 0, 0), calendar);
assignment.SplitTask(new DateTime(2000, 3, 18, 8, 0, 0), new DateTime(2000, 3, 18, 17, 0, 0), calendar);
```
## 第 5 步：設定工作輪廓
設定分配的工作輪廓類型：
```csharp
assignment.Set(Asn.WorkContour, WorkContourType.Contoured);
```
## 第 6 步：儲存項目
最後，儲存所做變更的項目文件：
```csharp
project.Save(DataDir + "CreateSplitTasks_out.xml", SaveFileFormat.Xml);
```
## 結論
總之，使用 Aspose.Tasks for .NET 處理 Microsoft Project 資源分配是一個簡單的過程。透過遵循本教程中概述的步驟，您可以有效地管理 .NET 應用程式中的資源分配。
## 常見問題解答
### Aspose.Tasks 可以處理複雜的專案結構嗎？
是的，Aspose.Tasks 提供了全面的功能來有效地處理複雜的專案結構。
### Aspose.Tasks 與不同版本的 Microsoft Project 相容嗎？
是的，Aspose.Tasks 支援各種版本的 Microsoft Project，確保不同環境之間的相容性。
### 我可以根據具體要求定制資源分配嗎？
當然，Aspose.Tasks 為資源分配提供了廣泛的自訂選項，以滿足特定的專案需求。
### Aspose.Tasks 是否支援將項目資料匯出為其他格式？
是的，Aspose.Tasks 允許將項目資料匯出為各種格式，例如 XML、PDF 和 HTML 等。
### Aspose.Tasks 用戶可以獲得技術支援嗎？
是的，Aspose 透過其論壇和其他管道提供專門的技術支持，以幫助用戶解決任何疑問或問題。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
