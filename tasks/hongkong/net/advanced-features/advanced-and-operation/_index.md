---
title: Aspose.Tasks 中的高階 AND 運算
linktitle: Aspose.Tasks 中的高階 AND 運算
second_title: Aspose.Tasks .NET API
description: 了解如何在 Aspose.Tasks for .NET 中執行進階 AND 運算，以根據多個條件有效篩選專案任務。
weight: 10
url: /zh-hant/net/advanced-features/advanced-and-operation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中的高階 AND 運算

## 介紹

在本教程中，我們將深入研究 Aspose.Tasks for .NET 中的高階 AND 操作，這是一個用於管理任務和專案的強大工具。我們將探索如何使用以下方法根據多個條件篩選專案任務`Util.And`班級。

## 先決條件

在我們開始之前，請確保您具備以下條件：

1. C# 程式語言的基礎知識。
2. 安裝了 .NET 的 Aspose.Tasks。如果沒有，您可以從以下位置下載[這裡](https://releases.aspose.com/tasks/net/).
3. 整合開發環境 (IDE)，例如 Visual Studio。

## 導入命名空間

首先，讓我們將必要的命名空間匯入到我們的 C# 專案中：

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;

```

## 步驟1：初始化項目並收集任務

首先初始化一個新的 Aspose.Tasks 專案並收集其中的所有任務：

```csharp
//文檔目錄的路徑。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

## 第2步：定義過濾條件

接下來，定義篩選條件。對於本範例，我們將建立兩個條件：一個用於篩選摘要任務，另一個用於篩選非空任務：

```csharp
var condition1 = new SummaryCondition();
var condition2 = new NotNullCondition();
```

## 步驟 3：使用 AND 運算組合條件

現在，使用以下組合條件`Util.And`類別來建立複合條件：

```csharp
var joinedCondition = new And<Task>(condition1, condition2);
```

## 步驟 4：應用條件和過濾任務

將組合條件應用於收集的任務並相應地過濾它們：

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

## 第5步：輸出過濾後的任務

最後輸出過濾後的任務：

```csharp
Console.WriteLine("Filtered tasks: ");
foreach (var task in collection)
{
    Console.WriteLine(" Name: " + task.Get(Tsk.Name));
    //可以在這裡進行額外的處理
}
```

## 結論

在本教程中，我們學習如何在 Aspose.Tasks for .NET 中執行高階 AND 運算。透過組合條件使用`Util.And`在類別中，我們可以根據多個標準有效地過濾任務。

## 常見問題解答

### Q1：什麼是 Aspose.Tasks for .NET？

答：Aspose.Tasks for .NET 是一個強大的 API，允許開發人員在 .NET 應用程式中以程式設計方式操作 Microsoft Project 檔案。

### Q2：我可以使用 Util.And 套用兩個以上的條件嗎？

答：是的，Util.And 可用於組合任意數量的條件來建立複雜的過濾條件。

### 問題 3：Aspose.Tasks for .NET 有沒有免費試用版？

答：是的，您可以從以下位置下載免費試用版：[這裡](https://releases.aspose.com/).

### 問題 4：在哪裡可以找到 Aspose.Tasks for .NET 的文件？

答：你可以找到文檔[這裡](https://reference.aspose.com/tasks/net/).

### Q5：如何獲得 Aspose.Tasks for .NET 支援？

答：您可以從 Aspose.Tasks 社群論壇獲得支持[這裡](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
