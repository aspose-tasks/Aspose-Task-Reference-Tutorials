---
date: 2026-06-15
description: 了解如何使用 Aspose.Tasks for Java 從 MS Project 資源中提取時間相位資料。一步一步的指南，說明如何依 ID
  取得資源。
keywords:
- get resource by id
- Aspose.Tasks timephased data
- Java MS Project API
linktitle: 在 Aspose.Tasks 中讀取資源的時間相位資料
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to extract timephased data from MS Project resources using
    Aspose.Tasks for Java. Step‑by‑step guide to get resource by id.
  headline: Read Timephased Data for Resources in Aspose.Tasks – get resource by id
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports MPP, XML, CSV, and several other formats, allowing
      you to read and write across different standards.
    question: Can Aspose.Tasks handle other types of project files apart from Microsoft
      Project?
  - answer: Absolutely. The library works with all major IDEs (IntelliJ IDEA, Eclipse,
      NetBeans) and build tools (Maven, Gradle).
    question: Is Aspose.Tasks compatible with different Java development environments?
  - answer: Yes, you can create, modify, and delete tasks, resources, assignments,
      and even custom fields through the API.
    question: Can I manipulate project data using Aspose.Tasks?
  - answer: It is. Enterprises rely on Aspose.Tasks for high‑volume processing, batch
      conversions, and server‑side reporting because it requires no Microsoft Project
      installation.
    question: Is Aspose.Tasks suitable for enterprise‑level projects?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for assistance from the community and support team.
    question: Where can I find support if I encounter issues while using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: 在 Aspose.Tasks 中讀取資源的時間相位資料 – 依 ID 取得資源
url: /zh-hant/java/resource-management/read-timephased-data/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 讀取 Aspose.Tasks 中資源的時間相位資料

## 介紹
在本教學中，您將學習 **how to get resource by id** 並使用 Aspose.Tasks for Java 讀取其時間相位資料。我們將逐步說明——從設定專案資料夾到列印工作與成本的時間相位值——讓您能以程式方式從任何 Microsoft Project 檔案中提取有價值的排程資訊。Aspose.Tasks for Java 是一套完整的 API，讓開發者能在不安裝 Microsoft Project 的情況下建立、讀取、修改與轉換 Microsoft Project 檔案，支援廣泛的專案管理功能與格式。

## 快速解答
- **What does “get resource by id” do?** 它會根據唯一識別碼從 `Project` 中檢索特定的 `Resource` 物件。  
- **Which library handles timephased data?** Aspose.Tasks for Java 提供 `Resource.getTimephasedData` API。  
- **Do I need a license?** 開發時可使用免費試用版；正式環境需購買商業授權。  
- **Can I read large projects?** 可以 — Aspose.Tasks 能在不將整個檔案載入記憶體的情況下處理最多 10,000 個工作項的檔案。  
- **What Java version is required?** Java 8 或更高版本；此函式庫相容所有主流 JDK。

## “get resource by id” 是什麼？
`get resource by id` 是一個方法呼叫，透過資源的數值 ID 從已載入的 `Project` 中取得 `Resource` 實例。此操作允許精確存取資源的詳細屬性，例如指派、行事曆與自訂欄位，對於擷取與該資源相關的時間相位工作或成本資料至關重要。

## 為什麼使用 Aspose.Tasks 取得時間相位資料？
Aspose.Tasks 支援 **50+ input and output formats**（MPP、XML、CSV 等），且能在保持低記憶體使用率的同時，抽取跨多年排程的資源工作與成本時間相位值。API 預設以 15 分鐘間隔回傳資料，提供細緻的洞察以供報表或自訂分析使用。

