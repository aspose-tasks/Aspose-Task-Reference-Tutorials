---
date: 2026-06-15
description: 了解如何使用 Aspose.Tasks for Java 在 MS Project 檔案中管理成本，包括如何載入 MPP 檔案以及讀取 actual
  cost work 和 budgeted cost schedule。
keywords:
- how to manage costs
- actual cost work
- load mpp file
- budgeted cost schedule
linktitle: 處理 Aspose.Tasks 中的資源成本
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to manage costs in MS Project files using Aspose.Tasks for
    Java, including how to load an MPP file and read actual cost work and budgeted
    cost schedule.
  headline: How to Manage Costs in MS Project with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to manage costs in MS Project files using Aspose.Tasks for
    Java, including how to load an MPP file and read actual cost work and budgeted
    cost schedule.
  name: How to Manage Costs in MS Project with Aspose.Tasks for Java
  steps:
  - name: Basic understanding of Java programming.
    text: Basic understanding of Java programming.
  - name: Aspose.Tasks for Java library added to your project (Maven/Gradle or manual
      JAR).
    text: Aspose.Tasks for Java library added to your project (Maven/Gradle or manual
      JAR).
  - name: Access to a Microsoft Project file (`.mpp`) you want to analyze.
    text: Access to a Microsoft Project file (`.mpp`) you want to analyze.
  type: HowTo
- questions:
  - answer: Yes, it fully supports nested summary tasks, multiple resource calendars,
      and custom fields across all supported Project versions.
    question: Can Aspose.Tasks for Java handle complex project structures?
  - answer: Absolutely. Aspose.Tasks reads and writes files from Microsoft Project
      2000 up to the latest 2023 format.
    question: Is the library compatible with different versions of Microsoft Project
      files?
  - answer: Yes, the API returns standard Java objects, allowing seamless integration
      with logging frameworks, ORM tools, or reporting libraries.
    question: Can I integrate Aspose.Tasks for Java with other Java libraries?
  - answer: Aspose provides dedicated forum support, detailed documentation, and responsive
      email assistance for licensed users.
    question: Does Aspose.Tasks for Java offer customer support?
  - answer: You can download a 30‑day evaluation license from the Aspose website to
      explore all features without cost.
    question: Is there a free trial available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: 如何在 MS Project 中使用 Aspose.Tasks for Java 管理成本
url: /zh-hant/java/resource-management/resource-cost/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 MS Project 中使用 Aspose.Tasks for Java 管理成本

## 介紹

管理專案預算是每位專案經理的核心職責，而**如何有效管理成本**可能決定專案的成敗。Aspose.Tasks for Java 為您提供對 Microsoft Project 檔案的程式化控制，讓您在不手動開啟 .mpp 檔案的情況下讀取與更新資源成本資料。在本教學中，您將一步步了解如何載入 MPP 檔案、檢查實際成本工作，並為每個資源提取預算成本排程。

## 快速解答
- **Aspose.Tasks for Java 的功能是什麼？** 它可以讀寫 Microsoft Project 檔案 (.mpp)，無需安裝 Microsoft Project。  
- **如何載入 MPP 檔案？** 使用 `new Project("path/to/file.mpp")` —— API 會在記憶體中解析檔案。  
- **有哪些成本欄位可用？** Actual Cost Work (ACWP)、Budgeted Cost of Work Scheduled (BCWS) 與 Budgeted Cost of Work Performed (BCWP)。  
- **開發是否需要授權？** 測試可使用免費暫時授權，正式環境需購買完整授權。  
- **支援哪些 Java 版本？** Java 8 及以上版本，包括 Java 17 LTS。

## 如何在 MS Project 中管理成本？

使用 `new Project("yourFile.mpp")` 載入您的專案，然後遍歷每個 `Resource` 物件以讀取如 ACWP、BCWS 與 BCWP 等成本相關屬性。Aspose.Tasks 會自動將內部成本值轉換為專案的貨幣，讓您直接顯示或儲存。此方法可省去手動試算表計算，並確保所有專案報告的資料一致性。

## 前置條件

1. 基本的 Java 程式設計概念。  
2. 已在專案中加入 Aspose.Tasks for Java 函式庫（Maven/Gradle 或手動 JAR）。  
3. 可取得您想要分析的 Microsoft Project 檔案（`.mpp`）。  

