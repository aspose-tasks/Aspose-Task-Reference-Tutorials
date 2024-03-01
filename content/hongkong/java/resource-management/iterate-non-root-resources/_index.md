---
title: 在 Aspose.Tasks 中迭代非根資源
linktitle: 在 Aspose.Tasks 中迭代非根資源
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 有效地迭代 Microsoft Project 檔案中的非根資源。增強您的開發流程。
type: docs
weight: 12
url: /zh-hant/java/resource-management/iterate-non-root-resources/
---
## 介紹
Aspose.Tasks for Java 是一個功能強大的函式庫，為開發人員提供了高效能操作 Microsoft Project 檔案所需的工具。憑藉其直覺的介面和廣泛的功能，Aspose.Tasks 簡化了處理專案資料的過程，使開發人員能夠專注於建立強大的應用程式。
## 先決條件
在深入使用 Aspose.Tasks for Java 之前，請確保您具備以下條件：
1.  Java 開發工具包 (JDK)：確保您的系統上安裝了 JDK。您可以從[甲骨文網站](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Tasks for Java Library：從下列位置下載並安裝 Aspose.Tasks for Java 函式庫[下載頁面](https://releases.aspose.com/tasks/java/).

## 導入包
在您的 Java 專案中，匯入必要的套件以開始使用 Aspose.Tasks：
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## 第 1 步：設定資料目錄
```java
String dataDir = "Your Data Directory";
```
代替`"Your Data Directory"`以及儲存項目文件的目錄的路徑。
## 第 2 步：載入專案文件
```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```
該行初始化一個新的`Project`物件透過載入名為的項目文件`"ResourceCosts.mpp"`從指定的資料目錄。
## 第 3 步：迭代非根資源
```java
for (Resource res : prj.getResources()) {
    if (res.isRoot()) {
        continue;
    }
    System.out.println(res.get(Rsc.NAME));
}
```
此循環迭代專案中的每個資源 (`prj.getResources()`）。如果該資源是根資源，則跳到下一次迭代。否則，它會列印非根資源的名稱。

## 結論
在本教程中，我們探索如何使用 Aspose.Tasks for Java 迭代非根資源。透過執行這些步驟，您可以有效地操作專案資料並簡化您的開發流程。
## 常見問題解答
### 我可以使用 Aspose.Tasks for Java 建立新的專案檔嗎？
是的，Aspose.Tasks 提供了建立、修改和保存各種格式的專案檔案的功能。
### Aspose.Tasks 支援所有版本的 Microsoft Project 檔案嗎？
Aspose.Tasks 支援 Microsoft Project 2003-2019 檔案格式，包括 MPP、MPT 和 XML。
### Aspose.Tasks 與 Spring 等 Java 框架相容嗎？
是的，Aspose.Tasks 可以無縫整合到 Spring 等 Java 框架中，用於企業級應用程式。
### 我可以使用 Aspose.Tasks 自訂項目資料欄位嗎？
當然，Aspose.Tasks 提供了廣泛的 API，用於根據您的要求自訂項目資料欄位。
### Aspose.Tasks 是否為開發人員提供支援和文件？
是的，Aspose.Tasks 提供全面的文件和專門的支援論壇，以協助開發人員解決遇到的任何疑問或問題。