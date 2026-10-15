---
date: 2026-10-15
description: 了解如何在 Aspose.Tasks for .NET 中新增自訂屬性並管理自訂專案屬性，提升您對專案中繼資料的控制。
keywords:
- add custom property
- manage custom properties
- read custom properties
- add boolean property
- add string property
lastmod: 2026-10-15
linktitle: 管理 Aspose.Tasks 中的自訂專案屬性集合
og_description: 使用 Aspose.Tasks for .NET 為您的專案檔案新增自訂屬性。本指南示範如何管理自訂屬性、讀取它們，以及有效地新增布林或字串值。
og_image_alt: Guide showing how to add custom property in Aspose.Tasks .NET
og_title: 使用 Aspose.Tasks .NET API 為專案新增自訂屬性
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  headline: How to add custom property in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom property and manage custom project properties
    in Aspose.Tasks for .NET, boosting your project metadata control.
  name: How to add custom property in Aspose.Tasks for .NET
  steps:
  - name: initialize project
    text: '`Project` is the primary class representing a project file in Aspose.Tasks.'
  - name: check custom properties collection readiness
    text: '`CustomProperties` is the collection that holds all custom property objects
      for a project.'
  - name: add custom properties
    text: '`Add` method inserts a new custom property into the project''s collection.'
  - name: access custom properties
    text: '`CustomProperties` collection implements IEnumerable, allowing iteration
      over each `CustomProperty`.'
  - name: retrieve a custom property value
    text: '`Get` method returns the value of a custom property by its name.'
  - name: iterate over custom property names
    text: '`Names` property provides a list of all custom property names in the collection.'
  - name: remove or clear custom properties
    text: '`Remove` method deletes a specific property, while `Clear` empties the
      entire collection.'
  type: HowTo
