---
title: 從 Aspose.Tasks 中的檔案讀取表數據
linktitle: 從 Aspose.Tasks 中的檔案讀取表數據
second_title: Aspose.Tasks Java API
description: 釋放 Aspose.Tasks for Java 的強大功能。在這個綜合教程中學習如何從文件中提取表資料。
type: docs
weight: 17
url: /zh-hant/java/project-data-reading/read-table-data/
---
## 介紹
在本教程中，我們將探討如何使用 Aspose.Tasks for Java 從檔案中讀取表格資料。 Aspose.Tasks 是一個功能強大的 Java 程式庫，可讓開發人員以程式設計方式處理 Microsoft Project 文件。
## 先決條件
在我們開始之前，請確保您具備以下先決條件：
1. Java 開發工具包 (JDK)：確保您的系統上安裝了 JDK。您可以從 Oracle 網站下載並安裝它。
2.  Aspose.Tasks for Java JAR 檔案：從下列位置下載 Aspose.Tasks for Java 函式庫[下載連結](https://releases.aspose.com/tasks/java/)並將其包含在您的 Java 專案中。

## 導入包
匯入必要的套件以在 Java 專案中使用 Aspose.Tasks：
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Table;
import com.aspose.tasks.TableField;
```
## 第 1 步：設定資料目錄
定義專案檔案所在目錄的路徑：
```java
String dataDir = "Your Data Directory";
```
代替`"Your Data Directory"`與資料目錄的實際路徑。
## 第 2 步：載入專案文件
使用 Aspose.Tasks 載入專案檔：
```java
Project project = new Project(dataDir + "Project2003.mpp");
```
確保更換`"Project2003.mpp"`與您的專案文件的名稱。
## 第 3 步：檢索表格信息
從項目中獲取表格並迭代其字段：
```java
Table t1 = project.getTables().toList().get(0);
System.out.println("Table Fields Count: " + t1.getTableFields().size());
System.out.println();
for (TableField f : t1.getTableFields()) {
    System.out.println("Field width: " + f.getWidth());
    System.out.println("Field Title: " + f.getTitle());
    System.out.println("Field Title Alignment: " + f.getAlignTitle());
    System.out.println("Field Align Data: " + f.getAlignData());
    System.out.println();
}
```
此程式碼片段會擷取有關表格欄位的信息，例如寬度、標題和對齊方式。

## 結論
在本教程中，我們學習如何使用 Aspose.Tasks for Java 從檔案中讀取表格資料。透過執行這些步驟，您可以在 Java 應用程式中有效地從 Microsoft Project 文件中提取和操作資料。
## 常見問題解答
### Q：Aspose.Tasks 是否與所有版本的 Microsoft Project 相容？
答：Aspose.Tasks 支援 Microsoft Project 的各個版本，包括 Project 2003、2007、2010、2013 和 2016。
### Q：我可以修改表格資料並將其保存回專案文件嗎？
答：是的，您可以使用Aspose.Tasks以程式設計方式修改表格資料並將變更儲存到原始專案檔案中。
### Q：Aspose.Tasks 是否需要單獨的商業用途授權？
答：是的，如果您打算在商業環境中使用Aspose.Tasks，您需要購買它的授權。您可以從以下機構獲得許可證[購買頁面](https://purchase.aspose.com/buy).
### Q：Aspose.Tasks 是否有免費試用版？
答：是的，您可以從 Aspose.Tasks 下載免費試用版[發布頁面](https://releases.aspose.com/).
### Q：在哪裡可以找到 Aspose.Tasks 的幫助和支援？
答：您可以訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)來自社區和 Aspose 團隊的幫助和支持。