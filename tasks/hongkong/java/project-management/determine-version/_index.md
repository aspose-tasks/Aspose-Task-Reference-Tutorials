---
title: 使用 Aspose.Tasks 確定 MS Project 版本
linktitle: 使用 Aspose.Tasks 確定項目版本
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 以程式設計方式確定 MS Project 檔案的版本。帶有程式碼範例的分步指南。
weight: 12
url: /zh-hant/java/project-management/determine-version/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 確定 MS Project 版本

## 介紹
本教學將引導您使用 Aspose.Tasks for Java 逐步確定 MS Project 檔案的版本。 Aspose.Tasks 是一個功能強大的 Java API，可讓開發人員操作 Microsoft Project 文件，而無需安裝 Microsoft Project。
## 先決條件
在我們開始之前，請確保您具備以下條件：
1. Java 開發工具包 (JDK)：確保您的系統上安裝了 JDK。
2.  Aspose.Tasks for Java JAR 檔案：從下列位置下載 Aspose.Tasks for Java 函式庫[網站](https://releases.aspose.com/tasks/java/)並將其添加到您的 Java 專案中。
3. MS Project 檔案：準備 MS Project 檔案（XML 格式）進行測試。

## 導入包
在深入研究程式碼之前，讓我們先導入必要的套件：
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```
## 第 1 步：設定項目
```java
//文檔目錄的路徑。
String dataDir = "Your Data Directory";
```
代替`"Your Data Directory"`包含 MS Project 檔案的目錄路徑。
## 第 2 步：載入項目
```java
Project project = new Project(dataDir + "input.xml");
```
代替`"input.xml"`與您的 MS Project 檔案的名稱。
## 步驟3：確定專案版本
```java
//顯示項目版本屬性
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```
此程式碼片段會擷取並列印 MS Project 檔案的版本和上次儲存日期。
## 第四步：顯示結果
```java
//顯示轉換結果。
System.out.println("Process completed Successfully");
```
該行表示該過程已完成。

## 結論
在本教學中，您學習如何使用 Aspose.Tasks for Java 確定 MS Project 檔案的版本。透過遵循逐步指南，您可以輕鬆地在 Java 應用程式中有效地使用 MS Project 檔案。

## 常見問題解答
### Q：我可以將 Aspose.Tasks 與其他程式語言一起使用嗎？
答：是的，Aspose.Tasks 支援多種程式語言，包括.NET、Java 和 C++.
### Q：Aspose.Tasks 適合大型專案嗎？
答：當然，Aspose.Tasks 旨在輕鬆處理任何規模的專案。
### Q：我可以使用 Aspose.Tasks 自訂項目資料嗎？
答：是的，您可以使用 Aspose.Tasks 操作專案資料、修改任務、資源等等。
### Q：Aspose.Tasks 是否需要安裝 Microsoft Project？
答：不需要，Aspose.Tasks 獨立運作，不需要安裝 Microsoft Project。
### Q：Aspose.Tasks 是否提供技術支援？
答：是的，您可以從 Aspose.Tasks 論壇獲得技術支援：[這裡](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
