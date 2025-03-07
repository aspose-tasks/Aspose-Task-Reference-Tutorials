---
title: 在 Aspose.Tasks 中管理專案資源集合
linktitle: 在 Aspose.Tasks 中管理資源集合
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks API 在 .NET 中有效管理 Microsoft Project 資源集合。提高生產力和靈活性。
weight: 13
url: /zh-hant/net/resource-risk-analysis/managing-resource-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中管理專案資源集合

## 介紹
在本教學中，我們將探討如何使用 Aspose.Tasks for .NET 有效管理 Microsoft Project 資源集合。 Aspose.Tasks 是一個功能強大的 API，使開發人員能夠以程式設計方式處理 Microsoft Project 文件，從而實現專案資料的無縫整合和操作。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
1. C# 和 .NET Framework 知識：本教學假設您熟悉 C# 程式語言和 .NET Framework。
2. 安裝Aspose.Tasks for .NET：確保您已經安裝了Aspose.Tasks for .NET。您可以從以下位置下載：[這裡](https://releases.aspose.com/tasks/net/).
3. 開發環境設定：使用 Visual Studio 或任何其他首選 IDE 設定開發環境。

## 導入命名空間
在開始之前，導入必要的命名空間以存取 Aspose.Tasks 功能：
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## 第 1 步：載入專案文件
首先，將 Microsoft Project 檔案載入到 Aspose.Tasks 專案物件中：
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "SampleProject.mpp");
```
## 第2步：新增空資源
接下來，讓我們為專案新增一個空資源：
```csharp
var resource = project.Resources.Add();
resource.Set(Rsc.Type, ResourceType.Work);
```
## 步驟 3：新增資源並指定名稱
現在，將具有指定名稱的資源新增至專案：
```csharp
var developer = project.Resources.Add("Developer");
developer.Set(Rsc.Type, ResourceType.Work);
```
## 步驟 4：在另一個資源之前新增資源
根據 ID 將具有指定名稱的資源新增到另一個資源之前：
```csharp
var manager = project.Resources.Add("Manager", developer.Get(Rsc.Id));
manager.Set(Rsc.Type, ResourceType.Work);
```
## 步驟5：透過ID或UID存取資源
您可以透過 ID 或 UID 存取資源：
```csharp
var devResource = project.Resources.GetById(4);
devResource.Set(Rsc.Code, "12345");
var manResource = project.Resources.GetByUid(4);
manResource.Set(Rsc.Code, "54321");
```
## 步驟6：列印資源資訊
列印有關專案資源的資訊：
```csharp
Console.WriteLine("Print the resources of " + project.Resources.ParentProject.Get(Prj.Name) + " project.");
Console.WriteLine("Count of resources: " + project.Resources.Count);
foreach (var rsc in project.Resources)
{
    Console.WriteLine("Resource Name: " + rsc.Get(Rsc.Name));
}
```
## 步驟7：刪除資源
從專案中刪除資源：
```csharp
List<Resource> list = project.Resources.ToList();
foreach (var rsc in list)
{
    rsc.Delete();
}
```

## 結論
使用 Aspose.Tasks for .NET 管理 Microsoft Project 資源集合為開發人員提供了一組強大的工具，可以以程式設計方式有效地處理專案資源。透過遵循本教學中概述的步驟，您可以無縫地操作專案中的資源，從而提高專案管理任務的生產力和靈活性。
## 常見問題解答
### Q：Aspose.Tasks 可以處理大型專案文件嗎？

答：是的，Aspose.Tasks 旨在高效處理大型專案文件，提供高效能和可靠性。

### Q：Aspose.Tasks 是否與不同版本的 Microsoft Project 相容？

答：Aspose.Tasks 支援各種版本的 Microsoft Project，確保不同環境下的相容性。

### Q：我可以使用 Aspose.Tasks 自訂資源屬性嗎？

答：當然，Aspose.Tasks 提供了根據特定專案需求自訂資源屬性的廣泛功能。

### Q：Aspose.Tasks 支援多執行緒並發操作嗎？

答：是的，Aspose.Tasks 支援多線程，允許對專案資料進行並發操作以提高效能。

### Q：Aspose.Tasks 用戶可以獲得技術支援嗎？

答：是的，Aspose.Tasks 用戶可以透過論壇獲得技術支持[這裡](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
