---
title: 在 Aspose.Tasks 中計算關鍵 MS 專案路徑
linktitle: 計算 Aspose.Tasks 專案中的關鍵路徑
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 計算 MS Project 中的關鍵路徑。這為高效的專案管理提供了逐步指導。
type: docs
weight: 10
url: /zh-hant/java/project-management/critical-path/
---
## 介紹
在本教程中，我們將引導您完成使用 Aspose.Tasks for Java 在 MS Project 中計算關鍵路徑的過程。關鍵路徑對於專案管理至關重要，因為它有助於確定必須按時完成的任務順序，以確保專案的整體進度不會延遲。
## 先決條件
在我們開始之前，請確保您符合以下先決條件：
1. 您的系統上安裝了 Java 開發工具包 (JDK)。
2.  Aspose.Tasks for Java 程式庫下載並新增到您的專案中。您可以從以下位置下載：[這裡](https://releases.aspose.com/tasks/java/).

## 導入包
首先，在 Java 類別中導入必要的套件：
```java
import com.aspose.tasks.*;
```
## 第1步：設定資料目錄
定義 MS Project 檔案所在的資料目錄的路徑。
```java
String dataDir = "Your Data Directory";
```
## 第 2 步：載入 MS 專案文件
使用 Aspose.Tasks 庫載入 MS Project 檔案。
```java
Project project = new Project(dataDir + "New project 2013.mpp");
```
## 第三步：設定計算模式
將計算模式設定為自動以啟用關鍵路徑的計算。
```java
project.setCalculationMode(CalculationMode.Automatic);
```
## 第 4 步：新增任務
將任務新增到您的專案中。在此範例中，我們新增三個子任務。
```java
Task subtask1 = project.getRootTask().getChildren().add("1");
Task subtask2 = project.getRootTask().getChildren().add("2");
Task subtask3 = project.getRootTask().getChildren().add("3");
```
## 第 5 步：建立任務鏈接
建立任務連結以定義任務之間的依賴關係。
```java
project.getTaskLinks().add(subtask1, subtask2, TaskLinkType.FinishToStart);
```
## 步驟6：顯示關鍵路徑
檢索並顯示專案的關鍵路徑。
```java
for (Task task : project.getCriticalPath()) {
    System.out.println(task.get(Tsk.NAME));
}
```
## 第7步：顯示結果
顯示一條訊息，指示該過程已成功完成。
```java
System.out.println("Process completed Successfully");
```

## 結論
使用 Aspose.Tasks for Java 計算 MS Project 中的關鍵路徑對於有效的專案管理至關重要。透過遵循本教程中概述的步驟，您可以準確地確定對專案時間軸至關重要的任務順序。
## 常見問題解答
### Q：我可以將 Aspose.Tasks for Java 與任何版本的 MS Project 檔案一起使用嗎？
答：是的，Aspose.Tasks for Java 支援各種版本的 MS Project 文件，包括從 MS Project 2003 到 MS Project 2019 的 .mpp 檔案。
### Q：Aspose.Tasks for Java 是否有免費試用版？
答：是的，您可以從以下位置下載免費試用版：[這裡](https://releases.aspose.com/).
### Q：在哪裡可以找到 Aspose.Tasks for Java 的支援？
答：您可以在[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15).
### Q：我可以購買 Aspose.Tasks for Java 的臨時授權嗎？
答：是的，您可以從以下位置購買臨時許可證：[這裡](https://purchase.aspose.com/temporary-license/).
### Q：如何購買 Aspose.Tasks for Java？
 A：您可以從網站購買Aspose.Tasks for Java[這裡](https://purchase.aspose.com/buy).