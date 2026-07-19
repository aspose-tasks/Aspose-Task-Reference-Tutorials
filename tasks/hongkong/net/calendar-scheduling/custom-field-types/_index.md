---
date: 2026-07-19
description: 了解如何在 Aspose.Tasks for .NET 中新增自訂欄位類型，包含逐步程式碼、先決條件與常見問題。
keywords:
- how to add custom field
- add custom field to project
- define extended attribute
lastmod: 2026-07-19
linktitle: Aspose.Tasks 中的自訂欄位類型
og_description: 了解如何在 Aspose.Tasks for .NET 中新增自訂欄位類型。遵循此逐步指南，建立、定義與有效使用 extended
  attributes。
og_image_alt: Guide showing how to add custom field types in Aspose.Tasks using .NET
og_title: 如何在 Aspose.Tasks for .NET 中新增自訂欄位類型
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  headline: How to Add Custom Field Types in Aspose.Tasks for .NET
  type: TechArticle
- description: Learn how to add custom field types in Aspose.Tasks for .NET with step‑by‑step
    code, prerequisites, and FAQs.
  name: How to Add Custom Field Types in Aspose.Tasks for .NET
  steps:
  - name: Create Project Object
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Project
      file in memory. Instantiating it loads the file and gives you access to tasks,
      resources, and extended attributes.'
  - name: Define Custom Field
    text: '`ExtendedAttributeDefinition` describes a new column. In this example we
      create a **Text** type custom field for tasks and give it the alias “MyText”.
      The `ExtendedAttributeTask.Text1` enum value tells Aspose.Tasks where to store
      the value.'
  - name: Add Custom Field Definition to Project
    text: The project’s `ExtendedAttributes` collection holds all custom field definitions.
      Adding the definition makes it available for every task in the project.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks works with .NET Framework, .NET Core, and .NET 5/6/7.
    question: Can I use Aspose.Tasks with other .NET frameworks?
  - answer: Absolutely. It supports processing of projects with **up to 10,000 tasks**
      and can run in multi‑threaded server environments.
    question: Is Aspose.Tasks suitable for enterprise‑level applications?
  - answer: Yes—Aspose.Tasks reads and writes MPP, XML, HTML, and CSV formats, covering
      **all major Microsoft Project versions**.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Yes, you can add, update, and delete resources, as well as assign custom
      fields to them.
    question: Can I manipulate resource data using Aspose.Tasks?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      to interact with other users and get support from the Aspose team.
    question: Is there a community forum for Aspose.Tasks users?
  type: FAQPage
second_title: Aspose.Tasks .NET API
tags:
- custom field
- Aspose.Tasks
- .NET project management
- extended attributes
title: 如何在 Aspose.Tasks for .NET 中新增自訂欄位類型
url: /zh-hant/net/calendar-scheduling/custom-field-types/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中新增自訂欄位類型

## 簡介

在本教學中，您將學習如何使用 Aspose.Tasks for .NET 為 Microsoft Project 檔案新增**自訂欄位**類型。自訂欄位可讓您在工作、資源或專案本身直接儲存額外資訊——例如風險分數、部門代碼或自訂備註。我們將從環境設定開始，逐步說明如何定義、加入及驗證自訂文字欄位。

## 快速解答
- **什麼是自訂欄位？** 使用者自訂的欄位，可在工作/資源上儲存文字、數字、日期或旗標。  
- **哪個類別定義自訂欄位？** `ExtendedAttributeDefinition`。  
- **我可以將自訂欄位加入現有專案嗎？** 可以——載入專案、建立定義，然後加入集合。  
- **使用 Aspose.Tasks 是否需要授權？** 正式環境需要授權；評估可使用免費試用版。  
- **支援的 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## 什麼是 Aspose.Tasks 中的「新增自訂欄位」？
**新增自訂欄位**是指建立 `ExtendedAttributeDefinition` 並將其附加至專案的 `ExtendedAttributes` 集合的過程。這讓您能儲存標準 Project 結構中未包含的額外中繼資料。它可用於工作、資源或整個專案，讓您捕捉如風險等級、部門代碼或預設欄位未提供的自訂備註等資訊。

