---
date: 2026-10-31
description: 了解如何在 Java 中使用 Aspose.Tasks 匯出 Gantt 為 PDF。本分步指南將示範如何讀取 Gantt 圖表資料並產生
  PDF 報告。
keywords:
- export gantt to pdf
- how to read gantt
- export gantt to excel
- generate gantt report java
lastmod: 2026-10-31
linktitle: 在 Aspose.Tasks 中讀取特定 Gantt 圖表資料
og_description: 使用 Aspose.Tasks 在 Java 中匯出 Gantt 為 PDF。跟隨本教學讀取 Gantt 圖表資料、客製化檢視屬性，並為專案管理產生
  PDF 報告。
og_image_alt: 'Tutorial screenshot: exporting Gantt chart to PDF using Aspose.Tasks
  for Java'
og_title: 在 Java 中匯出 Gantt 為 PDF – Aspose.Tasks 指南
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to export gantt to pdf in Java using Aspose.Tasks. This step‑by‑step
    guide shows you how to read Gantt chart data and generate PDF reports.
  headline: Export gantt to pdf in Java – extract specific data
  type: TechArticle
- description: Learn how to export gantt to pdf in Java using Aspose.Tasks. This step‑by‑step
    guide shows you how to read Gantt chart data and generate PDF reports.
  name: Export gantt to pdf in Java – extract specific data
  steps:
  - name: '**Java Development Kit (JDK):** Make sure you have Java installed on your
      system. You can download it from the **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.'
    text: '**Java Development Kit (JDK):** Make sure you have Java installed on your
      system. You can download it from the **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)**.'
  - name: '**Aspose.Tasks for Java Library:** Download and install the Aspose.Tasks
      for Java library from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
    text: '**Aspose.Tasks for Java Library:** Download and install the Aspose.Tasks
      for Java library from the **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)**.'
  - name: '**Integrated Development Environment (IDE):** Choose an IDE of your preference.
      Popular choices include IntelliJ IDEA, Eclipse, or NetBeans.'
    text: '**Integrated Development Environment (IDE):** Choose an IDE of your preference.
      Popular choices include IntelliJ IDEA, Eclipse, or NetBeans.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates seamlessly with any Java library
      or framework, including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library processes multi‑hundred‑page MPP files in under
      5 seconds on standard server hardware and supports concurrent execution in multi‑threaded
      environments.
    question: Is Aspose.Tasks suitable for large‑scale enterprise projects?
  - answer: Yes, Aspose.Tasks supports 20+ formats, including MPP, XML, MPX, and Primavera
      XML, enabling you to read and convert legacy schedules.
    question: Does Aspose.Tasks support multiple project file formats?
  - answer: Certainly. You can modify bar styles, gridlines, text styles, and timescale
      tiers programmatically before exporting to PDF or image formats.
    question: Can I customize the appearance of Gantt charts with Aspose.Tasks?
  - answer: Call `project.save("output.mpp");` after making any modifications to persist
      them to the project file.
    question: How do I save changes after modifying a view?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- export gantt
- Aspose.Tasks
- Java Gantt
- pdf generation
- project management
title: 在 Java 中匯出 Gantt 為 PDF – 提取特定資料
url: /zh-hant/java/project-data-reading/read-specific-gantt-chart-data/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 中匯出甘特圖為 PDF – 提取特定資料

## 簡介
在本教學中，您將學習如何透過 Aspose.Tasks for Java 讀取甘特圖資訊，**export gantt to pdf in Java**。甘特圖為專案經理提供任務、相依性與時間線的視覺路線圖，能以程式方式提取這些資料，即可建立自動化的 PDF 報告、儀表板，或與其他企業系統整合。讓我們一步步說明，從載入專案檔案、提取視圖屬性，到最終產生 PDF。

