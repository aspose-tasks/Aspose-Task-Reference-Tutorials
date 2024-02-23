---
title: 使用 Aspose.Tasks for .NET 計量 MS 專案使用情況
linktitle: 計量 Aspose.Tasks 中的使用情況
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 有效監控和最佳化 MS Project 使用情況。高效專案管理的逐步指南。
type: docs
weight: 17
url: /zh-hant/net/license-management/metering-usage/
---
## 介紹
您是否希望透過 Aspose.Tasks 有效管理和監控您的 MS Project 使用情況？借助計量功能，您可以追蹤您的使用情況並優化您的專案管理工作。在本教學中，我們將指導您使用 Aspose.Tasks for .NET 逐步完成計量 MS Project 使用情況的過程。
## 先決條件
在我們深入了解 MS Project 使用情況之前，請確保您符合以下先決條件：
1.  Aspose.Tasks for .NET 函式庫：從下列位置下載並安裝 Aspose.Tasks for .NET 函式庫：[下載頁面](https://releases.aspose.com/tasks/net/),按照安裝說明在您的開發環境中設定庫。
2. 公鑰和私鑰：從 Aspose 取得您的公鑰和私鑰。這些鍵對於計量使用至關重要。如果您還沒有金鑰，您可以透過 Aspose 請求金鑰[臨時執照](https://purchase.aspose.com/temporary-license/)頁。

## 導入命名空間
在繼續之前，將必要的命名空間匯入到您的專案中：
```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
using System.Net;

```
## 第 1 步：設定計量
要開始計量 MS Project 使用情況，請透過提供您的公鑰和私鑰來設定計量環境：
```csharp
String DataDir = "Your Document Directory";
var metered = new Metered();
metered.SetMeteredKey("<public key>", "<private key>");
```
代替`"Your Document Directory"`替換為文檔目錄的路徑`<public key>`和`<private key>`使用從 Aspose 獲得的實際密鑰。
## 第 2 步：載入 MS 專案文件
接下來，使用 Aspose.Tasks 載入 MS Project 檔案：
```csharp
var project = new Project(DataDir + "Project2.mpp");
Console.WriteLine("Project Name: " + project.Get(Prj.Name));
```
此步驟從指定目錄載入名為「Project2.mpp」的 MS Project 檔案。您可以將檔案名稱替換為您自己的 MS Project 檔案。
## 第 3 步：處理項目
現在專案已加載，您可以根據專案管理任務的需要對其執行各種操作。
```csharp
//在此執行專案管理任務
```
## 第 4 步：檢查積分和位元組消耗
您可以查看您在使用期間花費的積分和消耗的位元組數：
```csharp
try
{
    Console.WriteLine("Credits spent: {0}", Metered.GetConsumptionCredit());
    Console.WriteLine("Bytes consumed: {0}", Metered.GetConsumptionQuantity());
}
catch (WebException)
{
    //在這裡處理異常
}
```
此步驟檢索並顯示您的操作所花費的積分和消耗的位元組。處理此過程中可能出現的任何異常。
## 第 5 步：重設計量金鑰
或者，您可以重設計量鍵以停止計數字節：
```csharp
metered.ResetMeteredKey();
```
此步驟停止計量過程並重設計量鍵。

## 結論
在本教學中，您學習如何使用 Aspose.Tasks for .NET 計量 MS Project 使用情況。透過執行這些步驟，您可以有效地監控和優化專案管理工作，同時確保高效的資源利用。
### 常見問題解答
### Q：我可以計量多個 MS Project 檔案的使用情況嗎？
答：是的，您可以透過單獨載入每個檔案並相應地監控使用情況來計量多個 MS Project 檔案的使用情況。
### Q：計量 MS Project 使用情況是否與所有版本的 Aspose.Tasks for .NET 相容？
答：是的，Aspose.Tasks for .NET 的所有版本都支援計量 MS Project 使用情況。
### Q：我需要網路連線才能計量使用嗎？
答：是的，需要網路連線才能與 Aspose 的伺服器進行通訊以計量使用情況。
### Q：我可以即時追蹤使用情況嗎？
答：是的，您可以透過定期檢查消耗的積分和消耗的位元組來即時追蹤使用情況。
### Q：試用版中是否可以計量 MS Project 使用情況？
答：是的，Aspose.Tasks for .NET 的試用版和授權版均提供計量 MS Project 使用情況。