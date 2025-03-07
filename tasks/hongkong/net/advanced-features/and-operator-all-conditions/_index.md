---
title: 在 Aspose.Tasks 的所有條件下使用 AND 運算符
linktitle: 在 Aspose.Tasks 的所有條件下使用 AND 運算符
second_title: Aspose.Tasks .NET API
description: 了解如何在所有情況下透過 Aspose.Tasks for .NET 使用 AND 運算子來有效地篩選專案任務。
weight: 11
url: /zh-hant/net/advanced-features/and-operator-all-conditions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 的所有條件下使用 AND 運算符

## 介紹

您是否希望有效地簡化您的專案管理任務？透過 Aspose.Tasks for .NET，您可以利用強大的功能來有效地操作專案資料。其中一項功能是能夠在所有條件下使用 AND 運算符，讓您可以同時根據多個條件篩選任務。在本教程中，我們將指導您逐步完成此功能的實現過程。

## 先決條件

在深入學習本教程之前，請確保您具備以下先決條件：

1. C# 基礎：熟悉 C# 程式語言將會很有幫助。
2.  Aspose.Tasks for .NET 函式庫：下載並安裝 Aspose.Tasks for .NET 函式庫[這裡](https://releases.aspose.com/tasks/net/).
3. 整合開發環境 (IDE)：在系統上安裝 IDE（例如 Visual Studio）以方便編碼。

## 導入命名空間

首先，您需要匯入必要的名稱空間來存取所需的類別和方法。

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;

```

現在，讓我們將範例分解為多個步驟，以便清楚地理解該過程。

## 第 1 步：載入專案文件

```csharp
//文檔目錄的路徑。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

使用載入專案文件`Project`類別建構函數，指定檔案路徑。

## 第 2 步：收集所有專案任務

```csharp
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

利用`ChildTasksCollector`類別來收集項目中的所有任務。

## 步驟3：定義篩選條件

```csharp
var conditions = new List<ICondition<Task>>
{
    new NotNullCondition(),
    new SummaryCondition()
};
```

建立條件清單來過濾任務。在此範例中，我們過濾不為空且為摘要任務的任務。

## 步驟 4：對條件套用 AND 運算符

```csharp
var joinedCondition = new AndAllCondition<Task>(conditions);
```

使用加入條件`AndAllCondition`類，將 AND 運算子應用於所有條件。

## 第 5 步：過濾任務

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

將連接條件應用於收集的任務以相應地過濾它們。

## 第 6 步：處理過濾的任務

```csharp
foreach (var task in collection)
{
    Console.WriteLine("Name: " + task.Get(Tsk.Name));
    //使用過濾任務執行操作
}
```

迭代過濾後的任務並根據需要執行操作。

## 結論

總而言之，在所有情況下透過 Aspose.Tasks for .NET 使用 AND 運算子使您能夠同時根據多個條件有效地過濾專案任務。透過遵循本教學中提供的逐步指南，您可以將此功能無縫整合到專案管理工作流程中，從而提高生產力和組織性。

## 常見問題解答

### 問題 1：除了範例中示範的條件之外，我還可以套用其他條件嗎？

A1：是的，您可以根據您的專案要求定義和套用任何自訂條件。

### Q2：Aspose.Tasks for .NET 是否相容於不同的專案檔案格式？

A2：是的，Aspose.Tasks 支援各種專案文件格式，例如 MPP、XML 和 CSV。

### Q3：Aspose.Tasks 是否支援複雜的專案調度演算法？

A3：當然，Aspose.Tasks 提供了管理專案進度的進階功能，包括關鍵路徑分析和資源分配。

### Q4：我可以將 Aspose.Tasks 與其他 .NET 框架或函式庫整合嗎？

A4：是的，您可以將 Aspose.Tasks 與其他 .NET 框架和程式庫無縫整合以增強功能。

### Q5：Aspose.Tasks 使用者有可用的社群論壇或支援管道嗎？

 A5：是的，您可以造訪 Aspose.Tasks 社群論壇[這裡](https://forum.aspose.com/c/tasks/15)如有任何疑問或幫助。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
