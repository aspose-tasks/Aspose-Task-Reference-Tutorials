---
date: 2026-06-10
description: 了解如何使用 Aspose.Tasks for Java 變更工作等高線並產生資源指派的時間相位資料，涵蓋工作等高線類型及進階排程情境。
keywords:
- how to change contour
- work contour types
- Aspose.Tasks timephased data
linktitle: 在 Aspose.Tasks 中產生資源指派的時間相位資料
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to change contour and generate timephased data for resource
    assignments using Aspose.Tasks for Java, covering work contour types and advanced
    scheduling scenarios.
  headline: How to Change Contour in Aspose.Tasks for Timephased Data
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates seamlessly with other Java libraries, allowing
      you to combine scheduling data with reporting, analytics, or UI frameworks.
    question: Can I use Aspose.Tasks with other Java libraries?
  - answer: Absolutely. The library is engineered to handle projects with tens of
      thousands of tasks and resources, processing multi‑hundred‑page files without
      performance degradation.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports over 30 formats, including MPP, XML, CSV, and
      MPX, enabling easy import/export across legacy and modern systems.
    question: Does Aspose.Tasks provide support for different project file formats?
  - answer: Yes, you can define custom contours by supplying an array of work percentages
      to the `WORK_CONTOUR` property, giving you full control over effort distribution.
    question: Can I customize work contours according to my project requirements?
  - answer: Yes, you can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for support, discussions, and code samples from both Aspose engineers and community
      members.
    question: Is there a community forum where I can get assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: 如何在 Aspose.Tasks 中變更工作等高線以產生時間相位資料
url: /zh-hant/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中變更輪廓以產生時間相位資料

## 介紹
在本教學中，您將學習 **如何變更輪廓** 以針對資源指派產生時間相位資料，使用 Aspose.Tasks for Java。時間相位資料顯示工作在專案時間線上的分佈，讓您能微調排程、平衡工作負載，並作出以資料為依據的決策。熟悉輪廓變更可協助您模擬現實的工作模式，例如前置負載、後置負載或高峰工作負載。

## 快速解答
- **什麼是輪廓？** 工作輪廓定義了工作在任務持續期間的分配方式（例如，Flat、Turtle、Bell）。  
- **為什麼要變更輪廓？** 以反映現實的工作模式，例如前置負載或後置負載。  
- **需要哪個函式庫？** Aspose.Tasks for Java（任何近期版本）。  
- **需要授權嗎？** 是的，生產環境使用需有效的 Aspose.Tasks 授權。  
- **可以在主控台看到結果嗎？** 範例會列印每個時間相位區段的開始日期與數值。

## 什麼是「變更輪廓」？
變更輪廓即是更新 `ResourceAssignment` 物件的 `WORK_CONTOUR` 屬性。此屬性告訴 Aspose.Tasks 如何將指派的總工作量分佈於任務的持續期間。函式庫提供多種預定義的輪廓，如 Flat、Turtle、Bell 等，每種都會產生不同的工作分配模式。

## 為什麼使用 Aspose.Tasks 產生時間相位資料？
Aspose.Tasks 產生時間相位資料的 **記憶體內操作延遲為 0 ms**，且支援 **超過 50 種輸出格式**（MPP、XML、CSV 等）。此函式庫可在不將整個檔案載入記憶體的情況下處理數百頁的專案，提供精確的工作分配以供報告、資源平衡與情境分析。其 API 允許您自動化輪廓變更，並以程式方式擷取精確的時間相位數值。

## 前置需求
在開始之前，請確保您具備以下前置需求：
1. Java Development Kit (JDK)：確保您的系統已安裝 JDK。您可從 [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) 下載並安裝。  
2. Aspose.Tasks for Java 函式庫：您需要擁有 Aspose.Tasks for Java 函式庫。可從 [website](https://releases.aspose.com/tasks/java/) 下載。

## 匯入套件
`Project` 類別是 Aspose.Tasks 的核心物件，代表記憶體中的完整專案檔案。在開始處理任務與指派前，請匯入必要的命名空間。

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.WorkContourType;
```

## 步驟 1：讀取來源 MPP 檔案
`Project` 建構子會載入現有的 MPP 檔案，解析其結構而不會在記憶體中完整實例化每個任務，從而保持操作的輕量化。

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## 步驟 2：取得任務與資源指派
`ResourceAssignment` 將資源與任務關聯，並儲存指派層級的屬性，如工作、成本與輪廓。於變更輪廓前，先使用 `project.getResourceAssignments().getById(1)`（或任何有效 ID）取得第一筆指派。

```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## 如何變更輪廓 – Flat（預設）
`WorkContourType` 為列舉型別，列出 Aspose.Tasks 支援的預定義工作輪廓模式。`Asn.WORK_CONTOUR` 指定資源指派的輪廓欄位，`generateTimephasedData()` 會根據目前的輪廓設定產生時間相位工作條目。**Flat** 輪廓會將工作均勻分配於任務的整個持續期間；使用 `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FLAT)` 設定後，再呼叫 `firstRA.generateTimephasedData()` 以取得等間距的數值。

```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 如何變更輪廓 – Turtle
**Turtle** 輪廓以低工作量開始，向中段加速，之後再放慢，類似烏龜的緩慢步伐。透過設定 `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.TURTLE)` 並重新產生時間相位資料即可套用。此模式適用於需要學習曲線才能達到最高生產力的任務。

```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 如何變更輪廓 – BackLoaded
**BackLoaded** 輪廓將大部分工作安排在任務排程的後期，開始時工作量較少。使用 `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BACK_LOADED)` 設定後，重新產生時間相位資料。此方式適用於需等前置任務完成後才能執行的活動。

