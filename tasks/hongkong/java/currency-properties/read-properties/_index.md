---
title: 讀取 Aspose.Tasks 項目中的貨幣屬性
linktitle: 讀取 Aspose.Tasks 項目中的貨幣屬性
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 從 MS Project 檔案中提取貨幣資訊。提供逐步指南。
weight: 10
url: /zh-hant/java/currency-properties/read-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 讀取 Aspose.Tasks 項目中的貨幣屬性

## 介紹
在本教程中，我們將學習如何利用 Aspose.Tasks for Java 從 Microsoft Project 檔案讀取貨幣屬性。 Aspose.Tasks 是一個功能強大的 Java API，可讓開發人員操作 Microsoft Project 文檔，而無需安裝 Microsoft Project。透過執行下面概述的步驟，您將能夠輕鬆提取與貨幣相關的資訊。
## 先決條件
在繼續本教學之前，請確保您符合以下先決條件：
1. Java 開發工具包 (JDK)：確保您的系統上安裝了 JDK。
2.  Aspose.Tasks for Java JAR：從下列位置下載 Aspose.Tasks for Java 函式庫[這裡](https://releases.aspose.com/tasks/java/)並將其包含在您的 Java 專案中。
## 導入包
首先將必要的套件匯入到您的 Java 類別：
```java
import com.aspose.tasks.*;
```
## 第 1 步：設定您的專案目錄
首先，設定 Microsoft Project 檔案所在的專案目錄。您可以如下定義此目錄路徑：
```java
String dataDir = "Your Data Directory";
```
代替`"Your Data Directory"`與專案目錄的實際路徑。
## 第 2 步：建立專案讀取器實例
實例化一個`Project`透過提供 Microsoft Project 檔案的路徑來物件：
```java
Project project = new Project(dataDir + "project.mpp");
```
確保更換`"project.mpp"`與您的 MS Project 檔案的名稱。
## 步驟 3：顯示貨幣屬性
從項目文件中檢索並顯示貨幣屬性：
```java
System.out.println("Currency Code : " + project.get(Prj.CURRENCY_CODE).toString());
System.out.println("<br>Currency Digits : " + project.get(Prj.CURRENCY_DIGITS).toString());
System.out.println("<br>Currency Symbol : " + project.get(Prj.CURRENCY_SYMBOL).toString());
System.out.println("Currency Symbol Position" + project.get(Prj.CURRENCY_SYMBOL_POSITION).toString());
```
該代碼段從 MS Project 檔案中獲取貨幣代碼、數字、符號和符號位置等信息，並將其列印到控制台。
## 第 4 步：流程完成
最後，列印一條訊息，指示該過程成功完成：
```java
System.out.println("Process completed Successfully");
```
## 結論
在本教學中，我們探討如何使用 Aspose.Tasks for Java 從 Microsoft Project 檔案讀取貨幣屬性。透過遵循概述的步驟，您可以輕鬆地以程式設計方式從專案文件中提取與貨幣相關的信息，從而能夠無縫整合到您的 Java 應用程式中。
## 常見問題解答
### Q：Aspose.Tasks 是否與所有版本的 Microsoft Project 相容？
答：Aspose.Tasks 支援各種版本的 Microsoft Project，包括 MS Project 2003-2021 產生的 MPP 檔案。
### Q：我可以使用 Aspose.Tasks 來修改貨幣屬性嗎？
答：是的，Aspose.Tasks 允許您以程式設計方式讀取和修改 MS Project 檔案中的貨幣屬性。
### Q：Aspose.Tasks 適合商業用途嗎？
答：是的，Aspose.Tasks 是一個專為專業用途而設計的商業庫。您可以購買許可證[這裡](https://purchase.aspose.com/buy).
### Q：Aspose.Tasks 提供免費試用嗎？
答：是的，您可以免費試用 Aspose.Tasks[這裡](https://releases.aspose.com/).
### Q：我可以在哪裡尋求 Aspose.Tasks 的協助或支援？
答：您可以造訪Aspose.Tasks論壇[這裡](https://forum.aspose.com/c/tasks/15)如有任何幫助或疑問。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
