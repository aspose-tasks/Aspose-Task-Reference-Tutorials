---
title: 使用 Aspose.Tasks for .NET 掌握 WBS 程式碼遮罩
linktitle: Aspose.Tasks 中 WBS 代碼遮罩的集合
second_title: Aspose.Tasks .NET API
description: 使用 Aspose.Tasks for .NET 增強專案管理。在這個綜合教程中學習如何輕鬆建立、管理和傳輸 WBS 程式碼遮罩。
weight: 15
url: /zh-hant/net/view-wbs-code-configuration/wbs-code-mask-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks for .NET 掌握 WBS 程式碼遮罩

## 介紹
在專案管理的動態世界中，有效地組織任務至關重要。 Aspose.Tasks for .NET 提供了一個強大的解決方案來輕鬆管理專案工作分解結構 (WBS) 程式碼。在本教程中，我們將深入研究 WBS 程式碼遮罩集合，探索如何使用 Aspose.Tasks for .NET 實作和操作它們。
## 先決條件
在我們開始此編碼之旅之前，請確保您具備以下先決條件：
- C# 程式語言的應用知識。
-  Aspose.Tasks for .NET 安裝在您的開發環境中。如果沒有，請下載[這裡](https://releases.aspose.com/tasks/net/).
- 像 Visual Studio 這樣的程式碼編輯器可提供無縫的程式設計體驗。
## 導入命名空間
首先，讓我們導入必要的命名空間：
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. 初始化專案和WBS程式碼定義
```csharp
var project = new Project();
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## 2. 定義 WBS 代碼掩碼
清除所有現有的程式碼遮罩並新增新的程式碼遮罩：
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Clear();
var mask1 = new WBSCodeMask();
mask1.Length = 2;
mask1.Separator = "-";
mask1.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask1);
var mask2 = new WBSCodeMask();
mask2.Length = 1;
mask2.Separator = "-";
mask2.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask2);
```
## 3. 顯示代碼遮罩訊息
```csharp
Console.WriteLine("WBS Code mask's count: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
Console.WriteLine("Is WBS Code mask collection read-only?: " + project.WBSCodeDefinition.CodeMaskCollection.IsReadOnly);
Console.WriteLine("Masks: ");
Console.WriteLine();
foreach (var wbsMask in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 4. 將任務加入項目中
```csharp
var task1 = project.RootTask.Children.Add("Task 1");
task1.Children.Add("Task 2");
project.Recalculate();
```
## 5. 檢索任務訊息
```csharp
IEnumerable<Task> childTasks = project.RootTask.SelectAllChildTasks();
foreach (var childTask in childTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## 6. 操縱程式碼掩碼
刪除程式碼遮罩並確保將其刪除：
```csharp
project.WBSCodeDefinition.CodeMaskCollection.Remove(mask2);
if (project.WBSCodeDefinition.CodeMaskCollection.Contains(mask2))
{
    throw new InvalidOperationException("WBS code mask wasn't removed.");
}
```
## 7. 將程式碼遮罩複製到另一個項目
```csharp
var otherProject = new Project();
otherProject.WBSCodeDefinition = new WBSCodeDefinition();
otherProject.WBSCodeDefinition.GenerateWBSCode = true;
otherProject.WBSCodeDefinition.VerifyUniqueness = true;
otherProject.WBSCodeDefinition.CodePrefix = "CRS-";
var masks = new WBSCodeMask[project.WBSCodeDefinition.CodeMaskCollection.Count];
project.WBSCodeDefinition.CodeMaskCollection.CopyTo(masks, 0);
foreach (var mask in masks)
{
    otherProject.WBSCodeDefinition.CodeMaskCollection.Add(mask);
}
```
## 8. 在另一個專案中顯示程式碼遮罩
```csharp
List<WBSCodeMask> wbsMasks = otherProject.WBSCodeDefinition.CodeMaskCollection.ToList();
foreach (var wbsMask in wbsMasks)
{
    Console.WriteLine("Length: " + wbsMask.Length);
    Console.WriteLine("Level: " + wbsMask.Level);
    Console.WriteLine("Separator: " + wbsMask.Separator);
    Console.WriteLine("Sequence: " + wbsMask.Sequence);
    Console.WriteLine();
}
```
## 9. 將任務加入其他項目
```csharp
var otherTask1 = otherProject.RootTask.Children.Add("Other task 1");
otherTask1.Children.Add("Other task 2");
otherProject.Recalculate();
```
## 10. 在其他項目中顯示 WBS 代碼
```csharp
Console.WriteLine("Print WBS codes of the other project: ");
IEnumerable<Task> otherChildTasks = otherProject.RootTask.SelectAllChildTasks();
foreach (var childTask in otherChildTasks)
{
    Console.WriteLine("Task name: " + childTask.Get(Tsk.Name));
    Console.WriteLine("Task WBS code: " + childTask.Get(Tsk.WBS));
}
```
## 結論
借助 Aspose.Tasks for .NET，管理 WBS 程式碼變得毫不費力。本教學涵蓋了 WBS 程式碼遮罩的建立、操作和傳輸，為您提供了增強專案管理體驗的全面指南。
## 常見問題解答
### Q：我可以將 Aspose.Tasks for .NET 與其他程式語言一起使用嗎？
答：Aspose.Tasks 主要支援 .NET 語言，但您可以探索與其他語言的互通性選項。
### Q：Aspose.Tasks for .NET 有試用版嗎？
答：是的，您可以下載試用版[這裡](https://releases.aspose.com/).
### Q：如何尋求協助或回報 Aspose.Tasks for .NET 問題？
答：訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)以尋求支持和討論。
### Q：WBS 代碼在專案管理中的用途是什麼？
答：WBS 代碼有助於分層組織和建置專案任務，為專案規劃提供系統方法。
### Q：我可以在 Aspose.Tasks for .NET 中自訂 WBS 程式碼的格式嗎？
答：當然，您可以使用 Aspose.Tasks for .NET 來完全控制 WBS 程式碼的格式和結構。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
