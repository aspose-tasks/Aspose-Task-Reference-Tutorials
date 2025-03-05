---
title: 在 Aspose.Tasks 中另存為 CSV、文字和模板
linktitle: 在 Aspose.Tasks 中另存為 CSV、文字和模板
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 將 Microsoft Project 檔案儲存為 CSV、文字和範本格式。
type: docs
weight: 16
url: /zh-hant/java/project-file-operations/save-csv-text-template/
---
## 介紹
在本教程中，我們將探索如何使用 Aspose.Tasks for Java 以各種格式（例如 CSV、文字和範本）儲存專案檔。 Aspose.Tasks 是一個功能強大的 Java 程式庫，可讓開發人員使用 Microsoft Project 文件，而無需安裝 Microsoft Project。
## 先決條件
在我們開始之前，請確保您具備以下先決條件：
1. 您的系統上安裝了 Java 開發工具包 (JDK)。
2.  Aspose.Tasks for Java 函式庫已下載並在您的 Java 專案中配置。您可以從以下位置下載：[這裡](https://releases.aspose.com/tasks/java/).
3. Java 程式語言的基礎知識。

## 導入包
首先，您需要在 Java 檔案中匯入必要的套件：
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
## 將項目另存為 CSV
讓我們分解一下將項目另存為 CSV 的步驟：
### 第 1 步：載入項目
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### 第 2 步：另存為 CSV
```java
String csvFileName = "output.csv";
project.save(csvFileName, com.aspose.tasks.SaveFileFormat.CSV);
```
## 將項目另存為文字
以下是將項目另存為文字的方法：
### 第 1 步：載入項目
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### 第 2 步：另存為文本
```java
String textFileName = "output.txt";
project.save(textFileName, com.aspose.tasks.SaveFileFormat.TEXT);
```
## 將項目另存為模板
將項目儲存為範本涉及以下步驟：
### 第 1 步：載入項目
```java
String projectName = "YourProject.mpp";
Project project = new Project(projectName);
```
### 第 2 步：設定範本選項
```java
SaveTemplateOptions options = new SaveTemplateOptions();
options.setRemoveActualValues(true);
options.setRemoveBaselineValues(true);
```
### 第 3 步：另存為模板
```java
String templateName = "output.mpt";
project.saveAsTemplate(templateName, options);
```

## 結論
在本教程中，我們學習如何使用 Aspose.Tasks for Java 將 Microsoft Project 檔案儲存為 CSV、文字和範本。透過這些簡單的步驟，您可以有效地管理各種格式的專案文件，從而提高 Java 開發人員的工作效率。
## 常見問題解答
### Q：Aspose.Tasks for Java 可以處理複雜的專案檔嗎？
答：當然！ Aspose.Tasks for Java 可以輕鬆處理不同複雜程度的項目，為 Microsoft Project 檔案格式提供全面支援。
### Q：Aspose.Tasks for Java 有試用版嗎？
答：是的，您可以從以下位置獲得 Aspose.Tasks for Java 的免費試用版：[這裡](https://releases.aspose.com/).
### Q：在哪裡可以找到 Aspose.Tasks for Java 的支援？
答：您可以訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)有關 Aspose.Tasks for Java 的任何協助或問題。
### Q：我可以購買 Aspose.Tasks for Java 的臨時授權嗎？
答：是的，您可以從以下位置購買臨時許可證：[這裡](https://purchase.aspose.com/temporary-license/)，讓您能夠評估圖書館的全部潛力。
### Q：Aspose.Tasks for Java 是否相容於不同的作業系統？
答：是的，Aspose.Tasks for Java 與各種作業系統相容，包括 Windows、macOS 和 Linux。