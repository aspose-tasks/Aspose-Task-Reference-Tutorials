---
date: 2026-07-05
description: 了解如何使用 Aspose.Tasks for .NET 追蹤專案預算與管理專案成本。定義 Cost Accrual Types 以實現精確的成本追蹤。
keywords:
- track project budget
- manage project costs
- how to set accrual
- define project cost tracking
- access resource by id
linktitle: Aspose.Tasks 中的 Cost Accrual Types
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  headline: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  type: TechArticle
- description: Learn how to track project budget and manage project costs using Aspose.Tasks
    for .NET. Define cost accrual types for accurate cost tracking.
  name: Track Project Budget with Cost Accrual Types in Aspose.Tasks
  steps:
  - name: Import Namespaces
    text: 'Let''s start by importing the necessary namespaces to access Aspose.Tasks
      functionality in our .NET project: Now that we have the namespaces ready, we
      can move on to loading a project file.'
  - name: Load Project File
    text: The `Project` class represents a Microsoft Project file and provides access
      to its tasks, resources, and other data. First, we need to load the project
      file into our application. We create a new `Project` object and initialize it
      with the path to our project file.
  - name: Access Resource
    text: 'The `Resources` collection holds all resources defined in the project.
      The `GetById` method retrieves a resource by its unique identifier. Next, we
      access the resource to which we want to apply the cost accrual type. We use
      the `GetById` method of the `Resources` collection and pass the resource ID '
  - name: Set Cost Accrual Type
    text: The `Set` method assigns a value to a resource field. Here, we set the cost
      accrual type for the resource. In this example, we are setting it to `CostAccrualType.End`,
      which means costs will not be accrued until remaining work is zero. Choosing
      `End` is ideal when you want to **track project budget*
  - name: Continue Working with the Project
    text: After setting the cost accrual type, you can continue working with the project
      as needed, performing additional operations or calculations such as generating
      cost reports, updating assignments, or exporting the file.
  type: HowTo
- questions:
  - answer: Yes, iterate through `project.Resources` and assign the desired `CostAccrualType`
      to each resource within a `foreach` loop.
    question: Can I change the cost accrual type for multiple resources simultaneously?
  - answer: Aspose.Tasks provides `Start`, `Prorated`, and `Duration`—each aligns
      with a different billing strategy.
    question: What are the other available cost accrual types besides `End`?
  - answer: Retrieve the value via `resource.Get(TskResource.CostAccrualType)`; it
      returns the enum representing the current setting.
    question: How can I determine the current cost accrual type for a specific resource?
  - answer: Absolutely. Both tasks and resources expose a `CostAccrualType` property,
      allowing independent configuration per entity.
    question: Is it possible to apply different cost accrual types to different tasks
      in the same project?
  - answer: No, the library currently supports the four built‑in types only; custom
      logic must be implemented externally if required.
    question: Does Aspose.Tasks support custom cost accrual types?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: 使用 Aspose.Tasks 追蹤專案預算與 Cost Accrual Types
url: /zh-hant/net/calendar-scheduling/cost-accrual-types/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 的成本累計類型追蹤專案預算

## 簡介

準確 **追蹤專案預算** 是成功交付專案的基礎。當成本資訊在適當時機被捕捉時，你可以預測超支、調整資源，並讓利害關係人即時掌握。Aspose.Tasks for .NET 為開發者提供細緻的成本累計控制，讓你自行決定 *何時* 記錄成本——無論是在工作開始時、持續累計，或僅在工作完成時。本教學將說明相關概念、示範如何設定累計類型，並提供可靠預算追蹤的最佳實踐。

## 快速解答
- **成本累計類型的主要目的為何？** 它決定在任務生命週期的哪個階段認列成本，從而實現精確的預算追蹤。  
- **哪個列舉值會延遲成本至工作完成才認列？** `CostAccrualType.End`。  
- **執行程式碼是否需要授權？** 需要，有效的 Aspose.Tasks 授權是正式環境使用的前提。  
- **是否可以一次變更多個資源的累計類型？** 可以——遍歷 `Resources` 集合並指派所需類型即可。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## 什麼是成本累計類型？
**成本累計類型** 告訴 Aspose.Tasks 何時將資源的成本套用到專案預算。它以 `CostAccrualType` 列舉表示，可於資源或任務層級設定。選擇正確的類型可確保成本資料符合組織的計費政策，無論是需要在工作開始時記錄、依期間比例分配，或僅在完成後認列。

