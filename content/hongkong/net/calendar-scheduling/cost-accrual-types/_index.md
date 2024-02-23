---
title: Aspose.Tasks 中的成本應計類型
linktitle: Aspose.Tasks 中的成本應計類型
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 有效管理專案成本。定義成本應計類型以準確追蹤預算。
type: docs
weight: 19
url: /zh-hant/net/calendar-scheduling/cost-accrual-types/
---
## 介紹

在專案管理中，準確追蹤成本對於維持預算控制和確保專案成功至關重要。 Aspose.Tasks for .NET 提供了一套強大的工具來管理專案成本，包括定義不同成本應計類型的能力。本教學將引導您完成使用 Aspose.Tasks for .NET 來理解和實作成本應計類型的過程。

## 先決條件

在我們開始之前，請確保您符合以下先決條件：

### 1.安裝Aspose.Tasks for .NET

首先，您需要在開發環境中安裝 Aspose.Tasks for .NET。您可以從以下位置下載該程式庫[下載頁面](https://releases.aspose.com/tasks/net/)並按照提供的安裝說明進行操作。

### 2. 熟悉.NET Framework

遵循本教程中的範例需要具備 .NET 框架和 C# 程式語言的基本知識。

## 導入命名空間

首先，我們導入必要的命名空間來存取 .NET 專案中的 Aspose.Tasks 功能：

```csharp

```

現在我們已經介紹了先決條件並導入了所需的命名空間，讓我們繼續將每個範例分解為多個步驟。

## 第 1 步：載入專案文件

```csharp
var project = new Project("Project2.mpp");
```

首先，我們需要將專案文件載入到我們的應用程式中。我們創建一個新的`Project`物件並使用我們的專案文件的路徑對其進行初始化。

## 第 2 步：訪問資源

```csharp
var resource = project.Resources.GetById(1);
```

接下來，我們存取要應用成本應計類型的資源。我們使用`GetById`的方法`Resources`集合並將資源 ID 作為參數傳遞。

## 步驟 3：設定成本應計類型

```csharp
resource.Set(Rsc.AccrueAt, CostAccrualType.End);
```

在這裡，我們設定資源的成本應計類型。在本例中，我們將其設定為`CostAccrualType.End`，這意味著在剩餘工作量為零之前不會產生成本。

## 第 4 步：處理項目

設定成本應計類型後，您可以根據需要繼續處理項目，執行其他操作或計算。

## 結論

了解和實施成本應計類型對於有效的專案成本管理至關重要。透過 Aspose.Tasks for .NET，您可以根據專案需求輕鬆定義和自訂成本應計類型，確保整個專案生命週期中準確的成本追蹤和預算控制。

## 常見問題解答

### Q1：我可以同時更改多個資源的成本應計類型嗎？

A1：是的，您可以循環遍歷資源集合併單獨為每個資源設定成本應計類型。

### Q2：除了「結束」之外，還有哪些可用的成本應計類型？

 A2：Aspose.Tasks for .NET 提供了幾種其他成本應計類型，例如`Start`, `Prorated`，和`Duration`.

### 問題 3：如何確定資源目前的成本應計類型？

 A3：您可以使用下列指令擷取目前的成本應計類型：`Get`資源對像上的方法。

### 問題 4：我可以對同一專案中的不同任務應用不同的成本應計類型嗎？

A4：是的，您可以為專案中的每個任務和資源單獨設定成本應計類型。

### Q5：Aspose.Tasks for .NET 支援自訂成本應計類型嗎？

A5：從最新版本開始，Aspose.Tasks for .NET 不支援定義自訂成本應計類型。