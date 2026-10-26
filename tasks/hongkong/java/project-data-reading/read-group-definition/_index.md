---
date: 2026-10-26
description: 如何使用 Aspose.Tasks for Java 讀取群組定義資料。從 Microsoft Project 檔案中擷取任務分組、條件與格式設定，以自動化報告與遷移。
keywords:
- how to read group
- generate group report
- automate project grouping
lastmod: 2026-10-26
linktitle: 在 Aspose.Tasks 中讀取群組定義資料
og_description: 如何使用 Aspose.Tasks for Java 讀取群組定義資料。從 Microsoft Project 檔案中擷取任務分組、條件與格式設定，以自動化報告與遷移。
og_image_alt: 'Tutorial guide: Read group definition data in Aspose.Tasks for Java'
og_title: 如何使用 Aspose.Tasks for Java 讀取群組定義資料
schemas:
- author: Aspose
  dateModified: '2026-10-26'
  description: How to read group definition data using Aspose.Tasks for Java. Extract
    task grouping, criteria, and formatting from Microsoft Project files to automate
    reporting and migration.
  headline: How to read group definition data with Aspose.Tasks for Java
  type: TechArticle
- description: How to read group definition data using Aspose.Tasks for Java. Extract
    task grouping, criteria, and formatting from Microsoft Project files to automate
    reporting and migration.
  name: How to read group definition data with Aspose.Tasks for Java
  steps:
  - name: set up your data directory
    text: Define the folder that contains the `.mpp` file you want to inspect. Using
      `java.nio.file.Paths` guarantees platform‑independent path handling.
  - name: load the project file
    text: Create a `Project` instance by pointing it to your `.mpp` file. The constructor
      reads the file header and builds an in‑memory model.
  - name: retrieve task groups count
    text: Print the total number of task groups defined in the project. This quick
      check confirms that the file actually contains grouping information.
  - name: retrieve specific task group information
    text: Grab a particular group (index 1 in this example) and display its name and
      the number of criteria it contains. Each group can have multiple criteria that
      define how tasks are grouped.
  - name: retrieve group criterion information
    text: Each group can have one or more criteria. The snippet below extracts details
      such as the field used for grouping, the grouping mode, cell color, and pattern.
  - name: check parent group
    text: Sometimes a criterion belongs to a parent group. This check confirms the
      relationship and prevents null‑pointer issues when navigating the hierarchy.
  - name: retrieve criterion’s font information
    text: Group criteria can have custom font styling. The following code prints the
      font family, size, style, and sorting direction, allowing you to recreate the
      exact look in your own UI.
  type: HowTo
- questions:
  - answer: Yes, the library provides full read/write capabilities for Microsoft Project
      formats, allowing you to add tasks, change resources, and update group definitions
      programmatically.
    question: Can I use Aspose.Tasks for Java to modify project files?
  - answer: It supports MPP, XML, CSV, and other common Project formats across versions
      from Project 2000 up to the latest 2024 release.
    question: Is Aspose.Tasks for Java compatible with all versions of Microsoft Project
      files?
  - answer: Wrap file operations in `try‑catch` blocks and catch `TasksException`
      for detailed error information; inspect the exception’s `getMessage()` for clues.
    question: How should I handle errors while working with Aspose.Tasks for Java?
  - answer: Absolutely – you can export to PDF, XLSX, HTML, and more using the library’s
      dedicated export APIs.
    question: Does Aspose.Tasks for Java offer export to other formats?
  - answer: Visit the [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)
      for API references and the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for community assistance.
    question: Where can I find additional resources and support?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- read group definition
- Aspose.Tasks
- Java project data
- group reporting
title: 如何使用 Aspose.Tasks for Java 讀取群組定義資料
url: /zh-hant/java/project-data-reading/read-group-definition/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks for Java 中讀取群組定義資料

