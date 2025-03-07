---
title: 在 Aspose.Tasks 中監控加班、剩餘成本和工作
linktitle: 在 Aspose.Tasks 中監控加班、剩餘成本和工作
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks 監控加班、剩餘成本以及 Java 專案中的工作。有效專案管理的簡單步驟。
weight: 18
url: /zh-hant/java/resource-assignments/overtime-remaining-costs-work/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中監控加班、剩餘成本和工作

## 介紹
在本教程中，我們將學習如何使用 Aspose.Tasks for Java 來監控專案中的加班、剩餘成本和工作。這對於專案經理和團隊領導來說非常寶貴，可以確保專案按計劃進行並在預算之內。
## 先決條件
在我們開始之前，請確保您具備以下條件：
1. Java 開發工具包 (JDK)：Aspose.Tasks for Java 需要 Java SE 6 或更高版本。
2.  Aspose.Tasks for Java Library：從以下位置下載並安裝該程式庫[這裡](https://releases.aspose.com/tasks/java/).
3. 整合開發環境 (IDE)：任何 Java IDE，例如 Eclipse、IntelliJ IDEA 或 NetBeans。

## 導入包
首先在 Java 檔案中匯入必要的套件：
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
```

## 第 1 步：設定資料目錄
定義專案文件所在的目錄：
```java
String dataDir = "Your Data Directory";
```
代替`"Your Data Directory"`與您的專案文件的路徑。
## 第 2 步：載入項目
實例化一個`Project`物件並載入專案文件：
```java
Project project = new Project(dataDir + "ResourceAssignmentOvertimes.mpp");
```
代替`"ResourceAssignmentOvertimes.mpp"`與您的專案文件的名稱。
## 第 3 步：迭代資源分配
循環遍歷專案中的每個資源分配：
```java
for (ResourceAssignment ra : project.getResourceAssignments()) {
```
## 步驟 4： 列印加班費用和工時
檢索並列印每個資源分配的加班成本和工時：
```java
    System.out.println(ra.get(Asn.OVERTIME_COST));
    System.out.println(ra.get(Asn.OVERTIME_WORK).toString());
```
## 第 5 步：列印剩餘成本和工作
檢索並列印每個資源分配的剩餘成本和工時：
```java
    System.out.println(ra.get(Asn.REMAINING_COST));
    System.out.println(ra.get(Asn.REMAINING_WORK).toString());
```
## 步驟 6：列印剩餘加班成本和工時
檢索並列印每個資源分配的剩餘加班成本和工時：
```java
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_COST));
    System.out.println(ra.get(Asn.REMAINING_OVERTIME_WORK).toString());
}
```

## 結論
監控專案中的加班時間、剩餘成本和工作量對於成功的專案管理至關重要。借助 Aspose.Tasks for Java，您可以輕鬆存取和追蹤這些信息，確保您的專案按計劃進行並在預算之內。
## 常見問題解答
### 我可以將 Aspose.Tasks for Java 與其他 Java 函式庫一起使用嗎？
是的，Aspose.Tasks for Java 與其他 Java 函式庫和框架相容。
### Aspose.Tasks 支援不同的專案文件格式嗎？
是的，Aspose.Tasks 支援各種專案文件格式，包括 MPP、XML 等。
### 有試用版嗎？
是的，您可以從以下位置下載免費試用版[這裡](https://releases.aspose.com/).
### 如果遇到問題，我可以在哪裡找到支援？
您可以造訪 Aspose.Tasks 論壇[這裡](https://forum.aspose.com/c/tasks/15)為了支持。
### 如何購買 Aspose.Tasks 的許可證？
您可以從以下位置購買許可證[這裡](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
