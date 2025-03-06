---
title: 使用 Aspose.Tasks 掌握 MS 專案費率
linktitle: Aspose.Tasks 中的費率收集
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 管理 MS Project 檔案中的費率。有效資源管理的逐步教學。
type: docs
weight: 11
url: /zh-hant/net/rate-recurring-tasks/rate-collection/
---
## 介紹
歡迎來到我們關於使用 Aspose.Tasks for .NET 在 MS Project 中管理費率的教學！在本指南中，我們將引導您完成使用 Aspose.Tasks 處理 MS Project 檔案中的費率的過程。無論您是經驗豐富的開發人員還是剛開始 .NET 開發，本教學都將為您提供有效處理專案中的速率的分步說明。
## 先決條件
在我們深入學習本教程之前，請確保您具備以下先決條件：
### 1.安裝Visual Studio
確保您的系統上安裝了 Visual Studio。如果您還沒有下載，可以從網站下載。
### 2..NET 的 Aspose.Tasks
從下列位置下載並安裝 Aspose.Tasks for .NET 函式庫[網站](https://releases.aspose.com/tasks/net/).
### 3. C#和.NET基礎知識
熟悉 C# 程式語言和 .NET 框架基礎知識，以便更好地理解本教程中提供的程式碼範例。
## 導入命名空間
在您的 C# 專案中，匯入必要的命名空間以使用 Aspose.Tasks 功能：
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
現在，讓我們將每個範例分解為多個步驟：
## 第 1 步：載入 MS 專案文件
```csharp
//文檔目錄的路徑。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
在這裡，我們創建一個新的`Project`透過載入現有的 MS Project 檔案來建立物件。
## 步驟 2： 新增資源並設定工時和費率
```csharp
var resource = project.Resources.Add("Test Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
resource.Set(Rsc.StandardRate, 20m);
```
我們為專案新增一個新資源，將其類型設定為工時、工時量和標準費率。
## 步驟 3：向資源新增費率
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
```
我們向資源新增費率，指定開始日期和結束日期、標準費率和費率格式。
## 第 4 步：列印費率訊息
```csharp
Console.WriteLine("Print rates of '{0}' resource: ", resource.Rates.ParentResource.Get(Rsc.Name));
Console.WriteLine("Count of rates: {0}", resource.Rates.Count);
Console.WriteLine("Is rate collection read-only: {0}", resource.Rates.IsReadOnly);
foreach (KeyValuePair<RateType, RateByDateCollection> sortedRates in resource.Rates)
{
    foreach (KeyValuePair<DateTime, Rate> pair in sortedRates.Value)
    {
        var rate = pair.Value;
        Console.WriteLine("Rates From: " + rate.RatesFrom);
        Console.WriteLine("Rates To: " + rate.RatesTo);
        Console.WriteLine("Rate Table: " + rate.RateTable);
        Console.WriteLine();
    }
}
```
此步驟列印有關與資源關聯的費率的資訊。
## 第 5 步：更新費率
```csharp
var rateToUpdate = resource.Rates[RateType.B][new DateTime(2019, 11, 12, 8, 0, 0)];
rateToUpdate.RatesTo = new DateTime(2020, 12, 31, 17, 0, 0);
Console.WriteLine("Rates From: " + rateToUpdate.RatesFrom);
Console.WriteLine("Rates To: " + rateToUpdate.RatesTo);
```
我們更新特定費率的結束日期。
## 第 6 步：刪除費率
```csharp
List<Rate> rates = resource.Rates.ToList(RateType.A);
for (var i = 0; i < rates.Count; i++)
{
    var rateToRemove = rates[i];
    resource.Rates.Remove(rateToRemove);
}
```
此步驟刪除特定類型的所有費率。
## 第 7 步：迭代剩餘利率
```csharp
Console.WriteLine("Iterate over the rates after removing the A-typed values: ");
List<Rate> list = resource.Rates.ToList();
foreach (var rt in list)
{
    Console.WriteLine("Rates From: " + rt.RatesFrom);
    Console.WriteLine("Rates To: " + rt.RatesTo);
    Console.WriteLine("Rate Table: " + rt.RateTable);
}
```
最後，我們迭代刪除後的剩餘速率。
## 結論
總而言之，本教學為您提供了使用 Aspose.Tasks for .NET 管理 MS Project 檔案中的費率的綜合指南。透過遵循本教學中概述的逐步說明，您可以有效地處理專案中的費率，確保準確的資源管理。
## 常見問題解答
### Q：我可以將 Aspose.Tasks for .NET 與其他專案管理軟體一起使用嗎？
答：是的，Aspose.Tasks for .NET 支援與各種專案管理軟體集成，包括 MS Project、Primavera 等。
### Q：Aspose.Tasks for .NET 是否與不同版本的 MS Project 檔案相容？
答：當然，Aspose.Tasks for .NET 支援處理不同版本的 MS Project 文件，確保靈活性和相容性。
### Q：Aspose.Tasks for .NET 是否提供文件和支援？
答：是的，您可以在 Aspose.Tasks 上找到全面的文件並造訪支援論壇[網站](https://reference.aspose.com/tasks/net/).
### Q：我可以在購買前試用 Aspose.Tasks for .NET 嗎？
答：是的，您可以免費試用 Aspose.Tasks for .NET 來評估其功能以及與您的要求的兼容性。
### Q：如何購買 Aspose.Tasks for .NET 的授權？
答：您可以從 Aspose.Tasks for .NET 購買許可證[網站](https://purchase.aspose.com/temporary-license/)，它提供了靈活的許可選項來滿足您的需求。