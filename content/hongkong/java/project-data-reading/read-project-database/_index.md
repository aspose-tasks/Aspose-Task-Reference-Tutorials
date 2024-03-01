---
title: 在 Aspose.Tasks 中從 MS Project 資料庫讀取項目數據
linktitle: 在 Aspose.Tasks 中從 Microsoft Project 資料庫讀取專案數據
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 從 Microsoft Project 資料庫讀取專案資料。帶有程式碼範例的分步指南。
type: docs
weight: 12
url: /zh-hant/java/project-data-reading/read-project-database/
---
## 介紹
在本教程中，我們將探討如何使用 Aspose.Tasks for Java 從 Microsoft Project 資料庫讀取專案資料。 Aspose.Tasks 是一個功能強大的 Java API，可讓開發人員操作 Microsoft Project 文檔，而無需安裝 Microsoft Project。透過遵循本指南中概述的步驟，您將了解如何有效地從資料庫中提取項目資料並將其儲存為所需的格式。
## 先決條件
在我們開始之前，請確保您符合以下先決條件：
1. Java 程式設計的基礎知識。
2. 您的系統上安裝了 Java 開發工具包 (JDK)。
3. Aspose.Tasks for Java 程式庫已下載並在您的專案中配置。

## 導入包
首先，導入必要的套件：
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
## 第 1 步：設定資料庫連接
首先，您需要設定與 Microsoft Project 資料庫的連線。這包括指定資料庫 URL、伺服器名稱、連接埠號碼、資料庫名稱、使用者名稱和密碼。
```java
String url = "jdbc:sqlserver://”;
String serverName = "192.168.56.2\\MSSQLSERVER";
String portNumber = "1433";
String databaseName = "ProjectServer_Published";
String userName = "sa";
String password = "***";
MspDbSettings settings = new MspDbSettings(url + serverName + ":" + portNumber + ";databaseName=" + databaseName + ";user=" + userName + ";password=" + password);
```
## 步驟2：新增 JDBC 驅動程式
接下來，您需要將 JDBC 驅動程式新增至您的專案。此驅動程式有助於 Java 應用程式和 Microsoft SQL Server 資料庫之間的通訊。
```java
addJDBCDriver(new File("c:\\Program Files (x86)\\Microsoft JDBC Driver 4.0 for SQL Server\\sqljdbc_4.0\\enu\\sqljdbc4.jar"));
```
## 第 3 步：讀取項目數據
現在，建立一個`Project`物件並使用先前定義的設定從資料庫載入項目資料。
```java
Project project = new Project(settings);
```
## 第 4 步：儲存項目數據
最後，將項目資料儲存為所需的格式。在此範例中，我們將其另存為 XML 檔案。
```java
project.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```
恭喜！您已使用 Aspose.Tasks for Java 成功從 Microsoft Project 資料庫讀取專案資料。

## 結論
在本教程中，我們介紹了使用 Aspose.Tasks for Java 從 Microsoft Project 資料庫讀取專案資料的過程。透過遵循概述的步驟，您可以無縫提取專案資訊並根據您的要求對其進行操作。 Aspose.Tasks 簡化了 Microsoft Project 文件的處理，從而實現高效的資料提取和操作。
## 常見問題解答
### Q：Aspose.Tasks 是否可以用於從 Microsoft Project 以外的其他資料庫讀取專案資料？
答：是的，Aspose.Tasks 支援從各種來源讀取專案數據，包括 XML 檔案、Primavera 和 Microsoft Project 資料庫。
### Q：Aspose.Tasks 是否與不同版本的 Microsoft Project 相容？
答：是的，Aspose.Tasks 旨在與不同版本的 Microsoft Project 搭配使用，確保相容性和無縫整合。
### Q：我可以在儲存專案資料之前對其進行操作嗎？
答：當然，Aspose.Tasks 提供了廣泛的功能來操作項目數據，例如新增任務、更新資源和設定項目屬性。
### Q：Aspose.Tasks 支援多種輸出格式嗎？
答：是的，Aspose.Tasks 支援各種輸出格式，包括 XML、PDF、HTML 以及 PNG 和 JPEG 等影像格式。
### Q：我可以在哪裡找到有關 Aspose.Tasks 的進一步支援或協助？
答：如需其他支援或協助，您可以造訪 Aspose.Tasks 論壇或瀏覽網站上提供的文檔[這裡](https://forum.aspose.com/c/tasks/15).