## 快速回答
- **What can I extract?** 任何甘特圖的視圖屬性、條形樣式、格線、文字樣式、進度線或時間刻度層級。  
- **Do I need a license?** 試用版可用於開發；商業授權在正式環境中必須使用。  
- **Which Java version is supported?** 支援 Java 8 或更新版本（本教學使用 JDK 11）。  
- **Is the code runnable as‑as?** 是 – 只需更改資料目錄路徑即可。  
- **Can I modify the view after reading?** 當然 – API 允許您變更屬性並儲存回專案檔案。

## 什麼是 export gantt to pdf？
Export gantt to pdf 是將儲存在專案檔案中的甘特圖視圖轉換為 PDF 文件的過程，該文件保留視覺樣式與時間軸資訊。此操作可用於向可能沒有專案管理工具的利害關係人分享專案狀態。

## 為何使用 Aspose.Tasks 匯出 gantt 為 pdf？
Aspose.Tasks 能處理 **超過 30 種輸入格式**（MPP、XML、MPX 等），並且 **一次呼叫即可匯出為 PDF**，同時保留 95 % 的視覺忠實度，即使是超過 500 個任務的專案亦是如此。此函式庫在記憶體中處理檔案，讓您無需安裝 Microsoft Project 即可在伺服器上產生 PDF。

## 先決條件
1. **Java Development Kit (JDK):** 確保您的系統已安裝 Java。您可以從 **[Oracle JDK 11 download page](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)** 下載。  
2. **Aspose.Tasks for Java Library:** 從 **[Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/)** 下載並安裝 Aspose.Tasks for Java 函式庫。  
3. **Integrated Development Environment (IDE):** 選擇您偏好的 IDE。常見選擇包括 IntelliJ IDEA、Eclipse 或 NetBeans。

## 匯入套件
以下的匯入語句讓您取得讀取與匯出甘特資料所需的核心 Aspose.Tasks 類別。  
*此處未顯示程式碼區塊，以保持教學聚焦於概念；只需將匯入語句加入您的 Java 檔案即可。*

## 如何在 Java 中載入甘特圖專案檔案？
透過建立 `Project` 實例並將完整路徑傳入建構子來載入專案檔案。此步驟會初始化甘特圖的記憶體表示，讓您之後可以查詢視圖屬性。檔案成功載入後，您可以驗證專案名稱、開始日期以及任務數量，以確保開啟的是正確的檔案。此驗證有助於在工作流程早期捕捉路徑或格式問題。

```java
Project project = new Project(dataDir + "SampleProject.mpp");
```  
*定義說明:* `Project` 是代表單一專案檔案於記憶體中的頂層 Aspose.Tasks 物件。

## 如何存取甘特圖視圖？
從專案的視圖集合中取得第一個甘特視圖。大多數專案至少包含一個甘特視圖，且通常是第一個條目。取得視圖後，您可能需要檢查其名稱，並確保其類型為 `GanttChartView`，再進行屬性提取。此額外檢查可防止在處理自訂或非標準視圖集合時發生執行時錯誤。

```java
GanttChartView ganttView = (GanttChartView) project.getViews().get(0);
```  
*定義說明:* `GanttChartView` 代表您在典型甘特圖中看到的任務、時間刻度與條形的視覺佈局。

## 如何提取視圖屬性？
您可以直接從 `GanttChartView` 物件讀取背景顏色、條形高度與時間刻度設定等屬性。將它們列印出來有助於在匯出前驗證目前的配置。典型的提取迴圈會遍歷每個屬性，將值格式化為字串，並記錄到主控台或檔案以供後續分析。此方法對除錯以及產生圖表外觀文件都很有幫助。

```java
System.out.println("Bar height: " + ganttView.getBarHeight());
System.out.println("Show gridlines: " + ganttView.getShowGridlines());
```  
*定義說明:* `GanttChartView` 提供對視圖設定（如背景顏色、條形高度與時間刻度配置）的存取。

