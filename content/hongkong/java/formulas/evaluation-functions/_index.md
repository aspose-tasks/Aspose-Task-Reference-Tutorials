---
title: 支援 Aspose.Tasks 公式中的評估函數
linktitle: 支援 Aspose.Tasks 公式中的評估函數
second_title: Aspose.Tasks Java API
description: 了解如何使用 Java 支援對 Aspose.Tasks 公式中的 MS Project 函數求值。使用 Aspose.Tasks 提高您的工作效率。
type: docs
weight: 10
url: /zh-hant/java/formulas/evaluation-functions/
---

## 介紹
Aspose.Tasks for Java 是一個功能強大的函式庫，使開發人員能夠以程式設計方式操作 Microsoft Project 檔案。其主要功能之一是能夠支援在 Aspose.Tasks 公式中評估 MS Project 函數。此功能允許使用者直接在其 Java 應用程式中執行複雜的計算和分析。
## 先決條件
在開始將 MS Project 函數整合到 Aspose.Tasks 公式之前，請確保您具備以下條件：
1. Java 開發環境：確保您的系統上安裝了 Java 以及用於 Java 開發的相容 IDE，例如 IntelliJ IDEA 或 Eclipse。
2.  Aspose.Tasks for Java 函式庫：下載 Aspose.Tasks for Java 函式庫並將其包含在您的 Java 專案中。您可以從[Aspose.Tasks for Java 下載頁面](https://releases.aspose.com/tasks/java/).
## 導入包
首先，在 Java 類別中匯入必要的套件以利用 Aspose.Tasks 功能：
```java
import com.aspose.tasks.*;
```

## 第 1 步：建立一個新的專案對象
首先，建立一個新的`Project`使用對象：
```java
Project project = new Project();
```
這會初始化一個新的空項目。
## 步驟 2：定義任務的擴充屬性
接下來，定義任務的擴展屬性。此屬性將保存與任務關聯的自訂資料：
```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```
在這裡，我們建立一個類型的擴充屬性`Number`任務名稱為“Sine”。
## 步驟3：將擴充屬性加入到專案中
將擴充屬性定義新增至項目的擴充屬性清單：
```java
project.getExtendedAttributes().add(attr);
```
這會將自訂屬性新增至項目。
## 第 4 步：建立新任務
現在，讓我們在專案中建立一個新任務：
```java
Task task = project.getRootTask().getChildren().add("Task");
```
這將向專案新增一個名為「Task」的新任務。
## 步驟 5：將擴充屬性與任務關聯
將先前建立的擴充屬性與任務相關聯：
```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```
這會將「Sine」擴充屬性與任務關聯起來。

## 結論
總之，將 MS Project 函數整合到 Java 中的 Aspose.Tasks 公式中是一個簡單的過程。透過遵循提供的步驟，您可以有效地利用 Aspose.Tasks for Java 的強大功能以程式設計方式操作和分析 Microsoft Project 檔案。
## 常見問題解答
### Q：Aspose.Tasks for Java 可以處理複雜的 MS Project 公式嗎？
答：是的，Aspose.Tasks for Java 支援評估各種 MS Project 函數，允許在 Java 應用程式中進行複雜的計算。
### Q：Aspose.Tasks for Java 是否與不同版本的 Microsoft Project 檔案相容？
答：是的，Aspose.Tasks for Java 支援各種版本的 Microsoft Project 文件，包括 MPP、MPT 和 XML 格式。
### Q：我可以在購買前試用 Aspose.Tasks for Java 嗎？
答：是的，您可以從網站下載 Aspose.Tasks for Java 的免費試用版[這裡](https://purchase.aspose.com/buy).
### Q：如何獲得 Aspose.Tasks for Java 的支援？
答：您可以從 Aspose.Tasks 社群論壇獲得支持[這裡](https://forum.aspose.com/c/tasks/15).
### Q：Aspose.Tasks for Java 是否有可用的臨時授權？
答：是的，您可以從 Aspose 網站取得用於測試目的的臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).