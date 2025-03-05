---
title: 在 Aspose.Tasks 中管理自訂項目屬性集合
linktitle: 在 Aspose.Tasks 中管理自訂項目屬性集合
second_title: Aspose.Tasks .NET API
description: 了解如何在 Aspose.Tasks for .NET 中有效管理自訂專案屬性，從而增強您的專案管理體驗。
type: docs
weight: 24
url: /zh-hant/net/calendar-scheduling/custom-project-property-collection/
---
## 介紹

您準備好使用 Aspose.Tasks for .NET 來增強您的專案管理體驗了嗎？管理自訂專案屬性是專案管理的重要方面，它允許您新增根據專案要求自訂的特定元資料。在本教程中，我們將深入探討如何使用 Aspose.Tasks for .NET 有效地處理自訂項目屬性集合。

## 先決條件

在我們繼續之前，請確保您已設定以下先決條件：

1. Visual Studio 環境：在您的系統上安裝 Visual Studio。
2.  Aspose.Tasks for .NET：從下列位置下載並安裝 Aspose.Tasks for .NET[下載連結](https://releases.aspose.com/tasks/net/).
3. C# 基礎知識：熟悉 C# 程式語言基礎。

## 導入命名空間

首先匯入必要的命名空間以使用 Aspose.Tasks for .NET：

```csharp
using Aspose.Tasks;
using System;


```

我們將範例程式碼分解為多個步驟以便全面理解：

## 第 1 步：初始化項目

```csharp
var project = new Project(DataDir + "ReadProjectInfo.mpp");
```

此步驟使用 Aspose.Tasks 初始化一個新專案。

## 步驟 2： 檢查自訂屬性集合準備情況

```csharp
Console.WriteLine("Is custom properties collection read-only?: " + project.CustomProps.IsReadOnly);
```

此程式碼檢查自訂屬性集合是否是唯讀的。

## 第 3 步：新增自訂屬性

```csharp
project.CustomProps.Add("IsEnterprise", true);
project.CustomProps.Add("Project Start Date", new DateTime(2020, 4, 16, 8, 0, 0));
project.CustomProps.Add("Precision", 10d);
project.CustomProps.Add("Custom Name", "MyProject");
```

在這裡，我們為專案新增自訂屬性，支援 Boolean、DateTime、Double 和 String 類型。

## 第 4 步：存取自訂屬性

```csharp
foreach (var property in project.CustomProps)
{
    Console.WriteLine(property.Type);
    Console.WriteLine(property.Name);
    Console.WriteLine(property.Value);
    Console.WriteLine();
}
```

此循環允許我們迭代自訂屬性並顯示它們的類型、名稱和值。

## 步驟 5：檢索自訂屬性值

```csharp
Console.WriteLine("Custom Name: " + project.CustomProps["Custom Name"]);
```

此程式碼會擷取名為「自訂名稱」的特定自訂屬性的值。

## 第 6 步：迭代自訂屬性名稱

```csharp
foreach (var propName in project.CustomProps.Names)
{
    Console.WriteLine("Name: " + propName);
    Console.WriteLine();
}
```

在這裡，我們迭代自訂屬性的名稱並顯示它們。

## 步驟 7：刪除或清除自訂屬性

```csharp
if (project.CustomProps.Contains("Custom Name"))
{
    project.CustomProps.Remove("Custom Name");
}

project.CustomProps.Clear();
```

您可以按名稱刪除特定的自訂屬性或清除整個集合。

## 結論

掌握 Aspose.Tasks for .NET 中的自訂專案屬性集合可讓您有效管理專案元資料。透過遵循此逐步指南，您可以將自訂屬性無縫整合到專案管理工作流程中，從而增強組織和效率。

## 常見問題解答

### 問題 1：我可以使用 Aspose.Tasks for .NET 將任何資料類型的自訂屬性新增至我的專案嗎？

A1：是的，您可以新增支援布林、日期時間、雙精確度和字串類型的自訂屬性。

### Q2：是否可以在 Aspose.Tasks for .NET 中迭代自訂屬性名稱？

 A2：當然，您可以使用迭代自訂屬性名稱`Names`財產。

### 問題 3：如何從我的專案中刪除特定的自訂屬性？

 A3：您可以使用以下命令按名稱刪除自訂屬性`Remove`方法。

### Q4：Aspose.Tasks for .NET 是否提供臨時授權支援？

A4：是的，您可以從 Aspose 網站取得臨時許可證用於評估目的。

### Q5：在哪裡可以找到 Aspose.Tasks for .NET 的支援或進一步協助？

 A5：您可以造訪Aspose.Tasks論壇[這裡](https://forum.aspose.com/c/tasks/15)如有任何疑問或幫助。