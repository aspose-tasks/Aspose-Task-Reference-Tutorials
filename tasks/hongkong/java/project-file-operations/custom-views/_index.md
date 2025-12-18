---
date: 2025-12-18
description: 學習如何在 Aspose.Tasks for Java 中建立視圖，包括如何儲存專案視圖及設定視圖屬性。透過量身訂製的自訂 MS Project
  視圖提升專案管理效率。
linktitle: Custom Views in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何建立檢視：Aspose.Tasks 中的自訂 MS Project 檢視
url: /zh-hant/java/project-file-operations/custom-views/
weight: 24
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何建立視圖：Aspose.Tasks 中的自訂 MS Project 視圖

## 介紹
如果您正在尋找 **how to create view**，以符合專案獨特的報告需求，您來對地方了。在專案管理中，自訂視圖可以大幅提升處理任務與資源時的清晰度與效率。**Aspose.Tasks for Java** 為您提供豐富的 API，以 **add custom view java**‑style 解決方案，讓您能精確地依需求調整 MS Project 視圖。在本教學中，我們將一步一步說明整個流程，從建立專案到儲存專案視圖。

## 快速解答
- **What is the primary purpose?** 使用 Aspose.Tasks for Java 建立並保留自訂的 MS Project 視圖。  
- **Which class creates a view?** `GanttChartView`（或其他視圖類型）。  
- **How do I make the view appear in the menu?** 設定 `view.setShowInMenu(true)`。  
- **How can I save the view with the project?** 使用 `MPPSaveOptions` 並呼叫 `setWriteViewData(true)`。  
- **Do I need a license?** 是，需要有效的 Aspose.Tasks 授權才能於正式環境使用。

## 前置條件
在開始之前，請確保您具備以下前置條件：

### Java 開發環境
確保您的系統已安裝 Java。

### Aspose.Tasks for Java
從 [here](https://releases.aspose.com/tasks/java/) 下載並安裝 Aspose.Tasks for Java。

## 匯入套件
首先，將必要的套件匯入您的 Java 專案：
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

## 步驟 1：設定專案
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Create an empty project without views
Project project = new Project();
project.set(Prj.NAME, "Test View Project");
```

## 步驟 2：建立視圖
```java
// Create a standard Gantt chart view
View view = new GanttChartView();
```

## 步驟 3：自訂視圖屬性 *(set view properties)*
```java
// Set some view properties
view.setShowInMenu(true); // Indicate whether to show the view in the menu
view.setHighlightFilter(true); // Indicate whether to highlight the filter for the view
```

### 如何在視圖選單中顯示
呼叫 `view.setShowInMenu(true)` 可確保新建立的視圖出現在 MS Project **view menu** 中，讓最終使用者快速存取。

## 步驟 4：調整視圖設定
```java
// Tune some view settings
view.getPageInfo().getPageViewSettings().setFirstColumnsCount(4); // Set the number of first columns to print on all pages
view.getPageInfo().getPageViewSettings().setPrintFirstColumnsCountOnAllPages(true); // Indicate whether to print specified number of first columns on all pages
```

## 步驟 5：將視圖加入專案 *(add custom view java)*
```java
// Add the view to our project
project.getViews().add(view);
```

## 步驟 6：儲存專案 *(save project view)*
```java
// Save the project with the created view
MPPSaveOptions options = new MPPSaveOptions();
options.setWriteViewData(true); // Use WriteViewData flag to persist modifications of project.Views
project.save(dataDir + "workWithView_output.mpp", options);
```

### 為何儲存專案視圖很重要
設定 `options.setWriteViewData(true)` 讓 Aspose.Tasks 在 MPP 檔案內 **save project view** 資訊，確保自訂視圖在不同工作階段中持續存在。

## 步驟 7：檢查視圖屬性
```java
// Check properties of the newly added view
System.out.println("View Uid: " + view.getUid()); // Print the unique identifier of the view
System.out.println("View Screen: " + view.getScreen()); // Print the screen type for the view
System.out.println("View Type: " + view.getType()); // Print the type of the view
System.out.println("Parent Project of the view: " + view.getParentProject().get(Prj.NAME)); // Print the parent project of the view
```

## 常見使用情境
- **Stakeholder Reporting:** 建立僅顯示高階里程碑與關鍵任務的視圖。  
- **Resource Allocation:** 建立列出資源及其指派任務的視圖，以快速檢查容量。  
- **Print‑Ready Documents:** 調整頁面設定（如步驟 4）以產生可列印的專案快照。

## 疑難排解技巧
- **View Not Appearing in Menu:** 確認在儲存前已呼叫 `view.setShowInMenu(true)`。  
- **Missing Columns in Printout:** 確保 `setFirstColumnsCount` 與所需欄位相符，且已啟用 `setPrintFirstColumnsCountOnAllPages(true)`。  
- **License Exceptions:** 若遇到授權錯誤，請確認在建立 `Project` 物件前已載入有效的 Aspose.Tasks 授權檔案。

## 常見問答

### Q1：我可以自訂除甘特圖之外的視圖嗎？
A：可以，Aspose.Tasks for Java 提供彈性，可自訂除甘特圖之外的多種視圖，包括表格與圖表。

### Q2：Aspose.Tasks for Java 適用於大型專案嗎？
A：絕對適合。此函式庫設計能處理任何規模的專案，提供穩健的效能與記憶體管理。

### Q3：Aspose.Tasks for Java 支援將視圖匯出為不同格式嗎？
A：可以，您能將視圖匯出為 PDF、XLSX、HTML 等格式，確保跨平台的順暢分享。

### Q4：我可以使用 Aspose.Tasks for Java 自動化建立自訂視圖嗎？
A：當然可以。此 API 支援完整自動化，讓您能以程式方式產生與管理自訂視圖。

### Q5：是否有 Aspose.Tasks for Java 的社群論壇可供支援？
A：有，您可在 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 中取得協助，並與其他使用者討論 Java 相關問題。

---

**最後更新：** 2025-12-18  
**測試版本：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}