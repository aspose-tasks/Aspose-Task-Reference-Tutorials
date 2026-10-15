---
date: 2026-10-15
description: 了解如何使用 Aspose.Tasks for Java 建立活動、設定資料目錄、自訂表格欄位，並將專案儲存為 MPP。為 Java 開發人員提供的逐步指南。
keywords:
- how to create activity
- customize table fields
- save project as mpp
- how to save mpp
- create task programmatically
lastmod: 2026-10-15
linktitle: 如何使用 Aspose.Tasks for Java 建立活動並設定資料目錄
og_description: 如何使用 Aspose.Tasks for Java 建立活動、自訂表格欄位，並將專案儲存為 MPP。請參考此詳細指南以快速實作。
og_image_alt: Screenshot of Aspose.Tasks Java code configuring Gantt chart and saving
  as MPP
og_title: 如何在 Aspose.Tasks for Java 中建立活動並設定資料目錄
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  headline: How to create activity and set data directory using Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to create activity, set the data directory, customize table
    fields and save project as MPP with Aspose.Tasks for Java. Step‑by‑step guide
    for Java developers.
  name: How to create activity and set data directory using Aspose.Tasks for Java
  steps:
  - name: set up data directory
    text: Define the folder that contains your project files. The `dataDir` variable
      holds the absolute path and is reused throughout the tutorial. Replace `"Your
      Data Directory"` with the full path to the folder where `project.mpp` lives,
      for example `C:/Projects/MyGantt`.
  - name: load project file
    text: '`Project` is Aspose.Tasks'' top‑level object that represents a single Microsoft
      Project file in memory. Loading an existing file gives you access to its tasks,
      resources, and tables.'
  - name: add new activity
    text: '`Task` represents an individual activity in the schedule. Adding a task
      to the root task collection inserts it at the top level of the project hierarchy.'
  - name: define custom attribute
    text: '`ExtendedAttributeDefinition` lets you create a reusable custom field that
      can be attached to any task, resource, or assignment.'
  - name: add custom attribute to task
    text: '`ExtendedAttribute` is the concrete instance of a custom attribute that
      you assign to a specific task.'
  - name: customize table – add custom attribute as a column
    text: '`TableField` describes a column in a Gantt chart table. By adding a `TableField`
      that references the custom attribute, you make the attribute visible in the
      chart view.'
  - name: save project
    text: Calling `project.save` persists all changes to a new file. The `SaveFileFormat.MPP`
      constant tells Aspose.Tasks to write the file in Microsoft Project’s native
      binary format.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks is available for .NET, Java, and C++.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Yes, you can download a free trial from the **Aspose.Tasks free trial
      download page**.
    question: Is there a free trial available for Aspose.Tasks?
  - answer: You can find support and ask questions on the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find support for Aspose.Tasks?
  - answer: You can purchase a license from the **Aspose.Tasks purchase page**.
    question: How do I purchase a license for Aspose.Tasks?
  - answer: Yes, you can obtain a temporary license from the **temporary license request
      page**.
    question: Do I need a temporary license for testing purposes?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project automation
- Gantt chart customization
- MPP file handling
title: 如何使用 Aspose.Tasks for Java 建立活動並設定資料目錄
url: /zh-hant/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks for Java 建立活動並設定資料目錄的方法

## 介紹
在本教學中，您將學習如何以程式方式 **建立活動**、設定 **資料目錄**，以及 **將專案儲存為 MPP**，同時在甘特圖檢視中 **自訂表格欄位**。Aspose.Tasks for Java 是功能強大的 API，支援超過 30 種輸入與輸出格式，且能在不將整個檔案載入記憶體的情況下處理多達 10 000 個工作項目的專案。完成本指南後，您將能自動化建立專案、為工作項目加入自訂屬性，並產生可直接在 Microsoft Project 開啟的 MPP 檔案。

## 快速解答
- **第一步是什麼？** 設定專案檔案所在的資料目錄路徑。  
- **需要哪個函式庫？** Aspose.Tasks for Java（可從官方網站下載）。  
- **我可以加入自訂屬性嗎？** 可以——您可以定義擴充屬性並在甘特圖中顯示。  
- **測試需要授權嗎？** 可取得臨時授權供評估使用。  
- **哪個 IDE 最適合？** 任何 Java IDE（IntelliJ IDEA、Eclipse、NetBeans）皆可使用。

## 什麼是「設定資料目錄」以及為何重要？
設定資料目錄可告訴 Aspose.Tasks 在哪裡讀寫專案檔案。若路徑不正確，API 無法找到您的 `.mpp` 檔案，會導致 `FileNotFoundException` 錯誤。於程式碼開頭定義此目錄，可使工作流程可重複執行，並將檔案系統的關注點與業務邏輯分離。

## 為何在甘特圖中自訂表格欄位？
自訂表格欄位可讓您直接在甘特圖檢視中顯示額外資訊——例如自訂屬性、資源資料或專案特定備註。這可減少產生獨立報表的需求，為利害關係人提供單一、資料豐富的視覺呈現，並可將決策速度提升最高 30 %。

