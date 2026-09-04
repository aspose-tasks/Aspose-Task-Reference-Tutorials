---
date: 2026-06-15
description: 了解如何使用 Aspose.Tasks 在 Java 中計算資源百分比，包括如何取得 MS Project 資源的完成工作百分比。提供逐步說明與程式碼範例。
keywords:
- calculate resource percentage java
- get percent work complete
- Aspose.Tasks resource percentage
- Java project management API
linktitle: 在 Aspose.Tasks 中執行資源百分比計算
schemas:
- author: Aspose
  dateModified: '2026-06-15'
  description: Learn how to calculate resource percentage java with Aspose.Tasks,
    including how to get percent work complete for MS Project resources. Step‑by‑step
    guide with code examples.
  headline: calculate resource percentage java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: It’s the percentage of work a resource has completed relative to its total
      assigned work.
    question: What does “resource percentage” mean?
  - answer: '`Rsc.PERCENT_WORK_COMPLETE` via the `Resource` class.'
    question: Which API call returns this value?
  - answer: A temporary or full Aspose.Tasks license is required for production use.
    question: Do I need a license?
  - answer: Yes – the API works with Spring, Hibernate, and plain Java projects.
    question: Can I use this with other Java frameworks?
  - answer: Any recent version that supports the `Rsc` enumeration (e.g., 24.x).
    question: What version of Aspose.Tasks is needed?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks 在 Java 中計算資源百分比
url: /zh-hant/java/resource-management/percentage-calculations/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 計算資源百分比 Java 使用 Aspose.Tasks

## 簡介
歡迎！在本教學中，您將學習 **如何計算資源百分比 Java**，使用 Aspose.Tasks 函式庫 for Java。我們將示範如何提取每個資源在 Microsoft Project 檔案中的 *已完成工作百分比*，說明此指標的重要性，並提供您所需的完整程式碼。完成後，您將能將資源百分比計算整合到任何基於 Java 的專案管理解決方案中。

## 快速解答
- **資源百分比** 是什麼意思？它是資源已完成工作相對於其總指派工作量的百分比。  
- **哪個 API 呼叫會回傳此值？** `Rsc.PERCENT_WORK_COMPLETE` 透過 `Resource` 類別。  
- **我需要授權嗎？** 生產環境使用時需要臨時或完整的 Aspose.Tasks 授權。  
- **我可以在其他 Java 框架中使用嗎？** 可以 — 此 API 可與 Spring、Hibernate 以及純 Java 專案一起使用。  
- **需要哪個版本的 Aspose.Tasks？** 任何支援 `Rsc` 列舉的近期版本（例如 24.x）。

## 什麼是計算資源百分比 Java？
在 Java 中計算資源百分比涉及開啟 Microsoft Project 檔案，讀取每個資源的指派工作量，並判斷已完成工作所佔的比例。此指標協助專案經理評估進度、平衡工作負載，並在不需手動計算的情況下識別潛在延遲。

## 為何要取得已完成工作百分比？
取得每個資源的已完成工作百分比，可立即了解已完成的計畫工作量，讓您快速發現落後的任務或未充分利用的資源。此洞見支援即時決策與更精確的狀態報告。

## 先決條件
### Java 開發環境
確保已安裝 Java Development Kit (JDK)。您可以從 [此處](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) 下載 JDK。

