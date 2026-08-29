---
date: 2026-08-29
description: 了解如何使用 Aspose.Tasks for Java 設定基準持續時間並追蹤專案進度。本一步一步指南可協助您有效管理任務基準。
keywords:
- track project progress
- manage project baselines
- Aspose.Tasks baseline duration
- Java project scheduling
- baseline management
lastmod: 2026-08-29
linktitle: 如何在 Aspose.Tasks for Java 中設定基準持續時間
og_description: 了解如何使用 Aspose.Tasks for Java 設定基準持續時間並追蹤專案進度。請參考本詳細指南，以有效管理任務基準。
og_image_alt: Developer guide showing baseline duration setup with Aspose.Tasks for
  Java
og_title: 如何設定基準持續時間以追蹤專案進度
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  headline: How to set baseline duration to track project progress
  type: TechArticle
- description: Learn how to set baseline duration and track project progress using
    Aspose.Tasks for Java. This step‑by‑step guide helps you manage task baselines
    efficiently.
  name: How to set baseline duration to track project progress
  steps:
  - name: '**Java Development Environment** – JDK 8+ installed and configured.'
    text: '**Java Development Environment** – JDK 8+ installed and configured.'
  - name: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
    text: '**Aspose.Tasks for Java** – download the library from the [Aspose.Tasks
      for Java download page](https://releases.aspose.com/tasks/java/).'
  - name: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
    text: '**IDE or build tool** – Maven, Gradle, or any IDE you prefer.'
  type: HowTo
- questions:
  - answer: No. Calling `project.setBaseline(BaselineType.Baseline)` records the baseline
      for all tasks in the project at once.
    question: Do I need to call `setBaseline` for each task individually?
  - answer: Use `project.setBaseline(BaselineType.Baseline1)` (or Baseline2‑Baseline10)
      after updating the task’s schedule.
    question: How can I set an interim baseline for a specific task?
  - answer: Yes. Iterate over `task.getBaselines()` and write the desired fields to
      a CSV file using standard Java I/O.
    question: Is it possible to export the baseline data to CSV?
  - answer: Absolutely. Load the file with `new Project("myproject.mpp")` and then
      access each task’s baselines as shown above.
    question: Can I read an existing .mpp file that already contains baselines?
  - answer: Aspose.Tasks works with single‑project .mpp files. For multi‑project scenarios,
      combine the projects programmatically.
    question: Does Aspose.Tasks handle multi‑project files?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- baseline duration
- Aspose.Tasks
- Java project management
- task baselines
title: 如何設定基準持續時間以追蹤專案進度
url: /zh-hant/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何設定基準持續時間以追蹤專案進度

## 介紹
追蹤專案進度的起點是穩固的基準。在本教學中，您將學會如何使用 Aspose.Tasks for Java 在 Microsoft Project 檔案中 **設定基準持續時間**，並了解為何在專案早期建立基準有助於在整個專案生命週期中監控排程漂移、成本差異與資源過度配置。

## 快速解答
- **「設定基準」是什麼意思？** 它會記錄任務的原始開始、完成時間與持續時間，讓您能比較未來的變更。  
- **哪個 Aspose.Tasks 類別用於建立專案？** `Project` 類別 – 您還會學習如何正確 **建立專案實例**。  
- **執行程式碼是否需要授權？** 免費評估授權可用於測試；正式環境需商業授權。  
- **我可以取得中期基準嗎？** 可以，Aspose.Tasks 允許查詢中期基準及其固定成本。  
- **需要哪個 Java 版本？** 建議使用 Java 8 或更新版本。  
- **這如何協助我追蹤專案進度？** 設定基準後，您可即時使用內建報表功能將實際日期與原始計畫比較。

## 任務基準是什麼以及為何要設定？
任務基準會在特定時間點捕捉計畫的排程（開始日期、完成日期與持續時間）。透過設定基準，您建立了一個參考點，能輕鬆辨識排程漂移、成本超支與資源過度配置。

## 為何使用 Aspose.Tasks 進行基準管理？
Aspose.Tasks 提供 **完整的 .mpp 相容性**——您可以在未安裝 Microsoft Office 的情況下讀寫原生 Microsoft Project 檔案。此 API 讓您以程式方式存取 **超過 50 種輸入與輸出格式**，支援 **中期基準 1‑10**，且能在不將整個檔案載入記憶體的情況下處理 **數百頁的專案**，這對高效能批次處理至關重要。

## 前置條件
1. **Java 開發環境** – 已安裝並設定 JDK 8+。  
2. **Aspose.Tasks for Java** – 從 [Aspose.Tasks for Java 下載頁面](https://releases.aspose.com/tasks/java/) 下載程式庫。  
3. **IDE 或建置工具** – Maven、Gradle，或您偏好的任何 IDE。

## 匯入套件
以下匯入語句會將處理專案、任務、基準與時間相位資料所需的核心 Aspose.Tasks 類別帶入。

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## 步驟 1：建立專案實例
`Project` 類別在記憶體中代表一個 Microsoft Project 檔案，且是所有操作的入口點。

```java
Project project = new Project();
```

## 步驟 2：建立任務基準
`TaskBaseline` 用於儲存特定任務的計畫開始、完成與持續時間。

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## 步驟 3：顯示任務基準資訊
`getBaselines()` 方法會回傳與任務相關聯的基準集合。

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## 步驟 4：檢查中期基準與固定成本
`BaselineType` 列舉了主要基準與中期基準（Baseline、Baseline1‑Baseline10）。

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## 步驟 5：列印時間相位資料
`TimephasedData` 代表特定時間區間內的排程資訊片段。

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

依照上述步驟，您即可 **設定任務的基準持續時間**，並使用 Aspose.Tasks for Java 取得詳細的基準資訊，為整個專案生命週期提供可靠的 **追蹤專案進度** 方式。

## 常見問題與解決方案
- **基準未在 MS Project 中顯示：** 確保您在加入任務後呼叫 `project.setBaseline(BaselineType.Baseline)` **之後**。  
- **`getBaselines()` 發生 NullPointerException：** 請確認在設定基準前已將任務加入專案。  
- **時間單位不匹配：** 使用 `TimeUnitType` 正確格式化持續時間，特別是使用自訂行事曆時。

## 常見問答

### MS Project 中的任務基準是什麼？
MS Project 中的任務基準是對任務最初計畫排程的快照，包含其開始日期、完成日期與持續時間。

### 為何管理任務基準很重要？
管理任務基準有助於將計畫排程與實際進度進行比較，從而提升追蹤與決策的精確度。

### 設定後我可以修改任務基準嗎？
可以，您可以在 MS Project 中修改任務基準以反映專案計畫的變更。但必須記錄任何與原始基準的偏差。

### Aspose.Tasks 支援其他專案管理功能嗎？
是的，Aspose.Tasks 提供廣泛的專案管理功能，包括任務排程、資源配置與甘特圖產生等。

### 我可以在哪裡取得 Aspose.Tasks 的支援？
您可以在 [Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15) 上取得支援，提出問題並與其他使用者互動。

## 其他常見問題

**Q: 我需要為每個任務分別呼叫 `setBaseline` 嗎？**  
A: 不需要。呼叫 `project.setBaseline(BaselineType.Baseline)` 會一次為專案中所有任務記錄基準。

**Q: 我要如何為特定任務設定中期基準？**  
A: 在更新任務排程後，使用 `project.setBaseline(BaselineType.Baseline1)`（或 Baseline2‑Baseline10）即可。

**Q: 能否將基準資料匯出為 CSV？**  
A: 可以。遍歷 `task.getBaselines()`，使用標準 Java I/O 將所需欄位寫入 CSV 檔案。

**Q: 我可以讀取已包含基準的 .mpp 檔案嗎？**  
A: 當然可以。使用 `new Project("myproject.mpp")` 載入檔案，然後如上所示存取每個任務的基準。

**Q: Aspose.Tasks 能處理多專案檔案嗎？**  
A: Aspose.Tasks 僅支援單一專案的 .mpp 檔案。若需多專案情境，請以程式方式合併各專案。

**最後更新：** 2026-08-29  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose

## 相關教學

- [使用 Aspose.Tasks 建立任務清單 Java – MS Project 基準](/tasks/java/task-baselines/create-task-baseline/)
- [使用 Aspose.Tasks 建立 MPP 專案 Java – 變更任務進度](/tasks/java/task-properties/change-progress/)
- [專案管理基準 – 使用 Aspose.Tasks 進行任務排程](/tasks/java/task-baselines/baseline-task-scheduling/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}