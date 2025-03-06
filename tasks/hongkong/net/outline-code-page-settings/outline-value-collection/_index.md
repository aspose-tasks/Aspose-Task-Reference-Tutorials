---
title: 使用 Aspose.Tasks 管理 MS 專案大綱值
linktitle: Aspose.Tasks 中大綱值的集合
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 管理 Microsoft Project 檔案中的大綱值。帶有程式碼範例的分步教程。
weight: 17
url: /zh-hant/net/outline-code-page-settings/outline-value-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 管理 MS 專案大綱值

## 介紹
Aspose.Tasks for .NET 提供了一套全面的功能來與 Microsoft Project 檔案進行互動。其中一項功能是能夠管理專案內的大綱值。在本教程中，我們將探索如何使用 Aspose.Tasks for .NET 收集和操作大綱值。
## 先決條件
在我們開始之前，請確保您具備以下條件：
1.  Aspose.Tasks for .NET：您可以從下列位置下載程式庫：[這裡](https://releases.aspose.com/tasks/net/).
2. 開發環境：確保安裝了合適的IDE，例如Visual Studio。
3. C# 基礎：熟悉 C# 程式語言將會很有幫助。
## 導入命名空間
在您的 C# 程式碼檔案中，匯入必要的命名空間以存取 Aspose.Tasks 類別和方法：
```csharp
using Aspose.Tasks;
using System;

```
讓我們將提供的範例分解為多個步驟：
## 第 1 步：載入專案文件
首先，初始化一個`Project`透過載入現有的 Microsoft Project 檔案來物件：
```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## 第 2 步：清除現有大綱值
接下來，清除專案中任何現有的大綱值：
```csharp
foreach (var outlineCode in project.OutlineCodes)
{
    if (outlineCode.Values.Count <= 0)
    {
        continue;
    }
    if (!outlineCode.Values.IsReadOnly)
    {
        outlineCode.Values.Clear();
    }
}
```
## 第 3 步：定義新的大綱程式碼
現在，定義一個帶有描述和值的新大綱程式碼：
```csharp
var codeDefinition = new OutlineCodeDefinition
{
    Alias = "New task outline code1",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode1).ToString(),
    FieldName = "Outline Code1"
};
var value = new OutlineValue { Description = "Value description", ValueId = 1, Value = "123456", Type = OutlineValueType.Number };
codeDefinition.Values.Add(value);
project.OutlineCodes.Add(codeDefinition);
```
## 第 4 步：更新輪廓值
更新大綱程式碼的值：
```csharp
codeDefinition.Values[0].Value = "654321";
```
## 第 5 步：迭代輪廓值
遍歷輪廓值並列印其詳細資訊：
```csharp
foreach (var definitionValue in codeDefinition.Values)
{
    Console.WriteLine("Value: " + definitionValue.Value);
    Console.WriteLine("Value Id: " + definitionValue.ValueId);
    Console.WriteLine("Value Guid: " + definitionValue.ValueGuid);
    Console.WriteLine();
}
```
## 第 6 步：操縱輪廓值
根據需要執行刪除、插入和複製輪廓值等操作：
```csharp
if (codeDefinition.Values.Contains(value))
{
    codeDefinition.Values.Remove(value);
}
codeDefinition.Values.Insert(0, value);
Console.WriteLine("Index of inserted value: " + codeDefinition.Values.IndexOf(value));
codeDefinition.Values.RemoveAt(codeDefinition.Values.Count - 1);
var codeDefinition2 = new OutlineCodeDefinition
{
    Alias = "New outline code 2",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode2).ToString(),
    FieldName = "Outline Code2"
};
var outlineValues = new OutlineValue[codeDefinition.Values.Count];
codeDefinition.Values.CopyTo(outlineValues, 0);
foreach (var outlineValue in outlineValues)
{
    codeDefinition2.Values.Add(outlineValue);
}
```
## 結論
在本教學中，我們學習如何使用 Aspose.Tasks for .NET 處理 Microsoft Project 檔案中的大綱值。透過遵循提供的步驟，您可以有效地管理專案中的大綱值，從而實現更好的控制和靈活性。
## 常見問題解答
### Q：我可以同時操作多個大綱程式碼嗎？
答：是的，您可以使用 Aspose.Tasks 在專案中定義和操作多個大綱程式碼。
### Q：Aspose.Tasks 是否與不同版本的 Microsoft Project 檔案相容？
答：是的，Aspose.Tasks 支援各種版本的 Microsoft Project 文件，包括 MPP 和 XML 格式。
### Q：使用輪廓值時如何處理錯誤？
答：您可以實作錯誤處理機制（例如 try-catch 區塊）來優雅地管理異常。
### Q：我可以在專案中自訂輪廓值的外觀嗎？
答：是的，Aspose.Tasks 提供了廣泛的 API，可以根據您的要求自訂大綱值的外觀和行為。
### Q：在哪裡可以找到 Aspose.Tasks 的其他資源和支援？
答：您可以訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)尋求社區支持並探索[文件](https://reference.aspose.com/tasks/net/)有關 API 和功能的詳細資訊。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