## 為何使用成本累計類型追蹤專案預算？
Aspose.Tasks 支援 **四種** 累計選項——`Start`、`Prorated`、`Duration`、`End`——涵蓋常見的專案會計情境。選擇適當的選項可讓成本認列與合約計費週期同步、降低財務報表差異，並產生可順利整合至 ERP 系統的成本報表，同時在大型專案中保持低記憶體使用量。

## 先決條件

在開始之前，請確保具備以下條件：

### 1. 安裝 Aspose.Tasks for .NET
首先，需要在開發環境中安裝 Aspose.Tasks for .NET。可從[下載頁面](https://releases.aspose.com/tasks/net/)取得程式庫，並依照提供的安裝說明進行設定。

### 2. 熟悉 .NET Framework
需要具備 .NET Framework 與 C# 程式語言的基本知識，才能順利跟隨本教學中的範例。

## 如何為資源設定成本累計類型？

載入專案、定位目標資源，然後指派所需的 `CostAccrualType`。以下兩行程式碼模式是標準做法：建立 `Project` 實例、依 ID 取得資源，最後設定 `CostAccrualType`。此簡潔流程確保從資源加入的那一刻起，即可 **準確追蹤專案預算**。

### 步驟 1：匯入命名空間
先匯入必要的命名空間，以在 .NET 專案中存取 Aspose.Tasks 功能：

```csharp

```

完成命名空間的引用後，我們即可繼續載入專案檔案。

### 步驟 2：載入專案檔案
`Project` 類別代表 Microsoft Project 檔案，提供對其任務、資源及其他資料的存取。

```csharp
var project = new Project("Project2.mpp");
```

首先，我們需要將專案檔案載入應用程式。建立新的 `Project` 物件，並以專案檔案路徑作為建構子參數。

### 步驟 3：存取資源
`Resources` 集合包含專案中定義的所有資源。`GetById` 方法可依唯一識別碼取得資源。

```csharp
var resource = project.Resources.GetById(1);
```

接著，我們存取欲套用成本累計類型的資源。使用 `Resources` 集合的 `GetById` 方法，傳入資源 ID。此步驟示範 **依 ID 存取資源**，是自動化成本更新的常見需求。

### 步驟 4：設定成本累計類型
`Set` 方法用於為資源欄位指派值。

```csharp
resource.Set(Rsc.AccrueAt, CostAccrualType.End);
```

此處，我們將資源的成本累計類型設定為 `CostAccrualType.End`，表示成本將在剩餘工作為零時才累計。選擇 `End` 適用於希望在任務完全完成後才 **追蹤專案預算** 的情境。

### 步驟 5：繼續處理專案
設定完成本累計類型後，可依需求繼續對專案執行其他操作，例如產生成本報表、更新指派或匯出檔案。

## 常見陷阱與專業提示
- **專業提示：** 在修改累計類型後務必呼叫 `project.Save`，以確保變更寫入檔案。  
- **陷阱：** 若在從未開始工作的資源上設定 `CostAccrualType.Start`，會導致預算報表膨脹——請先確認任務排程。  
- **專業提示：** 需要批次更新大量資源時，可使用 `project.Resources.ToList()`，避免重複查找集合，提升大型專案的效能。

## 常見問題

**Q: 可以同時變更多個資源的成本累計類型嗎？**  
A: 可以，遍歷 `project.Resources`，在 `foreach` 迴圈中為每個資源指派所需的 `CostAccrualType`。

**Q: 除了 `End`，還有哪些可用的成本累計類型？**  
A: Aspose.Tasks 提供 `Start`、`Prorated`、`Duration`，每種皆對應不同的計費策略。

**Q: 如何取得特定資源目前的成本累計類型？**  
A: 透過 `resource.Get(TskResource.CostAccrualType)` 取得，回傳代表目前設定的列舉值。

**Q: 能否在同一專案的不同任務上套用不同的成本累計類型？**  
A: 當然可以。任務與資源皆暴露 `CostAccrualType` 屬性，允許針對每個實體獨立設定。

**Q: Aspose.Tasks 支援自訂成本累計類型嗎？**  
A: 不支援，函式庫目前僅提供四種內建類型；若需自訂邏輯，必須在程式外自行實作。

---

**最後更新：** 2026-07-05  
**測試環境：** Aspose.Tasks 24.8 for .NET  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [Aspose.Tasks 行事曆與排程](/tasks/net/calendar-scheduling/)
- [使用 Aspose.Tasks for .NET 處理 MS Project 费率](/tasks/net/rate-recurring-tasks/handling-rates/)
- [輕鬆管理 MS Project 資源的 Aspose.Tasks](/tasks/net/resource-risk-analysis/managing-resources/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}