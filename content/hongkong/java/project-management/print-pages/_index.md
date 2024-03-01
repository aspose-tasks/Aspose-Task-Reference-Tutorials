---
title: 在 Aspose.Tasks 中列印頁面以分隔影像
linktitle: 在 Aspose.Tasks 中列印頁面以分隔影像
second_title: Aspose.Tasks Java API
description: 了解如何在 Aspose.Tasks for Java 中列印頁面以分隔圖片。透過此逐步指南改進專案視覺化。
type: docs
weight: 22
url: /zh-hant/java/project-management/print-pages/
---
## 介紹
在本教程中，我們將指導您完成使用 Aspose.Tasks for Java 列印頁面以分離圖像的過程。當您需要單獨視覺化專案佈局或關鍵任務時，此功能特別有用。
## 先決條件
在我們開始之前，請確保您具備以下先決條件：
1.  Java 開發工具包 (JDK)：確保您的系統上安裝了 JDK。您可以從以下位置下載：[這裡](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
   
2.  Aspose.Tasks for Java 函式庫：下載 Aspose.Tasks for Java 函式庫並將其包含在您的專案中。你可以從[這裡](https://releases.aspose.com/tasks/java/).

## 導入包
確保在 Java 檔案的開頭導入必要的套件：
```java
import com.aspose.tasks.Gridline;
import com.aspose.tasks.GridlineType;
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.LinePattern;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.awt.*;
import java.util.ArrayList;
```
## 第 1 步：載入項目數據
首先，從 MPP 檔案載入專案資料：
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "CustomerFeedback.mpp");
```
## 第 2 步：設定影像儲存選項
定義儲存影像的選項，包括開始日期、結束日期、關鍵任務、圖例和網格線：
```java
ImageSaveOptions saveOptions = new ImageSaveOptions(SaveFileFormat.Png);
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.setTime(project.get(Prj.START_DATE));
cal.add(java.util.Calendar.DATE, -3);
saveOptions.setStartDate(cal.getTime());
saveOptions.setEndDate(project.get(Prj.FINISH_DATE));
saveOptions.setMarkCriticalTasks(true);
saveOptions.setLegendOnEachPage(false);
```
## 第 3 步：自訂網格線
自訂影像的網格線，指定類型、顏色和圖案：
```java
saveOptions.setGridlines(new ArrayList<Gridline>());
Gridline gridline = new Gridline();
gridline.setGridlineType(GridlineType.GanttRow);
gridline.setColor(Color.BLUE);
gridline.setPattern(LinePattern.Dashed);
saveOptions.getGridlines().add(gridline);
```
## 第 4 步：儲存影像
將專案佈局另存為圖像，既可以作為單一文件，也可以作為單獨的文件：
```java
project.save(dataDir + "CustomerFeedback.png", saveOptions);
saveOptions.setRenderToSinglePage(false);
project.save(dataDir + "CustomerFeedback_.png", saveOptions);
```

## 結論
在本教程中，我們示範如何使用 Aspose.Tasks for Java 列印頁面以分離圖像。透過執行上述步驟，您可以根據您的要求有效地視覺化專案佈局和關鍵任務。
## 常見問題解答
### Q：儲存專案佈局時可以自訂影像格式嗎？
答：是的，Aspose.Tasks for Java 支援多種圖片格式，如 PNG、JPEG、BMP 等。您可以在`ImageSaveOptions`班級。
### Q：Aspose.Tasks for Java 是否相容於不同的 Java 開發環境？
答：是的，Aspose.Tasks for Java 與大多數 Java 開發環境相容，包括 Eclipse、IntelliJ IDEA 和 NetBeans。
### Q：我可以將 Aspose.Tasks for Java 整合到我的 Maven 或 Gradle 專案中嗎？
答：是的，您可以透過在您的專案中新增適當的依賴項，輕鬆地將 Aspose.Tasks for Java 整合到您的 Maven 或 Gradle 專案中。`pom.xml`或者`build.gradle`文件。
### Q：Aspose.Tasks for Java 是否支援將專案資料匯出為圖像以外的其他格式？
答：是的，Aspose.Tasks for Java 支援將專案資料匯出為 PDF、HTML、XLSX 等各種格式，為資料視覺化和報表提供彈性。
### Q：Aspose.Tasks for Java 是否有任何社群支援？
答：是的，您可以在 上找到社群支援、提出問題並與其他使用者互動[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15).