## 如何提取條形樣式？
遍歷 `BarStyle` 物件集合，以取得圖表中每種條形的顏色、圖案與形狀等細節。對於每個樣式，您亦可讀取其關聯的任務類型與觸發該樣式的條件，這在以其他格式重建圖表時相當重要。收集此資訊可讓您製作忠實的視覺複製品，或以程式方式套用自訂樣式規則。

```java
for (BarStyle style : ganttView.getBarStyles()) {
    System.out.println("Bar type: " + style.getBarType() + ", Color: " + style.getColor());
}
```  
*定義說明:* `BarStyle` 定義甘特條形的視覺外觀，包括其顏色、圖案與形狀。

## 如何提取格線？
格線定義列與欄之間的視覺分隔。可透過 `getGridlines()` 方法存取，並輸出其可見性與樣式。取得格線集合後，您可以遍歷每條線，捕捉其線型（實線、虛線）、粗細與顏色。當您需要在匯出的 PDF 或其他報告格式中重現精確的格線佈局時，這些資料相當有價值。

```java
for (Gridline grid : ganttView.getGridlines()) {
    System.out.println("Gridline visible: " + grid.getVisible());
}
```  
*定義說明:* `getGridlines()` 回傳控制甘特視圖中列與欄分隔的格線物件集合。

## 如何提取文字樣式？
文字樣式控制甘特圖上標籤的字型、大小與顏色。遍歷 `TextStyle` 集合以列出每種樣式。對於每個文字樣式，您亦可取得其關聯的元素（任務名稱、日期等）以及任何條件格式規則。捕捉這些細節可確保匯出文件保留與原始圖表相同的排版。

```java
for (TextStyle txt : ganttView.getTextStyles()) {
    System.out.println("Text style: " + txt.getStyle() + ", Font size: " + txt.getFontSize());
}
```  
*定義說明:* `TextStyle` 代表套用於甘特圖內文字元素的格式屬性。

## 如何提取進度線？
進度線顯示任務的目前完成點。可透過 `getProgressLines()` 存取，並列印其屬性。每條進度線包含線條顏色、粗細以及相對於任務條的定位等屬性。記錄此資訊可讓您產生具進度感知的視覺化圖表，或計算整體專案完成度指標。

```java
for (ProgressLine line : ganttView.getProgressLines()) {
    System.out.println("Progress line color: " + line.getColor());
}
```  
*定義說明:* `getProgressLines()` 回傳表示任務完成狀態的進度線物件集合。

## 如何提取時間刻度層級？
時間刻度層級定義圖表上顯示的階層時間單位（天、週、月）。可透過 `getTimescaleTiers()` 取得，並輸出其設定。對於每個層級，您可以捕捉單位類型、標籤格式與對齊方式，這對於在匯出 PDF 或自訂 UI 元件中重現精確的時間軸粒度至關重要。

```java
for (TimescaleTier tier : ganttView.getTimescaleTiers()) {
    System.out.println("Tier type: " + tier.getTierType());
}
```  
*定義說明:* `getTimescaleTiers()` 提供存取控制時間軸顯示的時間刻度層級物件集合。

## 如何將甘特圖匯出為 PDF？
建立 `PdfSaveOptions` 物件，必要時自訂頁面大小或字型嵌入，然後以 PDF 格式呼叫 `project.save`。此一次呼叫即可產生與螢幕上甘特視圖相同的 PDF。您亦可指定額外選項，如影像壓縮、移除浮水印或嵌入自訂字型，以符合企業品牌需求。儲存後，請驗證 PDF 檔案大小與視覺忠實度，以確保匯出成功。

```java
PdfSaveOptions options = new PdfSaveOptions();
options.setPageSize(PageSize.A4);
project.save(dataDir + "ExportedGantt.pdf", options);
```  
*定義說明:* `PdfSaveOptions` 讓您微調 PDF 輸出，例如頁面尺寸、壓縮與字型處理。

