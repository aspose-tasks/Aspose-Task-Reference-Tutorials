---
title: Aspose.Tasks 中的資源類型
linktitle: Aspose.Tasks 中的資源類型
second_title: Aspose.Tasks .NET API
description: 透過逐步教學，了解如何在 Aspose.Tasks for .NET 中使用不同類型的資源，包括工時、材料和成本資源。
type: docs
weight: 14
url: /zh-hant/net/resource-risk-analysis/resource-types/
---
## 介紹
Aspose.Tasks for .NET 是一個功能強大的程式庫，可讓開發人員以程式設計方式處理 Microsoft Project 檔案。無論您是管理任務、資源還是計劃，Aspose.Tasks 都可以透過提供一套全面的 API 來簡化流程。在本教程中，我們將深入研究您可以使用 Aspose.Tasks for .NET 在專案中使用的不同類型的資源。
## 先決條件
在我們開始之前，請確保您具備以下條件：
1. Visual Studio：安裝 Visual Studio，這是一個用於 .NET 開發的強大整合開發環境 (IDE)。
2.  Aspose.Tasks for .NET：下載並安裝 Aspose.Tasks for .NET 函式庫[這裡](https://releases.aspose.com/tasks/net/).
3. C# 基礎：熟悉 C#，用於 .NET 開發的程式語言。

## 導入命名空間
首先，讓我們匯入必要的命名空間來存取 Aspose.Tasks for .NET 的功能：
```csharp
    
```

## 第 1 步：建立一個新的專案實例
```csharp
var project = new Project();
```
此行初始化一個新的 Project 對象，該物件充當所有與專案相關的資料和操作的容器。
## 第 2 步：新增工作資源
```csharp
var work = project.Resources.Add("Work resource");
work.Set(Rsc.Type, ResourceType.Work);
```
在這裡，我們建立一個名為「Work resources」的新工作資源，並將其類型指定為 ResourceType.Work。
## 步驟 3：新增材質資源
```csharp
var material = project.Resources.Add("Material resource");
material.Set(Rsc.Type, ResourceType.Material);
material.Set(Rsc.MaterialLabel, "kg");
```
此步驟新增名為「Material resources」的材質資源，其類型設定為 ResourceType.Material。此外，我們將材料標籤指定為“kg”以指示計量單位。
## 步驟 4：新增成本資源
```csharp
var cost = project.Resources.Add("Cost resource");
cost.Set(Rsc.Type, ResourceType.Cost);
cost.Set(Rsc.Cost, 59.99m);
```
最後，我們新增一個名為「Cost resource」的成本資源，並將其類型設定為ResourceType.Cost。此外，我們將成本值設為 59.99，表示與該資源相關的貨幣價值。

## 結論
在本教程中，我們探討如何在 Aspose.Tasks for .NET 中使用不同類型的資源，包括工時、材料和成本資源。透過遵循逐步指南，您可以以程式設計方式有效地管理專案中的資源。
## 常見問題解答
### Q：我可以將 Aspose.Tasks for .NET 與其他專案管理軟體格式一起使用嗎？
答：是的，Aspose.Tasks 支援多種格式，包括 Microsoft Project (MPP)、Primavera P6 等。
### Q：Aspose.Tasks for .NET 有沒有免費試用版？
答：是的，您可以免費試用[這裡](https://releases.aspose.com/).
### Q：如何獲得 Aspose.Tasks for .NET 的技術支援？
答：您可以造訪Aspose.Tasks論壇[這裡](https://forum.aspose.com/c/tasks/15)尋求技術援助。
### Q：我可以購買 Aspose.Tasks for .NET 的臨時授權嗎？
答：是的，您可以購買臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
### Q：Aspose.Tasks for .NET 是否提供參考文件？
答： 是的，你可以找到文檔[這裡](https://reference.aspose.com/tasks/net/).