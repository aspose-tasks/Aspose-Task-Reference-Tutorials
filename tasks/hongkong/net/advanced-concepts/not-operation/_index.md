---
date: 2026-03-14
description: 學習如何在 Aspose.Tasks for .NET 中使用 NOT 運算篩選任務，並探索如何在彈性任務查詢中使用帶有 NOT 條件的篩選。
linktitle: Working with NOT Operation in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: 在 Aspose.Tasks 中過濾非操作任務
url: /zh-hant/net/advanced-concepts/not-operation/
weight: 20
---

, OrCondition.

Proceed.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# filter tasks not operation in Aspose.Tasks

## Introduction

在本教學中，您將學習如何使用 Aspose.Tasks for .NET **篩選任務 NOT 操作**。NOT 操作會反轉篩選條件，使您能選取**不符合**特定標準的所有任務。當您需要排除某些項目（例如沒有值的任務）或在不撰寫額外程式碼的情況下建立複雜查詢時，這項功能相當重要。

## Quick Answers
- **NOT 操作的功能是什麼？** 它會反轉篩選條件，回傳未通過原始測試的項目。  
- **為什麼要使用 filter tasks not operation？** 它簡化排除邏輯，讓程式碼更易讀。  
- **哪個命名空間提供 NOT 類別？** `Aspose.Tasks.Util`。  
- **正式環境需要授權嗎？** 需要，非試用版必須使用有效的 Aspose.Tasks 授權。  
- **可以將 NOT 與其他條件結合使用嗎？** 當然可以——可與 `AndCondition`、`OrCondition` 等一起使用。

## What is filter tasks not operation?
**filter tasks not operation** 是對任務篩選套用的邏輯否定。它不會選取符合條件的任務，而是選取*不符合*該條件的任務。當您想忽略欄位為空的任務、特定狀態的任務，或任何其他想排除的屬性時，這非常實用。

## Why apply not condition when filtering tasks?
套用 **not condition** 可減少對專案資料的多次遍歷。它讓您撰寫簡潔、易於維護的程式碼，並透過 Aspose.Tasks 最佳化的引擎提升效能。

## Prerequisites

在開始之前，請確保您已具備以下條件：

1. Visual Studio：需要安裝 Visual Studio 以執行程式碼範例。  
2. Aspose.Tasks for .NET：從[官方網站](https://releases.aspose.com/tasks/net/)下載並安裝 Aspose.Tasks for .NET。  
3. 基本的 C# 知識：熟悉 C# 語言有助於理解範例程式碼。

## Import Namespaces

首先，匯入程式碼所需的命名空間：

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

## Step 1: Set Up Project and Tasks

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

我們使用 Aspose.Tasks 提供的 `Project` 類別載入名為 **Project2.mpp** 的專案檔。請確保該檔案存在於指定目錄中。

## Step 2: Collect Project Tasks

```csharp
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

在此，我們建立 `ChildTasksCollector` 物件以收集專案內的所有任務，然後使用 `TaskUtils.Apply` 走訪任務層級，將每個子任務加入集合。

## Step 3: Define Filter Condition

```csharp
var filter = new NullCondition();
```

我們使用自訂類別 `NullCondition` 定義篩選條件，該條件會選取值為 **null** 的任務。  

> **小技巧：** 可將 `NullCondition` 替換為其他條件（例如 `EqualsCondition`）以針對不同屬性進行篩選。

## Step 4: Apply NOT Operation

```csharp
var condition = new Not<Task>(filter);
```

使用 Aspose.Tasks 提供的 `Not<T>` 類別，我們對先前的篩選條件套用 **NOT 操作**。這會顛倒原始條件，使篩選結果變為**不具 null 值**的任務，這正是 **如何使用 not filter** 的核心技巧。

## Step 5: Filter Tasks

```csharp
List<Task> collection = Filter(coll.Tasks, condition);
```

透過自訂的 `Filter` 方法，我們依據已套用的條件過濾收集到的任務。此方法接受任務集合與篩選條件，回傳符合 **apply not condition** 的任務清單。

## Step 6: Process Filtered Tasks

```csharp
foreach (var task in collection)
{
    Console.WriteLine("Name: " + task.Get(Tsk.Name));

    // Work with other properties...
}
```

最後，我們遍歷過濾後的任務並執行所需操作。範例中僅將任務名稱印出至主控台，您亦可在此區塊加入更新欄位、移動任務或產生報表等功能。

## Common Use Cases

- 在產生待辦清單時 **排除已完成的任務**。  
- **找出缺少自訂欄位** 的任務（例如 null 的 “Owner” 欄位）。  
- **與其他條件結合** 以建立複雜查詢，例如「任務不是 null 且開始日期早於今天」。

## Troubleshooting & Tips

| Issue | Reason | Fix |
|-------|--------|-----|
| No tasks returned | 原始條件可能過於嚴格。 | 檢查條件邏輯，或改用較簡單的篩選如 `new TrueCondition()`。 |
| `NullReferenceException` | `DataDir` 路徑不正確。 | 確認 `DataDir` 指向包含 *Project2.mpp* 的資料夾。 |
| Unexpected results | `Not<T>` 與其他條件混用方式不正確。 | 使用括號：`new AndCondition(new Not<Task>(filter), otherCondition)`。 |

## Frequently Asked Questions

**Q: Can I use Aspose.Tasks with other .NET frameworks?**  
A: Yes, Aspose.Tasks supports .NET Core, .NET Standard, and the classic .NET Framework.

**Q: Is there a free trial available for Aspose.Tasks?**  
A: Yes, you can download a free trial from the [website](https://releases.aspose.com/).

**Q: How can I get support for Aspose.Tasks?**  
A: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for any support queries or technical assistance.

**Q: Can I purchase a temporary license for Aspose.Tasks?**  
A: Yes, you can purchase a temporary license from the [purchase page](https://purchase.aspose.com/temporary-license/).

**Q: Where can I find comprehensive documentation for Aspose.Tasks?**  
A: You can access the complete documentation on the [Aspose.Tasks documentation page](https://reference.aspose.com/tasks/net/).

## Conclusion

掌握 **filter tasks not operation** 並學會 **如何使用 not filter** 以及 **apply not condition** 後，您即可在 Aspose.Tasks 中對任務選取進行精細控制。這讓您能編寫更乾淨的程式碼、避免手動排除，並打造功能強大的專案管理工具。

---

**Last Updated:** 2026-03-14  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}