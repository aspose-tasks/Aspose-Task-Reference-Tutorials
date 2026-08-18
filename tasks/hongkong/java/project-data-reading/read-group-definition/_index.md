---
date: 2026-02-18
description: 學習如何使用 Aspose.Tasks for Java 從 Microsoft Project 檔案中讀取群組定義資料。本教學示範如何讀取群組詳細資訊並提取任務分組資訊。
linktitle: Read Group Definition Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何在 Aspose.Tasks 中讀取群組定義資料
url: /zh-hant/java/project-data-reading/read-group-definition/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 讀取 Aspose.Tasks 中的群組定義資料

## 介紹
Aspose.Tasks for Java 是一個功能強大的函式庫，讓開發人員能輕鬆操作 Microsoft Project 檔案。在本教學中，**您將一步步學會如何讀取群組定義**資料，從而在 Java 應用程式中擷取與處理工作群組資訊。了解**如何讀取群組**細節，可協助您自動化報表、遷移設定，以及以程式方式驗證專案結構。

## 快速回答
- **「讀取群組定義」是什麼意思？** 指的是從 Microsoft Project 檔案中抽取工作群組（名稱、條件、格式）的定義。  
- **需要哪個函式庫？** Aspose.Tasks for Java。  
- **需要授權嗎？** 開發階段可使用免費試用版；正式上線需購買商業授權。  
- **支援哪些 IDE？** 任何 Java IDE，例如 IntelliJ IDEA 或 Eclipse。  
- **需要多少程式碼？** 不到 30 行 Java 程式碼即可載入專案並顯示群組細節。

## 如何讀取群組定義資料
以下是一個簡潔的逐步說明，展示**如何讀取群組**資訊（.mpp 檔案）。每一步都有簡短說明，並附上您需要執行的完整程式碼。

## 什麼是讀取群組定義？
Microsoft Project 中的*群組定義*描述了依照某些條件（例如狀態、優先順序）將工作項目分組的方式。讀取此定義可讓您以程式方式檢查分組邏輯、顏色、字型以及排序順序。

## 為什麼要讀取群組定義資料？
- **自動化：** 產生與 Project 中相同分組方式的自訂報表。  
- **遷移：** 將分組規則搬移至其他專案或不同的專案管理系統。  
- **驗證：** 在執行批次更新前，確保預期的群組已存在。  
- **客製化：** 依據群組的字型或顏色設定套用額外的業務邏輯。  
- **洞察：** 瞭解**如何讀取群組**資料有助於排除工作項目排列異常的問題。

## 前置條件
在開始之前，請確保您已具備以下項目：

1. **Java Development Kit (JDK)** – 任意近期版本（8 或更新）。  
2. **Aspose.Tasks for Java Library** – 從 [此處](https://releases.aspose.com/tasks/java/) 下載。  
3. **IDE** – IntelliJ IDEA、Eclipse，或您慣用的任何編輯器。  

## 匯入套件
首先，匯入 Aspose.Tasks 的核心套件：

```java
import com.aspose.tasks.*;
```

## 步驟說明

### 步驟 1：設定資料目錄
定義包含欲檢查的 `.mpp` 檔案的資料夾路徑。

```java
String dataDir = "Your Data Directory";
```

將 `"Your Data Directory"` 替換為專案檔案所在的絕對路徑。

### 步驟 2：載入專案檔案
建立指向 `.mpp` 檔案的 `Project` 實例。

```java
Project project = new Project(dataDir + "project.mpp");
```

### 步驟 3：取得工作群組總數
印出專案中定義的工作群組總數。

```java
System.out.println("Task Groups Count: " + project.getTaskGroups().size());
```

### 步驟 4：取得特定工作群組資訊
取得範例中的第 1 個群組（索引 1），並顯示其名稱與條件數量。

```java
Group taskGroup = project.getTaskGroups().toList().get(1);
System.out.println("Percent Complete:" + taskGroup.getName());
System.out.println("Group Criteria count: " + taskGroup.getGroupCriteria().size());
```

### 步驟 5：取得群組條件資訊
每個群組可包含一或多個條件。以下程式碼擷取用於分組的欄位、分組模式、儲存格顏色與圖案等細節。

```java
GroupCriterion criterion = taskGroup.getGroupCriteria().toList().get(0);
System.out.println("Criterion Field: " + criterion.getField());
System.out.println("Criterion GroupOn: " + criterion.getGroupOn());
System.out.println("Criterion Cell Color: " + criterion.getCellColor());
System.out.println("Criterion Pattern: " + criterion.getPattern());
```

### 步驟 6：檢查父群組
有時條件屬於父群組，此檢查可確認兩者之間的關係。

```java
if (taskGroup == criterion.getParentGroup())
    System.out.println("Parent Group is equval to task Group.");
```

### 步驟 7：取得條件的字型資訊
群組條件可以自訂字型樣式。以下程式碼印出字型族、大小、樣式與排序方向。

```java
System.out.println("Font Family Name: " + criterion.getFont().getFontFamily());
System.out.println("Font Size: " + criterion.getFont().getSize());
System.out.println("Font Style: " + criterion.getFont().getStyle());
System.out.println("Ascending/Descending: " + criterion.getAscending());
```

## 常見問題與解決方案
| 問題 | 為何會發生 | 解決方式 |
|------|------------|----------|
| **`NullPointerException` on `criterion.getParentGroup()`** | 該條件可能沒有父群組。 | 在比較前加入 null 檢查。 |
| **File not found** | `dataDir` 路徑不正確。 | 使用 `Paths.get(dataDir, "project.mpp").toAbsolutePath()` 進行驗證。 |
| **License not set** | Aspose 函式庫處於評估模式，可能限制輸出。 | 使用 `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` 註冊授權。 |

## 常見問答

**Q: 可以使用 Aspose.Tasks for Java 來修改專案檔案嗎？**  
A: 可以，該函式庫提供完整的讀寫功能，支援 Microsoft Project 檔案。

**Q: Aspose.Tasks for Java 是否相容所有版本的 Microsoft Project 檔案？**  
A: 支援 MPP、XML 以及其他常見的 Project 格式，涵蓋多個版本。

**Q: 如何在使用 Aspose.Tasks for Java 時處理錯誤？**  
A: 將檔案操作包在 `try‑catch` 區塊，並檢查 `TasksException` 以取得詳細訊息。

**Q: Aspose.Tasks for Java 是否提供將專案資料匯出至其他格式的功能？**  
A: 當然可以 – 您可以使用匯出 API 將資料匯出為 PDF、XLSX、CSV 等格式。

**Q: 哪裡可以找到 Aspose.Tasks for Java 的其他資源與支援？**  
A: 前往 [Aspose.Tasks for Java 文件](https://reference.aspose.com/tasks/java/) 取得完整 API 參考，或至 [Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15) 取得社群協助。

## 結論
本教學示範了**如何讀取群組**定義資料，從 Microsoft Project 檔案中使用 Aspose.Tasks for Java 取得群組名稱、條件、格式與父群組關係。依循上述步驟，您即可在 Java 應用程式中抽取群組資訊，進而建立自訂報表、遷移設定或自動化驗證邏輯。

---

**最後更新：** 2026-02-18  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}