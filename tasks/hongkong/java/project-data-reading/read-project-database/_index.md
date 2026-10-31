---
date: 2026-10-31
description: 了解如何將專案另存為 PDF 並使用 Aspose.Tasks for Java 讀取 Microsoft Project 資料庫，此外還可連接
  Project Server、將專案轉換為 HTML，並匯出為 XML。
keywords:
- save project as pdf
- export project to pdf
- connect to project server
- export project to csv
- convert project to html
lastmod: 2026-10-31
linktitle: 在 Aspose.Tasks 中讀取 Microsoft Project 資料庫的專案資料
og_description: 將專案另存為 PDF 並使用 Aspose.Tasks for Java 讀取 Microsoft Project 資料庫。了解如何連接
  Project Server，並匯出為 HTML、XML 及 CSV。
og_image_alt: Tutorial showing how to save a project as PDF and read data from Microsoft
  Project Server using Aspise.Tasks Java API
og_title: 將專案另存為 PDF 並使用 Aspose.Tasks for Java 讀取 Microsoft Project 資料庫
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  headline: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  type: TechArticle
- description: Learn how to save project as PDF and read Microsoft Project database
    with Aspose.Tasks for Java, plus connect to Project Server, convert project to
    HTML, and export project to XML.
  name: Save project as PDF and read Microsoft Project database with Aspose.Tasks
    for Java
  steps:
  - name: A working Java development environment (JDK 8 or newer).
    text: A working Java development environment (JDK 8 or newer).
  - name: Aspose.Tasks for Java library added to your project’s classpath.
    text: Aspose.Tasks for Java library added to your project’s classpath.
  - name: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
    text: Access credentials for the Project Server SQL database (server name, port,
      database name, username, password) to connect to Project Server.
  - name: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
    text: The Microsoft JDBC Driver for SQL Server (e.g., `sqljdbc4.jar`).
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports reading project data from XML files, Primavera
      databases, and other standard project formats.
    question: Can Aspose.Tasks be used to read project data from other databases besides
      Microsoft Project?
  - answer: Yes, the library works with Microsoft Project 2007 through the latest
      2024 releases, ensuring seamless integration across versions.
    question: Is Aspose.Tasks compatible with different versions of Microsoft Project?
  - answer: Absolutely, you can add, update, or delete tasks, resources, and custom
      fields using the rich API before exporting.
    question: Can I manipulate the project data before saving it?
  - answer: Yes, you can save projects as PDF, XML, HTML, CSV, PNG, JPEG, and more—over
      20 formats in total.
    question: Does Aspose.Tasks support multiple output formats?
  - answer: For additional help, visit the Aspose.Tasks forum or explore the documentation
      available on the website [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I find further support or assistance with Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project integration
- PDF export
- Project Server
title: 將專案另存為 PDF 並使用 Aspose.Tasks for Java 讀取 Microsoft Project 資料庫
url: /zh-hant/java/project-data-reading/read-project-database/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks for Java 將專案儲存為 PDF 並讀取 Microsoft Project 資料庫

## 介紹
在本教學中，您將學會如何直接從 Microsoft Project Server **read Microsoft Project database**，然後使用 Aspose.Tasks Java API **save the project as PDF**。無論您是需要產生可列印的報告、遷移舊有資料，或是將專案資訊嵌入自訂入口網站，本指南都會一步步帶領您完成——從設定 JDBC 連線到將專案匯出為 PDF、XML 或 HTML。完成後，您將擁有一個可在任何 Java 伺服器上執行、且不需安裝 Microsoft Project 的生產就緒解決方案。

## 快速解答
- **Aspose.Tasks 的功能是什麼？** 它提供純 Java API 來讀取、寫入和操作 Microsoft Project 檔案與資料庫。  
- **需要安裝 Microsoft Project 嗎？** 不需要，Aspose.Tasks 可獨立於 Microsoft Project 運作。  
- **支援哪種資料庫類型？** Microsoft SQL Server，作為 Project Server 的後端。  
- **可以匯出成其他格式嗎？** 可以 — PDF、XML、HTML、CSV、PNG、JPEG 等。  
- **主要前置條件是什麼？** JDK 8 或更新版本、Aspose.Tasks for Java 函式庫、SQL Server JDBC 驅動程式，以及有效的 Project Server 憑證。

## 什麼是「read Microsoft Project database」？
讀取 Microsoft Project 資料庫是指連接至 Project Server 的 SQL Server 資料庫，擷取已儲存的專案資料，並載入到 Aspose.Tasks 可操作的 `Project` 物件中。此方法非常適合自動化報告、資料遷移或自訂分析。

## 為什麼使用 Aspose.Tasks for Java？
Aspose.Tasks for Java 讓您在不需要桌面應用程式的情況下處理 Microsoft Project 資料，提供可在任何平台上執行的純 Java 解決方案。它提供完整的物件模型，可操作任務、資源、行事曆與自訂欄位，且能有效處理大型企業專案，因而非常適合自動化報告、遷移與整合情境。

- **無需 Microsoft Project 依賴** – 可在任何伺服器或 CI 環境上執行。  
- **豐富的物件模型** – 以程式方式存取任務、資源、指派、行事曆與自訂欄位。  
- **多種匯出選項** – Aspose.Tasks 支援匯出至 **超過 20 種檔案格式**，包括 PDF、XML、HTML、CSV、PNG、JPEG，只需一次 API 呼叫。  
- **高效能** – 此函式庫可在不到一分鐘的時間內處理包含 **多達 10,000 個任務** 的專案，且採用串流方式避免將整個檔案載入記憶體。

## 前置條件
在開始之前，請確保您已具備以下條件：

1. 可正常運作的 Java 開發環境（JDK 8 或更新版本）。  
2. 已將 Aspose.Tasks for Java 函式庫加入專案的 classpath。  
3. 用於連接 Project Server 的 SQL 資料庫存取憑證（伺服器名稱、埠號、資料庫名稱、使用者名稱、密碼）。  
4. Microsoft JDBC Driver for SQL Server（例如 `sqljdbc4.jar`）。

## 匯入套件
首先，匯入您需要的類別。清單包含 Aspose.Tasks 核心類別以及標準的 Java 工具類。

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

## 如何連接至 Project Server
建立可靠的連線是讀取專案資料的基礎。請確保 SQL Server 執行個體可從您的 Java 主機存取，且您使用的登入帳號在 Project Server 綱要上具有 **SELECT** 權限。您亦應檢查網路延遲，並設定任何必要的 SSL 設定，以確保安全通訊。

## 步驟 1：設定資料庫連線
`MspDbSettings` 類別封裝了存取 Microsoft Project Server 資料庫所需的 JDBC 連線資訊。建立一個保存 JDBC 連線字串的 `MspDbSettings` 實例。將佔位值替換為您實際的伺服器資訊。

```java
String url = "jdbc:sqlserver://";
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```

> **小技巧:** 將連線字串儲存在安全的設定檔或環境變數中，而非硬編碼憑證。

## 步驟 2：加入 JDBC 驅動程式
在執行時載入 Microsoft SQL Server JDBC 驅動程式，使 JVM 能與資料庫通訊。

```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```

> **警告:** 確認驅動程式版本與您的 SQL Server 版本相符。使用不相容的驅動程式可能導致連線失敗。

## 步驟 3：讀取專案資料
`Project` 類別代表已載入記憶體的 Microsoft Project 檔案，提供任務、資源與指派的存取。透過傳入 `MspDbSettings` 來實例化 `Project` 物件。Aspose.Tasks 會自動從資料庫擷取專案資料。

```java
Project project = new Project(settings);
```

此時您可以探索 `project` 物件——列出任務、資源，或依需求修改欄位。

## 步驟 4：將專案儲存為 PDF
`SaveFileFormat` 列舉定義了 `Project.save` 方法的輸出格式，例如 PDF、XML 或 HTML。將載入的專案匯出為您選擇的檔案格式。以下範例將專案儲存為 **PDF**，非常適合列印報告。您也可以透過變更 `SaveFileFormat` 列舉 **export project to XML** 或 **convert project to HTML**。

```java
project.save(dataDir + "project1.pdf", SaveFileFormat.Pdf);
```

如果您偏好 XML，只需將 `SaveFileFormat.Pdf` 替換為 `SaveFileFormat.Xml`。若要輸出 HTML，使用 `SaveFileFormat.Html`。

## 常見問題與解決方案
| 問題 | 常見原因 | 解決方式 |
|-------|---------------|-----|
| **連線逾時** | 伺服器/埠號錯誤或防火牆阻擋 | 確認伺服器位址，開啟 1433 埠，並使用簡單的 JDBC 測試程式測試連線。 |
| **驗證錯誤** | 使用者名稱/密碼無效，或 SQL Server 未設定為 SQL 驗證模式 | 使用有效的 SQL 登入帳號，或在伺服器上啟用混合模式驗證。 |
| **找不到驅動程式** | JDBC jar 未在 classpath 中 | 確保 `addJDBCDriver` 指向正確的 `.jar` 檔案，且路徑使用雙反斜線 (`\\`)。 |
| **載入後專案為空** | 讀取 Project Server 表格的權限不足 | 授予該登入帳號對 Project Server 資料庫綱要的 SELECT 權限。 |

## 常見問答

**Q: Aspose.Tasks 能否從 Microsoft Project 之外的其他資料庫讀取專案資料？**  
A: 是的，Aspose.Tasks 支援從 XML 檔案、Primavera 資料庫以及其他標準專案格式讀取專案資料。

**Q: Aspose.Tasks 是否相容於不同版本的 Microsoft Project？**  
A: 是的，該函式庫支援 Microsoft Project 2007 直至最新的 2024 版，確保跨版本的無縫整合。

**Q: 我可以在儲存之前操作專案資料嗎？**  
A: 當然可以，您可以使用功能豐富的 API 在匯出前新增、更新或刪除任務、資源與自訂欄位。

**Q: Aspose.Tasks 是否支援多種輸出格式？**  
A: 是的，您可以將專案儲存為 PDF、XML、HTML、CSV、PNG、JPEG 等，總計超過 20 種格式。

**Q: 我該從哪裡取得 Aspose.Tasks 的進一步支援或協助？**  
A: 如需更多協助，請造訪 Aspose.Tasks 論壇或在網站上查閱文件，網址為 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)。

## 結論
透過本步驟指南，您現在已了解如何 **read Microsoft Project database**、**save the project as PDF**，以及使用 Aspose.Tasks for Java 匯出至其他格式。此方法消除對 Microsoft Project 的依賴，簡化自動化報告流程，並為強大的自訂整合開啟大門。

---

**最後更新:** 2026-10-31  
**測試環境:** Aspose.Tasks for Java 24.5 (latest at time of writing)  
**作者:** Aspose

## 相關教學

- [如何使用 Aspose.Tasks 將專案儲存為 PDF – 匯出指南](/tasks/java/project-file-operations/save-as-pdf/)
- [將專案儲存為 PDF – 使用 Aspose.Tasks for Java 渲染任務表](/tasks/java/task-properties/render-task-sheet/)
- [將專案匯出為 PDF 並減少任務清單與頁腳之間的間距 – Aspose.Tasks](/tasks/java/project-file-operations/reduce-gap-tasks-list-footer/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}