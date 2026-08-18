---
date: 2026-02-18
description: 學習如何將專案儲存為 PDF，並使用 Aspose.Tasks for Java 讀取 Microsoft Project 資料庫；此外，還可連接
  Project Server、將專案轉換為 HTML，以及匯出專案為 XML。
linktitle: Reading Project Data from Microsoft Project Database in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 將專案另存為 PDF，並使用 Aspose.Tasks for Java 讀取 Project DB
url: /zh-hant/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 將專案另存為 PDF 並使用 Aspose.Tasks for Java 讀取 Microsoft Project 資料庫

## 介紹
在本教學中，您將學會如何直接從 Microsoft Project Server **讀取 Microsoft Project 資料庫**，再使用 Aspose.Tasks Java API **將專案另存為 PDF**。無論您是需要產生報表、遷移資料，或是將專案資訊整合到自家應用程式，本指南都會一步步說明——從設定資料庫連線到匯出專案為 PDF、XML 或 HTML。完成後，您將擁有一套可直接在未安裝 Microsoft Project 的主機上執行的生產就緒解決方案。

## 快速答覆
- **Aspose.Tasks 的功能是什麼？** 提供純 Java API 以讀取、寫入與操作 Microsoft Project 檔案與資料庫。  
- **需要安裝 Microsoft Project 嗎？** 不需要，Aspose.Tasks 可獨立於 Microsoft Project 執行。  
- **支援哪種資料庫類型？** Microsoft SQL Server（Project Server 的後端）。  
- **可以匯出成其他格式嗎？** 可以，除了 PDF，還能儲存為 XML、HTML、CSV 等。  
- **主要前置條件是什麼？** JDK、Aspose.Tasks for Java 套件、SQL Server JDBC 驅動程式，以及 **連線至 Project Server** 的憑證。

## 什麼是「讀取 Microsoft Project 資料庫」？
讀取 Microsoft Project 資料庫即是連接至 Project Server 的 SQL Server 資料庫，擷取已儲存的專案資料，並將其載入 Aspose.Tasks 可操作的 `Project` 物件。此方式特別適合自動化報表、資料遷移或自訂分析。

## 為什麼使用 Aspose.Tasks for Java？
- **無需 Microsoft Project 依賴** ─ 可在任何伺服器或 CI 環境執行。  
- **豐富的物件模型** ─ 可程式化存取工作、資源、指派、行事曆與自訂欄位。  
- **多種匯出選項** ─ 只需一次 API 呼叫即可輸出 PDF、XML、HTML、PNG 等。  
- **高效能** ─ 為大型企業專案進行最佳化。

## 前置條件
在開始之前，請確保您已具備以下項目：

1. 可正常運作的 Java 開發環境（JDK 8 或更新版本）。  
2. 已將 Aspose.Tasks for Java 套件加入專案的 classpath。  
3. 用於 **連線至 Project Server** 的 SQL 資料庫憑證（伺服器名稱、埠號、資料庫名稱、使用者名稱、密碼）。  
4. Microsoft JDBC Driver for SQL Server（例如 `sqljdbc4.jar`）。

## 匯入套件
首先，匯入所需的類別。以下清單包含 Aspose.Tasks 核心類別與標準 Java 工具。

```java
import com.aspose.tasks.MspDbSettings;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.File;
import java.lang.reflect.Method;
import java.net.URL;
import java.net.URLClassLoader;
import java.util.UUID;
```

## 如何連線至 Project Server
建立可靠的連線是讀取專案資料的基礎。請確保 Java 主機能夠連到 SQL Server 執行個體，且使用的登入帳號在 Project Server 資料庫上具備 **SELECT** 權限。

## 步驟 1：設定資料庫連線
建立 `MspDbSettings` 例項，內含 JDBC 連線字串。將佔位值替換為實際的伺服器資訊。

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **小技巧：** 請將連線字串存放於安全的組態檔或環境變數中，避免在程式碼內硬編碼憑證。

## 步驟 2：加入 JDBC 驅動程式
在執行期間載入 Microsoft SQL Server JDBC 驅動程式，讓 JVM 能與資料庫通訊。

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **警告：** 請確認驅動程式版本與您的 SQL Server 版本相符。使用不相容的驅動程式可能導致連線失敗。

## 步驟 3：讀取專案資料
以 `MspDbSettings` 為參數建立 `Project` 物件，Aspose.Tasks 會自動從資料庫取得專案資料。

```java
Project project = new Project(settings);
```

此時您即可探索 `project` 物件──列出工作、資源，或依需求修改欄位。

## 步驟 4：將專案另存為 PDF
將載入的專案匯出為您選擇的檔案格式。以下範例將專案儲存為 **PDF**，非常適合列印報表。若要 **匯出為 XML** 或 **轉換為 HTML**，只需更改 `SaveFileFormat` 列舉值。

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

若想輸出為 XML，只需將 `SaveFileFormat.Pdf` 改為 `SaveFileFormat.Xml`。輸出為 HTML 時，使用 `SaveFileFormat.Html`。

## 常見問題與解決方案
| 問題 | 常見原因 | 解決方式 |
|------|----------|----------|
| **連線逾時** | 伺服器/埠號錯誤或防火牆阻擋 | 核對伺服器位址，開放 1433 埠，並使用簡易 JDBC 測試程式驗證連線。 |
| **驗證錯誤** | 使用者名稱/密碼不正確，或 SQL Server 未啟用 SQL 驗證 | 使用有效的 SQL 登入，或在伺服器上啟用混合模式驗證。 |
| **找不到驅動程式** | JDBC jar 未放入 classpath | 確認 `addJDBCDriver` 指向正確的 `.jar` 檔，且路徑使用雙反斜線 (`\\`)。 |
| **載入後專案為空** | 權限不足，無法讀取 Project Server 資料表 | 為登入帳號授予 Project Server 資料庫模式的 SELECT 權限。 |

## 常見問答

**Q: Aspose.Tasks 能否從除 Microsoft Project 之外的其他資料庫讀取專案資料？**  
A: 可以，Aspose.Tasks 支援從多種來源讀取專案資料，包括 XML 檔、Primavera 以及 Microsoft Project 資料庫。

**Q: Aspose.Tasks 與不同版本的 Microsoft Project 相容嗎？**  
A: 相容，Aspose.Tasks 設計能與多個 Microsoft Project 版本協同運作，確保無縫整合。

**Q: 我可以在儲存之前操作專案資料嗎？**  
A: 當然可以，Aspose.Tasks 提供完整的 API 讓您新增工作、更新資源、設定專案屬性等，然後再匯出。

**Q: Aspose.Tasks 支援哪些輸出格式？**  
A: 支援 PDF、XML、HTML、CSV、PNG、JPEG 等多種格式。

**Q: 我該去哪裡取得更多支援或協助？**  
A: 可前往 Aspose.Tasks 論壇或參考網站上的文件，連結如下：[here](https://forum.aspose.com/c/tasks/15)。

## 結論
透過本步驟指南，您已學會如何 **讀取 Microsoft Project 資料庫**、**將專案另存為 PDF**，以及使用 Aspose.Tasks for Java 匯出其他格式。此方法免除對 Microsoft Project 的依賴，簡化自動化報表流程，並為強大的自訂整合開啟可能。

---

**最後更新：** 2026-02-18  
**測試環境：** Aspose.Tasks for Java 24.5（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}