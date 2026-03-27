---
date: 2025-12-25
description: 探索此 Aspose Tasks Java 教程，了解如何判斷 MS Project 檔案的專案版本。提供逐步說明及程式碼範例。
linktitle: Determine Project Version with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose Tasks Java 教學 - 判斷 MS Project 版本
url: /zh-hant/java/project-management/determine-version/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose Tasks Java 教學：判斷 MS Project 版本

## 簡介
在本 **aspose tasks java tutorial** 中，您將學會如何使用 Aspose.Tasks for Java 程式化地取得 Microsoft Project 檔案的版本。了解檔案版本有助於處理相容性問題、執行遷移政策，或僅僅記錄是哪個 Project 版本建立的檔案。我們將一步步說明——從環境設定到列印版本與最後儲存日期——讓您能自信地將此檢查整合至任何 Java 應用程式。

## 快速解答
- **本教學涵蓋什麼內容？** 使用 Aspose.Tasks for Java 判斷 MS Project 檔案版本。  
- **需要安裝 Microsoft Project 嗎？** 不需要，Aspose.Tasks 可獨立運作。  
- **支援哪些檔案格式？** 基於 XML 的 Project 檔案（MPP、XML 等）。  
- **實作大約需要多久？** 基本檢查約 5‑10 分鐘即可完成。  
- **需要授權嗎？** 評估可使用免費試用版；正式環境需購買授權。

## 什麼是 Aspose Tasks Java 教學？
**aspose tasks java tutorial** 為您提供在 Java 專案中使用 Aspose.Tasks API 的實作指引，示範如何在不安裝 Microsoft Project 的情況下讀取、修改與分析 Microsoft Project 資料。

## 為什麼使用 Aspose.Tasks 來確定專案版本？
- **無需依賴 Microsoft Project** ─ 適合伺服器端自動化。  
- **精確的版本資訊** ─ 取得正確的 SAVE_VERSION 與 LAST_SAVED 欄位。  
- **跨平台** ─ 只要支援 Java 的作業系統皆可使用。  
- **高效能** ─ 輕量級解析，適合批次處理。

## 前提條件
在開始之前，請確保您已具備以下項目：

1. **Java Development Kit (JDK)** ─ 任意近期版本（8 以上）。  
2. **Aspose.Tasks for Java JAR** ─ 從 [website](https://releases.aspose.com/tasks/java/) 下載，並加入專案 classpath。  
3. **MS Project 檔案** ─ 以 XML 為基礎的 Project 檔（例如 `input.xml`），即您欲檢查的檔案。  

> **Pro tip:** 將 Project 檔放在專屬的 `data` 資料夾中，可簡化路徑管理。

## 導入包
首先，匯入必要的 Aspose.Tasks 類別：

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## 步驟 1：設定專案目錄
定義存放 Project 檔案的資料夾。

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

將 `"Your Data Directory"` 替換為 `input.xml` 所在的絕對或相對路徑。

## 步驟 2：載入項目
透過載入 XML 檔案建立 `Project` 實例。

```java
Project project = new Project(dataDir + "input.xml");
```

若檔名不同，請相應調整 `"input.xml"`。

## 步驟 3：如何確定專案版本
取得版本資訊與最後儲存的時間戳記。

```java
//Display project version property
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```

`Prj.SAVE_VERSION` 屬性會顯示儲存檔案時所使用的 Microsoft Project 版本（例如 12 代表 Project 2010）。`Prj.LAST_SAVED` 會回傳最近一次儲存的日期/時間。

## 步驟 4：顯示結果
顯示版本檢查成功的訊息。

```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```

## 常見問題及解決方案
| 問題 | 原因 | 解決方法 |
|-------|--------|-----|
| `NullPointerException` on `project.get(...)` | 找不到檔案或路徑不正確 | 檢查 `dataDir` 與檔名；測試時使用絕對路徑。 |
| Unexpected version number (e.g., 0) | 載入的不是 Project XML 檔案 | 確認檔案為有效的 Microsoft Project 檔（MPP/XML）。 |
| License exception | 在正式環境使用試用版未授權 | 套用 Aspose.Tasks 授權 (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`)。 |

## 常見問題解答

### 問：我可以將 Aspose.Tasks 與其他程式語言一起使用嗎？

答：可以，Aspose.Tasks 支援多種語言，包括 .NET、Java 和 C++。

### 問：Aspose.Tasks 適合大型專案嗎？

答：當然適合，Aspose.Tasks 的設計旨在輕鬆處理任何規模的專案。

### 問：我可以使用 Aspose.Tasks 自訂專案資料嗎？

答：可以，您可以使用 Aspose.Tasks 操作專案資料、修改任務、資源等等。

### 問：Aspose.Tasks 需要安裝 Microsoft Project 嗎？

答：不需要，Aspose.Tasks 可以獨立運行，無需安裝 Microsoft Project。

### 問：Aspose.Tasks 有提供技術支援嗎？

答：是的，您可以從 Aspose.Tasks 論壇[此處](https://forum.aspose.com/c/tasks/15)取得技術支援。

### 其他問答

**問：如何取得其他項目屬性（例如，作者、公司）？ ** 答：使用 `project.get(Prj.AUTHOR)` 或 `project.get(Prj.COMPANY)`，類似於版本範例。

**問：我可以查看 MPP 檔案（二進位格式）的版本嗎？ ** 答：是的，Aspose.Tasks 可以直接載入 `.mpp` 檔案；可以使用相同的 `Prj.SAVE_VERSION` 屬性。

Q：有沒有辦法透過程式設計方式將舊專案文件升級到新版本？答：載入舊文件，然後使用 `project.save("newfile.mpp", SaveFileFormat.MPP);` 儲存它－Aspose.Tasks 預設會將其寫入最新格式。

## 結論
您已完成本 **aspose tasks java tutorial**，學會如何使用 Aspose.Tasks for Java **判斷 MS Project 檔案的版本**。將此程式碼片段整合至更大的自動化工作流程、報表工具或遷移工具，即可隨時掌握所處理的 Project 版本。

---

**Last Updated:** 2025-12-25  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}