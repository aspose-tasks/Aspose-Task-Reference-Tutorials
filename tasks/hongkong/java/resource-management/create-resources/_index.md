---
date: 2026-08-18
description: 了解如何在 Java 中使用 Aspose.Tasks 新增 Microsoft Project 資源。本分步教學示範如何以程式方式建立與設定
  Microsoft Project 資源。
keywords:
- add resource ms project
- aspose tasks java
- resource management java
- add multiple resources
- how to add resource
lastmod: 2026-08-18
linktitle: 在 Aspose.Tasks 中建立資源
og_description: 了解如何在 Java 中使用 Aspose.Tasks 新增 Microsoft Project 資源。本指南在 10 分鐘內帶您完成前置作業、程式碼步驟及常見問題。
og_image_alt: Screenshot of Java code adding a resource to a Microsoft Project file
  with Aspose.Tasks
og_title: 使用 Aspose.Tasks for Java 新增 Microsoft Project 資源
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Learn how to add resource ms project in Java using Aspose.Tasks. This
    step‑by‑step tutorial shows creating and configuring Microsoft Project resources
    programmatically.
  headline: Add resource ms project with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to add resource ms project in Java using Aspose.Tasks. This
    step‑by‑step tutorial shows creating and configuring Microsoft Project resources
    programmatically.
  name: Add resource ms project with Aspose.Tasks for Java
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or newer installed.'
    text: '**Java Development Kit (JDK)** – version 8 or newer installed.'
  - name: '**Aspose.Tasks for Java library** – download it from the official Aspose.Tasks
      for Java download page [download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java library** – download it from the official Aspose.Tasks
      for Java download page [download page](https://releases.aspose.com/tasks/java/).'
  - name: An IDE (IntelliJ, Eclipse) or a build tool such as Maven/Gradle to reference
      the Aspose.Tasks JAR.
    text: An IDE (IntelliJ, Eclipse) or a build tool such as Maven/Gradle to reference
      the Aspose.Tasks JAR.
  type: HowTo
- questions:
  - answer: Call `project.getResources().add("Resource1");` repeatedly, or iterate
      over a collection of names and add each one inside a loop.
    question: How do I add multiple resources in one go?
  - answer: Yes—use `resource.set(ResourceFieldId.Text1, "Custom Value");` to store
      additional information such as department or skill level.
    question: Can I set custom fields for a resource?
  - answer: While Aspose.Tasks doesn’t read Excel directly, you can read the spreadsheet
      with Aspose.Cells, then create resources programmatically using the same `add`
      method.
    question: Is it possible to import resources from an Excel file?
  - answer: Yes—Aspose.Tasks can save to .xml, .pdf, .xlsx, and several other formats
      supported by the API.
    question: Does the library support saving to formats other than .mpp?
  - answer: The sample works with all recent releases; we tested it with Aspose.Tasks
      24.x for Java.
    question: What version of Aspose.Tasks is required for this code?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add resource ms project
- aspose.tasks
- java project automation
title: 使用 Aspose.Tasks for Java 新增 Microsoft Project 資源
url: /zh-hant/java/resource-management/create-resources/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 中使用 Aspose.Tasks 為 Microsoft Project 添加資源

## 簡介
在本教學中，您將學習如何使用 Aspose.Tasks for Java 程式化 **add resource ms project**（在 Microsoft Project 中添加資源）。無論您是構建自訂的專案管理解決方案，或是自動化大量更新現有的 Microsoft Project 檔案，以下步驟涵蓋從環境設定到儲存完整資源的全部過程。此方法可在任何執行 Java 的平台上運作，無需安裝 Microsoft Project。

## 快速解答
- **主要目的為何？** 使用 Java 向 Microsoft Project 檔案添加新資源（人員、設備或材料）。  
- **需要哪個函式庫？** Aspose.Tasks for Java。  
- **需要授權嗎？** 開發階段可使用免費試用版；正式上線則需永久授權以解鎖全部功能。  
- **實作需要多長時間？** 對於此處示範的基本情境，通常在 10 分鐘以內完成。  
- **可以一次添加多個資源嗎？** 可以——對每個額外資源重複 `add` 呼叫，或在集合上迴圈。

## 「add resource to project」是什麼？
**Add resource to project** 指將新資源記錄（例如團隊成員、設備或耗材）插入 Microsoft Project（.mpp）檔案中。加入後，該資源可指派給工作、追蹤成本，並出現在專案產生的報表中。

## 為何使用 Aspose.Tasks for Java？
只需兩行 Java 程式碼即可將資源添加至專案，且函式庫會自動處理所有底層 XML 與二進位結構。Aspose.Tasks 支援超過 **50+ API methods**，涵蓋工作、資源、行事曆與報表，且能在一般伺服器硬體上於 2 秒內處理超過 **10,000+ tasks** 的專案，十分適合企業級自動化。

## 前置條件
1. **Java Development Kit (JDK)** – 已安裝 8 版或更新版本。  
2. **Aspose.Tasks for Java library** – 從官方 Aspose.Tasks for Java 下載頁面下載 [download page](https://releases.aspose.com/tasks/java/)。  
3. IDE（如 IntelliJ、Eclipse）或建置工具（如 Maven/Gradle）以引用 Aspose.Tasks JAR。

## 匯入套件
在 Java 原始碼檔案中，匯入本教學將會使用的 Aspose.Tasks 必要類別：

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
```

## 步驟 1：初始化專案物件
`Project` 類別是 Aspose.Tasks 的頂層物件，代表記憶體中的單一 Microsoft Project 檔案。建立實例即可取得用於儲存工作、資源、行事曆及其他專案資料的容器。

```java
Project project = new Project();
```

## 步驟 2：添加資源
`Resource` 類別用於描述專案資源，例如人員、設備或材料。將實例加入專案的資源集合，即會在檔案中註冊該資源，之後即可指派給工作或設定成本費率。

```java
Resource resource = project.getResources().add("ResourceName");
```

> **專業提示：** 添加資源後，您可以設定額外屬性，例如 `resource.setCostRateTable(...)` 或 `resource.setType(ResourceType.Work)`，以微調其行為。

## 常見問題與解決方案
| 問題 | 原因 | 解決方式 |
|-------|-------|-----|
| **NullPointerException** 在呼叫 `project.getResources()` 時 | 專案物件尚未初始化。 | 確保在存取資源前先執行 `Project project = new Project();`。 |
| **資源未出現在已儲存的檔案中** | 在添加資源後忘記儲存專案。 | 呼叫 `project.save("MyProject.mpp");`（如有需要，加入儲存步驟）。 |
| **授權錯誤** | 使用試用版卻未套用臨時授權。 | 透過 `License license = new License(); license.setLicense("Aspose.Tasks.lic");` 套用臨時授權。 |

## 結論
您現在已學會如何使用 Aspose.Tasks for Java **add resource ms project**。此簡潔的程式化方法讓您能夠大規模管理資源、自動化大量更新，並將 Microsoft Project 資料整合至自己的 Java 應用程式，且不依賴任何 UI。

## 常見問答
**問：如何一次性添加多個資源？**  
A: 重複呼叫 `project.getResources().add("Resource1");`，或遍歷名稱集合，在迴圈中逐一加入。

**問：可以為資源設定自訂欄位嗎？**  
A: 可以——使用 `resource.set(ResourceFieldId.Text1, "Custom Value");` 來儲存額外資訊，例如部門或技能等級。

**問：能否從 Excel 檔案匯入資源？**  
A: 雖然 Aspose.Tasks 無法直接讀取 Excel，但您可以使用 Aspose.Cells 讀取試算表，然後以相同的 `add` 方法程式化建立資源。

**問：此函式庫支援儲存為 .mpp 以外的格式嗎？**  
A: 可以——Aspose.Tasks 能儲存為 .xml、.pdf、.xlsx 以及 API 支援的其他多種格式。

**問：此程式碼需要哪個版本的 Aspose.Tasks？**  
A: 此範例相容於所有近期版本；我們測試於 Aspose.Tasks 24.x for Java。

---

**最後更新：** 2026-08-18  
**測試環境：** Aspose.Tasks for Java 24.x (latest at time of writing)  
**作者：** Aspose

## 相關教學

- [如何建立資源 – 使用 Aspose.Tasks for Java 的資源管理](/tasks/java/resource-management/)
- [使用 Aspose.Tasks for Java 管理 Microsoft Project 資源成本](/tasks/java/resource-management/resource-cost/)
- [如何在 Aspose.Tasks 中添加資源至專案並處理層級延遲屬性](/tasks/java/resource-assignments/leveling-delay-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}