---
title: 為 Aspose.Tasks 中的任務新增擴充屬性
linktitle: 為 Aspose.Tasks 中的任務新增擴充屬性
second_title: Aspose.Tasks Java API
description: 探索 Aspose.Tasks Java 在使用擴充屬性自訂 Microsoft Project 檔案方面的強大功能。輕鬆增強您的專案管理能力。
weight: 11
url: /zh-hant/java/task-properties/add-extended-attributes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 為 Aspose.Tasks 中的任務新增擴充屬性

## 介紹
增強專案管理能力對於高效的任務追蹤和資源管理至關重要。 Aspose.Tasks for Java 為 Java 開發人員提供了一個強大的解決方案來無縫操作 Microsoft Project 檔案。在本教程中，我們將探索如何使用 Aspose.Tasks for Java 為任務新增擴充屬性，從而允許您根據您的特定要求自訂和組織專案資料。
## 先決條件
在深入學習本教程之前，請確保您符合以下先決條件：
- Java 程式設計的基礎知識。
- 安裝了 Java 函式庫的 Aspose.Tasks。您可以從[網站](https://releases.aspose.com/tasks/java/).
- 您的系統上安裝了 Java 整合開發環境 (IDE)。
## 導入包
在您的 Java 專案中，匯入必要的套件以存取 Aspose.Tasks 功能：
```java
import java.io.IOException;
import com.aspose.tasks.*;
```
現在，讓我們將每個範例分解為多個步驟：
## 1. 新增純文字屬性
1. 設定文檔目錄路徑：
```java
String dataDir = "Your Document Directory";
```
2. 建立一個新專案：
```java
Project project = new Project(dataDir + "project.mpp");
```
3. 建立 Text1 類型的擴充屬性定義：
```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```
4. 將定義新增至項目的擴充屬性集合：
```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```
5. 在專案中新增任務：
```java
Task task = project.getRootTask().getChildren().add("Task 1");
```
6. 從屬性定義建立擴充屬性：
```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```
7. 為產生的擴展屬性指派一個值：
```java
taskExtendedAttributeText1.setTextValue("London");
```
8. 將擴展屬性加入任務：
```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```
9. 儲存項目：
```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```
## 2. 新增帶有查找選項的文字屬性
按照與上述相同的步驟操作，將 Text1 替換為 Text2 並自訂查找值。
## 3. 新增帶有查找選項的持續時間屬性
按照與上述相同的步驟操作，將 Text1 替換為 Duration2 並自訂查找值。
## 結論
透過遵循本逐步指南，您已經了解如何利用 Aspose.Tasks for Java 為 Microsoft Project 檔案中的任務新增擴充屬性。這種客製化可讓您自訂專案管理方法，提高靈活性和效率。
## 經常問的問題
### Q：我可以將 Aspose.Tasks for Java 與其他 Java 函式庫一起使用嗎？
答：是的，Aspose.Tasks for Java 可以無縫整合到您的 Java 專案中，並且它可以與其他 Java 程式庫配合良好。
### Q：Aspose.Tasks for Java 適合大型專案管理應用嗎？
答：當然，Aspose.Tasks for Java 旨在處理不同規模的項目，包括大型應用程式。
### Q：在商業專案中使用 Aspose.Tasks for Java 是否有任何許可注意事項？
答：是的，請務必查看網站上提供的許可信息[Aspose.Tasks 網站](https://purchase.aspose.com/buy).
### Q：如何獲得 Aspose.Tasks for Java 的支援或協助？
答：訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)以獲得社區支持和討論。
### Q：我可以在購買前試用 Aspose.Tasks for Java 嗎？
答：是的，您可以存取免費試用版[這裡](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