## 前置條件
在開始之前，請確保您具備以下前置條件：
1. Java Development Kit (JDK)：確保系統已安裝 JDK。您可從 [website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) 下載並依照安裝說明進行。  
2. Aspose.Tasks for Java Library：從 [download page](https://releases.aspose.com/tasks/java/) 下載 Aspose.Tasks for Java 函式庫，並依文件中的安裝說明完成設定。

## 匯入套件
第一步是將所需的 Aspose.Tasks 類別匯入您的 Java 原始檔案中。

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```

## 步驟 1：設定資料目錄
首先，定義放置 MS Project 檔案的目錄。將資料夾與原始程式碼分離，可讓專案更易於維護。

```java
String dataDir = "Your Data Directory";
```

## 步驟 2：讀取 MS Project 範本檔案
指定您的 MS Project 範本檔案名稱。使用範本可確保不同專案之間的欄位設定保持一致。

```java
String fileName = "ResourceTimephasedData.mpp";
```

## 步驟 3：將輸入檔案讀取為 Project
`Project` 類別是 Aspose.Tasks 的核心物件，代表記憶體中的 Microsoft Project 檔案。載入檔案後，即可以程式方式存取工作、資源與排程資訊。

```java
Project project = new Project(dataDir + fileName);
```

## 步驟 4：依 ID 取得資源
若要取得特定資源，呼叫 `getResources().getById(id)` 方法。這正是主要關鍵字所指的操作。

```java
Resource resource = project.getResources().getByUid(1);
```

## 步驟 5：列印資源工作時間相位資料
取得 `Resource` 物件後，可呼叫 `resource.getTimephasedData(ResourceTimephasedDataType.Work)` 取得隨時間變化的工作分配。回傳的集合包含 `TimephasedData` 物件，內含開始日期、結束日期以及每個間隔的工作量。

```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```

## 步驟 6：列印資源成本時間相位資料
同理，`resource.getTimephasedData(ResourceTimephasedDataType.Cost)` 會以相同的時間間隔回傳成本資訊，對於預算與成本追蹤報表相當有用。

```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## 如何在單行取得資源 ID？
載入專案後，呼叫 `project.getResources().getById(5)`——將 **5** 替換為您實際需要的資源 ID。此單一呼叫會回傳 `Resource` 物件，之後您即可查詢其時間相位資料、指派或自訂欄位。此方法因資源在內部已索引，執行時間為 O(1)。

## 常見問題與解決方案
- **Resource not found** – 確認該 ID 在專案檔中存在；ID 從 1 開始，且每個資源唯一。  
- **Empty timephased data** – 驗證該資源是否有工作或成本指派；否則集合會是空的。  
- **Large file performance** – 使用 `Project.setLoadOptions(LoadOptions.fromFile(...))` 為超過 500 MB 的專案啟用延遲載入。

## 常見問答

**Q: Can Aspose.Tasks handle other types of project files apart from Microsoft Project?**  
A: 可以，Aspose.Tasks 支援 MPP、XML、CSV 等多種格式，讓您能在不同標準之間讀寫。

**Q: Is Aspose.Tasks compatible with different Java development environments?**  
A: 當然。此函式庫相容所有主流 IDE（IntelliJ IDEA、Eclipse、NetBeans）與建置工具（Maven、Gradle）。

**Q: Can I manipulate project data using Aspose.Tasks?**  
A: 可以，您能透過 API 建立、修改、刪除工作、資源、指派，甚至自訂欄位。

**Q: Is Aspose.Tasks suitable for enterprise‑level projects?**  
A: 是的。企業依賴 Aspose.Tasks 進行高量處理、批次轉換與伺服器端報表，因為它不需要安裝 Microsoft Project。

**Q: Where can I find support if I encounter issues while using Aspose.Tasks?**  
A: 您可前往 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 向社群與支援團隊尋求協助。

## 結論
在本教學中，我們學會了如何 **get resource by id** 並使用 Aspose.Tasks for Java 讀取其時間相位工作與成本資料。依循這些步驟，您即可有效從專案檔案中抽取有價值的排程資訊，並將其整合至自訂報表或分析管線。

---

**最後更新：** 2026-06-15  
**測試版本：** Aspose.Tasks 24.11 for Java  
**作者：** Aspose

## 相關教學

- [Add resource to project with Aspose.Tasks for Java](/tasks/java/resource-management/create-resources/)
- [Manage MS Project Resource Costs with Aspose.Tasks for Java](/tasks/java/resource-management/resource-cost/)
- [Read Work Weeks Java from MS Project Calendar Aspose.Tasks](/tasks/java/calendars/read-work-weeks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}