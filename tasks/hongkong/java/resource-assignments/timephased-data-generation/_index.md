---
date: 2026-01-10
description: 學習如何使用 Aspose.Tasks for Java 變更資源指派的輪廓並產生時間相位資料，以提升專案管理效率。
linktitle: Generate Timephased Data for Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何在 Aspose.Tasks 中更改時間相位資料的輪廓
url: /zh-hant/java/resource-assignments/timephased-data-generation/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中變更輪廓以產生時間相位資料

## 簡介
在本教學中，您將學習 **如何變更輪廓** 以針對資源指派產生時間相位資料，並使用 Aspose.Tasks for Java。時間相位資料揭示了工作在專案時間線上的分佈，讓您能微調排程、平衡工作負載，並作出以資料為依據的決策。

## 快速答覆
- **什麼是輪廓？** 工作輪廓定義了工作在任務持續期間的分佈方式（例如，Flat、Turtle、Bell）。  
- **為什麼要變更輪廓？** 以反映實際的工作模式，例如前置或後置工作量。  
- **需要哪個程式庫？** Aspose.Tasks for Java（任何近期版本）。  
- **是否需要授權？** 是的，正式使用時需要有效的 Aspose.Tasks 授權。  
- **可以在主控台看到結果嗎？** 範例會列印每個時間相位段的開始日期與數值。

## 什麼是「變更輪廓」？
變更輪廓即是更新 `ResourceAssignment` 的 `WORK_CONTOUR` 屬性。Aspose.Tasks 支援多種預定義輪廓（Flat、Turtle、Bell 等），這些輪廓會影響工作隨時間的分配方式。

## 為什麼使用 Aspose.Tasks 產生時間相位資料？
- **精確報表：** 匯出精確的工作分佈供報表工具使用。  
- **情境規劃：** 在不改變原始排程的情況下測試不同輪廓。  
- **自動化：** 整合至 CI 流程，自動驗證專案健康狀況。

## 先決條件
在開始之前，請確保您具備以下條件：
1. **Java Development Kit (JDK)：** 確認系統已安裝 JDK。您可以從 [此處](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) 下載並安裝。  
2. **Aspose.Tasks for Java 程式庫：** 必須擁有 Aspose.Tasks for Java 程式庫。您可以從 [官方網站](https://releases.aspose.com/tasks/java/) 下載。

## 匯入套件
首先，讓我們匯入使用 Aspose.Tasks 所需的套件：
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
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Read the source MPP file
Project project = new Project(dataDir + "project.mpp");
```

## 步驟 2：取得任務與資源指派
```java
// Get the first task of the Project
Task task = project.getRootTask().getChildren().getById(1);
// Get the first resource assignment of the project
ResourceAssignment firstRA = project.getResourceAssignments().toList().get(0);
```

## 如何變更輪廓 – Flat（預設）
```java
// Flat contour is the default contour
System.out.println("Flat contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 如何變更輪廓 – Turtle
```java
// Change contour to Turtle
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Turtle);
System.out.println("Turtle contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 如何變更輪廓 – BackLoaded
```java
// Change contour to BackLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
System.out.println("BackLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 如何變更輪廓 – FrontLoaded
```java
// Change contour to FrontLoaded
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.FrontLoaded);
System.out.println("FrontLoaded contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 如何變更輪廓 – Bell
```java
// Change contour to Bell
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.Bell);
System.out.println("Bell contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 如何變更輪廓 – EarlyPeak
```java
// Change contour to EarlyPeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.EarlyPeak);
System.out.println("EarlyPeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 如何變更輪廓 – LatePeak
```java
// Change contour to LatePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.LatePeak);
System.out.println("LatePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 如何變更輪廓 – DoublePeak
```java
// Change contour to DoublePeak
firstRA.set(Asn.WORK_CONTOUR, WorkContourType.DoublePeak);
System.out.println("DoublePeak contour");
for (TimephasedData td : task.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println(td.getStart().toString() + " " + td.getValue());
}
```

## 常見問題與技巧
- **輪廓未更新？** 確保在取得時間相位資料之前 *先* 呼叫 `firstRA.set(Asn.WORK_CONTOUR, …)`。  
- **數值異常？** 檢查來源 MPP 中任務的開始與結束日期是否正確設定。  
- **效能技巧：** 在遍歷多個輪廓時，重複使用同一個 `Project` 實例，以避免不必要的檔案 I/O。

## 常見問答
### 我可以將 Aspose.Tasks 與其他 Java 程式庫一起使用嗎？
可以，Aspose.Tasks 能與其他 Java 程式庫整合，以增強專案管理功能。

### Aspose.Tasks 適合大型企業專案嗎？
絕對適合，Aspose.Tasks 設計能處理各種規模的專案，包含大型企業級專案。

### Aspose.Tasks 是否支援不同的專案檔案格式？
是的，Aspose.Tasks 支援多種格式，例如 MPP、XML 與 MPX。

### 我可以根據專案需求自訂工作輪廓嗎？
可以，您可以自行定義工作輪廓，以符合特定排程需求。

### 有沒有社群論壇可以取得 Aspose.Tasks 的協助？
有，您可以前往 [Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15) 取得支援與討論。

---

**最後更新：** 2026-01-10  
**測試環境：** Aspose.Tasks for Java（最新發行版）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}