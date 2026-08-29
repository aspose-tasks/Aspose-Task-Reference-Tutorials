---
date: 2026-08-29
description: 了解如何在 Java 中向專案新增工作項目、建立工作項目清單，並在不使用 Microsoft Project 的情況下設定基準，使用 Aspose.Tasks。
keywords:
- add task to project
- how to set baseline
- how to create baseline
- how to add task
- java create ms project
lastmod: 2026-08-29
linktitle: 在 Aspose.Tasks 中建立工作項目基準
og_description: 了解如何在 Java 中新增工作項目並使用 Aspose.Tasks 設定基準。本指南提供逐步程式碼，無需 Microsoft Project。
og_image_alt: 'Tutorial: add task to project and set baseline with Aspose.Tasks Java'
og_title: 如何在 Java 中向專案新增工作項目並設定基準
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to add task to project in Java, create a task list, and set
    a baseline without Microsoft Project using Aspose.Tasks.
  headline: How to add task to project in Java and set a baseline
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks works independently and does not require Microsoft Project
      on the host machine.
    question: Can I use Aspose.Tasks for Java without Microsoft Project installed?
  - answer: Absolutely. The library supports Project files from 2007 through the latest
      2024 releases.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project?
  - answer: Yes, you can add, update, and delete resources programmatically, just
      like tasks.
    question: Can I manipulate project resources using Aspose.Tasks for Java?
  - answer: Yes, you can define predecessor‑successor relationships using the `TaskLink`
      class.
    question: Does Aspose.Tasks for Java support setting task dependencies?
  - answer: Yes, you can get help via the [support forum](https://forum.aspose.com/c/tasks/15),
      where Aspose staff and the community respond to queries.
    question: Is technical support available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add task to project
- Aspose.Tasks
- Java project automation
title: 如何在 Java 中向專案新增工作項目並設定基準
url: /zh-hant/java/task-baselines/create-task-baseline/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中向專案新增任務並設定基線

## 簡介
在本教學中，您將以程式方式 **add task to project**，產生 Microsoft Project 任務基線，並儲存檔案——全部不需要開啟 Microsoft Project。Aspose.Tasks for Java 為您提供純 Java API，可在任何平台上運作，非常適合自動化建置管線、報告服務或任何需要操作 .mpp 檔案的伺服器端解決方案。

## 快速答案
- **Aspose.Tasks 的功能是什麼？** 它提供一個 Java API，用於建立、讀取和編輯 Microsoft Project 檔案，且不需要安裝 Microsoft Project。  
- **需要安裝 Microsoft Project 嗎？** 不需要，該函式庫完全獨立運作。  
- **需要哪個 Java 版本？** JDK 8 或以上。  
- **可以為單一任務設定基線嗎？** 可以——對只包含您想要的任務的清單呼叫 `setBaseline`。  
- **在正式環境需要授權嗎？** 需要，商業授權會移除評估限制並解鎖所有功能。

## 什麼是任務基線？
任務基線會記錄任務在排程首次儲存時原先計畫的開始日期、完成日期與工作量。此快照作為參考點，使專案經理能將實際進度與成本與最初計畫進行比較，並計算績效分析的差異。

## 為何在 Java 中使用 Aspose.Tasks 來 add task to project？
您可以在不安裝任何桌面軟體的情況下建立、修改與設定任務基線，從而實現全自動化工作流程。Aspose.Tasks 支援 **50 多種輸入與輸出格式**，且能處理 **數百個任務** 的專案，同時將記憶體使用量控制在 200 MB 以下，這使其非常適合雲端服務與 CI/CD 管線。

## 先決條件
1. **Java Development Kit (JDK)** – 安裝 JDK 8 或更新版本。  
2. **Aspose.Tasks for Java** – 從 [download link](https://releases.aspose.com/tasks/java/) 下載函式庫。  

## 匯入套件
要在 Java 專案中開始使用 Aspose.Tasks，請匯入必要的套件：
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## 步驟 1：建立專案物件
`Project` 類別是 Aspose.Tasks 的頂層物件，代表記憶體中的 Microsoft Project 檔案。實例化它會得到一個空白專案，您可以在其中加入任務、資源與行事曆。
```java
Project project = new Project();
```
此處我們實例化一個新的 `Project` 物件——它代表將保存我們任務清單的 MS Project 檔案。

## 步驟 2：向專案新增任務
`Task` 類別代表專案排程中的單一工作項目。每個 `Task` 都可以有自己的工期、開始日期與資源指派。
```java
Task task = project.getRootTask().getChildren().add("Task");
```
透過 `getRootTask()` 我們取得專案階層的根節點，並 **add task to Microsoft Project**。字串 `"Task"` 為任務名稱；您可以自行替換為任何需要的描述。

## 步驟 3：為指定任務設定基線
`BaselineType` 是一個列舉，定義您要寫入的基線欄位（Baseline、Baseline1 … Baseline10）。透過傳遞任務清單，您可以僅為所選的項目設定基線。
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
若要 **set baseline without MS Project**，建立一個包含您想要設定基線的任務清單（此處為 `myList`），並將其傳遞給 `setBaseline`。如果只需要選擇性基線，請將您新增的任務填入 `myList`。

## 步驟 4：為整個專案設定基線
`setBaseline` 會將選定的基線值寫入專案中的每個任務。  
如果您想一次性為整個專案設定基線，只需使用所需的 `BaselineType` 呼叫 `setBaseline` 即可。
```java
project.setBaseline(BaselineType.Baseline);
```
此呼叫會為專案中的 **每個任務** 寫入選定的基線值，確保原始排程的完整快照。

## 如何使用 Aspose.Tasks 向 Microsoft Project add task
`add()` 會在指定的父任務下建立新的子任務，並回傳新建立的 `Task` 物件。  
您可透過在父 `Task` 物件（通常是根任務）上呼叫 `add()` 來新增任務。此方法會回傳一個新的 `Task` 實例，您可以在儲存專案檔之前進一步設定——工期、開始日期、資源或自訂欄位。

## 如何在未使用 MS Project 的情況下設定基線
Aspose.Tasks 完全透過程式碼即可建立基線。選擇一個 `BaselineType`（例如 `BaselineType.Baseline`）並呼叫 `setBaseline`。您可以使用 `Baseline1`‑`Baseline10` 重複此操作，以保留多個修訂基線，全部不需開啟 Microsoft Project。

## 常見問題與解決方案
- **基線未顯示：** 確保在設定基線後呼叫 `project.save("output.mpp")`（此處為簡化起見省略儲存步驟）。  
- **任務清單顯示為空：** 請確認您正將任務新增至正確的父節點（`getRootTask()` 或子任務）。  
- **版本不匹配錯誤：** 使用最新的 Aspose.Tasks JAR，以確保與較新 .mpp 格式相容。

## 常見問答

**Q: 我可以在未安裝 Microsoft Project 的情況下使用 Aspose.Tasks for Java 嗎？**  
A: 可以，Aspose.Tasks 獨立運作，主機上不需要 Microsoft Project。

**Q: Aspose.Tasks for Java 是否相容於不同版本的 Microsoft Project？**  
A: 完全相容。此函式庫支援從 2007 版到最新 2024 版的 Project 檔案。

**Q: 我可以使用 Aspose.Tasks for Java 操作專案資源嗎？**  
A: 可以，您可以以程式方式新增、更新與刪除資源，與任務操作相同。

**Q: Aspose.Tasks for Java 是否支援設定任務相依性？**  
A: 可以，您可使用 `TaskLink` 類別定義前置任務與後續任務的關係。

**Q: Aspose.Tasks for Java 是否提供技術支援？**  
A: 有，您可透過 [support forum](https://forum.aspose.com/c/tasks/15) 取得協助，Aspose 工作人員與社群會回應問題。

## 結論
透過上述步驟，您已學會如何在 Java 中 **add task to project**、建立任務清單，並使用 Aspose.Tasks **set baseline without MS Project**。此方法簡化了專案自動化，免除桌面 Project 的安裝需求，並讓您能以程式方式完整掌控排程的每個面向。

---

**最後更新：** 2026-08-29  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose

## 相關教學

- [如何建立 Project aspose.tasks – 設定新任務屬性](/tasks/java/project-file-operations/set-attributes-new-tasks/)
- [如何在 Aspose.Tasks for Java 中設定基線工期](/tasks/java/task-baselines/task-baseline-duration/)
- [建立任務 Aspose Java – 任務屬性](/tasks/java/task-properties/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}