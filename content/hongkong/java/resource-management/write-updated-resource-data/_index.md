---
title: 在 Aspose.Tasks 中寫入更新的資源數據
linktitle: 在 Aspose.Tasks 中寫入更新的資源數據
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 輕鬆更新 MS Project 檔案中的資源資料。
type: docs
weight: 21
url: /zh-hant/java/resource-management/write-updated-resource-data/
---
## 介紹
在本教程中，我們將指導您使用 Aspose.Tasks for Java 更新 Microsoft Project 資源資料。 Aspose.Tasks 是一個功能強大的 Java API，可讓您操作 Microsoft Project 文件，而無需在系統上安裝 Microsoft Project。

## 先決條件

在我們開始之前，請確保您具備以下條件：

1. 您的系統上安裝了 Java 開發工具包 (JDK)。
2.  Java 函式庫的 Aspose.Tasks。您可以從以下位置下載：[這裡](https://releases.aspose.com/tasks/java/).
3. Java 程式設計的基礎知識。

## 導入包

首先，您需要匯入必要的套件以便在 Java 程式碼中使用 Aspose.Tasks。將以下導入語句加入您的 Java 檔案：

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## 第 1 步：設定您的資料目錄

定義資料檔案所在的目錄：

```java
String dataDir = "Your Data Directory";
```

## 第 2 步：指定輸入和輸出文件

定義輸入 MS Project 檔案和產生的更新檔案的路徑：

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; //使用一個 rsc 來更新測試文件
String resultFile = dataDir + "OutputMPP.mpp"; //編寫測試項目的文件
```

## 第 3 步：載入項目

將 MS Project 檔案載入到`Project`目的：

```java
Project project = new Project(file);
```

## 步驟 4：新增資源並設定屬性

為項目新增資源並設定其屬性，例如標準費率、加班費率和群組：

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## 第 5 步：儲存項目

使用修改後的資源資料儲存更新的項目：

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## 結論

在本教學中，我們示範如何使用 Aspose.Tasks for Java 更新 MS Project 資源資料。透過執行這些步驟，您可以以程式設計方式有效地操作 MS Project 檔案中的資源資訊。

## 常見問題解答

### Q1：我可以使用 Aspose.Tasks for Java 更新同一專案中的多個資源嗎？

A1：是的，您可以透過迭代多個資源並相應地設定它們的屬性來更新它們。

### Q2：Aspose.Tasks 是否支援 MS Project 以外的其他檔案格式？

A2：是的，Aspose.Tasks 支援各種檔案格式，包括 XML、MPP 等。

### Q3：Aspose.Tasks 是否相容於不同版本的 Java？

A3：Aspose.Tasks 與 Java 版本 6 及更高版本相容。

### Q4：我可以使用 Aspose.Tasks 對 MS Project 檔案執行其他操作嗎？

A4：是的，您可以執行多種操作，例如讀取、寫入和操作任務、資源和日曆。

### Q5：我可以在哪裡找到有關 Aspose.Tasks 的其他協助或支援？

 A5：您可以訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)如有任何幫助或疑問。
