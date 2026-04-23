---
date: 2026-01-23
description: 了解如何使用 Aspose.Tasks for Java 設定基線持續時間並建立專案實例。本分步指南可協助您有效管理任務基線。
linktitle: How to Set Baseline Duration in Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: 如何在 Aspose.Tasks for Java 中設定基準持續時間
url: /zh-hant/java/task-baselines/task-baseline-duration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks for Java 中設定基準持續時間

## Introduction
設定基準是追蹤專案進度相對於原始計畫的基本步驟。在本教學中，您將學習如何使用 Aspose.Tasks for Java 套件在 Microsoft Project 中設定任務的基準持續時間，並了解為何提前建立基準能為您節省時間與避免後續麻煩錄任務的原始開始、完成與持續時間，讓您能比較未來的變更。  
- **哪個 Aspose.Tasks 類別用於建立專案？** `Project` 類別 – 您也會學習如何正確 **建立專案實例**。  
- **執行程式碼是否需要授權？** 免費評估授權可用於測試；正式環境需購買商業授權。  
- **我可以取得臨時基準嗎？** 可以，Aspose.Tasks 允許查詢臨時基準及其固定成本。  
- **需要哪個 Java 版本？** 建議使用 Java 8 或更新版本。

## What is a task baseline and why set it?
任務基準是捕捉在特定時間點的計畫排程（開始日期、完成日期與持續時間）。設定基準可建立參考點，讓您在專案演進時輕鬆辨識排程漂移、成本超支與資源過度配置。

## Why use Aspose.Tasks for baseline management?
- **完整的 .mpp 相容性** – 無需安裝 Office，即可讀寫原生 Microsoft Project 檔案。  
- **豐富的 API** – 可程式化存取基準資料、臨時基準與時間相位資訊。  
- **跨平台** – 在 Windows、Linux 與 macOS 上皆可使用任何標準 JDK。

## Prerequisites
1. **Java 開發環境** – 已安裝並設定 JDK 8 以上。  
2. **Aspose.Tasks for Java** – 從 [此處](https://releases.aspose.com/tasks/java/) 下載程式庫。  
3. **IDE 或建置工具** – Maven、Gradle，或您偏好的任何 IDE。

## Import Packages
First, import the necessary classes into your Java project:

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.TimephasedData;
```

## Step 1: Create a Project Instance
Creating a project instance is the foundation for any further manipulation. This step shows how to **create project instance** using Aspose.Tasks:

```java
Project project = new Project();
```

## Step 2: Create a Task Baseline
Add a new task to the project’s root and set its baseline. This records the original schedule for the task:

```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## Step 3: Display Task Baseline Information
Retrieve the baseline you just created and print its key properties. This helps you verify that the baseline was set correctly:

```java
TaskBaseline baseline = task.getBaselines().toList().get(0);
System.out.println("Baseline Start: " + baseline.getStart());
System.out.println("Baseline Duration: " + baseline.getDuration());
System.out.println("Baseline Duration Format: " + TimeUnitType.toString(TimeUnitType.class, baseline.getDuration().getTimeUnit()));
System.out.println("Is it an Estimated Duration?: " + baseline.getEstimatedDuration());
System.out.println("Baseline Finish: " + baseline.getFinish());
```

## Step 4: Check Interim Baseline and Fixed Cost
If you’re working with interim baselines, you can query whether the current baseline is interim and any associated fixed cost:

```java
System.out.println("Interim: " + baseline.getInterim());
System.out.println("Fixed Cost: " + baseline.getFixedCost());
```

## Step 5: Print Timephased Data
Time‑phased data shows how the baseline is distributed over time. Loop through the collection to inspect each entry:

```java
System.out.println("Number of Timephased Items: " + baseline.getTimephasedData().size());
for (TimephasedData data : baseline.getTimephasedData()) {
    System.out.println(" UID: " + data.getUid());
    System.out.println(" Start: " + data.getStart());
    System.out.println(" Finish: " + data.getFinish());
}
```

依照上述步驟，您即可為任何任務 **設定基準持續時間**，並使用 Aspose.Tasks for Java 取得詳細的基準資訊。

## Common Issues and Solutions
- **基準未在 MS Project 中顯示**：確保在新增任務**之後**呼叫 `project.setBaseline(BaselineType.Baseline)`。  
- **`getBaselines()` 出現 NullPointerException**：確認已在設定基準前將任務加入專案。  
- **時間單位不匹配**：使用 `TimeUnitType` 正確格式化持續時間，特別是在使用自訂行事曆時。

## FAQ's
### What is a task baseline in MS Project?
時間。

### Why is managing task baselines important?
管理任務基準有助於將計畫排程與專案實際進度比較，促進更好的追蹤與決策。

### Can I modify a task baseline once it's set?
可以，您可以在 MS Project 中修改任務基準以反映專案計畫的變更。但必須記錄任何與原始基準的偏差。

 project management functionalities?
是，Asp甘特圖產生等。

### Where can I find support for Aspose.Tasks?
您可在 [Aspose.Tasks 論壇](：如何為特定任：在更新任務排程後，使用 `project.setBaseline(BaselineType.Baseline1)`（或 Baseline2‑Baseline10）。

**問：能否將基準資料匯出為 CSV？**  
答：可以。遍歷 `task.getBaselines()`，使用標準 Java I/O 將所需欄位寫入 CSV 檔案。

**問：我可以讀取已包含基準的現有 .mpp 檔案嗎？**  
答：當然可以。使用 `new Project("myproject.mpp")` 載入檔案，然後如上所示存取每個任務的基準。

**問：Aspose.Tasks 能處理多專案檔案嗎？**  
答：Aspose.Tasks 僅支援單一專案的 .mpp 檔案。若需多專案情境，需以程式方式合併專案。

---

**最後更新：** 2026-01-23  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}