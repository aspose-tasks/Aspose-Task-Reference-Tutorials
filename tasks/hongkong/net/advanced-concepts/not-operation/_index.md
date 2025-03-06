---
title: 在 Aspose.Tasks 中使用 NOT 操作
linktitle: 在 Aspose.Tasks 中使用 NOT 操作
second_title: Aspose.Tasks .NET API
description: 了解如何在 Aspose.Tasks for .NET 中使用 NOT 操作來有效地過濾任務。立即增強您的專案管理能力。
weight: 20
url: /zh-hant/net/advanced-concepts/not-operation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中使用 NOT 操作

## 介紹

在本教程中，我們將探索如何在 Aspose.Tasks for .NET 中使用 NOT 操作。 NOT 操作讓我們可以反轉過濾條件，使我們能夠選擇不滿足指定條件的元素。

## 先決條件

在我們開始之前，請確保您具備以下條件：

1. Visual Studio：您需要安裝有效的 Visual Studio 才能完成程式碼範例。
2.  Aspose.Tasks for .NET：從下列位置下載並安裝 Aspose.Tasks for .NET 函式庫：[網站](https://releases.aspose.com/tasks/net/).
3. 對 C# 的基本了解：熟悉 C# 程式語言將有助於理解程式碼範例。

## 導入命名空間

首先，讓我們為我們的程式碼導入必要的命名空間：

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## 第 1 步：設定項目和任務

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

我們首先使用以下命令載入名為「Project2.mpp」的專案文件`Project`由Aspose.Tasks提供的類別。確保指定目錄中存在項目文件。

## 步驟2：收集專案任務

```csharp
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

在這裡，我們創建一個`ChildTasksCollector`物件收集項目內的所有任務。然後我們使用`TaskUtils.Apply`方法遍歷項目的任務層次結構並收集所有子任務。

## 步驟3：定義篩選條件

```csharp
var filter = new NullCondition();
```

我們使用名為的自訂類別定義過濾條件`NullCondition`。此條件選擇具有空值的任務。

## 步驟 4：應用 NOT 運算

```csharp
var condition = new Not<Task>(filter);
```

我們使用以下方法將 NOT 運算應用於篩選條件`Not<T>`由Aspose.Tasks提供的類別。這將反轉過濾條件，選擇不具有空值的任務。

## 第 5 步：過濾任務

```csharp
List<Task> collection = Filter(coll.Tasks, condition);
```

我們使用自訂篩選器根據應用條件過濾收集的任務`Filter`方法。此方法將任務的可枚舉集合和篩選條件作為輸入參數，並傳回符合條件的任務清單。

## 第 6 步：處理過濾的任務

```csharp
foreach (var task in collection)
{
    Console.WriteLine("Name: " + task.Get(Tsk.Name));

    //與其他屬性一起工作...
}
```

最後，我們迭代過濾後的任務並執行任何所需的操作。在此範例中，我們只是將任務名稱列印到控制台。

## 結論

在本教程中，我們學習如何在 Aspose.Tasks for .NET 中使用 NOT 操作。透過反轉過濾條件，我們可以選擇性地選擇不符合指定條件的元素，從而增強專案內任務操作的靈活性。

## 常見問題解答

### Q1：我可以將 Aspose.Tasks 與其他 .NET 框架一起使用嗎？

答：是的，Aspose.Tasks 支援各種 .NET 框架，包括 .NET Core、.NET Standard 和 .NET Framework。

### Q2：Aspose.Tasks 有免費試用版嗎？

答：是的，您可以從以下網站下載免費試用版：[網站](https://releases.aspose.com/).

### Q3：如何獲得 Aspose.Tasks 的支援？

答：您可以訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)如有任何支援查詢或技術援助。

### Q4：我可以購買 Aspose.Tasks 的臨時授權嗎？

答：是的，您可以從以下機構購買臨時許可證：[購買頁面](https://purchase.aspose.com/temporary-license/).

### Q5：在哪裡可以找到 Aspose.Tasks 的綜合文件？

答：您可以造訪以下網站上的完整文檔[Aspose.Tasks 文件頁面](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
