---
title: 使用 Aspose.Tasks for Java 掌握 MS 專案操作
linktitle: 將擴充屬性新增至 Aspose.Tasks 中的資源分配
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 有效地撰寫 MS Project 資訊。 Java 開發人員的逐步指南。
type: docs
weight: 10
url: /zh-hant/java/resource-assignments/add-extended-attributes/
---
## 介紹
在本教程中，我們將深入研究 Aspose.Tasks for Java 的使用，這是一個用於以程式設計方式操作 Microsoft Project 檔案的強大函式庫。我們將重點放在一項基本任務：使用 Aspose.Tasks 編寫 MS Project 資訊。無論您是經驗豐富的開發人員還是剛開始 Java 程式設計之旅，本指南都將引導您逐步完成整個過程。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
1. Java 開發工具包 (JDK)：確保您的系統上安裝了 JDK。
2.  Aspose.Tasks for Java 函式庫：下載並安裝 Aspose.Tasks for Java 函式庫。您可以從以下位置獲取它：[這裡](https://releases.aspose.com/tasks/java/).
3. 整合開發環境 (IDE)：選擇您喜歡的 IDE。我們推薦 IntelliJ IDEA 或 Eclipse。

## 導入包
首先，在 Java 專案中匯入必要的套件：
```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```
#讓我們將提供的範例分解為多個步驟：
## 第1步：設定資料目錄
定義儲存項目資料的目錄。
```java
String dataDir = "Your Data Directory";
```
## 步驟2：建立專案實例
初始化一個新的專案實例。
```java
Project project = new Project();
```
## 步驟 3：設定項目資訊屬性
設定項目的屬性，例如開始日期、開始時間安排和狀態日期。
```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```
## 第 4 步：將項目另存為 XML
將包含更新資訊的項目儲存為 XML 檔案。
```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## 結論
恭喜！您已經成功學習如何使用 Aspose.Tasks for Java 撰寫 MS Project 資訊。借助這些新發現的知識，您可以自動執行與 Microsoft Project 檔案相關的各種任務，從而提高 Java 開發人員的工作效率。
## 常見問題解答
### Q：我可以使用 Aspose.Tasks for Java 讀取 MS Project 檔案嗎？
答：是的，Aspose.Tasks for Java 為讀取和寫入 MS Project 檔案提供了強大的功能。
### Q：Aspose.Tasks for Java 是否與不同版本的 MS Project 相容？
答：當然，Aspose.Tasks for Java 支援各種版本的 MS Project，確保不同檔案格式的相容性。
### Q：Aspose.Tasks for Java 的試用版有什麼限制嗎？
答：雖然試用版允許您探索該庫的功能，但它有一定的限制，例如輸出檔案上的浮水印。
### Q：如何獲得 Aspose.Tasks for Java 的支援？
答：您可以從 Aspose.Tasks 社群論壇尋求協助[這裡](https://forum.aspose.com/c/tasks/15).
### Q：我可以購買 Aspose.Tasks for Java 的臨時授權嗎？
答：是的，臨時許可證可供短期使用。您可以從以下位置取得一份[這裡](https://purchase.aspose.com/temporary-license/).