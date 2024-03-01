---
title: 使用 Aspose.Tasks 檢索日曆異常
linktitle: 使用 Aspose.Tasks 檢索日曆異常
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 從 MS Project 擷取日曆異常。無縫整合的分步教程。
type: docs
weight: 13
url: /zh-hant/java/calendar-exceptions/retrieve/
---
## 介紹
在本教程中，我們將探討如何使用 Java 的 Aspose.Tasks 函式庫從 MS Project 擷取日曆異常。 Aspose.Tasks 是一個功能強大的工具，可讓開發人員以程式設計方式操作 Microsoft Project 檔案。我們將逐步引導您完成整個過程，將每個範例分解為多個步驟以便於理解。
## 先決條件
在我們開始之前，請確保您具備以下先決條件：
1. Java 開發工具包 (JDK)：確保您的系統上安裝了 JDK。
2.  Aspose.Tasks for Java：從下列位置下載並安裝 Aspose.Tasks for Java：[這裡](https://releases.aspose.com/tasks/java/).
3. 整合開發環境 (IDE)：您可以使用您選擇的任何 IDE，例如 IntelliJ IDEA 或 Eclipse。

## 導入包
首先，您需要匯入必要的套件來使用 Aspose.Tasks：
```java
import com.aspose.tasks.*;
```
## 第 1 步：設定您的資料目錄
```java
//文檔目錄的路徑。
String dataDir = "Your Data Directory";
```
確保更換`"Your Data Directory"`包含 MS Project 檔案的目錄路徑。
## 第 2 步：載入 MS 專案文件
```java
Project project = new Project(dataDir + "project.mpp");
```
該行初始化一個新的`Project`透過載入路徑指定的 MS Project 檔案來實現物件。
## 第 3 步：檢索日曆異常
```java
for (Calendar cal : project.getCalendars()) {
    for (CalendarException calExc : cal.getExceptions()) {
        System.out.println("From: " + calExc.getFromDate().toString());
        System.out.println("To: " + calExc.getToDate().toString());
    }
}
```
在這裡，我們遍歷項目中的每個日曆，然後遍歷該日曆中的每個日曆異常。我們列印出每個異常的開始和結束日期。

## 結論
在本教程中，我們學習如何使用 Aspose.Tasks for Java 從 MS Project 檢索日曆異常。透過遵循這些簡單的步驟，您可以將此功能無縫整合到您的 Java 應用程式中。
## 經常問的問題
### Aspose.Tasks 可以處理不同版本的 MS Project 檔案嗎？
是的，Aspose.Tasks 支援各種版本的 MS Project 文件，包括 MPP、MPT 和 XML 格式。
### Aspose.Tasks 是否有免費試用版？
是的，您可以從以下位置下載 Aspose.Tasks 的免費試用版：[這裡](https://releases.aspose.com/).
### 在哪裡可以找到 Aspose.Tasks for Java 的文檔？
你可以參考文檔[這裡](https://reference.aspose.com/tasks/java/).
### 我如何獲得 Aspose.Tasks 的支援？
您可以從社區論壇獲得支持[這裡](https://forum.aspose.com/c/tasks/15).
### 是否有 Aspose.Tasks 臨時許可證的選項？
是的，您可以從以下位置取得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).