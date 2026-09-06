---
date: 2026-08-29
description: 了解如何使用 Aspose.Tasks for Java 讀取基線資料並排程任務，以便有效比較計劃與實際進度。
keywords:
- how to read baseline
- how to set baseline
- compare planned vs actual
lastmod: 2026-08-29
linktitle: Aspose.Tasks 基線任務排程
og_description: 了解如何使用 Aspose.Tasks for Java 讀取基線資料並排程任務，實現精確比較計劃與實際進度。
og_image_alt: Tutorial showing how to read baseline and schedule tasks with Aspose.Tasks
  Java API
og_title: 如何使用 Aspose.Tasks 讀取基線並排程任務
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to read baseline data and schedule tasks using Aspose.Tasks
    for Java, so you can compare planned vs actual progress efficiently.
  headline: How to read baseline and schedule tasks with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Instantiate the `Project` class (`Project project = new Project();`).
      This creates a fresh project file ready for tasks and baselines.
    question: How do I create a new project instance in Aspose.Tasks?
  - answer: '`BaselineType.Baseline` refers to the primary baseline (Baseline 1).
      Aspose.Tasks also supports Baseline 2‑10 for additional snapshots.'
    question: What is the difference between `BaselineType.Baseline` and other baseline
      types?
  - answer: Yes, you can iterate over `TaskBaseline` objects and write the values
      to a CSV file using standard Java I/O.
    question: Can I export the baseline data to Excel or CSV?
  - answer: Setting a baseline captures the current dates but does not modify the
      task’s active schedule. You can still adjust start/finish dates after the baseline
      is set.
    question: Does setting a baseline affect existing task dates?
  - answer: Absolutely. Retrieve each baseline via `task.getBaselines().get(index)`
      and compare their `Start`, `Finish`, and `Duration` properties.
    question: Is it possible to compare multiple baselines programmatically?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- project baseline
- Aspose.Tasks
- Java project management
title: 如何使用 Aspose.Tasks 讀取基線並排程任務
url: /zh-hant/java/task-baselines/baseline-task-scheduling/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks 讀取基準並排程工作

在本指南中，您將了解 **如何讀取基準** 資訊並以程式方式使用 Aspose.Tasks for Java 排程工作。完成本教學後，您將能夠捕捉原始專案計畫、與實際進度比較，並產生差異報告——全部不需要安裝 Microsoft Project。

## 專案管理基準簡介
管理 **專案管理基準** 是有效專案管理的基石。它讓您能夠捕捉原始計畫，之後比較 **計畫進度與實際進度**，以便及早發現差異。在本教學中，我們將示範如何使用 Aspose.Tasks for Java 排程工作基準，為您提供自信管理 **專案基準** 的工具，確保專案順利進行。

## 快速解答
- **專案管理基準代表什麼？**  
  它記錄了專案開始時已核准的排程、成本與範圍，提供差異分析的參考依據。  
- **哪個程式庫在 Java 中處理基準排程？**  
  Aspose.Tasks for Java 提供純‑Java API，支援 45 種以上的輸入與輸出格式，且可處理多達 100 000 個工作的專案。  
- **執行程式碼是否需要授權？**  
  免費試用版可用於測試；正式上線則需商業授權。  
- **主要前置條件是什麼？**  
  Java Development Kit (JDK) 11 以上，以及 Aspose.Tasks for Java 程式庫。  
- **設定基準後可以查看基準日期嗎？**  
  可以——使用 `TaskBaseline` 物件讀取開始、結束與持續時間的值。

## 什麼是專案管理基準？
專案管理基準記錄了執行開始時已核准的排程、預算與範圍。它作為衡量績效與辨識整個專案生命週期中偏差的參考點。基準包括計畫的開始與結束日期、總成本以及範圍細節，提供完整的快照以供未來比較。

## 為什麼使用 Aspose.Tasks 進行基準排程？
Aspose.Tasks 提供純‑Java API，無需安裝 Microsoft Project。它支援 **45 種以上的輸入與輸出格式**，可在記憶體效能模式下處理 **多達 100 000 個工作** 的專案，並提供內建方法讀寫基準資料，使自動化報告與整合變得簡單直接。

