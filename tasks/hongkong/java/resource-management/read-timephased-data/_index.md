---
title: 讀取 Aspose.Tasks 中資源的時間分段數據
linktitle: 讀取 Aspose.Tasks 中資源的時間分段數據
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 從 MS Project 資源中提取時間分段資料。分步教程。
weight: 15
url: /zh-hant/java/resource-management/read-timephased-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 讀取 Aspose.Tasks 中資源的時間分段數據

## 介紹
在本教程中，我們將引導您完成使用 Aspose.Tasks for Java 讀取 MS Project 資源的時間分段資料的過程。該程式庫提供了以程式設計方式管理 Microsoft Project 檔案的強大功能。
## 先決條件
在我們開始之前，請確保您符合以下先決條件：
1.  Java 開發工具包 (JDK)：確保您的系統上安裝了 JDK。您可以從[網站](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html)並按照安裝說明進行操作。
2.  Aspose.Tasks for Java 函式庫：從下列位置下載 Aspose.Tasks for Java 函式庫：[下載頁面](https://releases.aspose.com/tasks/java/)並按照文件中提供的安裝說明進行操作。

## 導入包
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
```
## 第 1 步：設定資料目錄
首先，定義 MS Project 檔案所在的目錄。
```java
String dataDir = "Your Data Directory";
```
## 第 2 步：讀取 MS 專案範本文件
指定 MS Project 範本檔案的名稱。
```java
String fileName = "ResourceTimephasedData.mpp";
```
## 第 3 步：將輸入檔讀取為項目
使用 Aspose.Tasks 讀取輸入檔案並將其載入為 Project 物件。
```java
Project project = new Project(dataDir + fileName);
```
## 第四步：透過ID獲取資源
透過其唯一識別碼 (ID) 從專案中檢索所需的資源。
```java
Resource resource = project.getResources().getByUid(1);
```
## 步驟 5：列印資源工作的時間分段數據
列印資源工作的時間分段資料。
```java
System.out.println("Timephased data of ResourceWork");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE))) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Work: " + td.getValue());
}
```
## 步驟 6：列印資源成本的時間分段數據
列印資源成本的時間分段資料。
```java
System.out.println("Timephased data of ResourceCost");
for (TimephasedData td : resource.getTimephasedData(project.get(Prj.START_DATE), project.get(Prj.FINISH_DATE), TimephasedDataType.ResourceCost)) {
    System.out.println("Start: " + td.getStart().toString());
    System.out.println(" Cost: " + td.getValue());
}
```

## 結論
在本教程中，我們學習如何使用 Aspose.Tasks for Java 讀取 MS Project 資源的時間分段資料。透過執行這些步驟，您可以以程式設計方式有效地從專案文件中提取有價值的資訊。
## 常見問題解答
### Aspose.Tasks 可以處理 Microsoft Project 以外的其他類型的專案文件嗎？
是的，Aspose.Tasks 支援各種檔案格式，包括 MPP、XML 和 CSV。
### Aspose.Tasks是否相容於不同的Java開發環境？
是的，Aspose.Tasks 與所有主要的 Java IDE 和框架相容。
### 我可以使用 Aspose.Tasks 操作項目資料嗎？
當然，Aspose.Tasks 提供了廣泛的 API 用於建立、修改和分析專案資料。
### Aspose.Tasks適合企業級專案嗎？
是的，Aspose.Tasks 由於其可靠性和可擴展性而廣泛應用於企業環境。
### 如果在使用 Aspose.Tasks 時遇到問題，我可以在哪裡找到支援？
您可以訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)尋求社區和支持團隊的幫助。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
