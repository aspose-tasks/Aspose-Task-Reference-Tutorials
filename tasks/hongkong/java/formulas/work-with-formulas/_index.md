---
title: MS Project 公式與 Aspose.Tasks for Java
linktitle: 在 Aspose.Tasks 中使用公式
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks 函式庫在 Java 中操作 MS Project 檔案。輕鬆建立、修改和計算屬性。
weight: 11
url: /zh-hant/java/formulas/work-with-formulas/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# MS Project 公式與 Aspose.Tasks for Java

## 介紹
在本教程中，我們將深入研究如何使用 Aspose.Tasks for Java 來處理 MS Project Formulas。 Aspose.Tasks 是一個功能強大的函式庫，使開發人員能夠以程式設計方式操作 Microsoft Project 檔案。憑藉其廣泛的功能，您可以輕鬆地在 Java 應用程式中建立、讀取、修改和轉換專案檔案。
## 先決條件
在我們開始之前，請確保您已設定以下先決條件：
### Java開發環境
確保您的系統上安裝了 Java 開發工具包 (JDK)。您可以從 Oracle 網站下載並安裝最新的 JDK。
### Aspose.Tasks函式庫
您需要將 Aspose.Tasks 庫新增到您的 Java 專案中。您可以從以下位置下載該程式庫[Aspose.Tasks for Java 下載頁面](https://releases.aspose.com/tasks/java/)並將其包含在您的專案的依賴項中。

## 導入包
在深入研究範例之前，請將必要的套件匯入到您的 Java 程式碼中：
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

讓我們將提供的範例分解為多個步驟：
## 第 1 步：使用自訂欄位建立測試項目
```java
Project project = CreateTestProjectWithCustomField();
```
首先，使用以下命令建立一個帶有自訂欄位的測試項目`CreateTestProjectWithCustomField()`方法。此方法將傳回一個代表新建立的專案的 Project 物件。
## 步驟 2：定義擴充屬性定義
```java
ExtendedAttributeDefinition attr = project.getExtendedAttributes().get(0);
attr.setAlias("Days from finish to deadline");
attr.setFormula("[Deadline] - [Finish]");
```
從專案中檢索擴充屬性定義並設定其別名和公式。在此範例中，我們定義一個屬性來計算從完成日期到截止日期的天數。
## 第 3 步：設定任務的截止日期
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2015, Calendar.MARCH, 26, 8, 0, 0);
Task task = project.getRootTask().getChildren().getById(1);
task.set(Tsk.DEADLINE, cal.getTime());
```
建立一個 Calendar 物件並設定截止日期。然後，從專案中檢索任務並使用 Calendar 物件設定其截止日期。
## 第 4 步：儲存項目
```java
project.save("SaveFile.mpp", SaveFileFormat.Mpp);
```
最後，將項目儲存到具有指定名稱和格式的檔案中。在本例中，我們將其另存為 MPP 檔案。

## 結論
在本教程中，我們學習如何使用 Aspose.Tasks for Java 來處理 MS Project Formulas。透過執行這些步驟，您可以以程式設計方式有效地操作專案文件，新增自訂欄位並根據公式計算屬性。

## 常見問題解答
### Q：我可以將 Aspose.Tasks 與其他程式語言一起使用嗎？
答：是的，Aspose.Tasks 支援各種程式語言，包括 Java、.NET 等。
### Q：Aspose.Tasks 是否有免費試用版？
答：是的，您可以從以下位置下載 Aspose.Tasks 的免費試用版：[這裡](https://releases.aspose.com/).
### Q：在哪裡可以找到 Aspose.Tasks 的文檔？
 A：你可以找到Aspose.Tasks的文檔[這裡](https://reference.aspose.com/tasks/java/).
### Q：如何獲得 Aspose.Tasks 的支援？
答： 如需支持，您可以訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15).
### Q：使用 Aspose.Tasks 需要臨時許可證嗎？
答：如果您需要額外的功能，您可以從以下位置取得臨時許可證：[這裡](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
