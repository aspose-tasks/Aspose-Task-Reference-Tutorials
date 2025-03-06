---
title: 在 Aspose.Tasks 中將 MS Project 資料儲存到 Excel
linktitle: 在 Aspose.Tasks 中將資料儲存到 Excel
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 將 Microsoft Project 資料儲存到 Excel 檔案。 Java 開發人員可以輕鬆整合。
weight: 19
url: /zh-hant/java/project-file-operations/save-data-to-excel/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中將 MS Project 資料儲存到 Excel

## 介紹
Aspose.Tasks for Java 是一個功能強大的函式庫，可讓開發人員以程式設計方式處理 Microsoft Project 檔案。在本教學中，我們將逐步引導您完成將資料從專案文件儲存到 Excel 檔案的過程。
## 先決條件
在我們開始之前，請確保您具備以下先決條件：
1. Java 開發工具包 (JDK)：確保您的系統上安裝了 Java。您可以從 Oracle 網站下載並安裝最新版本的 JDK。
2.  Aspose.Tasks for Java 函式庫：從下列位置下載 Aspose.Tasks for Java 函式庫：[下載連結](https://releases.aspose.com/tasks/java/)並將其包含在您的 Java 專案中。

## 導入包
首先，您需要在 Java 程式碼中匯入必要的套件才能使用 Aspose.Tasks。
```java
import java.io.IOException;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

讓我們將提供的範例分解為多個步驟：
## 第 1 步：定義資料目錄路徑
```java
String dataDir = "Your Data Directory";
```
代替`"Your Data Directory"`以及專案文件所在的資料目錄的路徑。
## 第 2 步：載入專案文件
```java
Project project = new Project(dataDir + "project5.mpp");
```
此行程式碼從指定的資料目錄載入名為「project5.mpp」的專案檔案。
## 步驟 3：將項目另存為 XLSX
```java
project.save(dataDir + "project1.xlsx", SaveFileFormat.Xlsx);
```
在這裡，`save`方法用於將載入的專案文件儲存為 Excel 文件，名稱為“project1.xlsx”，位於同一資料目錄中。我們指定`SaveFileFormat.Xlsx`參數將其儲存為 XLSX 格式。

## 結論
在本教程中，我們學習如何使用 Aspose.Tasks for Java 將資料從 Microsoft Project 檔案儲存到 Excel 檔案。透過遵循提供的步驟，您可以將此功能無縫整合到您的 Java 應用程式中。
## 常見問題解答
### 我可以使用 Aspose.Tasks for Java 以程式設計方式操作專案資料嗎？
是的，Aspose.Tasks for Java 提供了廣泛的功能來操作專案數據，包括讀取、寫入和修改專案檔。
### Aspose.Tasks for Java 是否有免費試用版？
是的，您可以從以下位置下載 Aspose.Tasks for Java 的免費試用版：[這裡](https://releases.aspose.com/).
### 在哪裡可以找到 Aspose.Tasks for Java 的文檔？
您可以找到 Aspose.Tasks for Java 的文檔[這裡](https://reference.aspose.com/tasks/java/).
### 如何獲得與 Aspose.Tasks for Java 相關的任何問題或查詢的支援？
您可以透過造訪 Aspose.Tasks 論壇獲得支持[這裡](https://forum.aspose.com/c/tasks/15).
### 我可以購買 Aspose.Tasks for Java 的臨時授權嗎？
是的，您可以從以下位置購買臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
