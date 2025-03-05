---
title: 在 Aspose.Tasks 中管理 MS 專案屬性集合
linktitle: 管理 Aspose.Tasks 中的擴充屬性集合
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 以高效率管理 MS Project 擴充屬性。透過逐步指導無縫操作任務屬性。
type: docs
weight: 12
url: /zh-hant/net/tasks-project-management/extended-attribute-collection/
---
## 介紹
您是否希望使用 Aspose.Tasks for .NET 來高效管理 MS Project 擴充屬性？在本教程中，我們將逐步指導您完成流程。讓我們深入了解吧！
## 先決條件
在我們開始之前，請確保您具備以下條件：
1. Visual Studio：在您的系統上安裝 Visual Studio。
2.  Aspose.Tasks for .NET：從下列位置下載並安裝 Aspose.Tasks for .NET[這裡](https://releases.aspose.com/tasks/net/).
3. C# 基礎知識：熟悉 C# 程式語言基礎。

## 導入命名空間
首先將必要的命名空間匯入到您的專案中：
```csharp
    using Aspose.Tasks;
    using System;
    
```
## 第 1 步：載入專案文件
首先，使用以下程式碼片段載入 MS Project 檔案：
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## 步驟2：存取任務和擴充屬性
存取特定任務及其擴充屬性：
```csharp
var task = project.RootTask.Children.GetById(1);
```
## 第三步：清除擴充屬性
如果需要，清除現有的擴充屬性：
```csharp
if (!task.ExtendedAttributes.IsReadOnly && task.ExtendedAttributes.Count > 0)
{
    task.ExtendedAttributes.Clear();
}
```
## 步驟 4：建立擴充屬性定義
為新的擴充屬性建立定義：
```csharp
var taskDefinition1 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
var taskDefinition2 = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Finish, ExtendedAttributeTask.Finish7, "Finish 7");
project.ExtendedAttributes.Add(taskDefinition1);
project.ExtendedAttributes.Add(taskDefinition2);
```
## 第 5 步：迭代任務擴充屬性
迭代任務擴展屬性：
```csharp
Console.WriteLine("Iterate over task extended attributes of " + task.Get(Tsk.Name) + " task: ");
foreach (var attribute in task.ExtendedAttributes)
{
    Console.WriteLine("Attribute FieldId: " + attribute.FieldId);
    Console.WriteLine("Attribute Value: " + attribute.DateValue);
    Console.WriteLine();
}
```
## 第6步：新增擴充屬性
為任務新增新的擴充屬性：
```csharp
var extendedAttribute1 = taskDefinition1.CreateExtendedAttribute();
extendedAttribute1.DateValue = new DateTime(2020, 4, 14, 8, 0, 0);
if (task.ExtendedAttributes.IndexOf(extendedAttribute1) < 0)
{
    task.ExtendedAttributes.Insert(0, extendedAttribute1);
}
var extendedAttribute2 = taskDefinition2.CreateExtendedAttribute();
extendedAttribute2.DateValue = new DateTime(2020, 4, 14, 17, 0, 0);
task.ExtendedAttributes.Add(extendedAttribute2);
```
## 第 7 步：使用擴充屬性
根據需要對擴充屬性進行操作。
## 第8步：刪除擴充屬性
透過索引或有條件地刪除擴展屬性：
```csharp
task.ExtendedAttributes.RemoveAt(0);
task.ExtendedAttributes.Remove(extendedAttribute2);
```
## 第 9 步：將屬性複製到另一個任務
將屬性複製到同一或不同項目中的另一個任務：
```csharp
var otherProject = new Project();
var otherTask = otherProject.RootTask.Children.Add("Other task");
foreach (var attribute in attributes)
{
    otherTask.ExtendedAttributes.Add(attribute);
}
```

## 結論
使用 Aspose.Tasks for .NET 可以無縫管理 MS Project 擴充屬性集合。透過遵循本教學中概述的步驟，您可以有效地處理擴充屬性，從而增強您的專案管理能力。
## 常見問題解答
### Q：我可以跨多個項目操縱擴充屬性嗎？
答：是的，您可以使用 Aspose.Tasks for .NET 在不同專案的任務之間複製擴充屬性。
### Q：每個任務的擴展屬性數量有限制嗎？
答：Aspose.Tasks for .NET 對每個任務的擴充屬性數量沒有固有的限制。
### Q：我可以建立自訂擴充屬性欄位嗎？
答：當然！ Aspose.Tasks for .NET 可讓您定義適合您的專案需求的自訂擴充屬性欄位。
### Q：Aspose.Tasks for .NET 支援讀寫各種版本的 MS Project 檔案嗎？
答：是的，Aspose.Tasks for .NET 支援跨不同版本的 MS Project 檔案格式。
### Q：Aspose.Tasks for .NET 有試用版嗎？
答：是的，您可以從以下位置下載免費試用版：[這裡](https://releases.aspose.com/).