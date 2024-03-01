---
title: Aspose.Tasks 中的工作日屬性
linktitle: Aspose.Tasks 中的工作日屬性
second_title: Aspose.Tasks Java API
description: 了解在 Aspose.Tasks for Java 中有效管理工作日屬性。輕鬆自訂週開始日期、每月天數等。
type: docs
weight: 25
url: /zh-hant/java/project-file-operations/weekday-properties/
---
## 介紹
Aspose.Tasks for Java 是一個功能強大的 API，讓 Java 開發人員無需在電腦上安裝 Microsoft Project 即可使用 Microsoft Project 檔案。其關鍵功能之一是管理工作日屬性，允許用戶自訂週開始日期、每月天數、每天分鐘數和每週分鐘數。本教學將提供如何有效利用這些功能的詳細指南。
## 先決條件
在深入研究 Aspose.Tasks for Java 之前，請確保您具備以下先決條件：
### Java 開發工具包 (JDK)
確保您的系統上安裝了 JDK。您可以從 Oracle 網站下載並安裝最新的 JDK。
### Java 函式庫的 Aspose.Tasks
從網站下載並安裝 Aspose.Tasks for Java 函式庫。您可以訪問下載鏈接[這裡](https://releases.aspose.com/tasks/java/).
### 整合開發環境（IDE）
選擇您喜歡的 Java 開發 IDE。流行的選擇包括 IntelliJ IDEA、Eclipse 或 NetBeans。
## 導入包
首先，將必要的 Aspose.Tasks 套件匯入到您的 Java 專案中。就是這樣：

```java
import com.aspose.tasks.DayType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

現在，讓我們將提供的範例分解為多個步驟，以便更好地理解。
## 第 1 步：載入專案文件
```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
此步驟涉及從指定的資料目錄載入名為「project.mpp」的專案檔案。
## 第 2 步：顯示工作日屬性
```java
System.out.println("Week Start Date : " + project.get(Prj.WEEK_START_DAY).toString());
System.out.println("Days Per Month : " + project.get(Prj.DAYS_PER_MONTH).toString());
System.out.println("Minutes Per Day : " + project.get(Prj.MINUTES_PER_DAY).toString());
System.out.println("Minutes Per Week : " + project.get(Prj.MINUTES_PER_WEEK).toString());
```
在這裡，我們檢索並列印載入項目的周開始日期、每月天數、每天分鐘數和每週分鐘數屬性。
## 步驟 3：設定工作日屬性
```java
Project prj = new Project();
project.set(Prj.WEEK_START_DAY, DayType.Monday);
project.set(Prj.DAYS_PER_MONTH, 24);
project.set(Prj.MINUTES_PER_DAY, 540);
project.set(Prj.MINUTES_PER_WEEK, 3240);
```
此步驟涉及建立新的專案實例並設定自訂工作日屬性，例如一周開始日、每月天數、每天分鐘數和每週分鐘數。
## 第 4 步：儲存項目
```java
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
最後，我們將修改後的項目與更新的工作日屬性儲存為 XML 檔案。
## 第5步：顯示結果
```java
System.out.println("Process completed Successfully");
```
此步驟確認流程已成功完成。
## 結論
掌握 Aspose.Tasks for Java 中的工作日屬性對於有效的專案管理至關重要。透過學習本教程，您已經學會如何輕鬆操作和自訂工作日屬性。探索更多文件和範例以增強您的專案管理能力。
## 常見問題解答
### Q：Aspose.Tasks for Java 可以處理複雜的專案結構嗎？
答：是的，Aspose.Tasks for Java 為輕鬆處理複雜的專案結構提供了全面的支援。
### Q：Aspose.Tasks for Java 是否與不同版本的 Microsoft Project 檔案相容？
答：當然，Aspose.Tasks for Java 支援各種版本的 Microsoft Project 文件，確保跨平台的兼容性。
### Q：我可以將 Aspose.Tasks for Java 整合到我現有的 Java 應用程式中嗎？
答：是的，Aspose.Tasks for Java 提供無縫整合功能，讓您透過強大的專案管理功能增強 Java 應用程式。
### Q：Aspose.Tasks for Java 是否提供文件和支援？
答：是的，您可以在其網站上存取 Aspose.Tasks for Java 的廣泛文件和社群支援。[網站](https://releases.aspose.com/).
### Q：Aspose.Tasks for Java 是否有免費試用版？
答：是的，您可以從他們的網站下載 Aspose.Tasks for Java 的免費試用版[網站](https://reference.aspose.com/tasks/java/)在購買之前探索其功能。