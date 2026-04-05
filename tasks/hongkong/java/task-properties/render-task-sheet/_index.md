---
date: 2026-02-26
description: 學習如何將專案儲存為 PDF，並使用 Aspose.Tasks for Java 產生任務表。快速將 MPP 匯出為 PDF，請參考此一步一步的指引。
linktitle: Render Task Sheet in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 將專案另存為 PDF – 使用 Aspose.Tasks for Java 渲染任務表
url: /zh-hant/java/task-properties/render-task-sheet/
weight: 27
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 將專案另存為 PDF – 在 Aspose.Tasks 中呈現工作表

## 簡介
在本完整指南中，您將學會如何 **將專案另存為 PDF**，並使用 Aspose.Tasks for Java 產生工作表。無論是需要將 MPP 檔案匯出為 PDF 供利害關係人審閱，或是僅僅為報告產出整潔的工作表，本教學都會一步步帶您完成，說明每個設定的原因，並提供您執行所需的完整程式碼。

## 快速解答
- **「將專案另存為 PDF」的功能是什麼？** 它會將 Microsoft Project 檔案 (MPP) 轉換成 PDF 文件，並可選擇將其格式化為工作表。  
- **工作表 PDF 使用哪種格式？** 在 `PdfSaveOptions` 中使用 `PresentationFormat.TaskSheet` 選項。  
- **執行程式碼是否需要授權？** 生產環境需要臨時或正式授權；免費試用版可用於評估。  
- **主要前置條件是什麼？** Java JDK、Aspose.Tasks for Java 函式庫，以及有效的專案檔 (例如 *.mpp)。  
- **我可以自訂 PDF 版面嗎？** 可以，Aspose.Tasks 提供多個 `PdfSaveOptions` 屬性可用於樣式與頁面設定。

## 什麼是「將專案另存為 PDF」？
將專案另存為 PDF 會把內部的專案資料轉換成可攜帶、唯讀的文件。這對於需要與未安裝 Microsoft Project 的利害關係人分享排程、工作表或狀態報告而言，非常理想。

## 為什麼要呈現工作表？
工作表以表格方式呈現每個任務，顯示 ID、名稱、開始/結束日期以及其他欄位。將其渲染為 PDF 可確保跨平台的格式一致，且便於列印或嵌入其他文件。

## 前置條件
在開始之前，請確保您已具備以下項目：

1. **Java 開發工具包 (JDK)** – 安裝最新版本，且 `java`/`javac` 已在 PATH 中可用。  
2. **Aspose.Tasks for Java** – 從官方網站[此處](https://releases.aspose.com/tasks/java/)下載函式庫。  
3. 有效的**專案檔** (`*.mpp`) ，例如 `NewProductDev.mpp`。  

## 匯入套件
首先，匯入所需的 Aspose.Tasks 類別。這些匯入讓您能使用 PDF 儲存選項、呈現格式以及核心的 `Project` 物件。

```java
import com.aspose.tasks.PdfSaveOptions;
import com.aspose.tasks.PresentationFormat;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveOptions;
```

## 逐步指南

### 步驟 1：設定文件目錄
定義來源 MPP 檔所在的資料夾，以及產生的 PDF 要寫入的目錄。使用絕對或相對路徑皆可，只要確保資料夾已存在。

```java
String dataDir = "Your Document Directory";
```

### 步驟 2：載入專案檔
透過載入現有的 MPP 檔建立 `Project` 實例。此物件在記憶體中代表整個專案結構。

```java
Project project = new Project(dataDir + "NewProductDev.mpp");
```

### 步驟 3：設定儲存選項 – 將 MPP 匯出為 PDF
建立 `PdfSaveOptions`，並告訴 Aspose.Tasks 您希望 PDF 以 **工作表** 形式呈現。這是 *匯出專案 PDF* 使用情境的關鍵步驟。

```java
SaveOptions options = new PdfSaveOptions();
options.setPresentationFormat(PresentationFormat.TaskSheet);
```

### 步驟 4：將專案另存為工作表 – 專案另存為 PDF
在 `Project` 物件上呼叫 `save` 方法，傳入目標檔名與先前設定的選項。此動作 **將 MPP 檔轉換為以工作表格式的 PDF**。

```java
project.save(dataDir + "taskSheet.pdf", options);
```

### 步驟 5：檢查結果
前往您先前指定的目錄 (`dataDir`)。您應該會看到 `taskSheet.pdf`，其中列出了所有任務的整齊格式清單。使用任何 PDF 閱讀器開啟，以驗證轉換是否成功。

## 常見問題與解決方案
- **FileNotFoundException** – 確認 `dataDir` 以路徑分隔符 (`/` 或 `\\`) 結尾，且 MPP 檔名正確。  
- **LicenseException** – 若出現授權錯誤，請在呼叫任何 Aspose.Tasks API 前套用臨時或正式授權。  
- **Blank PDF** – 確認專案內確實有任務；空白專案會產生空的 PDF。

## 常見問答

**問：Aspose.Tasks 是否相容所有 Java 版本？**  
答：是，Aspose.Tasks 支援廣泛的 Java 版本。詳情請參閱[文件](https://reference.aspose.com/tasks/java/)。

**問：我可以在購買前試用 Aspose.Tasks 嗎？**  
答：當然可以！於[此處]探索免費試用版 [here](https://releases.aspose.com/).

**問：在哪裡可以取得 Aspose.Tasks 的支援？**  
答：加入 Aspose.Tasks 社群於[論壇](https://forum.aspose.com/c/tasks/15)取得支援與討論。

**問：如何取得 Aspose.Tasks 的臨時授權？**  
答：於[此處]取得臨時授權 [here](https://purchase.aspose.com/temporary-license/).

**問：在哪裡可以購買 Aspose.Tasks for Java？**  
答：於[此處]購買 Aspose.Tasks for Java [here](https://purchase.aspose.com/buy).

## 結論
透過上述步驟，您已學會如何 **將專案另存為 PDF**，特別是以工作表形式呈現，使用 Aspose.Tasks for Java。此功能讓您能快速 *將 MPP 匯出為 PDF*，分享可讀的專案快照，並將專案資料整合至更廣泛的報告工作流程中。

---

**Last Updated:** 2026-02-26  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}