## 匯入套件

`Project` 與 `Resource` 類別是操作專案資料的入口點。

`Project` 類別是 Aspose.Tasks 的最高層物件，代表記憶體中的單一 Microsoft Project 檔案。  
```text
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```
```

## 步驟 1：定義資料目錄

首先，指定包含 `.mpp` 檔案的資料夾。此路徑可以是絕對路徑或相對於應用程式工作目錄的路徑。

```text
```java
String dataDir = "Your Data Directory";
```
```

## 步驟 2：載入 MS Project 檔案

`Project` 會載入檔案並建立可供查詢的物件模型。API 在不需要安裝 Microsoft Project 的情況下解析檔案，支援超過 30 種輸入格式。

```text
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
```

## 步驟 3：遍歷資源

`Resource` 物件代表消耗預算的人員、設備或材料。您可以遍歷 `project.getResources()` 集合以存取每一個資源。

```text
```java
for (Resource res : prj.getResources()) {
```
```

## 步驟 4：檢查資源名稱與成本

對於每個資源，先確認名稱已定義，然後讀取成本欄位。`getActualCost()` 方法回傳 **實際成本工作** (ACWP)，而 `getBudgetedCost()` 則提供 **預算成本排程** (BCWS/BCWP)。

```text
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.COST));
    System.out.println(res.get(Rsc.ACWP));
    System.out.println(res.get(Rsc.BCWS));
    System.out.println(res.get(Rsc.BCWP));
}
```
```

## 為何使用 Aspose.Tasks for Java 載入 MPP 檔案？

Aspose.Tasks 支援 **30+ 檔案格式**（包括 `.mpp`、`.xml` 與 `.xlsx`），且能在使用低於 200 MB 記憶體的情況下處理最多 **10,000 個工作**的專案。此函式庫在伺服器端執行所有計算，免除需要授權的 Microsoft Project。

## 常見問題與解決方案

- **資源名稱為 null：** 某些舊版檔案包含佔位資源。存取成本屬性前務必檢查 `resource.getName() != null`。  
- **大型檔案導致記憶體壓力：** LoadOptions 為設定類別，可讓您指定載入哪些專案資料。使用 `project.setLoadOptions(LoadOptions.setLoadResourceData(false))` 只載入必要資料，之後如需再啟用。  
- **貨幣不匹配：** API 會遵循專案的貨幣設定；如有需要可使用 `project.getRootTask().setCostRateTable(CostRateTableType.CostRateTable1)` 進行覆寫。CostRateTableType 列舉了可套用於工作項目的不同成本費率表。  

## 常見問答

**Q: Aspose.Tasks for Java 能處理複雜的專案結構嗎？**  
A: 可以，它完整支援巢狀彙總工作、 多個資源行事曆，以及跨所有支援的 Project 版本的自訂欄位。

**Q: 此函式庫與不同版本的 Microsoft Project 檔案相容嗎？**  
A: 絕對相容。Aspose.Tasks 能讀寫從 Microsoft Project 2000 到最新 2023 版式的檔案。

**Q: 我可以將 Aspose.Tasks for Java 與其他 Java 函式庫整合嗎？**  
A: 可以，API 回傳標準的 Java 物件，讓您能與日誌框架、ORM 工具或報告函式庫無縫整合。

**Q: Aspose.Tasks for Java 提供客戶支援嗎？**  
A: Aspose 為授權使用者提供專屬論壇支援、詳細文件與即時的電子郵件協助。

**Q: 是否有 Aspose.Tasks for Java 的免費試用？**  
A: 您可從 Aspose 官方網站下載 30 天評估授權，免費體驗全部功能。

---

**最後更新：** 2026-06-15  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose

## 相關教學

- [How to Calculate Cost Variance and Manage Assignment Costs with Aspose.Tasks](/tasks/java/resource-assignments/assignment-cost/)
- [Budget, Work, and Cost Management for Tasks in Aspose.Tasks](/tasks/java/task-properties/task-budget-work-cost/)
- [Add resource to project with Aspose.Tasks for Java](/tasks/java/resource-management/create-resources/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}