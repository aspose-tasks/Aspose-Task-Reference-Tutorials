---
date: 2025-12-13
description: 學習如何使用 Aspose.Tasks for Java 讀取 Microsoft Project 資料庫。逐步指南，附程式碼範例與最佳實踐。
linktitle: Reading Project Data from Microsoft Project Database in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks for Java 讀取 Microsoft Project 數據庫
url: /zh-hant/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks for Java 讀取 Microsoft Project 資料庫

## 簡介
在本教學中，您將學會如何直接從 Microsoft Project Server 使用 Aspose.Tasks Java API **讀取 Microsoft Project 資料庫**。無論您是需要產生報表、遷移資料，或是將專案資訊整合到自家應用程式，都可以依循本指南的每一步——從設定資料庫連線到將專案匯出為 XML。完成後，您將擁有一套可在未安裝 Microsoft Project 的主機上執行的完整、可投入生產環境的解決方案。

## 快速解答
- **Aspose.Tasks 的功能是什麼？** 提供純 Java API 以讀取、寫入與操作 Microsoft Project 檔案與資料庫。  
- **需要安裝 Microsoft Project 嗎？** 不需要，Aspose.Tasks 可獨立於 Microsoft Project 執行。  
- **支援哪種資料庫類型？** Microsoft SQL Server（Project Server 的後端）。  
- **可以匯出成其他格式嗎？** 可以，除了 XML，還支援 PDF、HTML、CSV 等多種格式。  
- **主要前置條件是什麼？** JDK、Aspose.Tasks for Java 套件，以及 SQL Server JDBC 驅動程式。

## 什麼是「讀取 Microsoft Project 資料庫」？
讀取 Microsoft Project 資料庫即是連接至 Project Server 的 SQL Server 資料庫，擷取其中儲存的專案資料，並將其載入 Aspose.Tasks 可操作的 `Project` 物件。此方式特別適合自動化報表、資料遷移或自訂分析。

## 為什麼選擇 Aspose.Tasks for Java？
- **無需 依賴** ─ 可在任何伺服器或 CI 環境執行。  
- **完整物件模型** ─ 可程式化存取工作、資源、指派、行事曆與自訂欄位。  
- **多種匯出選項** ─ 只需一次 API 呼叫即可輸出 XML、PDF、HTML、PNG 等。  
- **高效能** ─ 為大型企業專案進行最佳化。

## 前置條件
在開始之前，請確保您已具備以下項目：

1. 可正常運作的 Java 開發環境（JDK 8 或更新版本）。  
2. 已將 Aspose.Tasks for Java 套件加入專案的 classpath。  
3. 取得 Project Server SQL 資料庫的存取憑證（伺服器名稱、埠號、資料庫名稱、使用者名稱、密碼）。  
4. Microsoft JDBC Driver for SQL Server（例如 `sqljdbc4.jar`）。

## 匯入套件
首先，匯入您將會使用的類別。以下清單包含 Aspose.Tasks 核心類別與標準 Java 工具類。

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

## 步驟 1：設定資料庫連線
建立 `MspDbSettings` 實例，內含 JDBC 連線字串。請將佔位符替換為實際的伺服器資訊。

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **小技巧：** 建議將連線字串存放於安全的設定檔或環境變數中，避免在程式碼內硬編碼憑證。

## 步驟 2：加入 JDBC 驅動程式
在執行期間載入 Microsoft SQL Server JDBC 驅動程式，使 JVM 能與資料庫通訊。

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **警告：** 請確認驅動程式版本與您的 SQL Server 版本相符。使用不相容的驅動程式可能導致連線失敗。

## 步驟 3：讀取專案資料
以 `MspDbSettings` 為參數建立 `Project` 物件，Aspose.Tasks 會自動從資料庫擷取專案資料。

```java
Project project = new Project(settings);
```

此時您即可探索 `project` 物件──列出工作、資源，或依需求修改欄位。

## 步驟 4：儲存專案資料
將載入的專案匯出為您選擇的檔案格式。以下範例將專案保存為 XML，之後可匯入 Microsoft Project 或進一步處理。

```java
project.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```

若需其他報表格式，只要將 `SaveFileFormat.Xml` 改為 `Pdf`、`Html`、`Csv` 等即可。

## 常見問題與解決方案
| 問題 | 常見原因 | 解決方式 |
|------|----------|----------|
| **連線逾時** | 伺服器/埠號錯誤或防火牆阻擋 | 確認伺服器位址，開放 1433 埠，並使用簡易 JDBC 測試程式驗證連線。 |
| **驗證錯誤** | 使用者名稱/密碼無效，或 SQL Server 未啟用 SQL 驗證 | 使用有效的 SQL 登入帳號，或在伺服器上啟用混合模式驗證。 |
| **找不到驅動程式** | JDBC jar 未加入 classpath | 確認 `addJDBCDriver` 指向正確的 `.jar` 檔案，且路徑使用雙反斜線 (`\\`)。 |
| **載入後專案為空** | 權限不足，無法讀取 Project Server 資料表 | 為登入帳號授予 Project Server 資料庫結構的 SELECT 權限。 |

## 常見問答

**Q: Aspose.Tasks 能否從 Microsoft Project 以外的資料庫讀取專案資料？**  
A: 可以，Aspose.Tasks 支援從多種來源讀取專案資料，包括 XML 檔案、Primavera 以及 Microsoft Project 資料庫。

**Q: Aspose.Tasks 與不同版本的 Microsoft Project 相容嗎？**  
A: 相容，Aspose.Tasks 設計可支援多個 Microsoft Project 版本，確保無縫整合。

**Q: 我可以在儲存之前操作專案資料嗎？**  
A: 當然可以，Aspose.Tasks 提供完整的 API 讓您新增工作、更新資源、設定專案屬性等，然後再匯出。

**Q: Aspose.Tasks 支援哪些輸出格式？**  
A: 支援 XML、PDF、HTML、CSV、PNG、JPEG 等多種格式。

**Q: 我該去哪裡取得更多支援或協助？**  
A: 可前往 Aspose.Tasks 論壇或參考官方網站上的文件，連結如下：[here](https://forum.aspose.com/c/tasks/15)。

## 結論
透過本步驟指南，您已掌握如何使用 Aspose.Tasks for Java **讀取 Microsoft Project 資料庫**、程式化操作資料，並匯出為所需格式。此方法免除對 Microsoft Project 的依賴，簡化自動化報表流程，並為強大的自訂整合開啟可能。

---

**最後更新：** 2025-12-13  
**測試環境：** Aspose.Tasks for Java 24.5（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
