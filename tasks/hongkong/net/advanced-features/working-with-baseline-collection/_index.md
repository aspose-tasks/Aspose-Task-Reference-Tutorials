---
date: 2026-04-06
description: 學習如何在 Aspose.Tasks for .NET 中刪除所有基線並管理基線集合，並提供一步一步的程式碼範例。
keywords:
- delete all baselines
- Aspose.Tasks baseline collection
- manage project baselines
linktitle: 使用 Aspose.Tasks 基線集合刪除所有基線
second_title: Aspose.Tasks .NET API
title: 使用 Aspose.Tasks 基線集合刪除所有基線
url: /zh-hant/net/advanced-features/working-with-baseline-collection/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 刪除所有基線（使用 Aspose.Tasks 基線集合）

## 簡介

Aspose.Tasks for .NET 讓您直接在 .NET 應用程式中操作 Microsoft Project 檔案。最強大的功能之一是 **刪除資源的所有基線**，當您需要重設專案的追蹤資料或開始新的基線期間時，這項功能相當重要。在本教學中，我們將從載入專案檔案到移除特定資源所附加的每一個基線，提供清晰、口語化的說明以及可直接執行的 C# 程式碼。

## 快速解答
- **刪除所有基線會怎樣？** 它會移除所選資源的所有已儲存基線記錄，清除歷史成本與工作資料。  
- **為什麼需要這樣做？** 在重大專案變更後或原始基線已不再相關時，用於重設追蹤。  
- **哪個函式庫提供此功能？** Aspose.Tasks for .NET。  
- **需要授權嗎？** 正式使用時需要有效的 Aspose.Tasks 授權；亦提供免費試用版。  
- **程式碼是否相容於 .NET 6 以上？** 是，API 支援 .NET Framework 4.5+、.NET Core 3.1+ 以及 .NET 5/6。

## 什麼是基線以及為什麼要刪除所有基線？

基線用於捕捉特定時間點的成本、工作與排程原始計畫。於專案執行期間，您可能會建立多個基線（Baseline 1、Baseline 2 等），以將實際進度與不同的規劃快照進行比較。然而，在某些情況下——例如專案重新範圍或全新開始——保留這些歷史基線會造成混亂。刪除所有基線可讓您重新開始，並設定反映當前實況的新基線。

## 先決條件

1. **Visual Studio** – 任意近期版本（Community、Professional 或 Enterprise）。  
2. **Aspose.Tasks for .NET** – 從[下載連結](https://releases.aspose.com/tasks/net/)下載。  
3. **Basic C# knowledge** – 您應該熟悉變數、迴圈與主控台輸出。  
4. **Microsoft Project 檔案** (`.mpp`) – 範例檔案名稱為 *WorkWithBaselineCollection.mpp*，將於範例中使用。

## 匯入命名空間

首先，將必要的命名空間匯入作用域，讓編譯器知道要從哪裡取得我們將使用的類別。

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## 步驟 1：載入專案檔案

我們先載入現有的 Project 檔案。請將 `DataDir` 調整為指向包含 `.mpp` 檔案的資料夾。

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## 步驟 2：取得目標資源

示範中，我們取得 UID = 1 的資源。實務上，您會依名稱或其他識別碼來定位資源。

```csharp
var resource = project.Resources.GetByUid(1);
```

## 步驟 3：顯示現有基線資訊

在刪除之前，先查看該資源目前附加的基線資訊會很有幫助。這可讓您確定正在移除正確的資料。

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## 步驟 4：遍歷所有基線

此處我們遍歷每個基線，列印關鍵指標，如成本、工作與賺得值 (BCWP/BCWS)。此步驟為可選，但對於記錄或稽核相當有用。

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## 刪除所有基線

現在執行核心動作：對選取的資源**刪除所有基線**。我們先將集合複製到清單，以避免在遍歷時修改集合，然後逐一移除每個基線。

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

此程式碼區塊執行後，`resource.Baselines.Count` 會變為 `0`，以確認所有基線記錄已被清除。

## 常見問題與提示

- **NullReferenceException** – 請確認專案檔確實包含您要定位的資源；否則 `GetByUid` 會回傳 `null`。  
- **Licensing** – 若未持有有效的 Aspose.Tasks 授權，輸出會出現浮水印且功能受限。  
- **Performance** – 對於極大型專案，可考慮使用 `Parallel.ForEach` 來加速移除過程，但請記得底層集合並非執行緒安全。

## 常見問與答

**Q: Aspose.Tasks 能處理大型專案檔案嗎？**  
A: 可以，Aspose.Tasks 已針對效能進行最佳化，能有效處理多 GB 的 `.mpp` 檔案。

**Q: 此函式庫相容於所有 Microsoft Project 版本嗎？**  
A: Aspose.Tasks 支援 Project 2000 至 Project 2024，涵蓋舊版 `.mpp` 格式與較新的 XML 為基礎的檔案。

**Q: 我可以在刪除前自訂基線嗎？**  
A: 當然可以。您可在決定移除前讀取或修改任何基線屬性（成本、工作、日期）。

**Q: Aspose.Tasks 能在雲端平台上運作嗎？**  
A: 能，API 可在任何相容 .NET 的環境執行，包括 Azure App Service、AWS Lambda（透過 .NET Core）以及 Docker 容器。

**Q: 我可以在哪裡向社群尋求協助？**  
A: 前往 [Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15) 與其他開發者及 Aspose 工作人員交流。

## 結論

本指南示範了如何使用 Aspose.Tasks for .NET **刪除資源的所有基線**。依循步驟式程式碼，您即可重設基線資料，保持專案追蹤的清晰，並為新一輪規劃周期做好排程準備。刪除後，您亦可嘗試建立新基線，以觀察函式庫如何更新專案檔案。

---

**最後更新：** 2026-04-06  
**測試於：** Aspose.Tasks 24.12 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}