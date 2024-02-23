---
title: 使用 Aspose.Tasks 掌握 MS 項目過濾標準
linktitle: Aspose.Tasks 中的篩選條件
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 在 MS Project 中實作篩選條件。透過有針對性的數據分析提高專案管理效率。
type: docs
weight: 18
url: /zh-hant/net/tasks-project-management/filter-criteria/
---
## 介紹
在專案管理領域，Microsoft Project 是一款強大的工具，提供大量功能來幫助專案規劃者和經理。其眾多功能包括過濾專案資料的能力，使用戶能夠專注於專案任務的特定方面。然而，如果沒有正確的指導，掌握這些過濾功能可能是一項艱鉅的任務。本教程旨在透過提供使用 Aspose.Tasks for .NET 在 MS Project 中實現標準過濾器的逐步指南來揭開該過程的神秘面紗。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
1. 對 C# 的基本了解：要掌握本教學中介紹的概念，需要熟悉 C# 程式語言。
2. 安裝 Aspose.Tasks for .NET：請確定您的開發環境中安裝了 Aspose.Tasks for .NET。你可以下載它[這裡](https://releases.aspose.com/tasks/net/).
3. Microsoft Project 檔案：準備好一個Microsoft Project 檔案（例如Project2003.mpp），您將使用它來實現過濾條件。

## 導入命名空間
首先，您需要匯入必要的命名空間以使用 Aspose.Tasks for .NET。按著這些次序：

```csharp
using Aspose.Tasks;
using System;
using System.Linq;

```

## 第 1 步：載入專案文件
```csharp
var project = new Project(DataDir + "Project2003.mpp");
```
說明：這行程式碼初始化了一個新的實例`Project`類別並載入由其路徑指定的 Microsoft Project 檔案。
## 第 2 步：檢索任務過濾器
```csharp
var filter = project.TaskFilters.ToList()[1];
```
說明：在這裡，我們從專案中檢索任務過濾器。調整索引（`[1]`）根據您的要求選擇所需的過濾器。
## 第 3 步：顯示條件行
```csharp
Console.WriteLine("Count of criteria rows: " + filter.Criteria.CriteriaRows.Count);
foreach (var row in filter.Criteria.CriteriaRows)
{
    Console.WriteLine("Field: " + row.Field);
    Console.WriteLine("Operation: " + row.Operation);
    Console.WriteLine("Test: " + row.Test);
    var values = row.Values.Where(c => c != null).ToArray();
    if (values.Length == 0)
    {
        continue;
    }
    Console.WriteLine("Value{0}: {1}", values.Length == 1 ? "" : "s", string.Join(", ", values));
}
```
說明：本部分迭代過濾器的每個條件行並顯示其欄位、操作、測試和值（如果有）。
## 第 4 步：列印過濾條件
```csharp
Console.WriteLine(filter.Criteria.Operation.ToString());
```
說明： 列印過濾條件的操作。
## 第 5 步：顯示標準詳細信息
```csharp
var criteria1 = filter.Criteria.CriteriaRows[0];
Console.WriteLine("Criteria filter 1:");
Console.WriteLine(criteria1.ToString());
var criteria2 = filter.Criteria.CriteriaRows[1];
Console.WriteLine(criteria2.Operation.ToString());
Console.WriteLine(criteria2.CriteriaRows.Count);
Console.WriteLine("Criteria filter 2:");
Console.WriteLine(criteria2.ToString());
var criteria21 = criteria2.CriteriaRows[0];
Console.WriteLine("Criteria filter 21:");
Console.WriteLine(criteria21.ToString());
var criteria22 = criteria2.CriteriaRows[1];
Console.WriteLine("Criteria filter 22:");
Console.WriteLine(criteria22.ToString());
```
說明：此部分檢索並顯示有關每個條件行的詳細信息，提供對過濾器配置的深入了解。

## 結論
使用 Aspose.Tasks for .NET 掌握 MS Project 中的過濾條件是一項寶貴的技能，可顯著提高專案管理效率。透過學習本教程，您已經了解如何以程式設計方式操作篩選條件，從而使您能夠根據您的特定需求自訂專案視圖。
## 常見問題解答
### Q：我可以在 MS Project 中同時套用多個過濾器嗎？
答：是的，您可以組合多個過濾器來進一步細化您的專案資料。
### Q：Aspose.Tasks 支援舊版的 Microsoft Project 檔案嗎？
答：是的，Aspose.Tasks 提供向後相容性，允許您使用各種版本的 Microsoft Project 檔案。
### Q：Aspose.Tasks 與其他 .NET 框架相容嗎？
答：Aspose.Tasks 支援 .NET Framework、.NET Core 和 .NET Standard，確保跨不同開發環境的彈性。
### Q：我可以根據動態條件自訂篩選條件嗎？
答：當然，您可以根據動態參數以程式方式調整篩選條件，從而實現自適應項目資料分析。
### Q：如果遇到 Aspose.Tasks 問題，我可以在哪裡尋求協助？
答：您可以訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)尋求社群支援或直接聯繫 Aspose.Tasks 支援以獲得個人化協助。