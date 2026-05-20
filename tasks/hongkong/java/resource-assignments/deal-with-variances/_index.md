---
date: 2026-05-20
description: 了解如何使用 Aspose.Tasks for Java 處理專案變異，包括如何有效取得成本變異、工作變異和日期變異。
keywords:
- handle project variances
- get cost variance
- Aspose.Tasks Java
linktitle: 處理 Aspense.Tasks 中的變異
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to handle project variances with Aspose.Tasks for Java, including
    how to get cost variance, work variance, and date variances efficiently.
  headline: How to Handle Project Variances with Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to handle project variances with Aspose.Tasks for Java, including
    how to get cost variance, work variance, and date variances efficiently.
  name: How to Handle Project Variances with Aspose.Tasks for Java
  steps:
  - name: Iterate through Resource Assignments
    text: 'To deal with variances, we need to iterate through resource assignments
      in the project. This is achieved using a simple loop:'
  - name: Retrieve Work Variance
    text: 'Work variance represents the deviation between planned work and actual
      work performed by a resource. To retrieve work variance for each resource assignment,
      use the following code snippet:'
  - name: Retrieve Start Variance
    text: 'Start variance signifies the variance between planned and actual start
      dates for a task. To fetch start variance, utilize the following code:'
  - name: Retrieve Finish Variance
    text: 'Finish variance denotes the difference between planned and actual finish
      dates for a task. To acquire finish variance, employ the following code:'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks integrates seamlessly with libraries such as Jackson
      for JSON, Apache POI for Excel, and JFreeChart for reporting.
    question: Can I integrate Aspose.Tasks with other Java libraries?
  - answer: Absolutely. It efficiently processes projects containing up to 10,000
      tasks and 5,000 resources without loading the entire file into memory.
    question: Is Aspose.Tasks suitable for large‑scale projects?
  - answer: Certainly. Use the variance values you retrieve to feed custom PDF, Excel,
      or HTML reports via Aspose.Words, Aspose.Cells, or standard Java templating
      engines.
    question: Can I customize reports based on variance analysis?
  - answer: Yes, users can access technical support through the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any assistance or queries.
    question: Is technical support available for Aspose.Tasks users?
  - answer: Yes, you can avail of a free trial of Aspose.Tasks from [here](https://releases.aspose.com/)
      to evaluate its features before making a purchase.
    question: Can I try Aspose.Tasks before purchasing?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks for Java 處理專案變異
url: /zh-hant/java/resource-assignments/deal-with-variances/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks for Java 處理專案變異

## 介紹
在本教學中，您將學習 **如何處理專案變異**，使用 Aspose.Tasks for Java。變異——指計畫與實際工作、成本、開始或完成日期之間的差異——是指示專案是否如期進行的重要訊號。Aspose.Tasks 為您提供簡潔、程式化的方式來取得並分析這些數值，讓您能快速進行資料驅動的調整。

## 快速解答
- **什麼是存取變異的主要類別？** `ResourceAssignment` 提供 `WorkVariance`、`CostVariance`、`StartVariance` 與 `FinishVariance` 等屬性。  
- **哪個方法會回傳成本變異？** 在 `ResourceAssignment` 實例上使用 `getCostVariance()`。  
- **此功能是否需要授權？** 是的，有效的 Aspose.Tasks 授權會解鎖所有變異 API。  
- **大型專案能否處理？** Aspose.Tasks 可處理最多 10,000 個工作項目的專案，且不需將整個檔案載入記憶體。  
- **需要哪個 Java 版本？** 支援 Java 8 及以上版本。

## 什麼是「處理專案變異」？
處理專案變異是指擷取基準（計畫）值與實際工作、成本、開始日期與完成日期之間的差異。透過分析這些差距，專案經理能評估績效、辨識時程或預算超支，並作出明智的重新規劃或資源調整決策，確保專案保持在正軌上。

## 為什麼使用 Aspose.Tasks 進行變異分析？
Aspose.Tasks 支援 **30 多種輸入/輸出檔案格式**，且能在一般伺服器硬體上於一秒內處理多百頁的排程。其 API 直接回傳變異數值，免除手動計算或第三方外掛的需求。

## 前置條件
1. 在系統上安裝 Java Development Kit (JDK)。  
2. 下載 Aspose.Tasks for Java 程式庫並加入至您的專案。您可從 [此處](https://releases.aspose.com/tasks/java/) 下載。  
3. 具備 Java 程式語言的基本知識。

## 匯入套件
`ResourceAssignment` 類別位於 `com.aspose.tasks` 命名空間。請在開始編寫程式碼前匯入必要的套件：

`ResourceAssignment` 類別代表資源與工作之間的關聯，提供可查詢的變異屬性。

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;

```

## 如何在 Aspose.Tasks 中處理專案變異？
使用 `new Project("yourfile.mpp")` 載入專案，然後遍歷每個 `ResourceAssignment` 以讀取其變異欄位。此單次遍歷即可取得每個指派的工作、成本、開始與完成變異，讓您即時建立績效儀表板。

### 步驟 1：遍歷資源指派
為了處理變異，我們需要遍歷專案中的資源指派。這可透過簡單的迴圈實現：

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "ResourceAssignmentVariance.mpp");
for (ResourceAssignment ra : project.getResourceAssignments()) {
    // Perform operations on each resource assignment
}
```

### 步驟 2：取得工作變異
工作變異代表資源的計畫工作與實際執行工作之間的偏差。若要取得每個資源指派的工作變異，請使用以下程式碼片段：

```java
System.out.println(ra.get(Asn.WORK_VARIANCE));
```

### 如何取得資源指派的成本變異？
若要取得特定指派的成本變異，請在 `ResourceAssignment` 實例上呼叫 `getCostVariance()` 方法。此方法計算基準成本與實際發生成本之間的金額差異，回傳一個 `double` 值，反映專案預設貨幣的變異。您可將此數值用於預算分析。

```java
System.out.println(ra.get(Asn.COST_VARIANCE));
```

### 步驟 4：取得開始變異
開始變異表示工作項目計畫開始日期與實際開始日期之間的差異。若要取得開始變異，請使用以下程式碼：

```java
System.out.println(ra.get(Asn.START_VARIANCE));
```

### 步驟 5：取得完成變異
完成變異表示工作項目計畫完成日期與實際完成日期之間的差異。若要取得完成變異，請使用以下程式碼：

```java
System.out.println(ra.get(Asn.FINISH_VARIANCE));
```

## 常見問題與解決方案
- **空值（null）:** 若工作項目沒有基準，變異屬性會回傳 `null`。使用前務必先檢查是否為 `null`。  
- **時區不匹配:** 日期以 UTC 儲存；若要顯示給使用者，請轉換為本地時區。  
- **大型檔案:** 對於包含數千個指派的專案，建議分批處理指派以降低記憶體使用量。

## 常見問答

**Q: 我可以將 Aspose.Tasks 與其他 Java 函式庫整合嗎？**  
A: 可以，Aspose.Tasks 可無縫整合如 Jackson（JSON）、Apache POI（Excel）以及 JFreeChart（報表）等函式庫。

**Q: Aspose.Tasks 適用於大型專案嗎？**  
A: 絕對適用。它能有效處理包含最多 10,000 個工作項目與 5,000 個資源的專案，且不需將整個檔案載入記憶體。

**Q: 我可以根據變異分析自訂報告嗎？**  
A: 當然可以。利用取得的變異數值，透過 Aspose.Words、Aspose.Cells 或標準的 Java 模板引擎產生自訂的 PDF、Excel 或 HTML 報告。

**Q: Aspose.Tasks 使用者是否有技術支援？**  
A: 有，使用者可透過 [Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15) 獲得任何協助或詢問。

**Q: 我可以在購買前試用 Aspose.Tasks 嗎？**  
A: 可以，您可從 [此處](https://releases.aspose.com/) 取得 Aspose.Tasks 的免費試用版，以評估其功能後再決定購買。

---

**最後更新：** 2026-05-20  
**測試環境：** Aspose.Tasks 24.12 for Java  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [使用 Aspose.Tasks 監控專案成本 - 加班與工作](/tasks/java/resource-assignments/overtime-remaining-costs-work/)
- [使用 Aspose.Tasks for Java 管理 MS Project 資源成本](/tasks/java/resource-management/resource-cost/)
- [使用 Aspose.Tasks for Java 在 MS Project 中設定專案開始日期](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}