- questions:
  - answer: Yes, you can add custom properties supporting Boolean, DateTime, Double,
      and String types.
    question: Can I add custom properties of any data type to my project using Aspose.Tasks
      for .NET?
  - answer: Absolutely, you can iterate over custom property names using the `Names`
      property.
    question: Is it possible to iterate over custom property names in Aspose.Tasks
      for .NET?
  - answer: You can remove a custom property by its name using the `Remove` method.
    question: How can I remove a specific custom property from my project?
  - answer: Yes, you can obtain a temporary license from the Aspose website for evaluation
      purposes.
    question: Does Aspose.Tasks for .NET provide support for temporary licenses?
  - answer: You can visit the Aspose.Tasks forum [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any queries or assistance.
    question: Where can I find support or further assistance regarding Aspose.Tasks
      for .NET?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom properties
- Aspose.Tasks
- .NET project management
- C# tasks API
title: 如何在 Aspose.Tasks for .NET 中新增自訂屬性
url: /zh-hant/net/calendar-scheduling/custom-project-property-collection/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks for .NET 中新增自訂屬性

## 介紹

新增自訂屬性支援讓您儲存專案特定的中繼資料，這些是內建欄位無法涵蓋的。在本教學中，您將學習如何 **新增自訂屬性**、讀取它，以及使用 Aspose.Tasks for .NET 管理整個自訂屬性集合。完成後，您將能夠使用 Boolean、DateTime、Double 和 String 值，依照業務規則客製化專案檔案。

## 快速解答
- **我可以新增 Boolean 自訂屬性嗎？** 是 – use `CustomPropertyType.Boolean`.
- **支援多少種自訂屬性類型？** 四種：Boolean、DateTime、Double、String.
- **自訂屬性集合是唯讀的嗎？** 若專案從唯讀來源載入，則可能為唯讀.
- **使用此功能需要授權嗎？** 臨時授權可用於評估；正式環境需使用完整授權.
- **相容的 .NET 版本有哪些？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7.

## 什麼是自訂屬性？

自訂屬性是您附加於 Project 物件的使用者自訂中繼資料欄位。它讓您儲存額外資訊，例如「風險等級」、「客戶編號」或任何標準 MS‑Project 欄位未涵蓋的 Boolean 標記。

## 為何在 Aspose.Tasks 中新增自訂屬性？

Aspose.Tasks 支援 **超過 50 種輸入與輸出格式**，且能在不將整個檔案載入記憶體的情況下處理 **多達 10,000 個工作**的專案。新增自訂屬性可讓您將關鍵業務資料直接嵌入專案檔案，免除外部資料庫的需求，確保資料隨專案一起傳遞。

## 前置條件

- 已在工作站上安裝 Visual Studio（任何較新版）.  
- Aspose.Tasks for .NET – 從 [download link](https://releases.aspose.com/tasks/net/) 下載.  
- 具備 C# 語法與 .NET 專案結構的基本了解.

## 匯入命名空間

以下命名空間可讓您存取核心專案模型與自訂屬性 API。

```csharp
using Aspose.Tasks;
using System;


```

## 如何在 Aspose.Tasks 中新增自訂屬性？

要新增自訂屬性，首先載入專案，然後建立 `CustomProperty` 物件，設定其名稱、類型與值，最後將其加入專案的 `CustomProperties` 集合。此操作會直接將中繼資料嵌入專案檔案，並在呼叫 `project.Save(...)` 時儲存變更。  

`CustomProperty` 代表附加於專案的單一使用者自訂欄位。

```csharp
// Direct answer: Load the project, create a CustomProperty, set its Type and Value, then add it to project.CustomProperties.
```

### 步驟 1：初始化專案

`Project` 是 Aspose.Tasks 中代表專案檔案的主要類別。

```csharp
var project = new Project(DataDir + "ReadProjectInfo.mpp");
```

### 步驟 2：檢查自訂屬性集合是否已就緒

`CustomProperties` 是保存專案所有自訂屬性物件的集合。

```csharp
Console.WriteLine("Is custom properties collection read-only?: " + project.CustomProps.IsReadOnly);
```

### 步驟 3：新增自訂屬性

`Add` 方法會將新自訂屬性插入至專案的集合中。

```csharp
project.CustomProps.Add("IsEnterprise", true);
project.CustomProps.Add("Project Start Date", new DateTime(2020, 4, 16, 8, 0, 0));
project.CustomProps.Add("Precision", 10d);
project.CustomProps.Add("Custom Name", "MyProject");
```

### 步驟 4：存取自訂屬性

`CustomProperties` 集合實作 IEnumerable，允許對每個 `CustomProperty` 進行迭代。

```csharp
foreach (var property in project.CustomProps)
{
    Console.WriteLine(property.Type);
    Console.WriteLine(property.Name);
    Console.WriteLine(property.Value);
    Console.WriteLine();
}
```

### 步驟 5：取得自訂屬性值

`Get` 方法依名稱返回自訂屬性的值。

```csharp
Console.WriteLine("Custom Name: " + project.CustomProps["Custom Name"]);
```

### 步驟 6：遍歷自訂屬性名稱

`Names` 屬性提供集合中所有自訂屬性名稱的清單。

```csharp
foreach (var propName in project.CustomProps.Names)
{
    Console.WriteLine("Name: " + propName);
    Console.WriteLine();
}
```

### 步驟 7：移除或清除自訂屬性

`Remove` 方法刪除特定屬性，而 `Clear` 會清空整個集合。

```csharp
if (project.CustomProps.Contains("Custom Name"))
{
    project.CustomProps.Remove("Custom Name");
}

project.CustomProps.Clear();
```

## 常見陷阱與故障排除

- **唯讀集合** – 若 `project.CustomProperties.IsReadOnly` 回傳 `true`，請確保來源檔案未以排他讀取方式開啟，或在編輯前將其複製至可寫入的位置.  
- **類型不匹配** – 指派與宣告的 `CustomPropertyType` 不符的值會拋出 `ArgumentException`。請在定義正確的 `Type` 後再設定 `Value`.  
- **儲存變更** – 新增或移除屬性後，呼叫 `project.Save("output.mpp")` 以永久保存修改；否則變更僅保留在記憶體中.

## 常見問答

**Q: 我可以在 Aspose.Tasks for .NET 中為我的專案新增任何資料類型的自訂屬性嗎？**  
A: 是的，您可以新增支援 Boolean、DateTime、Double 與 String 類型的自訂屬性.

**Q: 在 Aspose.Tasks for .NET 中是否可以遍歷自訂屬性名稱？**  
A: 當然可以，您可以使用 `Names` 屬性遍歷自訂屬性名稱.

**Q: 如何從專案中移除特定的自訂屬性？**  
A: 您可以使用 `Remove` 方法依名稱移除自訂屬性.

**Q: Aspose.Tasks for .NET 是否支援臨時授權？**  
A: 是的，您可從 Aspose 官方網站取得臨時授權以供評估使用.

**Q: 哪裡可以找到關於 Aspose.Tasks for .NET 的支援或進一步協助？**  
A: 您可前往 Aspose.Tasks 論壇 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 取得任何問題的協助.

---

**最後更新：** 2026-10-15  
**測試環境：** Aspose.Tasks 24.11 for .NET  
**作者：** Aspose

## 相關教學

- [如何使用 Aspose.Tasks for .NET 讀取內建專案屬性](/tasks/net/advanced-features/built-in-project-property-collection/)
- [在 Aspose.Tasks 中管理 MS Project 屬性集合](/tasks/net/tasks-project-management/extended-attribute-collection/)
- [Aspose.Tasks 自訂欄位類型 – 行事曆與排程](/tasks/net/calendar-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}