## 簡介
Aspose.Tasks for Java 讓您能以程式方式存取、修改與分析 Microsoft Project 檔案。在本教學中，您將學習 **如何讀取群組定義** 資料，從 `.mpp` 檔案中擷取每個群組的名稱、條件與視覺樣式，並利用這些資訊產生自訂報告或將設定遷移至其他專案。掌握此功能可讓您自動化報告、驗證專案結構，並精簡資料驅動的工作流程。

## 快速答案
- **「讀取群組定義」是什麼意思？** 這表示擷取 Microsoft Project 用於組織工作項目的分組規則（名稱、條件、顏色、字型）。  
- **需要哪個程式庫？** Aspose.Tasks for Java。  
- **需要授權嗎？** 免費試用可用於開發；正式環境需購買商業授權。  
- **支援哪些 IDE？** 任何 Java IDE，例如 IntelliJ IDEA 或 Eclipse。  
- **需要多少程式碼？** 少於 30 行 Java 程式碼即可載入專案並顯示群組詳細資訊。

## 如何讀取群組定義資料
載入專案、列舉其群組，並檢查每個群組的條件。直接的作法是：**建立 `Project` 實例，呼叫 `project.getTaskGroups()`，並遍歷集合以讀取名稱、條件、字型與顏色。** 以下各節將此流程分解為明確步驟，並提供短碼佔位符，您可將其替換為 Aspose.Tasks 文件中的實際程式碼片段。

## 什麼是讀取群組定義？
讀取群組定義是指擷取 Microsoft Project 用於排列工作項目的分組規則（名稱、條件、格式設定）。這些規則告訴應用程式如何依狀態、優先順序或自訂欄位將工作項目分群，並包含字型樣式與儲存格顏色等視覺屬性。

## 為什麼要讀取群組定義資料？
讀取群組定義資料可讓您 **自動化報告產生**、**將分組邏輯遷移**至其他專案，並在批次更新前 **驗證所需群組是否存在**。Aspose.Tasks for Java 能在不將整個檔案載入記憶體的情況下處理 **超過 10,000 個工作項目** 的專案，實現高效能的批次作業。此外，您還能擷取字型顏色、圖案與排序方向，以在自訂儀表板中重建完全相同的視覺佈局。

## 先決條件
1. **Java Development Kit (JDK) 8+** – 任何較新的版本皆可。  
2. **Aspose.Tasks for Java** – 從 [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/) 下載最新的 JAR。  
3. **A Java IDE** – IntelliJ IDEA、Eclipse，或您偏好的任何編輯器。  

> **專業提示：** 使用 Maven 或 Gradle 來管理 Aspose.Tasks 相依性，可避免手動處理 JAR。

## 匯入套件
`Project` 是 Aspose.Tasks for Java 中代表 Microsoft Project 檔案的主要類別。  

```java
import com.aspose.tasks.*;
```

## 逐步指南

### 步驟 1：設定資料目錄
定義包含您欲檢查的 `.mpp` 檔案的資料夾。使用 `java.nio.file.Paths` 可確保跨平台的路徑處理。

```java
String dataDir = "Your Data Directory";
```

### 步驟 2：載入專案檔案
透過指向您的 `.mpp` 檔案建立 `Project` 實例。建構子會讀取檔案標頭並建立記憶體中的模型。

```java
Project project = new Project(dataDir + "project.mpp");
```

### 步驟 3：取得工作群組數量
列印專案中定義的工作群組總數。此快速檢查可確認檔案確實包含分組資訊。

```java
System.out.println("Task Groups Count: " + project.getTaskGroups().size());
```

### 步驟 4：取得特定工作群組資訊
取得特定群組（本例中為索引 1），並顯示其名稱及其包含的條件數量。每個群組可有多個條件，用以定義工作項目的分組方式。

```java
Group taskGroup = project.getTaskGroups().toList().get(1);
System.out.println("Percent Complete:" + taskGroup.getName());
System.out.println("Group Criteria count: " + taskGroup.getGroupCriteria().size());
```

### 步驟 5：取得群組條件資訊
每個群組可以有一個或多個條件。以下程式碼片段會擷取如分組欄位、分組模式、儲存格顏色與圖案等細節。

