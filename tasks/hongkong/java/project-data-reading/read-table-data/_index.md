---
date: 2025-12-18
description: 學習如何在 Java 中使用 Aspose.Tasks 獲取表格欄位並讀取表格資料。本教學示範如何從 Project 檔案中擷取表格資訊。
linktitle: Read Table Data from File in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何在 Aspose.Tasks 中取得表格欄位並讀取表格資料
url: /zh-hant/java/project-data-reading/read-table-data/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中取得表格欄位並讀取表格資料

## Introduction
在本教學中，您將了解 **如何從 Microsoft Project 檔案取得表格欄位**，並使用 Aspose.Tasks for Java 讀取表格資料。無論您是建立報告工具、遷移資料，或自動化專案分析，程式化提取表格資訊都能節省大量手動工作。我們將一步步說明整個流程——從環境設定到列印每個欄位的詳細資訊——讓您立即將此功能整合到自己的應用程式中。

## Quick Answers
- **「取得表格欄位」是什麼意思？** 它指的是取得在 Project 檢視表格中顯示的每一欄的定義（寬度、標題、對齊方式等）。  
- **需要哪個函式庫？** Aspose.Tasks for Java。  
- **開發時需要授權嗎？** 免費試用版可用於評估；正式上線則需要商業授權。  
- **可以讀取任何版本的 Project 表格嗎？** 可以，Aspose.Tasks 支援 Project 2003‑2016 以及更新的格式。  
- **還需要其他設定嗎？** 只要安裝 JDK 8 以上，並將 Aspose.Tasks JAR 放入 classpath 即可。

## Prerequisites
在開始之前，請確保您已具備以下條件：

1. **Java Development Kit (JDK)** – 已安裝 JDK 8 或更新版本。可從 Oracle 官方網站下載。  
2. **Aspose.Tasks for Java JAR** – 從[下載連結](https://releases.aspose.com/tasks/java/)取得最新程式庫，並加入專案的建置路徑。

## Import Packages
匯入套件

Import the necessary Aspose.Tasks classes:

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Table;
import com.aspose.tasks.TableField;
```

## Step 1: Set up the Data Directory
步驟 1：設定資料目錄

Define the folder that contains your *.mpp* file:

```java
String dataDir = "Your Data Directory";
```

Replace `"Your Data Directory"` with the absolute path on your machine (e.g., `C:/Projects/Data/`).

將 `"Your Data Directory"` 替換為您機器上的絕對路徑（例如 `C:/Projects/Data/`）。

## Step 2: Load the Project File
步驟 2：載入專案檔案

Create a `Project` instance by pointing to the Project file you want to examine:

```java
Project project = new Project(dataDir + "Project2003.mpp");
```

If your file has a different name or extension, adjust the string accordingly.

如果您的檔案名稱或副檔名不同，請相應調整字串。

## Step 3: Retrieve table information
步驟 3：取得表格資訊

Now we’ll **get table fields** and display each field’s properties:

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

The snippet prints the width, title, and alignment for every column in the default table, giving you a full picture of the **table fields** defined in the project.

此程式碼會列印預設表格中每一欄的寬度、標題與對齊方式，讓您完整了解專案中定義的 **表格欄位**。

## Why retrieve table information?
為什麼要取得表格資訊？

- **自動化** – 產生自訂報告，免除手動複製貼上。  
- **遷移** – 將舊版 Project 檔案的資料搬移至現代資料庫。  
- **驗證** – 確保專案範本符合組織標準。  

## Common Pitfalls & Tips
常見陷阱與技巧

- **空表格** – 若專案沒有表格，`project.getTables()` 可能為空。存取索引 `0` 前請先檢查清單大小。  
- **編碼問題** – 使用最新的 Aspose.Tasks 版本時，標題中的非 ASCII 字元會正確顯示。  
- **效能** – 載入極大型 *.mpp* 檔案可能佔用大量記憶體；對於龐大資料集，請考慮使用串流 API。  

## Conclusion
結論

依照上述步驟操作後，您已掌握如何使用 Aspose.Tasks for Java **取得表格欄位** 並讀取 Microsoft Project 檔案中的表格資料。此功能為您的 Java 應用程式開啟了強大的自動化情境、資料遷移管道與自訂報告解決方案的大門。

## FAQ's
常見問答

### Q: Aspose.Tasks 是否相容於所有版本的 Microsoft Project？
A: Aspose.Tasks 支援多個 Microsoft Project 版本，包括 Project 2003、2007、2010、2013 以及 2016。

### Q: 我可以修改表格資料並儲存回 Project 檔案嗎？
A: 可以，您可使用 Aspose.Tasks 以程式方式修改表格資料，並將變更儲存回原始的 Project 檔案。

### Q: Aspose.Tasks 在商業使用時是否需要另外的授權？
A: 是的，若在商業環境中使用，必須購買 Aspose.Tasks 授權。您可於[購買頁面](https://purchase.aspose.com/buy)取得授權。

### Q: Aspose.Tasks 是否提供免費試用？
A: 可以，您可從[發行頁面](https://releases.aspose.com/)下載 Aspose.Tasks 的免費試用版。

### Q: 我可以在哪裡取得 Aspose.Tasks 的協助與支援？
A: 您可前往[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)尋求社群與 Aspose 團隊的協助與支援。

## Additional Frequently Asked Questions
其他常見問答

**Q: 如何在多專案環境中讀取表格資料？**  
A: 針對每個專案分別使用 `new Project(path)` 載入，並對每個實例重複表格欄位提取的迴圈。

**Q: 我可以將取得的表格欄位匯出為 CSV 嗎？**  
A: 可以，列印欄位細節後，您可以寫入 `FileWriter`，或使用如 OpenCSV 的 CSV 函式庫。

**Q: Aspose.Tasks 能處理使用者自訂的表格嗎？**  
A: 當然可以。`project.getTables()` 集合同時包含預設表格與使用者自訂表格，您可依需求遍歷它們。

**Q: 若 Project 檔案受密碼保護該怎麼辦？**  
A: 使用接受 `LoadOptions` 物件的 `Project` 建構子，於其中指定密碼。

**Q: 有辦法只篩選可見的欄位嗎？**  
A: 檢查每個 `TableField` 的 `getVisible()` 方法（較新版本提供），即可判斷該欄位是否在 UI 中顯示。

---

**最後更新：** 2025-12-18  
**測試環境：** Aspose.Tasks for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}