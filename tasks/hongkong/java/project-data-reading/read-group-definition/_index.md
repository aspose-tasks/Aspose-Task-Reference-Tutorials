---
date: 2025-12-11
description: 學習如何使用 Aspose.Tasks for Java 從 Microsoft Project 檔案中讀取群組定義資料。請跟隨我們的逐步教學。
linktitle: Read Group Definition Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 在 Aspose.Tasks 中讀取群組定義資料
url: /zh-hant/java/project-data-reading/read-group-definition/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 讀取 Aspose.Tasks 中的群組定義資料

## 介紹
Aspose.Tasks for Java 是一個功能強大的函式庫，可讓開發人員輕鬆操作 Microsoft Project 檔案。在本教學中，**您將一步步學會如何讀取專案檔案中的群組定義**，以便在 Java 應用程式中擷取並使用任務群組資訊。

## 快速回答
- **「讀取群組意思？** 指的是從 Microsoft Project 檔案中抽取任務群組（名稱、條件、格式）的定義。  
- **需要哪個函式庫？** Aspose.Tasks for Java。  
- **需要授權嗎？** 開發階段可使用免費試用版；正式上線需購買商業授權。  
- **支援哪些 IDE？** 任何 Java IDE，例如 IntelliJ IDEA 或 Eclipse。  
- **需要多少程式碼？** 不到 30 行 Java 程式碼即可載入專案並顯示群組詳細資訊。

## 什麼是讀取群組定義？
Microsoft Project 中的*群組定義*描述了任務如何依據特定條件（例如狀態、優先順序）被分組。讀取此定義可讓您以程式方式檢查分組邏輯、顏色、字型以及排序順序等設定。

## 為什麼要讀取群組定義資料？
- **自動化：** 產生與 Project 中相同分組方式的自訂報表。  
- **遷移：** 將分組規則搬移至其他專案或不同的專案管理系統。  
- **驗證：** 在執行大量更新前，確保預期的群組已存在。  
- **客製化：** 根據群組的字型或顏色設定套用額外的業務邏輯。

## 前置條件
在開始之前，請確保您已具備以下項目：

1. **Java Development Kit (JDK)** – 任意近期版本（8 以上）。  
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

### 步驟 3：取得任務群組總數
印出專案中已定義的任務群組總數。

```java
System.out.println("Task Groups Count: " + project.getTaskGroups().size());
```

### 步驟 4：取得特定任務群組資訊
取得範例中索引為 1 的群組，並顯示其名稱與條件數量。

```java
Group taskGroup = project.getTaskGroups().toList().get(1);
System.out.println("Percent Complete:" + taskGroup.getName());
System.out.println("Group Criteria count: " + taskGroup.getGroupCriteria().size());
```

### 步驟 5：取得群組條件資訊
每個群組可包含一個或多個條件。以下程式碼抽取分組欄位、分組模式、儲存格顏色與圖案等細節。

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
群組條件可以自訂字型樣式。以下程式碼列印字型族、大小、樣式與排序方向。

```java
System.out.println("Font Family Name: " + criterion.getFont().getFontFamily());
System.out.println("Font Size: " + criterion.getFont().getSize());
System.out.println("Font Style: " + criterion.getFont().getStyle());
System.out.println("Ascending/Descending: " + criterion.getAscending());
```

## 常見問題與解決方案
| 問題 | 為何會發生 | 解決方式 |
|------|------------|----------|
| **`NullPointerException` 於 `criterion.getParentGroup()`** | 該條件可能沒有父群組。 | 在比較前加入 null 檢查。 |
| **找不到檔案** | `dataDir` 路徑不正確。 | 使用 `Paths.get(dataDir, "project.mpp").toAbsolutePath()` 進行驗證。 |
| **未設定授權** | Aspose 函式庫處於評估模式，可能限制輸出。 | 使用 `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` 註冊授權。 |

## 常見問答

**Q: 我可以使用 Aspose.Tasks for Java 來修改專案檔案嗎？**  
A: 可以，該函式庫提供完整的讀寫功能。

**Q: Aspose.Tasks for Java 是否相容所有版本的 Microsoft Project 檔案？**  
A: 支援 MPP、XML 以及其他常見的 Project 格式，涵蓋多個版本。

**Q: 在使用 Aspose.Tasks for Java 時，如何處理錯誤？**  
A: 將檔案操作包在 `try‑catch` 區塊，並檢查 `TasksException` 以取得詳細訊息。

**Q: Aspose.Tasks for Java 是否提供將專案資料匯出為其他格式的支援？**  
A: 當然可以 – 您可以使用函式庫的匯出 API 輸出為 PDF、XLSX、CSV 等格式。

**Q: 我可以在哪裡找到 Aspose.Tasks for Java 的其他資源與支援？**  
A: 前往 [Aspose.Tasks for Java 文件](https://reference.aspose.com/tasks/java/) 取得完整 API 參考，或至 [Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15) 取得社群協助。

## 結論
本教學示範了如何使用 Aspose.Tasks for Java **讀取 Microsoft Project 檔案中的群組定義** 資料。依循上述步驟，您即可抽取群組名稱、條件、格式與父群組關係，進而在 Java 應用程式中建立自訂報表、遷移設定或自動化驗證邏輯。

---

**最後更新：** 2025-12-11  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}