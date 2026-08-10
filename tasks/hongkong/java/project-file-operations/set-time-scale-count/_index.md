---
date: 2026-03-29
description: 學習如何使用 Aspose.Tasks for Java 建立專案 PDF 檔案，同時自訂甘特圖時間刻度的計數。本指南將一步步示範如何完整掌控甘特圖匯出為
  PDF。
linktitle: Set Time Scale Count in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 建立專案 PDF – 自訂甘特圖時間刻度
url: /zh-hant/java/project-file-operations/set-time-scale-count/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立專案 PDF – 自訂甘特圖時間尺度

## 簡介
如果您需要 **建立專案 PDF** 檔案，以呈現完美調校的甘特圖，控制時間尺度的計數是關鍵。使用 Aspose.Tasks for Java，您可以以程式方式設定底層與中層時間尺度層級、隱藏刻度線，然後 **將專案另存為 PDF** 以便輕鬆分發。在本教學中，我們將逐步說明您所需的一切——從設定開發環境到產生展示自訂甘特視圖的精緻 PDF。

## 快速解答
- **「自訂甘特圖」是什麼意思？** 調整時間尺度層級、顏色和版面配置，以符合您的報告需求。  
- **哪個 API 方法設定底層層級計數？** `view.getBottomTimescaleTier().setCount(int)`.  
- **我可以直接從專案產生 PDF 嗎？** 是——使用 `project.save(..., SaveFileFormat.Pdf)`.  
- **我需要授權才能在正式環境使用嗎？** 需要商業授權；亦提供免費試用版。  
- **支援哪個 Java 版本？** Java 8 或更高版本可與最新的 Aspose.Tasks 函式庫一起使用。

## 在 Aspose.Tasks 中，什麼是「自訂甘特圖」？
自訂甘特圖是指以程式方式變更其視覺元件——例如時間尺度間隔、刻度線與工作條——使圖表符合您想要的 **管理專案視覺化** 方式。透過變更時間尺度的計數，您可以控制每個區段代表多少天、週或月，讓圖表對不同觀眾更清晰。

## 為何要使用自訂甘特圖建立專案 PDF？
- **適合利害關係人使用的輸出：** PDF 可在任何平台檢視，確保所有人看到相同的排程版面。  
- **列印友好：** 精確控制時間尺度層級，可避免列印時過於擁擠或模糊。  
- **自動化：** 將 PDF 產生整合至 CI 流程或報告服務，實現零人工操作。

## 先決條件
1. **Java 開發環境** – 已安裝 JDK 8 或更新版本。  
2. **Aspose.Tasks for Java 函式庫** – 從 [here](https://releases.aspose.com/tasks/java/) 下載。  
3. **基本的 Java 知識** – 熟悉 Java 語法與物件導向概念。

## 匯入套件
將必要的類別匯入您的 Java 專案：

```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## 步驟說明

### 步驟 1：設定資料目錄
定義專案檔案的讀寫位置：

```java
String dataDir = "Your Data Directory";
```

將 `"Your Data Directory"` 替換為您機器上的絕對路徑。

### 步驟 2：建立新的 Project 實例
建立一個全新的 `Project` 物件，用於保存所有工作與檢視設定：

```java
Project project = new Project();
```

### 步驟 3：設定甘特圖檢視
建立一個 `GanttChartView` 物件——在此您將 **產生 Gantt view Java** 程式碼以控制圖表外觀：

```java
GanttChartView view = new GanttChartView();
```

### 步驟 4：設定底層時間尺度計數
將底層時間尺度設定為顯示兩個間隔，並隱藏刻度線：

```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```

### 步驟 5：設定中層時間尺度計數
將相同設定套用至中層時間尺度：

```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```

### 步驟 6：將自訂檢視加入專案
將剛剛設定好的檢視附加至 `Project` 實例：

```java
project.getViews().add(view);
```

### 步驟 7：加入範例工作（測試資料）
建立幾個具有特定持續時間的工作，以示範自訂甘特圖：

```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```

### 步驟 8：將專案另存為 PDF
最後，將專案（包括您的 **自訂甘特圖**）匯出為 PDF 檔案：

```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```

產生的 PDF 展示了底層與中層時間尺度已被 **自訂**，為利害關係人提供清晰、可列印的排程檢視。

## 常見問題與疑難排解
- **PDF 為空白** – 確認 `dataDir` 路徑以檔案分隔符號 (`/` 或 `\`) 結尾，且目錄已存在。  
- **仍顯示刻度線** – 確認已在兩個層級上呼叫 `setShowTicks(false)`。  
- **持續時間未套用** – 確認在建立持續時間時使用 `TimeUnitType.Hour`（或相應的單位）。

## 常見問與答

**Q: Aspose.Tasks for Java 能處理大型專案檔案嗎？**  
A: 可以，函式庫已針對大量專案資料的高效能處理進行最佳化。

**Q: Aspose.Tasks for Java 相容於不同的 Java IDE 嗎？**  
A: 完全相容——它可無縫運作於 Eclipse、IntelliJ IDEA、NetBeans 以及其他主流 IDE。

**Q: 我可以在時間尺度設定之外自訂甘特圖的外觀嗎？**  
A: 可以，Aspose.Tasks 提供廣泛的樣式選項，如條形顏色、字型與格線。

**Q: 是否有 Aspose.Tasks for Java 的試用版？**  
A: 有，您可從 [here](https://releases.aspose.com/) 取得免費試用版。

**Q: 在哪裡可以取得 Aspose.Tasks for Java 的支援？**  
A: 您可在 Aspose.Tasks 論壇 [here](https://forum.aspose.com/c/tasks/15) 獲得支援與協助。

**Q: 如何以程式方式變更甘特圖的背景顏色？**  
A: 在匯入 `java.awt.Color` 後，使用 `view.getGanttChartProperties().setBackgroundColor(Color)` 方法。

## 結論
透過遵循上述步驟，您已學會如何使用 Aspose.Tasks for Java **建立專案 PDF** 檔案，並以完整自訂的甘特圖時間尺度提升 **專案視覺化**，以及 **將專案另存為 PDF**。此方法讓您完全掌控視覺輸出，便於與團隊或客戶分享清晰、專業的排程。

---

**最後更新：** 2026-03-29  
**測試環境：** Aspose.Tasks for Java (latest)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}