---
title: 在Aspose.Tasks中收集分割部分的MS項目
linktitle: Aspose.Tasks 中分割部分的集合
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 在 MS Project 中收集分割部分。這個綜合教程將逐步引導您完成整個過程。
weight: 19
url: /zh-hant/net/rate-recurring-tasks/split-part-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在Aspose.Tasks中收集分割部分的MS項目

## 介紹
在本教程中，我們將深入研究如何使用 Aspose.Tasks for .NET 在 MS Project 中收集分割部分。將任務拆分為多個部分可能是專案管理的重要方面，Aspose.Tasks 提供了有效處理此問題的便利方法。
## 先決條件
在我們開始之前，請確保您符合以下先決條件：
1. 安裝Aspose.Tasks for .NET：確保您已經安裝了Aspose.Tasks for .NET。您可以從以下位置下載：[這裡](https://releases.aspose.com/tasks/net/).
2. C# 的基本知識：熟悉 C# 程式語言將很有幫助，因為我們將用 C# 編寫程式碼片段。

## 導入命名空間
在您的 C# 專案中，包含必要的命名空間：
```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

```

## 第 1 步：設定您的項目
首先，在您首選的 IDE 中建立一個新項目，並確保正確引用 Aspose.Tasks for .NET。
## 第 2 步：初始化項目對象
```csharp
//文檔目錄的路徑。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Splits.mpp");
```
使用 MS Project 檔案的路徑初始化一個新的 Project 物件。
## 第 3 步：檢索任務並迭代拆分部分
```csharp
var task = project.RootTask.Children.GetById(1);
//迭代分割部分
Console.WriteLine("Iterate over split parts");
Console.WriteLine("Split parts count:" + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("Start: " + splitPart.Start);
    Console.WriteLine("Finish: " + splitPart.Finish);
}
```
從專案中檢索任務並迭代其拆分部分，列印出它們的開始和完成日期。
## 步驟 4：依索引取得拆分部分
```csharp
//透過索引取得零件
var split = task.SplitParts[0];
Console.WriteLine("Split start: " + split.Start);
```
按索引檢索特定的拆分部分並列印出其開始日期。

## 結論
管理 MS Project 檔案中的拆分部分可以顯著提高專案管理效率。 Aspose.Tasks for .NET 透過提供直覺的 API 來無縫處理分割任務，從而簡化了此流程。
## 常見問題解答
### Q：我可以在運行時動態分割任務嗎？
答：是的，您可以使用 Aspose.Tasks for .NET 以程式設計方式分割任務。
### Q：Aspose.Tasks 是否支援所有版本的 MS Project 檔案？
答：Aspose.Tasks支援各種版本的MS Project文件，確保不同平台的相容性。
### Q：是否有用於測試目的的試用版？
答：是的，您可以從以下位置取得免費試用版：[這裡](https://releases.aspose.com/)進行評估。
### Q：如何為我的專案獲得臨時許可證？
答：臨時許可證可以從[這裡](https://purchase.aspose.com/temporary-license/)供短期使用。
### Q：我可以在哪裡尋求有關 Aspose.Tasks 的協助或支援？
答：您可以造訪Aspose.Tasks論壇[這裡](https://forum.aspose.com/c/tasks/15)向社區或 Aspose 支援團隊尋求協助。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
