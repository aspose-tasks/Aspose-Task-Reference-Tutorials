---
date: 2026-03-19
description: 學習如何在所有條件中使用 AND 運算子，透過 Aspose.Tasks for .NET 高效篩選專案任務。
linktitle: Using AND Operator in All Conditions with Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: 如何在 Aspose.Tasks 的 All Conditions 中使用 AND 運算子
url: /zh-hant/net/advanced-features/and-operator-all-conditions/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 AND 運算子於所有條件（Aspose.Tasks）

## 介紹

您是否想要更有效率地簡化專案管理工作？使用 Aspose.Tasks for .NET，您可以運用強大的功能來有效操作專案資料。其中一項功能是 **在所有條件中使用 AND 運算子**，讓您能同時根據多個條件篩選工作。本文將一步步帶您實作此功能，讓您 **快速且可靠地篩選工作**。

## 快速回答
- **AND 運算子是做什麼的？** 它會將多個篩選條件結合，只有同時符合 *所有* 條件的工作才會被回傳。  
- **哪個程式庫提供此功能？** Aspose.Tasks for .NET。  
- **需要授權嗎？** 可使用免費試用版進行評估；正式環境需購買授權。  
- **可以載入 MPP 檔案嗎？** 可以 – 使用 `Project` 類別載入 *.mpp* 檔案。  
- **能篩選彙總工作嗎？** 當然可以，只要在條件清單中加入 `SummaryCondition` 即可。

## 什麼是「使用 AND 運算子」功能？
**使用 AND 運算子** 的能力讓您將多個 `ICondition<T>` 實作以 `AndAllCondition<T>` 連接。最終的篩選只會返回同時滿足 *每一個* 條件的工作。

## 為什麼要套用多個條件？
套用多個條件（例如「工作不為 null」 **且** 「工作為彙總工作」）可讓您精準控制所處理的資料。這在需要 **建立自訂篩選** 以處理複雜專案排程或產生聚焦於特定工作群組的報表時特別有用。

## 前置條件

在開始教學之前，請確保您已具備以下前置條件：

1. **C# 基礎知識** – 熟悉 C# 程式語言會更有幫助。  
2. **Aspose.Tasks for .NET 程式庫** – 從 [此處](https://releases.aspose.com/tasks/net/) 下載並安裝 Aspose.Tasks for .NET 程式庫。  
3. **整合開發環境 (IDE)** – 在系統上安裝 Visual Studio 等 IDE，以方便撰寫程式碼。  

## 匯入命名空間

首先，您需要匯入必要的命名空間，以存取所需的類別與方法。

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;
```

接下來，我們將範例分成多個步驟說明，讓您更清楚整體流程。

## 步驟 1：載入專案檔（load mpp file）

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

使用 `Project` 類別建構子載入專案檔，並指定檔案路徑。此步驟示範 **載入 mpp 檔案** 的處理方式。

## 步驟 2：收集所有專案工作

```csharp
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

利用 `ChildTasksCollector` 類別收集專案中所有的工作。

## 步驟 3：定義篩選條件

```csharp
var conditions = new List<ICondition<Task>>
{
    new NotNullCondition(),
    new SummaryCondition()
};
```

建立條件清單以篩選工作。在此範例中，我們篩選 **非 null 工作** 且 **為彙總工作**，即 **篩選彙總工作** 的示例。

## 步驟 4：對條件套用 AND 運算子（apply multiple conditions）

```csharp
var joinedCondition = new AndAllCondition<Task>(conditions);
```

使用 `AndAllCondition` 類別將條件連接起來，對所有條件套用 **使用 AND 運算子**。

## 步驟 5：篩選工作

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

將已連接的條件套用至收集到的工作，以進行相應的篩選。此步驟展示 **如何篩選工作**，使用的是組合條件。

## 步驟 6：處理篩選後的工作

```csharp
foreach (var task in collection)
{
    Console.WriteLine("Name: " + task.Get(Tsk.Name));
    // Perform operations with filtered tasks
}
```

遍歷篩選後的工作，依需求執行相應的操作。

## 常見問題與解決方案

- **條件清單為空** – 在建立 `AndAllCondition<T>` 前，請確保已加入至少一個 `ICondition<T>`。  
- **未回傳任何工作** – 請確認您加入的條件確實能匹配專案中的工作（例如，若專案中沒有彙總工作，篩選彙總工作會返回空）。  
- **找不到檔案** – 再次檢查 `DataDir` 路徑與 *.mpp* 檔案名稱是否正確。

## 常見問答

**Q: 我可以套用除範例外的其他條件嗎？**  
A: 可以，您可以根據專案需求自行定義並套用任何自訂條件。

**Q: Aspose.Tasks for .NET 是否支援不同的專案檔案格式？**  
A: 支援，Aspose.Tasks 可處理多種專案檔案格式，如 MPP、XML 與 CSV。

**Q: Aspose.Tasks 是否提供複雜的專案排程演算法支援？**  
A: 當然，Aspose.Tasks 提供進階功能來管理專案排程，包括關鍵路徑分析與資源分配等。

**Q: 我能將 Aspose.Tasks 與其他 .NET 框架或程式庫整合嗎？**  
A: 可以，您可以無縫將 Aspose.Tasks 與其他 .NET 框架或程式庫結合，以增強功能。

**Q: 是否有 Aspose.Tasks 使用者的社群論壇或支援管道？**  
A: 有，您可前往 Aspose.Tasks 社群論壇 [此處](https://forum.aspose.com/c/tasks/15) 取得協助或提問。

## 結論

總結來說，於 Aspose.Tasks for .NET 中使用 **所有條件的 AND 運算子**，可讓您同時依多項條件高效篩選專案工作。依照本教學提供的步驟操作，您即可將此功能順利整合至專案管理流程中，提升生產力與組織效率。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-03-19  
**測試版本：** Aspose.Tasks 24.11 for .NET  
**作者：** Aspose  

---