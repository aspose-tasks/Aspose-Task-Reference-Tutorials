---
date: 2025-12-11
description: 學習如何使用 Aspose.Tasks for Java 建立 mpp 檔案並儲存空白的 MS Project 檔案（MPP），輕鬆簡化專案管理工作。
linktitle: Create and Save Empty Project in MPP Format with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何建立 MPP 檔案 – 使用 Aspose.Tasks 建立並儲存空白專案為 MPP 格式
url: /zh-hant/java/project-configuration/create-save-mpp/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 建立與儲存專案

## 介紹
在本教學中，您將學習 **如何建立 mpp 檔案**，使用 Aspose.Tasks for Java，這是一個簡單的流程，可建立並儲存空白的 Microsoft Project 檔案 (MPP)。我們會一步一步說明，讓您能快速產生專案檔並將其整合到 Java 應用程式中。

## 快速答案
- **本教學涵蓋什麼內容？** 使用 Aspose.Tasks for Java 建立與儲存空白 MPP 檔案。  
- **需要哪個程式庫？** Aspose.Tasks for Java（最新版本）。  
- **需要授權嗎？** 提供免費試用版；正式環境需購買授權。  
- **支援哪個 Java 版本？** Java 8 或以上。  
- **實作需要多長時間？** 通常在 10 分鐘以內完成。

## 什麼是 MPP 檔案？
MPP 檔案是 Microsoft Project 的原生檔案格式，用於儲存專案排程、資源與工作階層結構。以程式方式產生 MPP 檔案，可自動化專案計畫的建立、與其他系統整合，或即時產生範本。

## 為什麼使用 Aspose.Tasks for Java？
- **不需要 Microsoft Project** – 可在任何平台產生 MPP 檔案。  
- **功能完整** – 支援工作、資源、行事曆等多項功能。  
- **高度相容** – 輸出的檔案可在 Microsoft Project 中正確開啟。  

## 前置條件
在開始之前，請確保您已具備以下項目：

1. 已在系統上安裝 Java Development Kit (JDK)。  
2. 已下載 Aspose.Tasks for Java 程式庫，並將其加入專案相依性。  
3. 具備基本的 Java 程式設計知識。  

## Java 建立 MS Project – 步驟說明

### 步驟 1：匯入套件
首先，匯入提供 Aspose.Tasks 功能所需的類別：

```java
import java.io.IOException;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
```

### 步驟 2：設定資料目錄
定義產生的專案檔案要儲存的資料夾：

```java
String dataDir = "Your Data Directory";
```

將 `"Your Data Directory"` 替換為您偏好的絕對或相對路徑。

### 步驟 3：建立 Project 實例
建立一個新的 `Project` 物件，這會在記憶體中建立一個空白的 MS Project：

```java
Project newProject = new Project();
```

### 步驟 4：以 MPP 格式儲存專案
使用 `save` 方法將專案寫入磁碟，格式為 MPP – **save project as mpp**：

```java
newProject.save(dataDir + "project1.mpp", SaveFileFormat.Mpp);
```

檔案 `project1.mpp` 會出現在您先前指定的資料夾中。

### 步驟 5：顯示確認訊息
印出確認訊息，讓您知道操作已成功完成：

```java
System.out.println("Project file generated Successfully");
```

## 常見問題與解決方案
- **目錄路徑無效** – 確認 `dataDir` 以檔案分隔符 (`/` 或 `\\`) 結尾，或使用 `Paths.get` 進行串接。  
- **缺少 Aspose.Tasks JAR** – 確認程式庫已加入 classpath；Maven/Gradle 使用者請加入相應的相依性。  
- **未設定授權** – 正式環境請使用 `License license = new License(); license.setLicense("Aspose.Tasks.lic");` 載入授權。

## 結論
依照上述步驟，您現在已掌握 **如何以程式方式建立 mpp 檔案**，使用 Aspose.Tasks for Java。此功能讓您能自動化專案計畫的產生、將排程資料整合至自訂應用程式，並避免在 Microsoft Project 中手動輸入。

## 常見問答
### Q: Aspose.Tasks for Java 能處理複雜的專案結構嗎？
A: 能，Aspose.Tasks for Java 提供強大的功能，可有效處理複雜的專案結構。  
### Q: 是否提供 Aspose.Tasks for Java 的試用版？
A: 有，您可從網站 [此處](https://releases.aspose.com/) 取得免費試用版。  
### Q: 我可以使用 Aspose.Tasks for Java 自訂工作與資源的屬性嗎？
A: 當然可以，Aspose.Tasks for Java 提供廣泛的能力，讓您依需求自訂工作與資源屬性。  
### Q: Aspose.Tasks for Java 是否支援除 MPP 之外的其他專案檔案格式？
A: 支援，Aspose.Tasks for Java 可處理多種專案檔案格式，包括 XML、CSV 等。  
### Q: 我可以在哪裡取得 Aspose.Tasks for Java 的其他支援？
A: 您可前往 Aspose.Tasks 的 [論壇](https://forum.aspose.com/c/tasks/15) 取得 Java 專屬的支援與協助。  

## Frequently Asked Questions

**Q: 是否需要安裝 Microsoft Project 才能開啟產生的 MPP 檔案？**  
A: 不需要，該檔案可使用任何版本的 Microsoft Project 或相容的檢視器開啟。

**Q: 我可以在儲存前加入工作或資源嗎？**  
A: 可以，您可以在呼叫 `save` 之前操作 `Project` 物件（新增工作、資源、行事曆等）。

**Q: 產生的 MPP 檔案是否相容舊版 Project？**  
A: Aspose.Tasks 產生的檔案相容於 Microsoft Project 2007 及之後的版本。

**Q: 如何設定自訂的專案開始日期？**  
A: 在儲存之前使用 `newProject.setStartDate(java.util.Date)` 設定。

**Q: 有哪些授權方案可供選擇？**  
A: Aspose 提供開發者、站點與 OEM 授權，詳情請參閱 Aspose 官方網站。

---

**最後更新：** 2025-12-11  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}