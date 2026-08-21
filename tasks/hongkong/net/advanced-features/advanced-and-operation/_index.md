---
date: 2026-03-16
description: 學習如何結合多個條件，並使用 Aspose.Tasks for .NET 中的進階 AND 運算來篩選專案任務。
linktitle: Advanced AND Operation in Aspise.Tasks
second_title: Aspose.Tasks .NET API
title: 如何在 Aspose.Tasks 中使用進階 AND 運算結合多個條件
url: /zh-hant/net/advanced-features/advanced-and-operation/
weight: 10
---

ose.Tasks for .NET (latest) -> keep.

**Author:** Aspose -> keep.

Close shortcodes.

Then backtop button shortcode.

All good.

Now produce final content with same markdown structure.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks 中的進階 AND 運算

## 簡介

在本教學中，您將了解如何在 Aspose.Tasks for .NET 中使用 *進階 AND 運算* **結合多個條件**。完成本指南後，您將能夠根據多項條件 **篩選專案任務**——這在需要一次過 **篩選任務**（例如彙總項目、非空條目或自訂旗標）時相當重要。

## 快速解答
- **Advanced AND 運算的功能是什麼？** 它會合併兩個或多個篩選條件，僅返回同時符合 *全部* 條件的任務。  
- **哪個類別負責合併條件？** `Util.And<T>`（在 API 中以 `And<T>` 形式公開）。  
- **是否需要特殊授權？** 正式使用需購買一般的 Aspose.Tasks 授權；亦提供免費試用版。  
- **可以串接超過兩個條件嗎？** 可以——`And<T>` 可接受任意數量的條件。  
- **支援哪個版本的 .NET？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。

## 什麼是 Aspose.Tasks 中的「結合多個條件」？

結合多個條件是指建立一個複合篩選器，同時對每個任務套用多項規則。此方式比起多次遍歷任務清單更為高效，因為函式庫一次即可套用所有邏輯。

## 為什麼要使用進階 AND 運算？

- **效能：** 減少對任務集合的遍歷次數。  
- **可讀性：** 讓篩選邏輯保持宣告式，易於維護。  
- **彈性：** 可將內建條件（例如 `SummaryCondition`）與自訂謂詞混合使用。  

## 先決條件

在開始之前，請確保您已具備：

1. 具備 C# 程式設計的基礎知識。  
2. 已安裝 Aspose.Tasks for .NET。若尚未下載，請前往 **[here](https://releases.aspose.com/tasks/net/)** 取得。  
3. 使用如 Visual Studio 等任一版本的 IDE。  

## 匯入命名空間

首先，匯入提供任務模型與工具類別的命名空間：

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;
```

## 步驟 1：初始化專案並收集任務

我們將建立 `Project` 實例，並使用 `ChildTasksCollector` 收集檔案中的所有任務。此示範 **如何使用 collector** 取得平面任務清單。

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

## 步驟 2：定義篩選條件

在此我們定義欲套用的個別條件。此範例中，我們 **篩選彙總任務**，同時確保任務物件不為 null。

```csharp
var condition1 = new SummaryCondition();
var condition2 = new NotNullCondition();
```

## 步驟 3：使用 AND 運算結合條件

現在，我們使用 `And<T>` 類別 **結合多個條件**。這即是 **進階 AND 運算** 的核心。

```csharp
var joinedCondition = new And<Task>(condition1, condition2);
```

## 步驟 4：套用條件並篩選任務

當複合條件準備好後，我們呼叫 `Filter` 以 **根據結合的邏輯篩選專案任務**。

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

## 步驟 5：輸出篩選後的任務

最後，我們顯示符合 **全部** 條件的任務。您可以將 `Console.WriteLine` 呼叫替換為任何自訂的處理程序。

```csharp
Console.WriteLine("Filtered tasks: ");
foreach (var task in collection)
{
    Console.WriteLine(" Name: " + task.Get(Tsk.Name));
    // Additional processing can be done here
}
```

## 常見問題與解決方案

| 問題 | 發生原因 | 快速解決方案 |
|------|----------|--------------|
| `Filter` 方法未找到 | 缺少 `using Aspose.Tasks.Util;` | 確保已匯入 Util 命名空間（請參考匯入命名空間）。 |
| 未返回任何任務 | 條件過於嚴格（例如篩選彙總任務但實際上不存在） | 確認專案確實包含彙總任務，或調整條件。 |
| NullReferenceException | `coll.Tasks` 包含 null 條目 | `NotNullCondition` 已經防護此情況，請保留於 AND 鏈中。 |

## 常見問答

### Q1：什麼是 Aspose.Tasks for .NET？

A：Aspose.Tasks for .NET 是一套功能強大的 API，讓開發人員能在 .NET 應用程式中以程式方式操作 Microsoft Project 檔案。

### Q2：可以使用 Util.And 套用超過兩個條件嗎？

A：可以，Util.And 可用於結合任意數量的條件，以建立複雜的篩選標準。

### Q3：是否提供 Aspose.Tasks for .NET 的免費試用？

A：可以，您可從 **[here](https://releases.aspose.com/)** 下載免費試用版。

### Q4：在哪裡可以找到 Aspose.Tasks for .NET 的文件？

A：文件可於 **[here](https://reference.aspose.com/tasks/net/)** 取得。

### Q5：如何取得 Aspose.Tasks for .NET 的支援？

A：您可在 Aspose.Tasks 社群論壇 **[here](https://forum.aspose.com/c/tasks/15)** 獲得支援。

**其他問答**

**Q：如何依自訂欄位值篩選任務？**  
A：建立 `CustomFieldCondition`（或實作 `ICondition<Task>`），並將其加入 `And<T>` 鏈中。

**Q：可以用相同方式篩選資源嗎？**  
A：可以——將 `Task` 替換為 `Resource`，並使用相對應的條件類別。

## 結論

依照上述步驟，您現在已了解如何在 Aspose.Tasks for .NET 中使用 **進階 AND 運算** **結合多個條件**。此技巧可讓您有效 **篩選專案任務**，無論是針對彙總項目、非空條目或任何自訂條件。

---

**Last Updated:** 2026-03-16  
**Tested With:** Aspose.Tasks for .NET (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}