---
title: 在 Aspose.Tasks 中建立自訂 MS 專案視圖
linktitle: Aspose.Tasks 中的自訂視圖
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 輕鬆建立自訂 MS Project 視圖。透過客製化視圖提高專案管理效率。
type: docs
weight: 24
url: /zh-hant/java/project-file-operations/custom-views/
---
## 介紹
在專案管理中，自訂視圖可以顯著提高管理任務和資源的清晰度和效率。 Aspose.Tasks for Java 提供了強大的工具來建立根據特定專案要求自訂的自訂視圖。在本教程中，我們將逐步探索如何使用 Aspose.Tasks for Java 建立自訂 MS Project 視圖。
## 先決條件
在我們開始之前，請確保您符合以下先決條件：
### Java開發環境
確保您的系統上安裝了 Java。
### Java 的 Aspose.Tasks
下載並安裝 Aspose.Tasks for Java 從[這裡](https://releases.aspose.com/tasks/java/).
## 導入包
首先，將必要的套件匯入到您的 Java 專案中：
```java
import com.aspose.tasks.Field;
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.HorizontalStringAlignment;
import com.aspose.tasks.MPPSaveOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.TableField;
import com.aspose.tasks.View;
```
現在，讓我們將範例分解為多個步驟：
## 第 1 步：設定項目
```java
//文檔目錄的路徑。
String dataDir = "Your Data Directory";
//建立一個沒有視圖的空白項目
Project project = new Project();
project.set(Prj.NAME, "Test View Project");
```
## 第2步：建立視圖
```java
//建立標準甘特圖視圖
View view = new GanttChartView();
```
## 第 3 步：自訂視圖屬性
```java
//設定一些視圖屬性
view.setShowInMenu(true); //指示是否在選單中顯示視圖
view.setHighlightFilter(true); //指示是否要反白顯示視圖的篩選器
```
## 第 4 步：調整視圖設置
```java
//調整一些視圖設定
view.getPageInfo().getPageViewSettings().setFirstColumnsCount(4); //設定要在所有頁面上列印的第一列數
view.getPageInfo().getPageViewSettings().setPrintFirstColumnsCountOnAllPages(true); //指示是否在所有頁面上列印指定數量的第一列
```
## 第 5 步：將視圖新增至專案中
```java
//將視圖新增到我們的專案中
project.getViews().add(view);
```
## 第 6 步：儲存項目
```java
//使用建立的視圖儲存項目
MPPSaveOptions options = new MPPSaveOptions();
options.setWriteViewData(true); //使用 WriteViewData 標誌來儲存 project.Views 的修改
project.save(dataDir + "workWithView_output.mpp", options);
```
## 第 7 步：檢查視圖屬性
```java
//檢查新新增的視圖的屬性
System.out.println("View Uid: " + view.getUid()); //列印視圖的唯一識別符
System.out.println("View Screen: " + view.getScreen()); //列印檢視的螢幕類型
System.out.println("View Type: " + view.getType()); //列印視圖的類型
System.out.println("Parent Project of the view: " + view.getParentProject().get(Prj.NAME)); //列印檢視的父項目
```
## 結論
自訂 MS Project 視圖提供了一種根據特定需求視覺化專案資料的靈活方法。使用 Aspose.Tasks for Java，建立自訂視圖變得簡單，使專案經理能夠有效地簡化他們的工作流程。
## 經常問的問題
### 問題 1：我可以自訂甘特圖以外的視圖嗎？
答：是的，Aspose.Tasks for Java 提供了靈活性，可以自訂甘特圖以外的各種類型的視圖，包括表格和圖形。
### Q2：Aspose.Tasks for Java適合大型專案嗎？
答：當然。 Aspose.Tasks for Java 旨在處理各種規模的項目，為高效的專案管理提供強大的功能。
### Q3：Aspose.Tasks for Java 支援將視圖匯出為不同格式嗎？
答：是的，Aspose.Tasks for Java 支援將視圖匯出為 PDF、XLSX 和 HTML 等各種格式，確保與不同平台的兼容性。
### Q4：我可以使用 Aspose.Tasks for Java 自動建立自訂視圖嗎？
答：當然可以。 Aspose.Tasks for Java 提供了全面的自動化 API，使開發人員能夠根據需要以程式設計方式建立和管理自訂視圖。
### Q5：是否有 Aspose.Tasks for Java 支援的社群論壇？
答：是的，您可以在以下位置尋求協助並與其他使用者互動[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)用於 Java 相關的查詢和討論。