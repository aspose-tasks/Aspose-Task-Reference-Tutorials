---
title: Aspose.Tasks 中的渲染資源使用情況和工作表視圖
linktitle: Aspose.Tasks 中的渲染資源使用情況和工作表視圖
second_title: Aspose.Tasks Java API
description: 了解如何在 Aspose.Tasks for Java 中渲染 MS Project 資源使用情況和工作表視圖。按照我們的逐步指南輕鬆產生詳細的 PDF 報告。
type: docs
weight: 16
url: /zh-hant/java/resource-management/render-resource-usage-sheet-view/
---
## 介紹
在本教程中，我們將學習如何使用 Aspose.Tasks for Java 渲染 MS Project 資源使用情況和工作表視圖。 Aspose.Tasks 是一個功能強大的 Java 程式庫，可讓開發人員使用 Microsoft Project 文件，而無需安裝 Microsoft Project。
## 先決條件
在開始之前，請確保您已安裝並設定以下先決條件：
1. Java 開發工具包 (JDK)：確保您的系統上安裝了 Java 開發工具包。您可以從 Oracle 網站下載並安裝最新版本的 JDK。
2.  Aspose.Tasks for Java：從下列位置下載並安裝 Aspose.Tasks for Java 函式庫[下載頁面](https://releases.aspose.com/tasks/java/).

## 導入包
首先，您需要將必要的套件匯入到您的 Java 專案中：
```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```
## 第 1 步：閱讀來源項目
```java
//文檔目錄的路徑。
String dataDir = "Your Data Directory";
//閱讀來源項目
Project project = new Project(dataDir + "ResourceUsageView.mpp");
```
在此步驟中，我們指定來源項目檔案的路徑（`ResourceUsageView.mpp` ）並使用`Project`類別來閱讀它。
## 步驟 2：使用所需的時間刻度設定定義 SaveOptions
```java
//將所需的 TimeScale 設定定義為 Days
SaveOptions options = new PdfSaveOptions();
options.setTimescale(Timescale.Days);
```
在這裡，我們定義`SaveOptions`與所需的`TimeScale`設定.在這個例子中，我們設定`TimeScale`至天。
## 步驟 3：將示範格式設定為 ResourceUsage
```java
//將簡報格式設定為 ResourceUsage
options.setPresentationFormat(PresentationFormat.ResourceUsage);
```
我們將演示格式設定為`ResourceUsage`，表示我們要渲染資源使用情況視圖。
## 第 4 步：儲存項目
```java
//保存項目
project.save(dataDir + days, options);
```
最後，我們使用指定的選項來儲存項目。在此範例中，輸出檔案將另存為`result_days.pdf`.
## 第 5 步：渲染其他時間刻度設定的視圖
重複步驟 2 到 4 以使用不同的時間刻度設定（ThirdsOfMonths 和 Months）渲染視圖。
```java
//將時間刻度設定為 ThirdsOfMonths
options.setTimescale(Timescale.ThirdsOfMonths);
//保存項目
project.save(thirds, options);
//將時間刻度設定設定為月
options.setTimescale(Timescale.Months);
//保存項目
project.save(dataDir + months, options);
```
確保更改`Timescale`為每個視圖進行相應的設定。

## 結論
在本教程中，我們探索如何使用 Aspose.Tasks for Java 來渲染 MS Project 資源使用情況和工作表視圖。透過執行上述步驟，您可以有效率地產生 PDF 格式的視圖，從而更好地視覺化和分析專案資料。
## 常見問題解答
### 除了資源使用情況和工作表之外，Aspose.Tasks 還可以渲染其他視圖嗎？
Aspose.Tasks 支援渲染各種視圖，例如甘特圖、任務使用情況和日曆視圖等。
### Aspose.Tasks 是否與不同版本的 Microsoft Project 檔案相容？
是的，Aspose.Tasks 支援多種 Microsoft Project 檔案格式，包括 MPP、MPT 和 XML 格式。
### 我可以使用 Aspose.Tasks 自訂渲染視圖的外觀嗎？
絕對地！ Aspose.Tasks 提供了廣泛的選項來自訂渲染視圖的外觀和佈局以滿足您的特定要求。
### Aspose.Tasks 是否需要在系統上安裝 Microsoft Project？
不需要，Aspose.Tasks 是一個獨立的函式庫，不需要安裝 Microsoft Project 即可運作。
### Aspose.Tasks 用戶可以獲得技術支援嗎？
是的，Aspose.Tasks 用戶可以透過以下方式獲得技術支援：[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15).