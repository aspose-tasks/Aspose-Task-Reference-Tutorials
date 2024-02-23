---
title: 使用 Aspose.Tasks 高效管理 MS 專案過濾器
linktitle: 在 Aspose.Tasks 中管理篩選器集合
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 有效管理篩選器 MS Project 集合。
type: docs
weight: 17
url: /zh-hant/net/tasks-project-management/filter-collection/
---
## 介紹
在本教程中，我們將探索如何使用 Aspose.Tasks for .NET 有效管理篩選器 MS Project 集合。管理過濾器對於有效組織和分析專案資料至關重要。 Aspose.Tasks 提供了強大的功能來無縫處理任務和資源過濾器。
## 先決條件
在我們開始之前，請確保您符合以下先決條件：
1. 安裝 Aspose.Tasks for .NET：從下列位置下載並安裝 Aspose.Tasks for .NET[下載連結](https://releases.aspose.com/tasks/net/).
2. 存取 .NET 開發環境：確保您已設定 .NET 開發環境以使用 Aspose.Tasks。

## 導入命名空間
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## 第 1 步：載入專案文件
```csharp
//文檔目錄的路徑。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadFilterDefinitionData.mpp");
```
## 第 2 步：迭代任務過濾器
```csharp
Console.WriteLine("Print task filters of {0} project: ", project.Get(Prj.Name));
Console.WriteLine("Task Filters Count: " + project.TaskFilters.Count);
foreach (var filter in project.TaskFilters)
{
    Console.WriteLine("All Tasks: " + filter.Name);
    Console.WriteLine("Task Item: " + filter.FilterType);
    Console.WriteLine("Task Filters Show In Menu: " + filter.ShowInMenu);
    Console.WriteLine("Task filter ShowRelatedSummaryRows: " + filter.ShowRelatedSummaryRows);
    Console.WriteLine();
}
```
## 第 3 步：迭代資源過濾器
```csharp
Console.WriteLine("Project.ResourceFilters count: " + project.ResourceFilters.Count);
foreach (var filter in project.ResourceFilters)
{
    Console.WriteLine("Resource Filter Item Type: Item.ResourceType: " + filter.FilterType);
    Console.WriteLine("Resource filter ShowInMenu" + filter.ShowInMenu);
    Console.WriteLine("Resource filter ShowRelatedSummaryRows: " + filter.ShowRelatedSummaryRows);
}
```
## 第 4 步：清除並複製過濾器
```csharp
var otherProject = new Project(DataDir + "Blank2010.mpp");
//清除其他項目的過濾器
otherProject.TaskFilters.Clear();
//將過濾器複製到其他項目
var filters = new Filter[project.TaskFilters.Count];
project.TaskFilters.CopyTo(filters, 0);
foreach (var filter in filters)
{
    otherProject.TaskFilters.Add(filter);
}
```
## 第 5 步：新增自訂任務過濾器
```csharp
//新增自訂任務過濾器
var customFilter = new Filter();
customFilter.Name = "Custom Filter";
customFilter.ShowInMenu = true;
customFilter.ShowRelatedSummaryRows = true;
if (!otherProject.TaskFilters.Contains(customFilter))
{
    if (!otherProject.TaskFilters.IsReadOnly)
    {
        otherProject.TaskFilters.Add(customFilter);
    }
}
```
## 第 6 步：刪除所有過濾器
```csharp
//刪除所有過濾器
List<Filter> filtersToDelete = otherProject.TaskFilters.ToList();
foreach (var filter in filtersToDelete)
{
    otherProject.TaskFilters.Remove(filter);
}
```
透過執行下列步驟，您可以使用 Aspose.Tasks for .NET 高效管理篩選器 MS Project 集合。

## 結論
有效管理 MS Project 集合中的篩選器對於組織和分析專案資料至關重要。 Aspose.Tasks for .NET 提供了全面的功能來無縫處理任務和資源過濾器，使開發人員能夠有效地簡化專案管理任務。
## 常見問題解答
### Q：Aspose.Tasks 可以處理複雜的專案結構嗎？
答：Aspose.Tasks 提供強大的功能來處理各種專案結構，包括複雜的專案結構，確保全面的專案管理能力。
### Q：Aspose.Tasks 是否與不同版本的 MS Project 檔案相容？
答：是的，Aspose.Tasks 支援多種 MS Project 檔案格式，確保不同版本之間的相容性。
### Q：我可以根據具體專案需求客製化過濾器嗎？
答：當然！ Aspose.Tasks 讓開發人員可以建立適合獨特專案需求的自訂過濾器，從而提高靈活性和效率。
### Q：Aspose.Tasks 是否提供文件和支援資源？
答：是的，Aspose.Tasks 提供了廣泛的文件、教學課程和專門的支援論壇，以幫助開發人員完成專案實施的每一步。
### Q：Aspose.Tasks 有試用版嗎？
答：是的，開發人員可以在做出購買決定之前訪問 Aspose.Tasks 的免費試用版來探索其功能。