---
title: 使用 Aspose.Tasks 計算 MS 專案資源百分比
linktitle: 在 Aspose.Tasks 中執行資源百分比計算
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 計算 MS Project 資源百分比。包含程式碼範例的分步指南。
weight: 14
url: /zh-hant/java/resource-management/percentage-calculations/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 計算 MS 專案資源百分比

## 介紹
歡迎使用我們的逐步指南，了解如何使用 Aspose.Tasks for Java 對 MS Project 資源執行百分比計算。在本教程中，我們將深入研究利用 Aspose.Tasks 從 Microsoft Project 檔案中高效操作和提取資源資料的過程。 Aspose.Tasks 是一個強大的 Java API，提供了處理 Microsoft Project 文件的全面功能，讓開發人員將專案管理功能無縫整合到他們的 Java 應用程式中。
## 先決條件
在深入學習本教學之前，請確保您已設定以下先決條件：
### Java開發環境
確保您的系統上安裝了 Java 開發工具包 (JDK)。您可以從以下位置下載並安裝 JDK[這裡](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
### Aspose.Tasks函式庫
您需要將 Aspose.Tasks 庫整合到您的 Java 專案中。如果您還沒有這樣做，您可以從以下位置下載該庫[這裡](https://releases.aspose.com/tasks/java/)並按照文件中提供的安裝說明進行操作[這裡](https://reference.aspose.com/tasks/java/).

## 導入包
在開始編碼之前，讓我們先匯入本教學所需的必要套件：
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```
## 第1步：設定專案文件路徑
```java
String dataDir = "Your Data Directory";
```
代替`"Your Data Directory"`以及 Microsoft Project 檔案的路徑。
## 第 2 步：載入項目
```java
Project prj = new Project(dataDir + "Software Development.mpp");
```
此程式碼載入位於指定資料目錄中名為「Software Development.mpp」的 Microsoft Project 檔案。
## 第 3 步：迭代資源
```java
for (Resource res : prj.getResources()) {
```
我們循環訪問專案中的每個資源。
## 步驟 4：檢查資源名稱和工作完成百分比
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.PERCENT_WORK_COMPLETE));
}
```
我們檢查資源名稱是否不為空，然後列印每個資源完成的工作百分比。

## 結論
在本教程中，我們學習如何利用 Aspose.Tasks for Java 有效地執行 MS Project 資源的百分比計算。透過執行這些步驟，您可以將專案管理功能無縫整合到 Java 應用程式中，從而增強對專案資源利用率的控制和洞察。
## 常見問題解答
### 我可以將 Aspose.Tasks for Java 與其他 Java 框架一起使用嗎？
是的，Aspose.Tasks for Java 與各種 Java 框架相容，例如 Spring、Hibernate 等。
### Aspose.Tasks 支援所有版本的 Microsoft Project 檔案嗎？
Aspose.Tasks 提供對所有版本的 Microsoft Project 檔案的支持，包括 MPP、MPT、XML 等。
### 我可以使用 Aspose.Tasks 操縱專案進度嗎？
當然，Aspose.Tasks 提供了操作專案進度的全面功能，包括任務、資源、日曆等。
### 是否有 Aspose.Tasks 支援的社群論壇？
是的，您可以在 Aspose.Tasks 社群論壇上尋求協助並與其他使用者互動[這裡](https://forum.aspose.com/c/tasks/15).
### Aspose.Tasks 是否提供用於評估目的的臨時許可證？
是的，您可以從以下位置取得臨時評估許可證[這裡](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
