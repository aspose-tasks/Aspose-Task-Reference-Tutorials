---
date: 2026-02-18
description: 學習如何使用 Aspose.Tasks Java 讀取 MS Project Online 資料。本指南說明如何取得專案清單、列出 SharePoint
  專案，以及取得資源數量。
linktitle: Reading Project Online Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: Aspose.Tasks Java：輕鬆讀取 MS Project Online 數據
url: /zh-hant/java/project-data-reading/read-project-online/
weight: 13
---

取 MS Project Online 資料". Keep as is.

Proceed.

Make sure bullet points and table content translated.

Let's craft.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose tasks java：輕鬆讀取 MS Project Online 資料

## 介紹
在專案管理領域，能有效處理 Microsoft Project Online 資料對於流程化運作至關重要。**aspose tasks java** 提供一套穩健且易於使用的 API，讓您不必自行撰寫低階 HTTP 呼叫，即可讀取 Project Online 資料。本教學將示範如何取得專案清單、**列出 SharePoint 專案**，以及**取得每個專案的資源數量**，全部只需幾行 Java 程式碼。

## 快速回答
- **aspose tasks java 有什麼功能？** 它可程式化地讀取與操作 Microsoft Project 檔案以及 Project Online 資料。  
- **試用需要授權嗎？** 提供免費試用版；正式上線需購買授權。  
- **需要哪些憑證？** SharePoint 網域、使用者名稱與密碼（或 Azure AD 令牌）。  
- **可以列出 SharePoint 專案嗎？** 可以——使用 `ProjectServerManager.getProjectList()` 取得。  
- **如何取得資源數量？** 載入每個 `Project` 物件後呼叫 `project.getResources().size()`。

## 什麼是 aspose tasks java？
**aspose tasks java** 是一套針對開發者設計的函式庫，抽象化了 Microsoft Project 檔案格式與 Project Server REST API 的複雜性。它讓您能直接在 Java 應用程式中讀取、建立與修改專案資料，輕鬆與既有企業系統整合。

## 為何使用 aspose tasks java 讀取 MS Project Online？
- **不需手動處理 HTTP** —— 函式庫會自動處理驗證與 REST 呼叫。  
- **強型別安全** —— 使用 `Project`、`ProjectInfo` 等 POJO 取代原始 JSON。  
- **跨平台** —— 可在任何相容 JVM 的環境執行。  
- **功能豐富** —— 除了讀取，還能更新工作、資源與時間表。  
- **內部使用 Project Server REST API**，提供穩定且受支援的通訊層。

## 前置條件
在開始之前，請確保您已具備以下項目：

1. **Java Development Kit (JDK)** —— 已安裝 JDK 8 或更新版本。  
2. **Aspose.Tasks for Java 函式庫** —— 從 [here](https://releases.aspose.com/tasks/java/) 下載。  
3. **Microsoft Project Online 帳號** —— 具備讀取專案的權限。  
4. **SharePoint 網域位址** —— 您的 Project Online 實例所在的網域。  
5. **使用者名稱與密碼** —— 或適用的 Azure AD 憑證以進行驗證。

## 匯入套件
首先，匯入本教學中將會使用的 Aspose.Tasks 核心類別：

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectInfo;
import com.aspose.tasks.ProjectServerCredentials;
import com.aspose.tasks.ProjectServerManager;
```

## 步驟 1：設定 SharePoint 網域、使用者名稱與密碼
為您的 Project Online 環境定義連線資訊。請將佔位字串替換為您自己的憑證。

```java
String sharepointDomainAddress = "https://contoso.sharepoint.com";
String userName = "admin@contoso.onmicrosoft.com";
String password = "MyPassword";
```

## 步驟 2：使用 Project Server 憑證進行驗證
建立 `ProjectServerCredentials` 物件，並初始化 `ProjectServerManager`。此管理員負責處理之後所有對 Project Online 的呼叫。

```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```

## 步驟 3：取得專案清單並顯示資訊
使用管理員 **取得專案清單**（即列出 SharePoint 專案），並印出名稱、建立日期與最後儲存日期等基本資訊。

```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```

## 步驟 4：載入個別專案並輸出資源數量
對先前取得的每個專案，載入完整的 `Project` 物件——此呼叫 **載入特定 ID 的專案資料**——並顯示 **資源數量**。

```java
for (ProjectInfo p : reader.getProjectList()) {
    Project project = reader.getProject(p.getId());
    System.out.println("Project " + p.getName() + " loaded.");
    System.out.println("Resources count:" + project.getResources().size());
}
```

## 常見問題與解決方案
| 問題 | 原因 | 解決方式 |
|------|------|----------|
| **驗證失敗** | 網域、使用者名稱或密碼錯誤。 | 核對憑證，並確保帳號具備 Project Online 讀取權限。 |
| **SSLHandshakeException** | Java 執行環境缺少所需的 TLS 版本。 | 更新至最新的 JDK，或啟用 TLS 1.2 以上。 |
| **`reader.getProjectList()` 回傳空集合** | 帳號沒有任何專案的存取權。 | 檢查 Project Online 權限，或改用管理員帳號。 |
| **大型專案導致 OutOfMemoryError** | 同時載入過多專案佔用記憶體。 | 一次只載入單一專案，使用完畢後釋放參考。 |

## 常見問答
**Q:** 我可以使用 aspose tasks java 修改 MS Project Online 資料嗎？  
**A:** 可以，Aspose.Tasks 同時支援讀取 **與** 修改 Project Online 資料。

**Q:** Aspose.Tasks 是否支援其他專案管理檔案格式？  
**A:** 當然支援。它支援 MPP、XML、Primavera 等多種格式，確保在不同專案生態系統間的相容性。

**Q:** 有提供 Aspose.Tasks for Java 的免費試用嗎？  
**A:** 有，您可從 [here](https://releases.aspose.com/) 取得免費試用版，體驗其功能與特性。

**Q:** 哪裡可以找到 Aspose.Tasks for Java 的完整文件？  
**A:** 請參考詳細文件 [here](https://reference.aspose.com/tasks/java/)，獲取在 Java 專案中使用 Aspose.Tasks 的完整指引。

**Q:** Aspose.Tasks for Java 提供哪些支援管道？  
**A:** 若遇到問題或有任何疑問，可前往 Aspose.Tasks 社群論壇 [here](https://forum.aspose.com/c/tasks/15) 尋求協助。

---

**最後更新：** 2026-02-18  
**測試環境：** Aspose.Tasks for Java 24.11（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}