## 為何在專案管理中使用自訂欄位？
Aspose.Tasks 支援 **超過 50 種內建延伸屬性類型**，且允許您定義 **任意數量的自訂欄位**，對檔案大小影響不大。使用自訂欄位您可以：  
這些欄位會在 Microsoft Project 中顯示為額外的欄位，且可在公式、報表與篩選器中引用。它們儲存在專案檔內，隨檔案一起傳遞，確保下游工具仍保有自訂資料。

## 先決條件

### 1. 已安裝 Visual Studio
確保您的電腦已安裝 Visual Studio（2019 或更新版本）。可從 Microsoft 官方網站下載。

### 2. Aspose.Tasks for .NET
將 Aspose.Tasks NuGet 套件加入您的專案。可從 [here](https://releases.aspose.com/tasks/net/) 下載最新版本。

### 3. 基本的 C# 知識
您應熟悉 C# 語法、類別以及 .NET 專案結構。

## 匯入命名空間

`Project`、`ExtendedAttributeDefinition` 以及相關列舉皆屬於 `Aspose.Tasks` 命名空間。請在檔案頂部匯入：

`Aspose.Tasks` 命名空間提供處理 Microsoft Project 檔案所需的所有核心類型。

```csharp

```

## 如何將自訂欄位加入專案？

載入現有專案、建立自訂欄位定義，並將其加入專案的延伸屬性集合——只需三個簡潔步驟。此模式適用於工作、資源及整個專案，並確保在儲存檔案時自訂欄位會被保留。

### 步驟 1：建立 Project 物件
`Project` 是 Aspose.Tasks 的頂層物件，代表記憶體中的單一 Project 檔案。實例化它會載入檔案，並讓您存取工作、資源與延伸屬性。

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

### 步驟 2：定義自訂欄位
`ExtendedAttributeDefinition` 用於描述新欄位。在此範例中，我們為工作建立一個 **文字** 類型的自訂欄位，並將別名設為 “MyText”。`ExtendedAttributeTask.Text1` 列舉值告訴 Aspose.Tasks 該將值儲存於何處。

```csharp
var definition = ExtendedAttributeDefinition.CreateTaskDefinition(
    CustomFieldType.Text,
    ExtendedAttributeTask.Text1,
    "MyText");
```

### 步驟 3：將自訂欄位定義加入專案
專案的 `ExtendedAttributes` 集合保存所有自訂欄位定義。將定義加入後，即可在專案的每個工作中使用。

```csharp
project.ExtendedAttributes.Add(definition);
```

## 常見問題與解決方案
- **欄位未在 MS Project 介面顯示** – 確認已設定 `Alias` 屬性；MS Project 會以別名作為欄位標題。  
- **儲存時拋出例外** – 檢查專案檔案是否為唯讀，且已擁有有效授權。  
- **重新載入後自訂欄位值遺失** – 確保在為工作指派值後呼叫 `project.Save("output.mpp")`。

## 常見問與答

**Q: 我可以在其他 .NET 框架上使用 Aspose.Tasks 嗎？**  
A: 可以，Aspose.Tasks 支援 .NET Framework、.NET Core 以及 .NET 5/6/7。

**Q: Aspose.Tasks 是否適用於企業級應用程式？**  
A: 絕對適用。它支援處理 **多達 10,000 個工作** 的專案，且可在多執行緒伺服器環境中執行。

**Q: Aspose.Tasks 是否支援多種專案檔案格式？**  
A: 支援——Aspose.Tasks 能讀寫 MPP、XML、HTML 與 CSV 格式，涵蓋 **所有主要的 Microsoft Project 版本**。

**Q: 我可以使用 Aspose.Tasks 操作資源資料嗎？**  
A: 可以，您可以新增、更新、刪除資源，並為其指派自訂欄位。

**Q: 是否有 Aspose.Tasks 使用者社群論壇？**  
A: 有，您可前往 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 與其他使用者交流，並獲得 Aspose 團隊的支援。

---

**最後更新：** 2026-07-19  
**測試環境：** Aspose.Tasks 24.12 for .NET  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [精通 Aspose.Tasks 中的 MS Project 延伸屬性定義](/tasks/net/tasks-project-management/extended-attribute-definition-collection/)
- [使用 Aspose.Tasks 操作 MS Project 延伸屬性](/tasks/net/tasks-project-management/working-with-extended-attributes/)
- [Aspose.Tasks 中的欄位助手與 MS Project 整合](/tasks/net/tasks-project-management/field-helper/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}