### Aspose.Tasks 函式庫
從 [此處](https://releases.aspose.com/tasks/java/) 下載並將 Aspose.Tasks 函式庫加入您的專案，並依照文件中提供的安裝說明於 [此處](https://reference.aspose.com/tasks/java/) 進行設定。

## 匯入套件
`Resource` 類別代表專案資源，並提供存取如已完成工作百分比等欄位的功能。  
在開始編寫程式碼之前，讓我們匯入本教學所需的套件：
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## 如何設定專案檔案路徑？
透過提供絕對路徑或相對於應用程式工作目錄的路徑，指定您的 Microsoft Project 檔案位置。路徑字串必須指向有效的 *.mpp* 檔案，以便 Aspose.Tasks 能夠找到並開啟進一步處理。
```java
String dataDir = "Your Data Directory";
```
將 `"Your Data Directory"` 替換為包含 Microsoft Project 檔案的資料夾路徑。

## 如何載入專案？
使用先前定義的檔案路徑建立 `Project` 類別的新實例。`Project` 類別代表 Microsoft Project 檔案，提供對其任務、資源及其他專案資料的存取，並將所有內容載入記憶體以供分析。
```java
Project prj = new Project(dataDir + "Software Development.mpp");
```
此程式會從您指定的目錄載入 **Software Development.mpp** 檔案。

## 如何遍歷資源？
使用 `project.getResources()` 方法取得已載入專案中所有定義的資源集合。使用標準的 Java `for` 迴圈或增強的 `for‑each` 結構遍歷此集合，以便逐一檢查每個 `Resource` 物件並取得其相關欄位。
```java
for (Resource res : prj.getResources()) {
```
我們會遍歷專案中定義的每個資源。

## 如何檢查資源名稱並取得已完成工作百分比？
首先確保 `Resource` 物件的名稱非空，以避免處理佔位項目。接著呼叫 `res.get(Rsc.PERCENT_WORK_COMPLETE)`，它會回傳一個 double，代表該資源已完成工作的百分比，範圍為 0 到 100。您可以將此值格式化後顯示，或在後續計算中使用，以評估整體專案健康狀況。
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.PERCENT_WORK_COMPLETE));
}
```
程式碼首先確保資源具有名稱，然後列印該資源的 **已完成工作百分比** 值。

## 常見問題與解決方案
- **NullPointerException** — 確認專案檔案路徑正確且檔案能順利載入。  
- **百分比不正確** — 確認資源確實有指派工作；否則百分比會是 `0`。  
- **授權錯誤** — 使用有效的 Aspose.Tasks 授權或臨時評估授權，以避免執行時限制。

## 常見問題 (原文)
### 我可以在其他 Java 框架中使用 Aspose.Tasks for Java 嗎？
是的，Aspose.Tasks for Java 相容於各種 Java 框架，如 Spring、Hibernate 等。

### Aspose.Tasks 是否支援所有版本的 Microsoft Project 檔案？
Aspose.Tasks 支援所有版本的 Microsoft Project 檔案，包括 MPP、MPT、XML 等。

### 我可以使用 Aspose.Tasks 操作專案排程嗎？
當然，Aspose.Tasks 提供完整功能，可操作專案排程，包括任務、資源、行事曆等。

### 是否有 Aspose.Tasks 社群論壇可供支援？
是的，您可在 Aspose.Tasks 社群論壇 [此處](https://forum.aspose.com/c/tasks/15) 獲得協助並與其他使用者交流。

### Aspose.Tasks 是否提供臨時授權供評估使用？
是的，您可從 [此處](https://purchase.aspose.com/temporary-license/) 取得臨時評估授權。

## 其他常見問題
**Q:** 如何將輸出格式化為顯示帶有 % 符號的百分比？  
**A:** 使用 `res.get(Rsc.PERCENT_WORK_COMPLETE)` 取得數值，並以 `String.format("%.2f%%", value)` 進行格式化。

**Q:** 我可以篩選資源，只顯示完成度低於 50 % 的嗎？  
**A:** 可以，在列印前加入 `if` 條件檢查 `res.get(Rsc.PERCENT_WORK_COMPLETE) < 50`。

**Q:** 是否能將百分比寫回至 Project 檔案？  
**A:** `Rsc.PERCENT_WORK_COMPLETE` 欄位為唯讀；您需要改變任務指派才能調整此值。

**Q:** 這能用於 Project Online（雲端）檔案嗎？  
**A:** 必須先將 .mpp 檔案下載至本機；Aspose.Tasks 僅支援檔案格式，無法直接操作雲端服務。

## 使用 Aspose.Tasks 的量化效益
Aspose.Tasks 支援 **30 多種檔案格式**（MPP、MPT、XML、CSV 等），且可處理 **多達 10,000 個任務** 的專案，同時透過串流資料將記憶體使用量控制在 200 MB 以下。函式庫的 **唯讀 `Rsc.PERCENT_WORK_COMPLETE`** 欄位以 O(n) 時間計算，確保即使在大型排程中也能快速取得。

## 結論
本指南示範了使用 Aspose.Tasks **如何計算資源百分比 Java**，重點在於取得每個資源的 *已完成工作百分比*。依照上述步驟，您即可將精確的資源百分比分析嵌入 Java 應用程式，提升對專案健康與資源使用情況的可見性。

---

**最後更新：** 2026-06-15  
**測試環境：** Aspose.Tasks for Java 24.10  
**作者：** Aspose

## 相關教學

- [使用 Aspose.Tasks for Java 新增資源至專案](/tasks/java/resource-management/create-resources/)
- [使用 Aspose.Tasks for Java 管理 MS Project 資源成本](/tasks/java/resource-management/resource-cost/)
- [Aspose.Tasks 任務百分比完成計算](/tasks/java/task-properties/percentage-complete-calculations/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}