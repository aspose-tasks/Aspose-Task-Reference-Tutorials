---
title: 停止並恢復 Aspose.Tasks 中的資源分配
linktitle: 停止並恢復 Aspose.Tasks 中的資源分配
second_title: Aspose.Tasks Java API
description: 透過此逐步教學，了解如何在 Aspose.Tasks for Java 中有效管理資源分配。
weight: 23
url: /zh-hant/java/resource-assignments/stop-resume-assignment/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 停止並恢復 Aspose.Tasks 中的資源分配

## 介紹
在本教程中，我們將學習如何使用 Aspose.Tasks for Java 停止和恢復資源分配。 Aspose.Tasks 是一個功能強大的 Java API，允許開發人員使用 Microsoft Project 文件，而無需在其係統上安裝 Microsoft Project。我們將把這個過程分解為可管理的步驟，以便於遵循。
## 先決條件
在我們開始之前，請確保您符合以下先決條件：
- 您的系統上安裝了 Java 開發工具包 (JDK)。
- 下載了 Java 函式庫的 Aspose.Tasks。您可以從以下位置下載：[這裡](https://releases.aspose.com/tasks/java/).
- 對 Java 程式設計有基本的了解。
## 導入包
首先，讓我們將必要的套件匯入到我們的 Java 專案中：
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```
## 第 1 步：載入專案文件
```java
//文檔目錄的路徑。
String dataDir = "Your Data Directory";
//載入專案文件
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```
在此步驟中，我們將專案文件載入到`Project`使用檔案路徑的物件。
## 第 2 步：迭代資源分配
```java
//定義最短日期
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
//迭代資源分配
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```
在這裡，我們定義一個最短日期並開始迭代專案中的每個資源分配。
## 第 3 步：檢查停止和恢復日期
```java
    //檢查停止日期
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    //檢查簡歷日期
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```
在此步驟中，我們檢查每個資源分配的停止日期和恢復日期是否早於最短日期。如果是，我們列印“NA”，否則，我們會列印相應的日期。
## 結論
在本教程中，我們學習如何在 Aspose.Tasks for Java 中停止和恢復資源分配。透過遵循提供的步驟，您可以在 Java 專案中輕鬆實現此功能。

## 常見問題解答
### 我可以在未安裝 Microsoft Project 的情況下使用 Aspose.Tasks 嗎？
是的，Aspose.Tasks 允許您使用 Microsoft Project 文件，而無需在系統上安裝 Microsoft Project。
### 在哪裡可以找到更多文件？
你可以找到詳細的文檔[這裡](https://reference.aspose.com/tasks/java/).
### 有免費試用嗎？
是的，您可以獲得免費試用[這裡](https://releases.aspose.com/).
### 如果遇到任何問題，我該如何獲得支援？
您可以獲得社區的支持[這裡](https://forum.aspose.com/c/tasks/15).
### 我可以購買臨時許可證嗎？
是的，您可以購買臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
