---
title: 使用 Aspose.Tasks for .NET 處理 MS 專案費率
linktitle: 在 Aspose.Tasks 中處理費率
second_title: Aspose.Tasks .NET API
description: 使用 Aspose.Tasks for .NET 輕鬆掌握管理 MS 專案費率。有效率地自動化任務，讓專案工作流程更加順暢。
type: docs
weight: 10
url: /zh-hant/net/rate-recurring-tasks/handling-rates/
---
## 介紹
歡迎來到我們關於使用 Aspose.Tasks for .NET 處理 MS 專案費率的教學！在本指南中，我們將逐步引導您完成整個過程，確保您可以有效管理 MS Project 文件中的費率。 Aspose.Tasks for .NET 提供了以程式設計方式操作 MS Project 檔案的強大功能，讓您可以輕鬆簡化專案管理任務。
## 先決條件
在我們深入學習本教程之前，請確保您具備以下先決條件：
1. 已安裝 Visual Studio：確保您的系統上安裝了 Visual Studio。
2.  Aspose.Tasks for .NET 函式庫：下載並安裝 Aspose.Tasks for .NET 函式庫。你可以找到下載鏈接[這裡](https://releases.aspose.com/tasks/net/).
3. C# 的基本了解：熟悉 C# 程式語言基礎。
## 導入命名空間
首先，您需要將必要的命名空間匯入到您的 C# 專案中。這些命名空間將提供對處理 MS 項目費率所需的類別和方法的存取。
## 步驟1：導入Aspose.Tasks命名空間
```csharp
using Aspose.Tasks;
using System;

```
現在，讓我們將提供的範例分解為多個步驟並徹底理解每個步驟。
## 第 1 步：載入專案文件
```csharp
//文檔目錄的路徑。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```
在此步驟中，我們將使用以下命令載入名為「Project1.mpp」的現有 MS Project 文件`Project`由Aspose.Tasks提供的類別。
## 第 2 步：新增資源並設定工作
```csharp
var resource = project.Resources.Add("Resource 1");
resource.Set(Rsc.Type, ResourceType.Work);
resource.Set(Rsc.Work, project.GetDuration(2d, TimeUnitType.Hour));
```
在這裡，我們為專案新增一個名為「Resource 1」的新資源，並將其類型設定為「Work」。我們也定義了該資源的工作持續時間。
## 第 3 步：設定標準費率
```csharp
resource.Set(Rsc.StandardRate, 20m);
```
在此步驟中，我們將資源的標準費率設定為每小時 20 美元。
## 第 4 步：定義費率期間
```csharp
var rate1 = resource.Rates.Add(new DateTime(2019, 1, 1, 8, 0, 0));
rate1.RateTable = RateType.A;
rate1.RatesFrom = new DateTime(2019, 1, 1, 8, 0, 0);
rate1.RatesTo = new DateTime(2019, 11, 11, 17, 0, 0);
rate1.StandardRate = 5m;
rate1.StandardRateFormat = RateFormatType.Hour;
rate1.OvertimeRate = 10m;
rate1.OvertimeRateFormat = RateFormatType.Hour;
```
在這裡，我們定義資源的費率週期。費率1的設定時間為2019年1月1日至2019年11月11日，指定了標準費率和加班費率。
## 第 5 步：新增另一個費率期間
```csharp
var rate2 = resource.Rates.Add(new DateTime(2019, 11, 12, 8, 0, 0));
rate2.RatesTo = new DateTime(2019, 12, 31, 17, 0, 0);
rate2.StandardRate = 10m;
rate2.StandardRateFormat = RateFormatType.Hour;
rate2.CostPerUse = 2m;
```
在最後一步中，我們新增了另一個費率期限，從 2019 年 11 月 12 日到 2019 年 12 月 31 日，並定義了不同的標準費率和每次使用成本。
恭喜！您已使用 Aspose.Tasks for .NET 成功處理了 MS Project Rates。
## 結論
以程式設計方式管理 MS 專案費率可以顯著增強您的專案管理工作流程。透過 Aspose.Tasks for .NET，您可以有效率地自動執行速率處理任務，從而節省時間和資源。
## 常見問題解答
### Q：Aspose.Tasks 可以處理複雜的專案結構嗎？
答：是的，Aspose.Tasks 提供了強大的功能來輕鬆處理複雜的專案結構。
### Q：Aspose.Tasks 是否與所有版本的 MS Project 檔案相容？
答：Aspose.Tasks支援各種版本的MS Project文件，確保不同平台的相容性。
### Q：我可以使用 Aspose.Tasks 修改 MS Project 檔案中的現有費率嗎？
答：當然！ Aspose.Tasks 可讓您修改現有費率、新增費率並動態管理它們。
### Q：Aspose.Tasks 是否支援自訂費率計算？
答：是的，您可以使用 Aspose.Tasks 實作自訂費率計算，以滿足特定的專案要求。
### Q：Aspose.Tasks 使用者是否有社群論壇或支援？
答： 是的，您可以訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)尋求協助並與其他使用者互動。