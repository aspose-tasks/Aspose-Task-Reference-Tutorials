---
date: 2026-02-15
description: 學習如何在 Java 中讀取 Access 資料庫、將 Access 轉換為 XML，並使用 Aspose.Tasks for Java
  匯出 MS Project XML。
linktitle: Reading Project Data from Microsoft Access Database with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks 將 Java Access DB 讀取為 XML
url: /zh-hant/java/project-data-reading/read-access-database/
weight: 11
---

遷移流程中。"

Make sure bold markers.

Then horizontal rule.

"Last Updated:" keep date.

"Tested With:" etc.

Translate labels: "最後更新：" "測試環境：" "作者：" maybe keep English? The instruction: translate all text content naturally. So translate.

"Last Updated: 2026-02-15" => "最後更新：2026-02-15"

"Tested With: Aspose.Tasks for Java (latest)" => "測試環境：Aspose.Tasks for Java（最新）"

"Author: Aspose" => "作者：Aspose"

Then closing shortcodes.

Make sure to keep all shortcodes unchanged.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何讀取 Access：Java Access DB 轉 XML 使用 Aspose.Tasks

## 介紹
如果您需要 **如何讀取 Access** 資料，這些資料儲存在舊版 Microsoft Access 資料庫中，並將其轉換為現代的 Microsoft Project XML 檔案，您來對地方了。在本教學中，我們將逐步說明如何從 Java 連接 Access 檔案、使用 Aspose.Tasks 取得專案資訊、**將 Access 轉換為 XML**，以及最終 **將專案另存為 XML**，讓其他工具可以使用。完成後，您將擁有一段可在 Windows、Linux 或 macOS 上重複使用的程式碼片段。

## 快速回答
- **本教學涵蓋什麼？** 從 Access DB 讀取 MS Project 資料並使用 Aspose.Tasks 匯出為 XML。  
- **需要哪個函式庫？** Aspose.Tasks for Java（最新版本）。  
- **是否需要授權？** 在正式環境使用需取得臨時或正式授權。  
- **可以將 Access 轉換為 XML 嗎？** 是的 – `MpdSettings` 類別會自動處理轉換。  
- **支援 Java 8 以上嗎？** 當然，任何 JDK 8 或更新版本皆可使用。

## “如何讀取 Access” 是什麼意思？
在 Java 環境中，**如何讀取 Access** 指的是為 Access（.mdb/.accdb）檔案建立正確的 JDBC 風格連接字串，取得儲存的專案資料列，然後將這些資料傳入能理解 Microsoft Project 結構的函式庫。Aspose.Tasks 會抽象化繁重的工作，讓您專注於轉換邏輯。

## 為什麼要使用 Aspose.Tasks 完成此任務？
- **無需 COM 互操作** – 不需要在伺服器上安裝 Microsoft Project。  
- **直接資料庫存取** – `MpdSettings` 直接讀取 Access 檔案，無需中間匯出步驟。  
- **內建轉換** – 自動 **將 Access 轉換為 XML** 並 **匯出 MS Project XML**。  
- **跨平台** – 在 Windows、Linux 與 macOS 上皆可相同運作。  

## 前置條件
- **Java Development Kit (JDK)** – 已安裝 JDK 8 或更新版本。  
- **Aspose.Tasks for Java 函式庫** – 從官方網站下載。請依照[下載連結](https://releases.aspose.com/tasks/java/)取得函式庫，並將其加入專案的 classpath。  

## 匯入套件
首先，匯入能處理專案與資料庫連線的類別。
```java
import com.aspose.tasks.MpdSettings;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.IOException;
```

## 如何使用 Aspose.Tasks 讀取 Access 資料庫？
以下為逐步說明。每個步驟在程式碼區塊前都有簡易說明，讓您清楚了解發生了什麼。

### 步驟 1：定義資料目錄
設定最終 XML 檔案要儲存的資料夾。將佔位符替換為實際路徑。
```java
String dataDir = "Your Data Directory";
```

### 步驟 2：定義 MpdSettings
建立一個 `MpdSettings` 實例，內含連接字串以及要讀取的專案識別碼（此處 `1` 代表第一筆專案記錄）。這是 **讀取 Access 資料庫 Java** 的核心。
```java
MpdSettings settings = new MpdSettings(getConnectionString(), 1);
```

> **小技巧：** 如果您需要為多個專案 **讀取 MS Project Access** 資料，請遍歷各 ID，並為每次迭代建立新的 `MpdSettings`。

### 步驟 3：從資料庫載入專案
將 `MpdSettings` 物件傳入 `Project` 建構子。Aspose.Tasks 會直接從 Access 檔案取得專案資料。
```java
Project project = new Project(settings);
```

### 步驟 4：儲存專案資料
最後，將載入的專案匯出為 XML 檔案。此步驟 **匯出 MS Project XML** 讓其他工具可以使用，同時也 **將專案另存為 XML** 到磁碟。
```java
project.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| *連接字串錯誤* | 請確認 Access 檔案路徑，並確保機器已安裝 Jet/ACE OLEDB 提供程式。 |
| *儲存時權限被拒* | 確保 `dataDir` 資料夾存在且應用程式具有寫入權限。 |
| *專案顯示為空* | 確認已將正確的專案 ID 傳遞給 `MpdSettings`。可使用資料庫檢視器檢查 `ProjectID` 欄位。 |

## 常見問答
### Q: 我可以在 Java 中使用 Aspose.Tasks 搭配除 Microsoft Access 之外的其他資料庫系統嗎？  
A: 可以，Aspose.Tasks 支援多種資料庫系統，例如 SQL Server、MySQL 與 Oracle。

### Q: 是否提供 Aspose.Tasks for Java 的免費試用？  
A: 是的，您可以從[此處](https://releases.aspose.com/)取得免費試用。

### Q: 如何取得 Aspose.Tasks for Java 的技術支援？  
A: 您可以從[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)取得技術支援。

### Q: 使用 Aspose.Tasks for Java 是否需要臨時授權？  
A: 某些進階功能可能需要臨時授權。請從[此處](https://purchase.aspose.com/temporary-license/)取得。

### Q: 在哪裡可以購買 Aspose.Tasks for Java？  
A: 您可以從[此連結](https://purchase.aspose.com/buy)購買。

## 結論
您現在擁有一個完整、可投入生產的範例，說明如何 **如何讀取 Access** 資料、**將 Access 轉換為 XML**，以及使用 Aspose.Tasks for Java **將專案另存為 XML**。隨時可以將此程式碼片段調整為批次處理，或整合到更大的遷移流程中。

---

**最後更新：** 2026-02-15  
**測試環境：** Aspose.Tasks for Java（最新）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}