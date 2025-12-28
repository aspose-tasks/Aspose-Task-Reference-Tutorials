---
date: 2025-12-28
description: 了解如何使用 Aspose.Tasks for Java（Java 專案管理函式庫）新增任務並更新 MPP 檔案。請依照我們的逐步指南，在
  MPP 中建立任務並將專案儲存為 MPP。
linktitle: How to Add Task and Update MPP File in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何在 Aspose.Tasks 中新增任務並更新 MPP 檔案
url: /zh-hant/java/project-management/update-mpp/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中新增任務並更新 MPP 檔案

## 簡介
在本教學中，我們將示範如何 **新增任務** 並使用 Aspose.Tasks for Java（領先的 **java 專案管理函式庫**）更新 MPP 檔案。無論您是要建立自訂排程器，或是需要以程式方式修改既有專案計畫，本指南都會一步步帶您完成——從載入檔案到將變更儲存為新的 MPP 文件。

## 快速解答
- **「新增任務」在此情境下是什麼意思？** 它指的是以程式方式在現有的 Microsoft Project (MPP) 檔案中建立一個新任務。  
- **是哪個函式庫負責此操作？** Aspose.Tasks for Java，一個功能強大的 java 專案管理函式庫。  
- **需要授權嗎？** 開發階段可使用免費試用版；正式上線則需購買商業授權。  
- **可以將結果儲存為 MPP 嗎？** 可以——使用 `project.save(..., SaveFileFormat.Mpp)` 來 **將專案儲存為 mpp**。  
- **需要哪個 Java 版本？** Java 8 或更新版本。

## 什麼是 MPP 檔案中的「新增任務」？
新增任務即是在專案層級中插入一個新的工作項目，設定其開始/結束日期，並將變更寫回 MPP 檔案。Aspose.Tasks 抽象化了底層檔案格式的細節，讓您專注於業務邏輯。

## 為什麼使用 Aspose.Tasks for Java？
- **完整相容** Microsoft Project 2007‑2021 檔案。  
- **不需 COM 或 Office 安裝**——純 Java API。  
- **功能豐富**：任務連結、資源分配、自訂欄位等。  
- **高效能** 處理大型專案檔，適合伺服器端自動化。

## 先決條件
1. **Java 開發環境** – 已安裝並設定 JDK 8+。  
2. **Aspose.Tasks for Java** – 從 [download page](https://releases.aspose.com/tasks/java/) 下載。  
3. **基本 Java 知識** – 熟悉類別、物件與日期處理。

## 匯入套件
首先，匯入您需要的類別，以取得專案操作、任務屬性與日期處理的功能。

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## 步驟 1：定義資料目錄
```java
String dataDir = "Your Data Directory";
```
將 `"Your Data Directory"` 替換為存放來源 MPP 檔案的絕對路徑。

## 步驟 2：讀取現有專案
```java
Project project = new Project(dataDir + "SampleMSP2010.mpp");
```
`Project` 建構子會載入 **SampleMSP2010.mpp**，為您提供可操作的物件模型。

## 步驟 3：建立新任務（如何新增任務）
```java
Task task = project.getRootTask().getChildren().add("Task1");
```
此行 **creates task in mpp**，透過在根任務下加入名為 *Task1* 的子任務來建立新任務。

## 步驟 4：設定開始與結束日期
```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2012, Calendar.JULY, 1, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2012, Calendar.JULY, 1, 17, 0, 0);
task.set(Tsk.FINISH, cal.getTime());
```
在此為新加入的任務定義排程。請依您的專案時間表調整日期。

## 步驟 5：儲存專案（將專案儲存為 mpp）
```java
project.save(dataDir + "AfterLinking.mpp", SaveFileFormat.Mpp);
```
更新後的專案已包含新任務，並以 **AfterLinking.mpp** 形式持久化。

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| **找不到檔案** | 確認 `dataDir` 以路徑分隔符 (`/` 或 `\\`) 結尾，且檔名正確。 |
| **日期不正確** | 記得 `Calendar` 的月份是從 0 開始計算；`Calendar.JULY` 才是七月。 |
| **授權例外** | 在呼叫任何 API 前先安裝有效的 Aspose.Tasks 授權，以避免評估水印。 |

## 常見問答
### 問：Aspose.Tasks for Java 能處理複雜的專案結構嗎？
答：可以，Aspose.Tasks for Java 提供強大的功能，能有效處理複雜的專案結構。  
### 問：是否提供 Aspose.Tasks for Java 的免費試用？
答：可以，您可從 [website](https://releases.aspose.com/) 下載免費試用版。  
### 問：Aspose.Tasks for Java 是否支援不同版本的 Microsoft Project 檔案？
答：當然支援，Aspose.Tasks for Java 支援多種 Microsoft Project 檔案版本，包括 MPP、MPT 與 XML 格式。  
### 問：我可以取得 Aspose.Tasks for Java 的臨時授權嗎？
答：可以，臨時授權可供測試使用。您可從 [temporary license page](https://purchase.aspose.com/temporary-license/) 取得。  
### 問：我可以在哪裡尋求 Aspose.Tasks for Java 的協助或支援？
答：您可前往 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 取得協助或提出問題。

## 常見問題
**問：如何一次新增多個任務？**  
答：在任務名稱集合上迴圈，於迴圈內重複「建立任務」的程式碼區塊。

**問：可以為新任務設定自訂欄位嗎？**  
答：可以——使用 `task.set(Tsk.CUSTOM_FIELD_x, value)`，其中 *x* 為欄位索引。

**問：是否可以將既有任務複製為範本？**  
答：可將來源任務克隆 (`Task cloned = sourceTask.clone();`) 後加入至目標父任務。

**問：如果需要更新既有任務而非新增，該怎麼做？**  
答：透過 ID 取得任務 (`Task existing = project.getRootTask().getChildren().getById(id);`) 後修改其屬性。

**問：Aspose.Tasks 是否支援儲存為 PDF 或 PNG 等其他格式？**  
答：支援——使用 `project.save("output.pdf", SaveFileFormat.Pdf);` 或 `SaveFileFormat.Png` 產生視覺化圖像。

---

**最後更新：** 2025-12-28  
**測試版本：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}