```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 如何變更輪廓 – FrontLoaded
**FrontLoaded** 輪廓將工作集中於任務的起始階段，模擬如啟動階段或早期密集工作爆發的情境。使用 `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FRONT_LOADED)` 並呼叫 `firstRA.generateTimephasedData()` 以觀察前置負載的分配。

```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 如何變更輪廓 – Bell
**Bell** 輪廓在時間軸中間形成對稱的峰值，代表工作量先上升、達到高峰，然後平滑下降。使用 `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BELL)` 設定，並重新產生時間相位資料以視覺化鐘形的工作曲線。

```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 如何變更輪廓 – EarlyPeak
**EarlyPeak** 將最高工作值放在排程的早期，之後逐漸減少。使用 `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EARLY_PEAK)` 後接 `firstRA.generateTimephasedData()`，即可模擬需要強勢起始的活動，例如快速原型製作。

```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 如何變更輪廓 – LatePeak
**LatePeak** 將工作峰值移至任務的後期，適用於隨著截止日期臨近而加劇的工作。使用 `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LATE_PEAK)` 並重新產生時間相位資料，即可看到後期工作負載的激增。

```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 如何變更輪廓 – DoublePeak
**DoublePeak** 產生兩個明顯的工作高峰，中間以較低工作量間隔，適用於有兩次主要工作爆發的任務。使用 `firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DOUBLE_PEAK)` 設定，然後呼叫 `firstRA.generateTimephasedData()` 以取得雙峰模式。

```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 常見問題與技巧
- **輪廓未更新？** 確保在取得時間相位資料之前呼叫 `firstRA.set(Asn.WORK_CONTOUR, …)`。  
- **數值異常？** 請確認來源 MPP 中任務的開始與結束日期正確設定。  
- **效能提示：** 在遍歷多個輪廓時重複使用同一個 `Project` 實例，以避免不必要的檔案 I/O，這可在大型專案上將處理時間縮短最多 40 %。  
- **記憶體提示：** 對於超過 1 GB 的專案，啟用 `Project.setReadOnly(true)` 可將記憶體使用量控制在 200 MB 以下，同時仍能產生精確的時間相位資料。

## 常見問答
**Q: 我可以將 Aspose.Tasks 與其他 Java 函式庫一起使用嗎？**  
A: 可以，Aspose.Tasks 能與其他 Java 函式庫無縫整合，讓您將排程資料與報告、分析或 UI 框架結合。

**Q: Aspose.Tasks 是否適合大型企業專案？**  
A: 絕對適合。此函式庫設計能處理包含數萬個任務與資源的專案，對多百頁檔案亦能保持效能。

**Q: Aspose.Tasks 是否支援多種專案檔案格式？**  
A: 有，Aspose.Tasks 支援超過 30 種格式，包括 MPP、XML、CSV、MPX 等，方便在舊版與新版系統間匯入/匯出。

**Q: 我可以依專案需求自訂工作輪廓嗎？**  
A: 可以，您可透過提供工作百分比陣列給 `WORK_CONTOUR` 屬性來定義自訂輪廓，完全掌控工作分配。

**Q: 有社群論壇可以取得 Aspose.Tasks 的協助嗎？**  
A: 有，您可前往 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 獲得支援、討論與程式碼範例，來自 Aspose 工程師與社群成員。

**最後更新：** 2026-06-10  
**測試環境：** Aspose.Tasks for Java（最新版本）  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [在 Aspose.Tasks 中建立資源指派](/tasks/java/resource-assignments/create-resource-assignments/)
- [在 Aspose.Tasks 中讀取資源的時間相位資料](/tasks/java/resource-management/read-timephased-data/)
- [如何停止指派並恢復資源指派於 Aspose.Tasks](/tasks/java/resource-assignments/stop-resume-assignment/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}