---
title: 在 Aspose.Tasks 專案中設定貨幣屬性
linktitle: 在 Aspose.Tasks 專案中設定貨幣屬性
second_title: Aspose.Tasks Java API
description: 了解如何使用 Java 在 Aspose.Tasks 專案中設定貨幣屬性。輕鬆操作 Microsoft Project 檔案。
weight: 11
url: /zh-hant/java/currency-properties/set-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 專案中設定貨幣屬性

## 介紹
在本教程中，我們將探討如何使用 Java 在 Aspose.Tasks 專案中設定貨幣屬性。 Aspose.Tasks 是一個功能強大的 Java 程式庫，可讓開發人員以程式設計方式操作 Microsoft Project 檔案。
## 先決條件
在我們開始之前，請確保您具備以下條件：
1. Java 開發工具包 (JDK)：確保您的系統上安裝了 JDK。
2.  Aspose.Tasks for Java 函式庫：從下列位置下載並安裝 Aspose.Tasks for Java 函式庫：[下載連結](https://releases.aspose.com/tasks/java/).
3. 整合開發環境 (IDE)：選擇您喜歡的 IDE，例如 Eclipse 或 IntelliJ IDEA。
## 導入包
首先，讓我們匯入必要的套件以在 Java 中使用 Aspose.Tasks。
```java
import com.aspose.tasks.CurrencySymbolPositionType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```
## 第1步：設定資料目錄
設定項目文件所在的資料目錄。
```java
String dataDir = "Your Data Directory";
```
## 步驟2：建立專案實例
使用 Aspose.Tasks 建立一個新的專案實例。
```java
Project project = new Project();
```
## 步驟 3：設定貨幣屬性
現在，讓我們設定項目的貨幣屬性。
```java
project.set(Prj.CURRENCY_CODE, "AUD");
project.set(Prj.CURRENCY_DIGITS, 2);
project.set(Prj.CURRENCY_SYMBOL, "$");
project.set(Prj.CURRENCY_SYMBOL_POSITION, CurrencySymbolPositionType.After);
```
## 第 4 步：儲存項目
使用更新的貨幣屬性儲存項目。
```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```
## 第 5 步：顯示完成訊息
顯示一條訊息，指示該過程已成功完成。
```java
System.out.println("Process completed Successfully");
```
恭喜！您已使用 Java 在 Aspose.Tasks 專案中成功設定貨幣屬性。
## 結論
在本教程中，我們學習如何使用 Aspose.Tasks for Java 在專案檔案中設定貨幣屬性。借助Aspose.Tasks，開發人員可以有效地操作專案數據，使其成為專案管理應用程式的寶貴工具。
## 常見問題解答
### 我可以使用 Aspose.Tasks 在單一項目中設定多種貨幣嗎？
是的，Aspose.Tasks 允許您在單一專案檔案中處理多種貨幣。
### Aspose.Tasks 是否與不同版本的 Microsoft Project 檔案相容？
是的，Aspose.Tasks 支援各種版本的 Microsoft Project 文件，確保不同環境之間的相容性。
### Aspose.Tasks 是否提供自訂貨幣格式的支援？
當然，Aspose.Tasks 提供了定義自訂貨幣格式的靈活性，以滿足特定的專案要求。
### 我可以將 Aspose.Tasks 與其他 Java 程式庫或框架整合嗎？
是的，Aspose.Tasks 可以與其他 Java 程式庫和框架無縫集成，從而增強其功能和多功能性。
### 在哪裡可以找到有關 Aspose.Tasks 的其他支援或協助？
如需更多支持，您可以訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)，您可以在這裡找到有用的資源並與社區互動。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