## 如何建立新活動？
您可以透過實例化 `Task` 物件並將其加入專案的根工作項目集合來建立新活動（工作項目）。此方式可自動產生大型排程、從外部系統擷取工作項目資料，或在不需手動編輯的情況下執行批次更新。

## 前置條件
1. **Java Development Kit (JDK)** – 8 版或更新版本。  
2. **Aspose.Tasks for Java** – 從 **Aspose.Tasks Java 釋出頁面** 下載。  
3. **IDE** – 您偏好的 IntelliJ IDEA、Eclipse，或任何相容 Java 的編輯器。  

## 匯入套件
`com.aspose.tasks` 命名空間包含您在專案操作中所需的所有類別。匯入該命名空間即可使用 `Project`、`Task`、`ExtendedAttributeDefinition` 以及其他核心類型。

```java
import com.aspose.tasks.*;
```

## Maven 相依性（可選）
若使用 Maven 管理專案，請將 Aspose.Tasks 相依性加入 `pom.xml`。這可確保在建置過程中自動解析該函式庫。

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-tasks</artifactId>
    <version>24.12</version>
</dependency>
```

## 步驟說明

### 步驟 1：設定資料目錄
定義包含專案檔案的資料夾。`dataDir` 變數保存絕對路徑，並在整個教學中重複使用。

```java
String dataDir = "Your Data Directory";
```

將 `"Your Data Directory"` 替換為 `project.mpp` 所在資料夾的完整路徑，例如 `C:/Projects/MyGantt`。

### 步驟 2：載入專案檔案
`Project` 是 Aspose.Tasks 的最高層物件，代表記憶體中的單一 Microsoft Project 檔案。載入現有檔案後，您即可存取其工作項目、資源與表格。

```java
Project project = new Project(dataDir + "project.mpp");
```

### 步驟 3：新增活動
`Task` 代表排程中的單一活動。將工作項目加入根工作項目集合，即會插入至專案階層的最上層。

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### 步驟 4：定義自訂屬性
`ExtendedAttributeDefinition` 讓您建立可重複使用的自訂欄位，該欄位可附加於任何工作項目、資源或指派上。

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### 步驟 5：將自訂屬性加入工作項目
`ExtendedAttribute` 是自訂屬性的具體實例，您可將其指派給特定的工作項目。

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### 步驟 6：自訂表格 – 將自訂屬性加入為欄位
`TableField` 描述甘特圖表格中的一個欄位。透過加入參考自訂屬性的 `TableField`，即可在圖表檢視中顯示該屬性。

```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```

### 步驟 7：儲存專案
呼叫 `project.save` 可將所有變更寫入新檔案。`SaveFileFormat.MPP` 常數告訴 Aspose.Tasks 以 Microsoft Project 原生的二進位格式寫入檔案。

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## 常見問題與解決方案
| 問題 | 為何發生 | 解決方式 |
|------|----------|----------|
| **FileNotFoundException** 載入專案時發生 | **設定資料目錄** 的路徑不正確或缺少結尾的斜線。 | 確認 `dataDir` 指向正確的資料夾，並包含正確的檔案分隔符（`/` 或 `\\`）。 |
| 自訂屬性在甘特圖檢視中未顯示 | 表格欄位被加入了錯誤的索引，或欄寬過小。 | 確保 `table.getTableFields().add(3, attrField);` 使用有效的索引，並根據需要調整 `setWidth`。 |
| 儲存時發生 LicenseException | 未為正式使用套用有效授權。 | 在呼叫 `project.save()` 前套用臨時或永久授權。 |

## 常見問答

**Q: 我可以將 Aspose.Tasks 用於其他程式語言嗎？**  
A: 可以，Aspose.Tasks 支援 .NET、Java 與 C++。

**Q: Aspose.Tasks 有提供免費試用嗎？**  
A: 有，您可從 **Aspose.Tasks 免費試用下載頁面** 下載免費試用版。

**Q: 我可以在哪裡取得 Aspose.Tasks 的支援？**  
A: 您可在 [Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15) 上取得支援並提出問題。

**Q: 我要如何購買 Aspose.Tasks 的授權？**  
A: 您可在 **Aspose.Tasks 購買頁面** 購買授權。

**Q: 測試時需要臨時授權嗎？**  
A: 需要，您可從 **臨時授權申請頁面** 取得臨時授權。

## 結論
您現在已了解 **如何建立活動**、設定資料目錄、定義並附加自訂屬性，以及使用 Aspose.Tasks for Java 在甘特圖檢視中 **自訂表格欄位** 並 **將專案儲存為 MPP**。這些功能讓您能完整以程式方式控制專案資料，實現自動化排程產生，並為利害關係人提供更豐富的視覺報告。

---

**最後更新：** 2026-10-15  
**測試環境：** Aspose.Tasks Java 24.12（最新）  
**作者：** Aspose

## 相關教學

- [如何在 Aspose.Tasks（MS Project）中建立空白專案檔案](/tasks/java/project-configuration/create-empty-project-file/)
- [如何建立 MPP 檔案 – 使用 Aspose.Tasks 建立並儲存空白 MPP 格式專案](/tasks/java/project-configuration/create-save-mpp/)
- [如何建立專案 aspose.tasks – 設定新工作項目屬性](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}