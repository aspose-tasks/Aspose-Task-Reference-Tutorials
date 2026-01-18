---
date: 2026-01-18
description: 學習如何使用 Java 建立工作清單，並將工作新增至 Microsoft Project，使用 Aspose.Tasks 在不使用 MS
  Project 的情況下設定基準。
linktitle: Creating a Task Baseline in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks 建立 Java 任務清單 – MS Project 基線
url: /zh-hant/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立任務清單 Java – MS Project 基線與 Aspose.Tasks

## 介紹
在本教學中，您將 **建立任務清單 Java**，透過 Aspose.Tasks for Java 產生 Microsoft Project 任務基線。Aspose.Tasks 讓您在未安裝 Microsoft Project 的情況下操作 Project 檔案，您可以 **將任務新增至 Microsoft Project**、操作資源，甚至 **在未使用 MS Project 的情況下設定基線**——全部以純 Java 程式碼完成。

## 快速回答
- **Aspose.Tasks 做什麼？** 它提供一套 Java API，用於在沒有 MS Project 的環境下建立、讀取與編輯 Microsoft Project 檔案。  
- **需要安裝 Microsoft Project 嗎？** 不需要，Aspose.Tasks 可獨立運作。  
- **需要哪個版本的 Java？** JDK 8 或以上。  
- **可以為單一任務設定基線嗎？** 可以，使用 `setBaseline` 搭配任務清單即可。  
- **正式環境需要授權嗎？** 需要，商業授權可移除評估版限制。

## 什麼是任務基線？
任務基線會記錄任務原始規劃的開始、結束與工作量數值，作為比較實際進度與原始計畫的參考點。

## 為什麼使用 Aspose.Tasks 來建立任務清單 Java？
- **無需 MS Project 相依** – 非常適合伺服器端自動化。  
- **完整控制** 任務、資源與行事曆，全部透過 Java 程式碼。  
- **跨版本相容**，支援 Project 2007‑2024 檔案。

## 前置條件
1. **Java Development Kit (JDK)** – 安裝 JDK 8 或更新版本。  
2. **Aspose.Tasks for Java** – 從 [download link](https://releases.aspose.com/tasks/java/) 下載程式庫。  

## 匯入套件
開始在 Java 專案中使用 Aspose.Tasks 前，先匯入必要的套件：
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## 步驟 1：建立 Project 物件
```java
Project project = new Project();
```
此處我們實例化一個新的 `Project` 物件——它代表將要保存任務清單的 MS Project 檔案。

## 步驟 2：將任務新增至專案
```java
Task task = project.getRootTask().getChildren().add("Task");
```
使用 `getRootTask()` 取得專案層級的根節點，**將任務新增至 Microsoft Project**。字串 `"Task"` 為任務名稱，您可以自行替換成任何描述。

## 步驟 3：為指定任務設定基線
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
要 **在未使用 MS Project 的情況下設定基線**，先建立要設定基線的任務清單（此處為 `myList`），再傳入 `setBaseline`。如果只需要針對特定任務設定基線，請將您新增的任務加入 `myList`。

## 步驟 4：為整個專案設定基線
```java
project.setBaseline(BaselineType.Baseline);
```
若想一次為整個專案設定基線，只需以所需的 `BaselineType` 呼叫 `setBaseline` 即可。

## 如何使用 Aspose.Tasks 將任務新增至 Microsoft Project
除了上述單一任務外，您還可以新增多個任務、子任務，並指派資源。每次呼叫 `add()` 都會回傳一個 `Task` 物件，您可以進一步設定其持續時間、開始日期等屬性。

## 如何在未使用 MS Project 的情況下設定基線
Aspose.Tasks 完全透過程式碼建立基線。您可以透過變更 `BaselineType` 列舉（Baseline、Baseline1‑Baseline10）來設定不同的基線類型，從而追蹤多次修訂的基線，而不必開啟 MS Project。

## 常見問題與解決方案
- **基線未顯示：** 確認在設定基線後呼叫 `project.save("output.mpp")`（此處為簡化示範，未列出保存步驟）。  
- **任務清單顯示為空：** 檢查是否將任務新增至正確的父節點（`getRootTask()` 或子任務）。  
- **版本不相容錯誤：** 使用最新的 Aspose.Tasks JAR，以確保與較新 .mpp 格式相容。

## 常見問答

**Q: 可以在未安裝 Microsoft Project 的環境下使用 Aspose.Tasks for Java 嗎？**  
A: 可以，Aspose.Tasks 可獨立運作，無需在主機上安裝 Microsoft Project。

**Q: Aspose.Tasks for Java 是否相容不同版本的 Microsoft Project？**  
A: 完全相容。此程式庫支援 2007 年至最新 2024 版的 Project 檔案。

**Q: 可以使用 Aspose.Tasks for Java 操作專案資源嗎？**  
A: 可以，您可以以程式方式新增、更新與刪除資源，操作方式與任務相同。

**Q: Aspose.Tasks for Java 支援設定任務相依性嗎？**  
A: 支援，您可以使用 `TaskLink` 類別定義前置任務與後續任務的關係。

**Q: 有提供 Aspose.Tasks for Java 的技術支援嗎？**  
A: 有，您可透過 [support forum](https://forum.aspose.com/c/tasks/15) 向 Aspose 工作人員與社群尋求協助。

## 結論
透過上述步驟，您已學會如何 **建立任務清單 Java**、**將任務新增至 Microsoft Project**，以及 **在未使用 MS Project 的情況下設定基線**，全部使用 Aspose.Tasks。此方法可簡化專案自動化流程，免除桌面版 Project 的安裝需求，並讓您完整程式化掌控專案資料。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-01-18  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

---