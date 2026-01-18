---
date: 2026-01-18
description: 學習如何使用 Aspose.Tasks for Java 安排專案管理基準，讓您能管理專案基準並比較計劃與實際進度。
linktitle: Baseline Task Scheduling in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 項目管理基準 – 使用 Aspose.Tasks 進行任務排程
url: /zh-hant/java/task-baselines/baseline-task-scheduling/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 專案管理基線 – 使用 Aspose.Tasks 進行工作排程

## 專案管理基線簡介
管理 **專案管理基線** 是有效專案管理的基石。它讓您能夠捕捉原始計畫，之後比較 **計畫與實際進度**，以便及早發現差異。在本教學中，我們將示範如何使用 Aspose.Tasks for Java 來排程工作基線，讓您能自信地 **管理專案基線**，並確保專案保持在正軌上。

## 快速回答
- **專案管理基線代表什麼？**  
  基線記錄原始的排程、成本與範圍，以便日後進行差異分析。  
- **哪個程式庫在 Java 中處理基線排程？**  
  Aspose.Tasks for Java 提供強大的 API 來建立與管理基線。  
- **執行程式碼是否需要授權？**  
  免費試用可用於測試；正式環境需購買商業授權。  
- **主要前置條件是什麼？**  
  Java Development Kit (JDK) 與 Aspose.Tasks for Java 程式庫。  
- **設定基線後可以查看基線日期嗎？**  
  可以——使用 `TaskBaseline` 物件讀取開始、結束與持續時間值。

## 什麼是專案管理基線？
專案管理基線捕捉在執行開始時已核准的專案排程、預算與範圍版本。它作為衡量績效與辨識整個專案生命週期中偏差的參考點。

## 為什麼使用 Aspose.Tasks 進行基線排程？
Aspose.Tasks 提供純 Java API，無需安裝 Microsoft Project。它讓您 **建立專案實例**、定義工作、設定基線，並以程式方式取得基線資訊——非常適合自動化報表或整合到自訂的專案管理工具中。

## 前置條件
在開始之前，請確保已具備以下環境：

### Java 開發環境
請確認您的系統已安裝 Java Development Kit (JDK)。您可以從 [官方網站](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) 下載並安裝 JDK。

### Aspose.Tasks for Java 程式庫
從 [下載頁面](https://releases.aspose.com/tasks/java/) 取得 Aspose.Tasks for Java 程式庫，並將其加入您的 Java 專案中。

## 匯入套件
先在 Java 專案中匯入必要的套件：

```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskBaseline;
```

接下來，我們將把範例程式分解為多個步驟說明：

## 步驟 1：建立新專案實例
```java
Project project = new Project();
```

## 步驟 2：定義工作並設定基線
```java
Task task = project.getRootTask().getChildren().add("Task");
project.setBaseline(BaselineType.Baseline);
```

## 步驟 3：存取基線資訊
```java
TaskBaseline baseline = task.getBaselines().get(0);
```

## 步驟 4：顯示基線持續時間
```java
System.out.println(baseline.getDuration().toString());
```

## 步驟 5：顯示基線開始日期
```java
System.out.println("Baseline Start: " + baseline.getStart());
```

## 步驟 6：顯示基線結束日期
```java
System.out.println("Baseline Finish: " + baseline.getFinish());
```

依照上述步驟操作，即可有效利用 Aspose.Tasks for Java **管理專案基線**。

## 常見問題與解決方案
- **基線未設定：** 確保在加入工作後呼叫 `project.setBaseline(BaselineType.Baseline)` **之後** 再設定基線；否則基線集合會是空的。  
- **空值：** 若 `task.getBaselines()` 回傳空列表，請確認工作已加入專案階層後再設定基線。  
- **日期格式：** `getStart()` 與 `getFinish()` 方法回傳 `Date` 物件。如需自訂顯示格式，請使用格式化程式。

## 常見問答

### Aspose.Tasks for Java 能處理複雜的專案結構嗎？
可以，Aspose.Tasks for Java 提供強大的功能，能有效管理各種複雜度的專案。

### Aspose.Tasks for Java 與其他 Java 程式庫相容嗎？
絕對相容，Aspose.Tasks for Java 可無縫整合其他 Java 程式庫，提升您的專案管理能力。

### 我可以使用 Aspose.Tasks for Java 自訂工作基線嗎？
當然可以，Aspose.Tasks for Java 提供廣泛的功能，讓您依專案需求自訂與管理工作基線。

### Aspose.Tasks for Java 有提供試用版嗎？
有，您可從 [發行頁面](https://releases.aspose.com/) 取得 Aspose.Tasks for Java 的免費試用版。

### 我該去哪裡取得 Aspose.Tasks for Java 的支援？
如有任何問題或需要協助，請前往 Aspose.Tasks 論壇 [此處](https://forum.aspose.com/c/tasks/15)。

## Frequently Asked Questions

**Q: 如何在 Aspose.Tasks 中建立新專案實例？**  
A: 直接實例化 `Project` 類別 (`Project project = new Project();`) 即可。這會建立一個全新的專案檔，供您加入工作與基線使用。

**Q: `BaselineType.Baseline` 與其他基線類型有何差異？**  
A: `BaselineType.Baseline` 代表主要基線（基線 1）。Aspose.Tasks 亦支援基線 2‑10，以便建立額外的快照。

**Q: 能否將基線資料匯出為 Excel 或 CSV？**  
A: 可以，您可以遍歷 `TaskBaseline` 物件，並使用標準的 Java I/O 將資料寫入 CSV 檔案。

**Q: 設定基線會影響現有的工作日期嗎？**  
A: 設定基線會捕捉當前的日期，但不會修改工作本身的排程。基線設定後，仍可調整開始/結束日期。

**Q: 是否可以程式化比較多個基線？**  
A: 完全可以。透過 `task.getBaselines().get(index)` 取得各基線，然後比較其 `Start`、`Finish` 與 `Duration` 屬性。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-01-18  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

---