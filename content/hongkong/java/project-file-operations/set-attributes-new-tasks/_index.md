---
title: 在 Aspose.Tasks 中設定新任務的 MS 項目屬性
linktitle: 在 Aspose.Tasks 中設定新任務的屬性
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 設定新任務的 MS Project 屬性。透過這份綜合指南輕鬆自訂任務屬性。
type: docs
weight: 21
url: /zh-hant/java/project-file-operations/set-attributes-new-tasks/
---
## 介紹
歡迎來到我們關於在 Aspose.Tasks for Java 中為新任務設定 MS Project 屬性的綜合教學！在本指南中，我們將逐步引導您完成整個過程，確保您可以使用這個強大的 Java 程式庫輕鬆管理和自訂您的任務。
## 先決條件
在我們深入學習本教程之前，請確保您具備以下先決條件：
1. Java 開發環境：確保您的系統上安裝了 Java，並且熟悉基本的 Java 程式設計概念。
2.  Aspose.Tasks for Java 函式庫：從下列位置下載並安裝 Aspose.Tasks for Java 函式庫：[下載連結](https://releases.aspose.com/tasks/java/).
3. Java IDE：選擇 Java 整合開發環境 (IDE)，例如 Eclipse 或 IntelliJ IDEA 進行程式設計。

## 導入包
在開始為新任務設定 MS Project 屬性之前，讓我們先匯入必要的套件：
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.TaskStartDateType;
```

## 第 1 步：定義資料目錄
首先，指定要儲存專案文件的目錄路徑：
```java
String dataDir = "Your Data Directory";
```
代替`"Your Data Directory"`以及您所需目錄的路徑。
## 步驟2：建立專案實例
實例化一個新的 Project 物件以開始使用您的專案：
```java
Project prj = new Project();
```
這將建立一個新的專案實例。
## 步驟 3：設定新任務屬性
現在，讓我們設定新任務的開始日期。在此範例中，我們將其設定為當前日期：
```java
prj.set(Prj.NEW_TASK_START_DATE, TaskStartDateType.CurrentDate);
```
該行設定屬性`NEW_TASK_START_DATE`到`TaskStartDateType.CurrentDate`.
## 第 4 步：儲存項目
使用 XML 格式的新任務屬性儲存項目：
```java
prj.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```
此行使用指定的檔案名稱將項目保存在先前定義的目錄中。
## 第5步：顯示結果
最後，我們列印一條訊息來確認專案文件已成功產生：
```java
System.out.println("Project file generated Successfully");
```
此行在控制台中顯示成功訊息。

## 結論
恭喜！您已經成功學習如何使用 Aspose.Tasks for Java 設定新任務的 MS Project 屬性。有了這些知識，您現在可以根據您的要求自訂任務屬性，從而增強您的專案管理能力。
## 常見問題解答
### Q：我可以使用 Aspose.Tasks for Java 來操作現有的專案檔嗎？
答：是的，Aspose.Tasks for Java 提供了廣泛的功能來操作現有專案文件，包括讀取、修改和以各種格式保存它們。
### Q：在哪裡可以找到更多有關 Aspose.Tasks for Java 的文件和資源？
答：您可以瀏覽以下文件和資源：[Aspose.Tasks for Java 文件頁面](https://reference.aspose.com/tasks/java/).
### Q：Aspose.Tasks for Java 是否有免費試用版？
答：是的，您可以從以下位置下載 Aspose.Tasks for Java 的免費試用版：[這裡](https://releases.aspose.com/).
### Q：如何取得 Aspose.Tasks for Java 的臨時授權？
答：Aspose.Tasks for Java 的臨時許可證可以從[臨時許可證頁面](https://purchase.aspose.com/temporary-license/).
### Q：對於與 Aspose.Tasks for Java 相關的任何問題或查詢，我可以在哪裡獲得支援？
答：您可以透過以下方式獲得支持並與社區互動：[Aspose.Tasks for Java 支援論壇](https://forum.aspose.com/c/tasks/15).