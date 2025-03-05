---
title: Aspose.Tasks 中大綱程式碼的集合 MS 項目
linktitle: Aspose.Tasks中大綱程式碼的集合
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 收集 Microsoft Project 大綱程式碼。這個綜合教程提供了逐步說明。
type: docs
weight: 11
url: /zh-hant/net/outline-code-page-settings/outline-code-collection/
---
## 介紹
在本教學中，我們將探討如何使用 Aspose.Tasks for .NET 收集 Microsoft Project 大綱程式碼。我們將把該過程分解為逐步說明，以確保清晰度和理解性。
## 先決條件
在我們開始之前，請確保您具備以下條件：
1. Visual Studio：在您的系統上安裝 Visual Studio。
2.  Aspose.Tasks for .NET：從下列位置下載並安裝 Aspose.Tasks for .NET[這裡](https://releases.aspose.com/tasks/net/).
3. 對 C# 程式設計的基本了解：熟悉 C# 將會很有幫助。

## 導入命名空間
首先，匯入必要的命名空間以存取 C# 專案中的 Aspose.Tasks 功能。
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Util;
```
## 第 1 步：載入專案文件
首先使用以下命令載入 Microsoft Project 文件`Project`班級。
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes2003.mpp");
```
## 步驟2：收集大綱程式碼
建立一個收集器來收集專案任務中的大綱程式碼。
```csharp
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
```
## 第 3 步：迭代任務和大綱程式碼
迭代收集的任務和大綱程式碼，列印它們的詳細資料。
```csharp
for (var i = 0; i < collector.Tasks.Count; i++)
{
    var current = collector.Tasks[i];
    if (current.Get(Tsk.Id) == 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes for the " + current.Get(Tsk.Name) + " task.");
    Console.WriteLine("Count of outline codes: " + current.OutlineCodes.Count);
    foreach (var outlineCode in current.OutlineCodes)
    {
        Console.WriteLine("Field Id: " + outlineCode.FieldId);
        Console.WriteLine("Value Id: " + outlineCode.ValueId);
        Console.WriteLine("Value Guid: " + outlineCode.ValueGuid);
        Console.WriteLine();
    }
}
```
## 步驟 4：新增自訂大綱程式碼定義
將自訂大綱程式碼定義新增至專案。
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
project.OutlineCodes.Add(outlineCodeDefinition);
```
## 第 5 步：建立並插入大綱程式碼
建立大綱程式碼並將其插入任務中。
```csharp
var value = new OutlineValue { Type = OutlineValueType.Text, Value = "Val1", Description = "Descr1", ValueId = 1 };
outlineCodeDefinition.Values.Add(value);
var codeOne = new OutlineCode { FieldId = outlineCodeDefinition.FieldId, ValueId = 1, ValueGuid = value.ValueGuid.ToString("D").ToUpperInvariant() };
var task = project.RootTask.Children.GetByUid(2);
task.OutlineCodes.Add(codeOne);
```
## 第 6 步：操作大綱程式碼
根據需要操作大綱程式碼，例如插入、刪除或清除。
```csharp
//操縱範例
//…
//在正確位置插入帶有 2 的程式碼
task.OutlineCodes.Insert(2, code2);
//檢查代碼是否插入
Console.WriteLine("Is outline codes contains the inserted value: " + task.OutlineCodes.Contains(code2));
```

## 結論
在本教學中，我們學習如何使用 Aspose.Tasks for .NET 收集 Microsoft Project 大綱程式碼。透過執行這些步驟，您可以有效地管理專案中的大綱程式碼，從而增強組織性和清晰度。
## 常見問題解答
### Q：我可以將 Aspose.Tasks for .NET 與其他程式語言一起使用嗎？
答：是的，Aspose.Tasks for .NET 主要針對 .NET 平台，但它也透過 Aspose.Tasks for Cloud 提供對其他程式語言的支援。
### Q：Aspose.Tasks for .NET 可以處理的專案檔案的大小是否有任何限制？
答：Aspose.Tasks for .NET 可以有效地處理大型專案文件，但效能可能會根據文件的複雜性和大小而有所不同。
### Q：Aspose.Tasks for .NET 與最新版本的 Microsoft Project 相容嗎？
答：是的，Aspose.Tasks for .NET 支援各種版本的 Microsoft Project，包括最新版本。
### Q：使用 Aspose.Tasks for .NET 時可以自訂輸出格式嗎？
答：當然，Aspose.Tasks for .NET 提供了廣泛的選項，可根據您的要求自訂輸出格式。
### Q：在哪裡可以找到 Aspose.Tasks for .NET 的其他支援或資源？
答：您可以訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)任何有關 Aspose.Tasks for .NET 的協助或疑問。