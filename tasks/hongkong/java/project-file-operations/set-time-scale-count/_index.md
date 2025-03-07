---
title: 在 Aspose.Tasks 中掌握 MS 專案時間尺度計數
linktitle: 在 Aspose.Tasks 中設定時間刻度計數
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 有效管理 MS Project 中的時間刻度計數。輕鬆優化專案視覺化和管理。
weight: 22
url: /zh-hant/java/project-file-operations/set-time-scale-count/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中掌握 MS 專案時間尺度計數

## 介紹
在 MS Project 中管理時間尺度計數可以顯著影響專案視覺化和管理。使用 Aspose.Tasks for Java（一種用於以程式設計方式處理專案管理任務的強大 API），您可以有效地操作時間刻度計數，以根據您的特定需求自訂專案視圖。
## 先決條件
在開始之前，請確保您已具備以下條件：
1. Java 開發環境：確保您的系統上安裝了 Java 開發工具包 (JDK)。
2.  Aspose.Tasks for Java 函式庫：下載並安裝 Aspose.Tasks for Java 函式庫。你可以從[這裡](https://releases.aspose.com/tasks/java/).
3. Java 程式設計基礎知識：熟悉 Java 程式語言將會很有幫助。

## 導入包
將必要的套件匯入到您的 Java 專案中：
```java
import com.aspose.tasks.GanttChartView;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## 第1步：設定資料目錄
定義將儲存項目檔案的資料目錄的路徑：
```java
String dataDir = "Your Data Directory";
```
代替`"Your Data Directory"`與您的資料目錄的路徑。
## 步驟2：建立專案實例
實例化一個新的`Project`目的：
```java
Project project = new Project();
```
這將建立一個新的專案物件。
## 步驟 3：配置甘特圖視圖
創建一個`GanttChartView`物件來配置甘特圖視圖：
```java
GanttChartView view = new GanttChartView();
```
## 步驟 4：設定底層的時間刻度計數
設定底部時間刻度層的計數和刻度可見性：
```java
view.getBottomTimescaleTier().setCount(2);
view.getBottomTimescaleTier().setShowTicks(false);
```
這指定間隔計數以及是否顯示底層的刻度。
## 步驟 5：設定中間層的時間刻度計數
同樣，配置中間時間刻度層：
```java
view.getMiddleTimescaleTier().setCount(2);
view.getMiddleTimescaleTier().setShowTicks(false);
```
## 第 6 步：將視圖新增至專案中
將配置好的視圖新增至專案：
```java
project.getViews().add(view);
```
這會將自訂視圖新增至專案中。
## 步驟7：將測試資料新增至專案中
專案中加入一些測試資料進行示範：
```java
Task task1 = project.getRootTask().getChildren().add("Task 1");
Task task2 = project.getRootTask().getChildren().add("Task 2");
task1.set(Tsk.DURATION, task1.getParentProject().getDuration(24, TimeUnitType.Hour));
task2.set(Tsk.DURATION, task1.getParentProject().getDuration(40, TimeUnitType.Hour));
```
這將建立兩個具有指定持續時間的任務。
## 第 8 步：將項目另存為 PDF
將項目另存為 PDF 檔案：
```java
project.save(dataDir + "temp.pdf", SaveFileFormat.Pdf);
```
這會將套用了配置的項目儲存到 PDF 檔案中。

## 結論
使用 Aspose.Tasks for Java 有效管理 MS Project 中的時間刻度計數，讓您能夠自訂專案視圖，以實現更好的視覺化和管理。
## 常見問題解答
### Q：Aspose.Tasks for Java 可以處理大型專案檔嗎？
答：是的，Aspose.Tasks for Java 能夠有效地處理大型專案檔。
### Q：Aspose.Tasks for Java 是否與不同的 Java IDE 相容？
答：是的，Aspose.Tasks for Java 可以與流行的 Java 整合開發環境 (IDE) 無縫協作，例如 Eclipse 和 IntelliJ IDEA。
### Q：我可以使用 Aspose.Tasks for Java 自訂甘特圖的外觀嗎？
答：當然，Aspose.Tasks for Java 提供了廣泛的功能，可以根據您的要求自訂甘特圖的外觀。
### Q：Aspose.Tasks for Java 有試用版嗎？
答：是的，您可以從以下位置取得免費試用版[這裡](https://releases.aspose.com/).
### Q：在哪裡可以獲得 Aspose.Tasks for Java 的支援？
答：您可以在 Aspose.Tasks 論壇上找到支援和協助[這裡](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
