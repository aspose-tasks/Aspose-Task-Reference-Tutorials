---
date: 2025-12-21
description: 了解如何使用 Aspose.Tasks for Java 自訂甘特圖視圖、管理專案視覺化，並將專案另存為 PDF。輕鬆調整時間刻度數量。
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 自訂甘特圖 – 精通 Aspose.Tasks 中的 MS Project 時間尺度計數
url: /zh-hant/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 自訂甘特圖 – 精通 Aspose.Tasks 中的 MS Project 時間尺度計數

## Introduction
如果您需要在 Microsoft Project 中自訂甘特圖的視覺效果，控制時間尺度計數是一項關鍵技術。使用 Aspose.Tasks for Java，您可以以程式方式設定底層與中層時間尺度層級，微調刻度線可見性，然後 **將專案儲存為 PDF** 以與利害關係人分享。本教學將帶您完成整個流程——從環境設定到產生反映您自訂甘特圖檢視的精緻 PDF。

## Quick Answers
- **「自訂甘特圖」是什麼意思？** 調整時間尺度層級、顏色與版面配置，以符合您的報告需求。  
- **哪個 API 方法設定底層層級計數？** `view.getBottomTimescaleTier().setCount(int)`。  
- **我可以直接從專案產生 PDF 嗎？** 可以——使用 `project.save(..., SaveFileFormat.Pdf)`。  
- **生產環境需要授權嗎？** 需要商業授權；亦提供免費試用版。  
- **支援哪個 Java 版本？** Java 8 或更高版本可與最新的 Aspose.Tasks 函式庫一起使用。

## What is “customize Gantt chart” in Aspose.Tasks?
自訂甘特圖是指以程式方式改變其視覺元件——例如時間尺度間隔、刻度線與工作條——使圖表符合您想要的 **專案視覺化管理**。透過變更時間尺度計數，您可以控制每個區段代表多少天、週或月，讓圖表對不同觀眾更清晰。

## Prerequisites
Before you begin, make sure you have:

1. **Java 開發環境** – 已安裝 JDK 8 或更新版本。  
2. **Aspose.Tasks for Java 函式庫** – 從 [此處](https://releases.aspose.com/tasks/java/) 下載。  
3. **基本的 Java 知識** – 熟悉 Java 語法與物件導向概念。

## Import Packages
將必要的類別匯入您的 Java 專案：

```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## Step‑by‑Step Guide

### Step 1: Set Data Directory
定義專案檔案的讀寫目錄：

```java
String dataDir = "Your Data Directory";
```

將 `"Your Data Directory"` 替換為您機器上的絕對路徑。

### Step 2: Create a New Project Instance
建立一個全新的 `Project` 物件，用於保存所有工作與檢視設定：

```java
Project project = new Project();
```

### Step 3: Configure the Gantt Chart View
建立 `GanttChartView` 物件——在此您將 **產生 Gantt 檢視 Java** 程式碼以控制圖表外觀：

```java
GanttChartView view = new GanttChartView();
```

### Step 4: Set Time Scale Count for the Bottom Tier
將底層層級設定為顯示兩個間隔，並隱藏刻度線：

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### Step 5: Set Time Scale Count for the Middle Tier
將相同設定套用至中層層級：

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### Step 6: Add the Customized View to the Project
將剛剛設定好的檢視附加至 `Project` 例項：

```java
project.getViews().add(view);
```

### Step 7: Add Sample Tasks (Test Data)
建立幾個具有特定工期的工作，以示範自訂甘特圖：

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### Step 8: Save the Project as a PDF
最後，將專案（包括您的 **自訂甘特圖**）匯出為 PDF 檔案：

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

產生的 PDF 展示了底層與中層時間尺度層級已被 **自訂**，為利害關係人提供清晰、可列印的排程檢視。

## Common Issues & Troubleshooting
- **PDF 為空白** – 確認 `dataDir` 路徑以檔案分隔符（`/` 或 `\`）結尾，且該目錄確實存在。  
- **刻度線仍顯示** – 確認在兩個層級上皆呼叫了 `setShowTicks(false)`。  
- **工期未套用** – 確認在建立工期時使用了 `TimeUnitType.Hour`（或相應的單位）。

## Frequently Asked Questions

**問：Aspose.Tasks for Java 能處理大型專案檔案嗎？**  
答：可以，該函式庫已針對大量專案資料的高效能處理進行最佳化。

**問：Aspose.Tasks for Java 是否相容於不同的 Java IDE？**  
答：絕對相容——它可無縫運作於 Eclipse、IntelliJ IDEA、NetBeans 以及其他主流 IDE。

**問：我可以在時間尺度設定之外自訂甘特圖的外觀嗎？**  
答：可以，Aspose.Tasks 提供豐富的樣式選項，如條形顏色、字型與格線等。

**問：是否提供 Aspose.Tasks for Java 的試用版？**  
答：有，您可從 [此處](https://releases.aspose.com/) 取得免費試用版。

**問：在哪裡可以取得 Aspose.Tasks for Java 的支援？**  
答：您可在 Aspose.Tasks 論壇的 [此處](https://forum.aspose.com/c/tasks/15) 獲得支援與協助。

**問：如何以程式方式變更甘特圖的背景顏色？**  
答：在匯入 `java.awt.Color` 後，使用 `view.getGanttChartProperties().setBackgroundColor(Color)` 方法。

## Conclusion
透過上述步驟，您已學會如何 **自訂甘特圖** 的時間尺度層級、提升 **專案視覺化**，以及使用 Aspose.Tasks for Java **將專案儲存為 PDF**。此方法讓您完整掌控視覺輸出，便於與團隊或客戶分享清晰、專業的排程。

---

**最後更新：** 2025-12-21  
**測試環境：** Aspose.Tasks for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}