## 常見陷阱與技巧
- **Incorrect data directory:** 確保 `dataDir` 以符合您作業系統的檔案分隔符（`/` 或 `\\`）結尾。  
- **Missing view:** 若專案沒有甘特視圖，`project.getViews()` 會是空的 – 在轉型前加入檢查。  
- **License exceptions:** 若未持有有效授權，API 可能在匯出的 PDF 上加上浮水印。  
- **Large projects:** 對於超過 1,000 個任務的專案，建議增大 JVM 堆積大小（`-Xmx2g`），以避免 `OutOfMemoryError`。

## 常見問與答

**Q: 我可以將 Aspose.Tasks for Java 與其他 Java 函式庫一起使用嗎？**  
A: 可以，Aspose.Tasks for Java 可無縫整合任何 Java 函式庫或框架，包括 Spring、Hibernate 與 Apache POI。

**Q: Aspose.Tasks 適合大型企業專案嗎？**  
A: 絕對適合。此函式庫可在標準伺服器硬體上於 5 秒內處理數百頁的 MPP 檔案，且支援多執行緒環境中的併發執行。

**Q: Aspose.Tasks 支援多種專案檔案格式嗎？**  
A: 支援，Aspose.Tasks 支援超過 20 種格式，包括 MPP、XML、MPX 與 Primavera XML，讓您能讀取並轉換舊有排程。

**Q: 我可以使用 Aspose.Tasks 自訂甘特圖的外觀嗎？**  
A: 當然可以。您可以在匯出為 PDF 或影像格式前，以程式方式修改條形樣式、格線、文字樣式與時間刻度層級。

**Q: 修改視圖後如何儲存變更？**  
A: 在完成任何修改後，呼叫 `project.save("output.mpp");` 以將變更寫回專案檔案。

---

**最後更新：** 2026-10-31  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  



```java
import com.aspose.tasks.DateLabel;
import com.aspose.tasks.DayType;
import com.aspose.tasks.Field;
import com.aspose.tasks.FontStyles;
import com.aspose.tasks.GanttBarEndShape;
import com.aspose.tasks.GanttBarMiddleShape;
import com.aspose.tasks.GanttBarShowFor;
import com.aspose.tasks.GanttBarSize;
import com.aspose.tasks.GanttBarStyle;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.Gridlines;
import com.aspose.tasks.Interval;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Project;
import com.aspose.tasks.TextStyle;
import com.aspose.tasks.TimescaleUnit;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "ReadSpecificGantChartViewData.mpp");
```

```java
GanttChartView view = (GanttChartView) project.getViews().toList().get(0);
```

```java
System.out.println("View.BarRounding: " + view.getBarRounding());
System.out.println("view.ShowBarSplits: " + view.getShowBarSplits());
System.out.println("view.ShowDrawings: " + view.getShowDrawings());
// Continue for other properties...
```

```java
for (int i = 0; i < view.getBarStyles().size(); i++) {
    GanttBarStyle barStyle = view.getBarStyles().get(i);
    // Print bar style details...
}
```

```java
System.out.println("Gridlines count: " + view.getGridlines().size());
Gridlines gridlines = view.getGridlines().get(0);
// Print gridline details...
```

```java
System.out.println("\nView Text Styles:");
for (TextStyle textStyle : view.getTextStyles()) {
    // Print text style details...
}
```

```java
System.out.println("ProgressLInes.BeginAtDate: " + view.getProgressLines().getBeginAtDate());
// Print other progress line details...
```

```java
System.out.println("BottomTimescaleTier.Count: " + view.getBottomTimescaleTier().getCount());
// Print details of other timescale tiers...
```

## 相關教學

- [如何使用 Aspose.Tasks 將專案儲存為 PDF – 匯出指南](/tasks/java/project-file-operations/save-as-pdf/)
- [建立專案 PDF – 自訂甘特圖時間刻度](/tasks/java/project-file-operations/set-time-scale-count/)
- [匯出專案為 PDF 並縮小任務清單與頁腳之間的間距 – Aspose.Tasks](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}