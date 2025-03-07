---
title: 使用 Aspose.Tasks 掌握項目數據
linktitle: 在 Aspose.Tasks 中處理項目數據
second_title: Aspose.Tasks .NET API
description: 了解如何使用 .NET 中的 Aspose.Tasks 操作 Microsoft Project 資料。輕鬆建立任務、新增資源和保存項目。
weight: 16
url: /zh-hant/net/project-management-integration/project-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 掌握項目數據

## 介紹
在本教學中，我們將探討如何使用 .NET 的 Aspose.Tasks 函式庫處理 Microsoft Project 資料。 Aspose.Tasks 提供了強大的功能來操作專案文件，包括建立任務、新增資源、設定屬性以及以各種格式儲存專案。
## 先決條件
在開始之前，請確保您具備以下條件：
1.  Aspose.Tasks 函式庫的安裝：從下列位置下載並安裝 Aspose.Tasks 函式庫：[這裡](https://releases.aspose.com/tasks/net/).
2. 開發環境：確保您已設定 .NET 開發環境。
3. C# 基礎：熟悉 C# 程式語言將會很有幫助。

## 導入命名空間
在使用 Aspose.Tasks 之前，將必要的命名空間匯入到您的專案中：
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Data.SqlClient;
using System.Diagnostics;
using System.Diagnostics.CodeAnalysis;
using System.Drawing.Printing;
using System.IO;
using System.Text;
using System.Text.RegularExpressions;
using Aspose.Tasks.Connectivity;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## 第 1 步：初始化項目對象
```csharp
//文檔目錄的路徑。
String DataDir = "Your Document Directory";
var project = new Project();
```
這一行初始化了一個新的實例`Project`類，代表 Microsoft Project 文件。
## 第2步：設定項目屬性
```csharp
project.Set(Prj.WorkFormat, TimeUnitType.Hour);
project.Set(Prj.NewTasksAreManual, false);
```
這些行示範如何設定項目的屬性，例如工作格式和任務建立模式。
## 第三步：新增任務
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
```
這裡，一個名為「Task 1」的新任務被加入到專案的根任務中。
## 步驟 4：設定任務屬性
```csharp
task1.Set(Tsk.Start, new DateTime(2020, 2, 5, 8, 0, 0));
task1.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task1.Set(Tsk.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
這些行設定「任務 1」的開始日期、持續時間和完成日期。
## 第 5 步：新增資源
```csharp
var workResource = project.Resources.Add("Work Resource");
workResource.Set(Rsc.Type, ResourceType.Work);
```
本部分示範如何為專案新增工作資源。
## 步驟 6：為任務分配資源
```csharp
var workResourceAssignment = project.ResourceAssignments.Add(task1, workResource);
workResourceAssignment.Set(Asn.Start, new DateTime(2020, 2, 5, 8, 0, 0));
workResourceAssignment.Set(Asn.Work, project.GetWork(8));
workResourceAssignment.Set(Asn.Finish, new DateTime(2020, 2, 5, 17, 0, 0));
```
這些行顯示如何將先前新增的工作資源指派給具有特定開始、工作和完成日期的「任務 1」。
## 第7步：保存項目
```csharp
project.Save(DataDir + "ProjectCreation_out.xml", SaveFileFormat.Xml);
```
最後，專案以 Microsoft Project XML 文件格式儲存。

## 結論
在本教學中，我們學習如何使用 .NET 中的 Aspose.Tasks 函式庫處理 Microsoft Project 資料。透過遵循逐步指南，您可以操作專案文件、新增任務、資源、向任務分配資源以及以各種格式儲存項目。
## 常見問題解答
### Q：Aspose.Tasks 可以處理複雜的專案結構嗎？
答：是的，Aspose.Tasks 為複雜的專案結構提供全面的支持，使您能夠有效地管理任務、資源和分配。
### Q：Aspose.Tasks 是否與不同版本的 Microsoft Project 相容？
答：Aspose.Tasks 支援多種 Microsoft Project 版本，確保不同環境之間的相容性。
### Q：我可以將 Aspose.Tasks 與其他 .NET 函式庫整合嗎？
答：當然，Aspose.Tasks 與其他 .NET 函式庫無縫集成，為您的開發專案提供靈活性。
### Q：Aspose.Tasks 是否提供對專案調度演算法的支援？
答：是的，Aspose.Tasks 包含先進的調度演算法，可協助您優化專案時程和資源利用率。
### Q：是否有針對 Aspose.Tasks 使用者的社群論壇？
答：是的，您可以找到有用的資源並與其他 Aspose.Tasks 使用者互動[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