```java
GroupCriterion criterion = taskGroup.getGroupCriteria().toList().get(0);
System.out.println("Criterion Field: " + criterion.getField());
System.out.println("Criterion GroupOn: " + criterion.getGroupOn());
System.out.println("Criterion Cell Color: " + criterion.getCellColor());
System.out.println("Criterion Pattern: " + criterion.getPattern());
```

### 步驟 6：檢查父群組
有時候條件屬於父群組。此檢查可確認關係，避免在遍歷層級時發生 NullPointerException。

```java
if (taskGroup == criterion.getParentGroup())
    System.out.println("Parent Group is equval to task Group.");
```

### 步驟 7：取得條件的字型資訊
群組條件可以有自訂的字型樣式。以下程式碼會列印字型族、大小、樣式與排序方向，讓您在自訂 UI 中重建完全相同的外觀。

```java
System.out.println("Font Family Name: " + criterion.getFont().getFontFamily());
System.out.println("Font Size: " + criterion.getFont().getSize());
System.out.println("Font Style: " + criterion.getFont().getStyle());
System.out.println("Ascending/Descending: " + criterion.getAscending());
```

## 常見問題與解決方案
| 問題 | 發生原因 | 解決方法 |
|------|----------|----------|
| **`NullPointerException` on `criterion.getParentGroup()`** | 此條件可能沒有父群組。 | 在存取父項目之前加入 null 檢查。 |
| **File not found** | `dataDir` 路徑不正確或檔名拼寫錯誤。 | 使用 `Paths.get(dataDir, "project.mpp").toAbsolutePath()` 並確認檔案是否存在。 |
| **License not set** | Aspose 以評估模式執行，可能會截斷輸出。 | 在載入專案之前使用 `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` 註冊授權。 |

## 常見問答

**Q: 我可以使用 Aspose.Tasks for Java 來修改專案檔案嗎？**  
A: 是的，該程式庫提供完整的讀寫功能，支援 Microsoft Project 格式，讓您能以程式方式新增工作項目、變更資源，並更新群組定義。

**Q: Aspose.Tasks for Java 是否相容所有版本的 Microsoft Project 檔案？**  
A: 它支援 MPP、XML、CSV 以及其他常見的 Project 格式，涵蓋從 Project 2000 到最新 2024 版的所有版本。

**Q: 使用 Aspose.Tasks for Java 時，該如何處理錯誤？**  
A: 將檔案操作包在 `try‑catch` 區塊中，捕捉 `TasksException` 以取得詳細錯誤資訊；檢查例外的 `getMessage()` 以獲取線索。

**Q: Aspose.Tasks for Java 是否提供匯出至其他格式的功能？**  
A: 當然可以——您可使用程式庫的專屬匯出 API，將檔案匯出為 PDF、XLSX、HTML 等格式。

**Q: 我可以在哪裡找到更多資源與支援？**  
A: 前往 [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/) 取得 API 參考，並至 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 參與社群討論。

## 結論
在本教學中，我們示範了 **如何讀取群組定義資料**，透過 Aspose.Tasks for Java 從 Microsoft Project 檔案中取得。只要載入 `Project`、列舉其 `TaskGroupCollection`，並檢查每個群組的條件、字型與顏色，即可建立自動化報告管線、遷移分組規則，或自信地驗證專案結構。此方法亦能擴展至包含數千個工作項目的大型專案，同時保持低記憶體使用量。

---

**最後更新：** 2026-10-26  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose

## 相關教學

- [如何使用 Aspose.Tasks for Java 讀取 Microsoft Project 的專案資訊](/tasks/java/project-properties/read-project-info/)
- [如何取得表格欄位並讀取 Aspose.Tasks 中的表格資料](/tasks/java/project-data-reading/read-table-data/)
- [讀取 Gantt 圖表 Java – 擷取特定 Gantt 資料](/tasks/java/project-data-reading/read-specific-gantt-chart-data/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}