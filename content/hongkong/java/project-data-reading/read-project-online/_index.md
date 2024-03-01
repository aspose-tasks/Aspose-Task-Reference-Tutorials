---
title: 使用 Aspose.Tasks 輕鬆讀取 MS Project 線上數據
linktitle: 在Aspose.Tasks中讀取項目在線數據
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 輕鬆讀取 Microsoft Project Online 資料。增強您的專案管理能力。
type: docs
weight: 13
url: /zh-hant/java/project-data-reading/read-project-online/
---
## 介紹
在專案管理領域，有效處理 Microsoft Project Online 資料對於簡化操作至關重要。 Aspose.Tasks for Java 提供了一個強大的解決方案來輕鬆讀取此類資料。本教學深入探討如何利用 Aspose.Tasks 無縫存取和操作 MS Project Online 資料。
## 先決條件
在深入學習本教學之前，請確保您具備以下條件：
1. Java開發工具包（JDK）：安裝JDK來編譯和執行Java程式。
2.  Aspose.Tasks for Java Library：下載 Aspose.Tasks 函式庫並將其包含在您的 Java 專案中。您可以從以下位置獲取它[這裡](https://releases.aspose.com/tasks/java/).
3. Microsoft Project Online 帳戶：取得用於存取 MS Project Online 資料的有效憑證。
4. SharePoint 網域位址：MS Project Online 資料所在的 SharePoint 網域位址。
5. 使用者名稱和密碼：用於驗證 MS Project Online 存取權限的憑證。
## 導入包
在您的 Java 專案中，匯入必要的 Aspose.Tasks 套件以實現無縫整合：
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.ProjectInfo;
import com.aspose.tasks.ProjectServerCredentials;
import com.aspose.tasks.ProjectServerManager;
```

## 步驟 1：設定 SharePoint 網域位址、使用者名稱和密碼
```java
String sharepointDomainAddress = "https://contoso.sharepoint.com";
String userName = "admin@contoso.onmicrosoft.com";
String password = "MyPassword";
```
代替`"https://contoso.sharepoint.com"`與您的 SharePoint 網域位址，`"admin@contoso.onmicrosoft.com"`與您的用戶名，以及`"MyPassword"`用你的密碼。
## 步驟 2：使用 Project Server 憑證進行驗證
```java
ProjectServerCredentials credentials = new ProjectServerCredentials(sharepointDomainAddress, userName, password);
ProjectServerManager reader = new ProjectServerManager(credentials);
```
創造`ProjectServerCredentials`包含 SharePoint 網域位址、使用者名稱和密碼的物件。然後初始化`ProjectServerManager`有了這些憑證。
## 步驟 3：檢索項目清單並顯示訊息
```java
for (ProjectInfo p : reader.getProjectList()) {
    System.out.println("Project Name:" + p.getName());
    System.out.println("Project Created Date:" + p.getCreatedDate());
    System.out.println("Project Last Saved Date:" + p.getLastSavedDate());
}
```
迭代獲得的項目列表`reader.getProjectList()`並顯示項目詳細信息，例如名稱、建立日期和上次儲存日期。
## 步驟 4：載入單一項目並輸出資源計數
```java
for (ProjectInfo p : reader.getProjectList()) {
    Project project = reader.getProject(p.getId());
    System.out.println("Project " + p.getName() + " loaded.");
    System.out.println("Resources count:" + project.getResources().size());
}
```
對於每個項目，使用加載它`reader.getProject(p.getId())`並輸出項目名稱以及關聯資源的數量。

## 結論
Aspose.Tasks for Java 簡化了讀取 MS Project Online 資料的過程，為開發人員提供了一個強大的工具集來簡化專案管理任務。透過遵循本教程，您可以有效地將 Aspose.Tasks 整合到您的 Java 應用程式中，以輕鬆存取和操作專案資料。
## 常見問題解答
### Q：我可以使用 Aspose.Tasks for Java 修改 MS Project Online 資料嗎？
答：是的，Aspose.Tasks 提供了廣泛的功能，不僅可以讀取，還可以透過程式修改 MS Project Online 資料。
### Q：Aspose.Tasks 是否支援其他專案管理文件格式？
答：當然，Aspose.Tasks 支援各種檔案格式，包括 MPP、XML 等，確保與各種專案管理系統的兼容性。
### Q：Aspose.Tasks for Java 是否有免費試用版？
答：是的，您可以透過以下方式免費試用：[這裡](https://releases.aspose.com/)探索 Aspose.Tasks 的特性和功能。
### Q：在哪裡可以找到 Aspose.Tasks for Java 的綜合文件？
答：可以參考詳細文檔[這裡](https://reference.aspose.com/tasks/java/)有關在 Java 專案中使用 Aspose.Tasks 的全面指導。
### Q：Aspose.Tasks for Java 有哪些支援選項？
答：如果您遇到任何問題或有疑問，可以向 Aspose.Tasks 社群論壇尋求協助[這裡](https://forum.aspose.com/c/tasks/15).