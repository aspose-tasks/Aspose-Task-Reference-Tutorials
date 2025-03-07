---
title: 在 Aspose.Tasks 中掌握 MS 專案的擴充屬性定義
linktitle: Aspose.Tasks 中擴充屬性定義的集合
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 在 Microsoft Project 中管理擴充屬性定義。輕鬆自訂和增強您的專案數據。
weight: 14
url: /zh-hant/net/tasks-project-management/extended-attribute-definition-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中掌握 MS 專案的擴充屬性定義

## 介紹
在本教程中，我們將探索如何使用 Aspose.Tasks for .NET 在 Microsoft Project 中使用擴充屬性定義。擴充屬性提供了一種靈活的方式來自訂和增強項目數據，允許使用者添加預設提供的標準欄位之外的其他欄位。透過 Aspose.Tasks，您可以輕鬆管理這些擴充屬性，以滿足您的專案管理需求。
## 先決條件
在繼續之前，請確保您已安裝以下先決條件：
- [.NET框架](https://dotnet.microsoft.com/download)
- .NET 函式庫的 Aspose.Tasks。您可以從以下位置下載：[這裡](https://releases.aspose.com/tasks/net/).

## 導入命名空間
首先，您需要匯入必要的命名空間來存取 .NET 專案中的 Aspose.Tasks 類別和方法。按著這些次序：
## 第 1 步：開啟您的 .NET 項目
在您首選的 IDE（例如 Visual Studio）中開啟 .NET 專案。
## 步驟2：新增Aspose.Tasks命名空間
在程式碼檔案的開頭新增以下行以匯入 Aspose.Tasks 命名空間：
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```

現在，讓我們將提供的程式碼範例分解為多個步驟，以便全面理解：
## 第 1 步：載入專案文件
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## 步驟 2：清除現有的擴充屬性定義（可選）
```csharp
if (!project.ExtendedAttributes.IsReadOnly)
{
    if (project.ExtendedAttributes.Count > 0)
    {
        project.ExtendedAttributes.Clear();
    }
}
```
## 步驟 3：為任務建立並新增擴充屬性定義
```csharp
var taskDefinition = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
project.ExtendedAttributes.Add(taskDefinition);
```
## 步驟 4：迭代任務擴充屬性
```csharp
Console.WriteLine("Iterate over extended attributes of " + project.ExtendedAttributes.ParentProject.Get(Prj.Name) + " project: ");
foreach (var attribute in project.ExtendedAttributes)
{
    Console.WriteLine("Attribute Alias: " + attribute.Alias);
    Console.WriteLine("Attribute CfType: " + attribute.CfType);
    Console.WriteLine();
}
```
## 步驟 5：建立並新增資源的擴充屬性定義
```csharp
var resourceDefinition = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Cost, ExtendedAttributeResource.Cost5, "My cost");
if (!project.ExtendedAttributes.Contains(resourceDefinition))
{
    project.ExtendedAttributes.Add(resourceDefinition);
}
```
## 步驟 6：插入資源擴充屬性定義
```csharp
var resourceDefinition2 = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Number, ExtendedAttributeResource.Cost1, "My Cost 2");
if (project.ExtendedAttributes.IndexOf(resourceDefinition2) < 0)
{
    project.ExtendedAttributes.Insert(0, resourceDefinition2);
}
```
## 步驟 7：透過索引刪除擴充屬性
```csharp
project.ExtendedAttributes.RemoveAt(0);
```

## 結論
在本教程中，我們介紹了使用 Aspose.Tasks for .NET 在 Microsoft Project 中處理擴充屬性定義的基礎知識。透過執行這些步驟，您可以有效地管理和自訂擴充屬性，以滿足您的專案管理要求。
## 常見問題解答
### Q：我可以修改現有的擴充屬性定義嗎？
答：是的，您可以根據需要修改現有的擴充屬性定義或建立新的擴充屬性定義。
### Q：Microsoft Project 的所有版本都支援擴充屬性嗎？
答：是的，大多數版本的 Microsoft Project（包括最新版本）都支援擴充屬性。
### Q：我可以使用擴充屬性來計算自訂欄位嗎？
答：當然，擴充屬性可用於根據您定義的特定條件計算自訂欄位。
### Q：Aspose.Tasks 與其他 .NET 框架相容嗎？
答：Aspose.Tasks 與各種.NET 框架相容，確保靈活性和易於整合。
### Q：在哪裡可以找到更多有關 Aspose.Tasks 的資源和支援？
答：您可以訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)尋求支持並探索文檔[這裡](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
