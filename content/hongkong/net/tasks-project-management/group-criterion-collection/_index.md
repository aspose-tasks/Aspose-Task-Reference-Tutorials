---
title: 使用 Aspose.Tasks 管理 MS 專案組標準
linktitle: 在 Aspose.Tasks 中管理群組標準集合
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 管理 Group Criterion MS Project 集合。開發人員的分步指南。
type: docs
weight: 28
url: /zh-hant/net/tasks-project-management/group-criterion-collection/
---
## 介紹
Aspose.Tasks for .NET 是一個功能強大的 API，可讓開發人員以程式設計方式處理 Microsoft Project 檔案。在本教程中，我們將探索如何使用 Aspose.Tasks 管理 MS Project 中的 Group Criterion 集合。

## 先決條件

在我們開始之前，請確保您具備以下條件：

1.  Aspose.Tasks for .NET：請確定您的.NET專案中安裝了Aspose.Tasks函式庫。您可以從以下位置下載：[這裡](https://releases.aspose.com/tasks/net/).

2. Microsoft Project 檔案：準備好可供使用的 Microsoft Project 檔案 (MPP)。

## 導入命名空間

首先，您需要將必要的命名空間匯入到 C# 程式碼中。此步驟對於存取 Aspose.Tasks 提供的功能至關重要。

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## 第 1 步：載入專案文件

初始化一個`Project`透過載入 MPP 檔案來取得物件。 

```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```

## 第 2 步：訪問群組標準

從專案中檢索群組並存取其標準。

```csharp
var group = project.TaskGroups.ToList()[0];
```

## 第 3 步：迭代組標準

循環遍歷組中的每個條件並顯示其屬性。

```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Index: " + criterion.Index);
    Console.WriteLine("Field: " + criterion.Field);
    Console.WriteLine("Group On: " + criterion.GroupOn);
    Console.WriteLine();
}
```

## 第 4 步：明確小組標準

如果現有群組條件不是唯讀的，請清除它。

```csharp
group.GroupCriteria.Clear();
```

## 第 5 步：新增標準

建立一個新的群組標準並將其新增至群組。

```csharp
var criterionToAdd = new GroupCriterion
{
    Ascending = true,
    Field = Field.TaskActive
};

if (!group.GroupCriteria.Contains(criterionToAdd))
{
    group.GroupCriteria.Add(criterionToAdd);
}
```

## 第 6 步：將條件複製到另一個群組

將條件從一組複製到另一組。

```csharp
var otherGroup = project.TaskGroups.ToList()[0];

var criteria = new GroupCriterion[group.GroupCriteria.Count];
group.GroupCriteria.CopyTo(criteria, 0);
foreach (var criterion in criteria)
{
    otherGroup.GroupCriteria.Add(criterion);
}
```

### 結論

在本教學中，我們學習如何使用 Aspose.Tasks for .NET 管理 Group Criterion MS Project 集合。透過執行這些步驟，您可以以程式設計方式有效地操作 Microsoft Project 檔案中的群組條件。

## 常見問題解答

### Q1：Aspose.Tasks 是否與所有版本的 Microsoft Project 相容？

答：是的，Aspose.Tasks支援各種版本的Microsoft Project文件，包括2003、2007、2010、2013和2016。

### Q2：我可以對一個群組應用多個標準嗎？

答：當然，您可以透過迭代每個條件並相應地添加它們來將多個條件添加到群組中。

### Q3：Aspose.Tasks 有試用版嗎？

答：是的，您可以從以下位置取得 Aspose.Tasks 的免費試用版：[這裡](https://releases.aspose.com/).

### Q4：在哪裡可以找到 Aspose.Tasks 的文件？

答：可以參考文檔[這裡](https://reference.aspose.com/tasks/net/).

### Q5：如果我遇到任何問題，我該如何獲得支援？

答：如果您有任何疑問或遇到任何問題，您可以從 Aspose.Tasks 論壇尋求支持[這裡](https://forum.aspose.com/c/tasks/15).