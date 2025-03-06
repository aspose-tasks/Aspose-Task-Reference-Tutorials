---
title: 在 Aspose.Tasks 中高效能管理 MS 專案屬性
linktitle: 管理 Aspose.Tasks 中的預設項目屬性
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 管理預設的 MS Project 屬性。輕鬆簡化您的專案管理工作流程。
type: docs
weight: 11
url: /zh-hant/java/project-management/default-properties/
---
## 介紹
您是否希望使用 Aspose.Tasks for Java 簡化您的專案管理流程？管理 Microsoft Project 檔案中的預設屬性可以顯著提高效率。在本教學中，我們將逐步說明如何使用 Aspose.Tasks 管理預設的 MS Project 屬性。
## 先決條件
在我們深入研究本教程之前，請確保您具備以下先決條件：
### 1.Java開發工具包（JDK）
   - 確保您的系統上安裝了 JDK。
   - 您可以從以下位置下載：[這裡](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
### 2. Java 庫的 Aspose.Tasks
   - 下載 Aspose.Tasks for Java 程式庫並將其包含在您的專案中。
   - 您可以從[網站](https://releases.aspose.com/tasks/java/).
## 導入包
首先，在 Java 檔案中匯入必要的套件：
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```
讓我們將這個過程分解為可管理的步驟：
## 第 1 步：載入專案文件
```java
//文檔目錄的路徑。
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
## 第 2 步：顯示預設屬性
```java
//顯示預設屬性
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("New Task Default Start: " + project.get(Prj.DEFAULT_START_TIME));
System.out.println("New Task Default Type: " + project.get(Prj.DEFAULT_TASK_TYPE));
System.out.println("Resource Default Standard Rate: " + project.get(Prj.DEFAULT_STANDARD_RATE));
System.out.println("Resource Default Overtime Rate: " + project.get(Prj.DEFAULT_OVERTIME_RATE));
System.out.println("Default Task EV Method: " + project.get(Prj.DEFAULT_TASK_EV_METHOD));
System.out.println("Default Cost Accrual: " + project.get(Prj.DEFAULT_FIXED_COST_ACCRUAL));
```
## 步驟 3：設定預設屬性
```java
//設定預設屬性
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 0, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.DEFAULT_START_TIME, project.get(Prj.START_DATE));
project.set(Prj.DEFAULT_TASK_TYPE, TaskType.FixedDuration);
project.set(Prj.DEFAULT_STANDARD_RATE, 15d);
project.set(Prj.DEFAULT_OVERTIME_RATE, 12d);
project.set(Prj.DEFAULT_TASK_EV_METHOD, EarnedValueMethodType.PercentComplete);
project.set(Prj.DEFAULT_FIXED_COST_ACCRUAL, CostAccrualType.Prorated);
```
## 第 4 步：將項目儲存為 XML 格式
```java
//將項目儲存為 XML 格式
project.save(dataDir + "project4.xml", SaveFileFormat.Xml);
```
## 第5步：顯示結果
```java
//顯示轉換結果。
System.out.println("Process completed Successfully");
```
透過執行這些步驟，您可以使用 Aspose.Tasks for Java 有效管理預設的 MS Project 屬性。
## 結論
在本教程中，我們學習如何使用 Aspose.Tasks for Java 管理預設的 MS Project 屬性。透過利用這些技術，您可以優化專案管理工作流程，提高生產力和組織能力。
## 常見問題解答
### Q1：我可以將 Aspose.Tasks 與其他程式語言一起使用嗎？
A1：是的，Aspose.Tasks 支援各種程式語言，例如.NET、Python 和 Java。
### Q2：Aspose.Tasks 適合個人和企業使用嗎？
A2：當然！無論您是管理小型個人專案還是大型企業計劃，Aspose.Tasks 都能滿足您的需求。
### Q3：Aspose.Tasks 提供客戶支援嗎？
A3：是的，您可以在[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15).
### Q4：我可以在購買前試用 Aspose.Tasks 嗎？
 A4：當然！您可以從以下網站獲得免費試用[網站](https://releases.aspose.com/).
### Q5：如何取得Aspose.Tasks的臨時授權？
 A5：您可以從以下機構獲得臨時許可證：[購買頁面](https://purchase.aspose.com/temporary-license/)用於測試和評估目的。