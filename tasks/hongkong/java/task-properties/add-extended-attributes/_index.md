---
date: 2026-09-30
description: 了解如何使用 Aspose.Tasks for Java 建立任務擴充屬性，這是領先的 Java project management library，用於新增
  custom task fields。
keywords:
- create task extended attribute
- java project management library
- add custom task field
lastmod: 2026-09-30
linktitle: 如何使用 Aspose.Tasks Java 建立任務擴充屬性
og_description: 了解如何使用 Aspose.Tasks for Java 建立任務擴充屬性，這是領先的 Java project management
  library，用於新增 custom task fields。
og_image_alt: 'Developer guide: create task extended attribute in Aspose.Tasks Java'
og_title: 如何使用 Aspose.Tasks Java 建立任務擴充屬性
schemas:
- author: Aspose
  dateModified: '2026-09-30'
  description: Learn how to create task extended attribute using Aspose.Tasks for
    Java, the leading java project management library for adding custom task fields.
  headline: How to create task extended attribute with Aspose.Tasks Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java integrates smoothly with any Java ecosystem,
      including Spring, Hibernate, and Apache POI.
    question: Can I use Aspose.Tasks for Java with other Java libraries?
  - answer: Absolutely. The library is engineered to handle multi‑thousand‑task projects
      and supports streaming to keep memory usage low.
    question: Is Aspose.Tasks for Java suitable for large‑scale project management
      applications?
  - answer: Yes, you need a valid commercial license. You can review the details on
      the [Aspose.Tasks website](https://purchase.aspose.com/buy).
    question: Are there any licensing considerations for using Aspose.Tasks for Java
      in a commercial project?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community help, or open a support ticket through your Aspose account.
    question: How can I get support or assistance with Aspose.Tasks for Java?
  - answer: Yes, you can access a free trial version on the [Aspose.Tasks free trial](https://releases.aspose.com/)
      page.
    question: Can I try Aspose.Tasks for Java before purchasing?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project management
- extended attributes
- task customization
title: 如何使用 Aspose.Tasks Java 建立任務擴充屬性
url: /zh-hant/java/task-properties/add-extended-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks Java 建立工作項目延伸屬性

## 介紹
在本教學中，您將學習如何透過 Aspose.Tasks for Java 在 Microsoft Project 檔案中**建立工作項目延伸屬性**。新增自訂欄位可讓您捕捉專案特有的資料，這些資料不在內建欄位中，從而在報告與資源規劃上取得更細緻的控制。完成本指南後，您將能為任何工作項目新增純文字、具查閱功能及持續時間屬性。

## 快速回答
- **「延伸屬性」是什麼意思？** 它是一個您自行定義並附加於工作項目、資源或指派的自訂欄位。  
- **哪個函式庫提供此功能？** Aspose.Tasks for Java，一個 Java 專案管理函式庫。  
- **我需要授權才能試用嗎？** 是的 – 可從 Aspose 官方網站取得 30 天免費試用版。  
- **我可以加入查閱值嗎？** 當然可以；您可以為文字或持續時間欄位提供允許值清單。  
- **API 是否相容於 Java 8 及以上版本？** 是的，支援 Java 8 以上，且可在所有主要作業系統上執行。

## 什麼是工作項目延伸屬性？
工作項目延伸屬性是一個使用者自訂的欄位，用於在專案檔案中為每個工作項目儲存額外資訊。它的行為類似內建欄位，但可容納您需要的任何資料類型，例如文字、數字、日期或持續時間。

## 為什麼使用 Aspose.Tasks for Java？
Aspose.Tasks 支援**超過 50 種檔案格式**，且可處理**超過 10,000 個工作項目**的專案，無需安裝 Microsoft Project。此函式庫完全離線運作，確保資料隱私並為企業級解決方案提供確定性的效能。

## 前置條件
- 基本的 Java 程式設計知識。  
- 已安裝 Aspose.Tasks for Java 函式庫。您可從[網站](https://releases.aspose.com/tasks/java/)下載。  
- 在您的機器上配置好的 Java IDE（IntelliJ IDEA、Eclipse 或 VS Code）。

## 匯入套件
`import` 陳述式讓您取得所需的核心類別，例如 `Project`、`ExtendedAttributeDefinition` 與 `ExtendedAttribute`。

`Project` 代表一個 Microsoft Project 檔案，提供讀取、修改與儲存的方法。  
`ExtendedAttributeDefinition` 定義可附加於工作項目、資源或指派的自訂欄位。  
`ExtendedAttribute` 是定義的實例，用於保存特定實體的實際值。

## 如何為工作項目新增純文字延伸屬性？
若要新增純文字延伸屬性，您需要先載入專案，接著建立 Text 類型的定義，將其加入專案的集合，建立工作項目，從定義實例化屬性，設定其文字值，附加至工作項目，最後儲存專案。

### 1. 設定文件目錄路徑
指定來源檔案與輸出檔案所在的目錄。

```java
import java.io.IOException;
import com.aspose.tasks.*;
```

### 2. 建立新專案
實例化 `Project` 物件，可選擇載入現有的 .mpp 檔案。

```java
String dataDir = "Your Document Directory";
```

### 3. 建立 Text1 類型的延伸屬性定義
將自訂欄位定義為名為「Text1」的純文字欄位。

```java
Project project = new Project(dataDir + "project.mpp");
```

### 4. 將定義加入專案的延伸屬性集合
註冊新定義，使專案能識別它。

```java
ExtendedAttributeDefinition taskExtendedAttributeText1Definition = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Text, ExtendedAttributeTask.Text1, "Task City Name");
```

### 5. 向專案新增工作項目
建立一個將接收自訂欄位的工作項目。

```java
project.getExtendedAttributes().add(taskExtendedAttributeText1Definition);
```

### 6. 從屬性定義建立延伸屬性
產生可綁定至特定工作項目的實例。

```java
Task task = project.getRootTask().getChildren().add("Task 1");
```

### 7. 為產生的延伸屬性指派值
設定您想儲存的實際文字，例如「Design Review」。

```java
ExtendedAttribute taskExtendedAttributeText1 = taskExtendedAttributeText1Definition.createExtendedAttribute();
```

### 8. 將延伸屬性加入工作項目
將屬性實例附加至工作項目的 `ExtendedAttributes` 集合。

```java
taskExtendedAttributeText1.setTextValue("London");
```

### 9. 儲存專案
將更新後的專案寫回磁碟，使用所需的格式。

```java
task.getExtendedAttributes().add(taskExtendedAttributeText1);
```

## 如何新增具查閱選項的文字屬性？
在新增具查閱功能的文字屬性時，步驟與純文字屬性相同，但在加入定義之前，需先將允許的字串填入其 `LookupValues` 集合。這些值會在 Microsoft Project 中顯示為下拉式清單，確保資料一致性。

## 如何新增具查閱選項的持續時間屬性？
若要新增具查閱功能的持續時間屬性，建立定義時將 `Text1` 類型改為 `Duration2`，然後在 `LookupValues` 集合中填入持續時間字串，例如「1 day」、「2 days」等。將定義加入專案後，建立屬性實例，設定持續時間值，附加至工作項目，最後儲存檔案。

## 常見問題與疑難排解
- **查閱值未顯示** – 確保在呼叫 `project.getExtendedAttributes().add(definition)` 之前，已將每個查閱項目加入 `LookupValues` 集合。  
- **屬性值未儲存** – 請確認在設定值之後，再將 `ExtendedAttribute` 實例加入工作項目。  
- **檔案大小意外增大** – 處理極大型專案時，建議呼叫 `project.setSaveOptions(new ProjectSaveOptions())` 以啟用增量儲存。

## 常見問答

**Q: 我可以將 Aspose.Tasks for Java 與其他 Java 函式庫一起使用嗎？**  
A: 可以，Aspose.Tasks for Java 能與任何 Java 生態系統順暢整合，包括 Spring、Hibernate 與 Apache POI。

**Q: Aspose.Tasks for Java 是否適用於大型專案管理應用程式？**  
A: 絕對適用。此函式庫設計能處理數千個工作項目的專案，並支援串流以降低記憶體使用量。

**Q: 在商業專案中使用 Aspose.Tasks for Java 有哪些授權考量？**  
A: 有，需要有效的商業授權。您可在 [Aspose.Tasks 網站](https://purchase.aspose.com/buy) 查看詳細資訊。

**Q: 我該如何取得 Aspose.Tasks for Java 的支援或協助？**  
A: 前往 [Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15) 獲取社群協助，或透過您的 Aspose 帳號開立支援票證。

**Q: 我可以在購買前試用 Aspose.Tasks for Java 嗎？**  
A: 可以，您可在 [Aspose.Tasks 免費試用](https://releases.aspose.com/) 頁面取得免費試用版。

---

**最後更新：** 2026-09-30  
**測試環境：** Aspose.Tasks for Java 24.10  
**作者：** Aspose

```java
project.save(dataDir + "PlainTextExtendedAttribute_out.mpp", SaveFileFormat.Mpp);
```

## 相關教學

- [Java 專案管理中的自訂欄位與延伸屬性](/tasks/java/project-management/extended-attributes/)
- [使用 Aspose.Tasks for Java 讀取延伸工作項目屬性](/tasks/java/task-properties/extended-task-attributes/)
- [如何建立 Project aspose.tasks – 設定新工作項目屬性](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}