## 前置條件
- **Java Development Kit (JDK)** – 安裝 JDK 11 或更新版本。您可從[網站](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)下載。  
- **Aspose.Tasks for Java 程式庫** – 從[下載頁面](https://releases.aspose.com/tasks/java/)取得最新版本，並將 JAR 加入專案的 classpath。

## 匯入套件
`Project`、`Task` 與 `TaskBaseline` 類別位於 `com.aspose.tasks` 命名空間。請在原始檔案的最上方匯入它們：

`Project` 類別是 Aspose.Tasks 的頂層物件，代表記憶體中的單一專案檔。它提供對工作、資源與基準集合的存取。

## 如何讀取基準？
載入專案後，針對每個工作查詢 `TaskBaseline` 集合。`TaskBaseline` 物件會回傳在呼叫 `setBaseline` 時捕捉的基準開始、結束與持續時間。此直接方式讓您在不解析 XML 或二進位檔的情況下讀取基準值。

## 步驟 1：建立新的專案實例
`Project` 類別代表記憶體中的整個專案檔。
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
```

## 步驟 2：定義工作並設定基準
`Task` 代表單一工作項目，`setBaseline` 會將其目前的排程捕捉為基準。
```java
Project project = new Project();
```

## 步驟 3：存取基準資訊
`TaskBaseline` 保存基準的開始、結束與持續時間值。
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## 步驟 4：顯示基準持續時間
`Duration` 代表工作或基準的時間長度。
```java
TaskBaseline baseline = task.getBaselines().get(0);
```

## 步驟 5：顯示基準開始日期
`Start` 為基準的排程開始日期。
```java
System.out.println(baseline.getDuration().toString());
```

## 步驟 6：顯示基準結束日期
`Finish` 為基準的排程完成日期。
```java
System.out.println("Baseline Start: " + baseline.getStart());
```

## 常見問題與解決方案
- **基準未設定：** 確保在加入工作後呼叫 `project.setBaseline(BaselineType.Baseline)` **之後**；否則基準集合會是空的。  
- **空值：** 若 `task.getBaselines()` 回傳空清單，請確認在設定基準前已將工作加入專案層級。  
- **日期格式：** `getStart()` 與 `getFinish()` 方法會回傳 `java.util.Date` 物件。如需自訂顯示格式，可使用 `SimpleDateFormat`。

## 常見問答

**Q：如何在 Aspose.Tasks 中建立新的專案實例？**  
A：實例化 `Project` 類別（`Project project = new Project();`）。這會建立一個全新的專案檔，供工作與基準使用。

**Q：`BaselineType.Baseline` 與其他基準類型有何差異？**  
A：`BaselineType.Baseline` 代表主要基準（基準 1）。Aspose.Tasks 亦支援 Baseline 2‑10 作為額外快照。

**Q：我可以將基準資料匯出為 Excel 或 CSV 嗎？**  
A：可以，您可以遍歷 `TaskBaseline` 物件，使用標準 Java I/O 將值寫入 CSV 檔案。

**Q：設定基準會影響現有工作的日期嗎？**  
A：設定基準會捕捉當前日期，但不會修改工作的實際排程。基準設定後仍可調整開始/結束日期。

**Q：能否以程式方式比較多個基準？**  
A：當然可以。透過 `task.getBaselines().get(index)` 取得各基準，並比較其 `Start`、`Finish` 與 `Duration` 屬性。

---

**最後更新：** 2026-08-29  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

```java
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## 相關教學

- [使用 Aspose.Tasks 建立 Java 任務清單 – MS Project 基準](/tasks/java/task-baselines/create-task-baseline/)
- [如何在 Aspose.Tasks for Java 中設定基準持續時間](/tasks/java/task-baselines/task-baseline-duration/)
- [建立 MPP 專案 Java – 使用 Aspose.Tasks 變更工作進度](/tasks/java/task-properties/change-progress/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}