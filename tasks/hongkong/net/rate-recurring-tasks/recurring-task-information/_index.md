---
title: 在 Aspose.Tasks 中提取重複任務訊息
linktitle: 在 Aspose.Tasks 中提取重複任務訊息
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 從 MS Project 檔案中提取重複任務資訊。 .NET 開發人員可以輕鬆整合。
weight: 13
url: /zh-hant/net/rate-recurring-tasks/recurring-task-information/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中提取重複任務訊息

## 介紹
Aspose.Tasks for .NET 是一個功能強大的程式庫，可讓開發人員在其 .NET 應用程式中使用 Microsoft Project 檔案。在本教程中，我們將探索如何使用 Aspose.Tasks 從 MS Project 檔案中提取重複任務資訊。
## 先決條件
在我們開始之前，請確保您具備以下先決條件：
1. 對 C# 程式語言有基本了解。
2. Visual Studio 安裝在您的系統上。
3. 安裝了 .NET 函式庫的 Aspose.Tasks。您可以從以下位置下載：[這裡](https://releases.aspose.com/tasks/net/).
## 導入命名空間
首先，在 C# 程式碼中導入必要的命名空間：
```csharp
    using Aspose.Tasks;
    using System;
    
```
現在，讓我們將範例分解為多個步驟：
## 第一步：設定專案文件路徑
```csharp
String DataDir = "Your Document Directory";
```
代替`"Your Document Directory"`以及 MS Project 檔案的路徑。
## 第 2 步：載入 MS 專案文件
```csharp
var project = new Project(DataDir + "TestRecurringTask2016.mpp");
```
該行初始化一個新的`Project`透過載入路徑指定的 MS Project 檔案來實現物件。
## 步驟 3：讀取任務的重複訊息
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    var info = task.RecurringInfo;
    if (info == null)
    {
        continue;
    }
    //訪問並顯示重複任務訊息
    Console.WriteLine("Start Date: " + info.StartDate);
    Console.WriteLine("Duration: " + info.Duration);
    Console.WriteLine("End Date: " + info.EndDate);
    //根據需要繼續顯示其他重複任務訊息
}
```
此循環迭代專案中的所有任務，並檢查每個任務是否具有與其關聯的重複資訊。如果是，它會檢索並顯示重複任務的各種屬性，例如開始日期、持續時間、結束日期等。
## 結論
在本教程中，我們學習如何使用 Aspose.Tasks for .NET 從 MS Project 檔案中提取重複任務資訊。有了這些知識，您現在可以將此功能整合到您的 .NET 應用程式中，以更有效地處理重複任務。
## 常見問題解答
### Q：我可以使用 Aspose.Tasks for .NET 修改重複任務資訊嗎？
答：是的，您可以使用提供的 API 以程式設計方式修改重複任務資訊。
### Q：Aspose.Tasks 是否支援 MS Project 以外的其他專案文件格式？
答：是的，Aspose.Tasks 支援各種專案文件格式，例如 MPP、XML 和 CSV。
### Q：Aspose.Tasks for .NET 有沒有免費試用版？
答：是的，您可以從以下位置下載免費試用版：[這裡](https://releases.aspose.com/).
### Q：在哪裡可以找到 Aspose.Tasks for .NET 的文檔？
答：你可以找到文檔[這裡](https://reference.aspose.com/tasks/net/).
### Q：如何獲得 Aspose.Tasks for .NET 的技術支援？
 A：您可以從Aspose.Tasks論壇獲得技術支持[這裡](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
