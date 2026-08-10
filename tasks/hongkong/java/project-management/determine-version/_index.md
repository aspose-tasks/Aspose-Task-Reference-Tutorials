---
date: 2026-05-31
description: 了解如何使用 Aspose.Tasks for Java 從 MS Project 檔案取得專案版本與最後儲存日期。一步一步的指南，附有程式碼範例。
keywords:
- how to get project version
- retrieve last saved date
- determine ms project version
- aspose tasks version java
- read project version java
linktitle: 使用 Aspose.Tasks 確定專案版本
schemas:
- author: Aspose
  dateModified: '2026-05-31'
  description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  headline: How to Get Project Version – Aspose Tasks Java Tutorial
  type: TechArticle
- description: Learn how to get project version and retrieve last saved date from
    MS Project files using Aspose.Tasks for Java. Step‑by‑step guide with code examples.
  name: How to Get Project Version – Aspose Tasks Java Tutorial
  steps:
  - name: '**Java Development Kit (JDK)** – version 8 or newer.'
    text: '**Java Development Kit (JDK)** – version 8 or newer.'
  - name: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
    text: '**Aspose.Tasks for Java JAR** – download from the [website](https://releases.aspose.com/tasks/java/)
      and add it to your project’s classpath.'
  - name: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
    text: '**MS Project file** – an XML‑based Project file (e.g., `input.xml`) that
      you want to inspect.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Tasks supports .NET, Java, and C++ among others.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Absolutely; it can process multi‑hundred‑page projects in seconds without
      loading the entire file into memory.
    question: Is Aspose.Tasks suitable for large‑scale projects?
  - answer: Yes, you can modify tasks, resources, calendars, and any other project
      element through the API.
    question: Can I customize project data using Aspose.Tasks?
  - answer: No, the library works independently and does not need Microsoft Project
      on the host machine.
    question: Does Aspose.Tasks require Microsoft Project installation?
  - answer: Yes, you can get help from the Aspose.Tasks forum [here](https://forum.aspose.com/c/tasks/15).
    question: Is technical support available for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: 如何取得專案版本 – Aspose Tasks Java 教程
url: /zh-hant/java/project-management/determine-version/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何取得專案版本 – Aspose Tasks Java 教學

在本 **Aspose Tasks Java tutorial** 中，您將學習 **how to get project version** of a Microsoft Project file，並使用 Aspose.Tasks for Java **retrieve last saved date**。了解檔案版本與儲存時間戳記有助於避免相容性問題、執行遷移政策，並保持精確的稽核記錄。  
我們將逐步說明從環境設定到列印版本與日期的每個步驟，讓您能自信地將此檢查嵌入任何 Java 應用程式中。

## 快速解答
- **What does this tutorial cover?** 確定 MS Project 檔案的版本與最後儲存日期，使用 Aspose.Tasks for Java。  
- **Do I need Microsoft Project installed?** 不需要，Aspose.Tasks 可獨立於 Microsoft Project 執行。  
- **Which file formats are supported?** 完全支援 XML 為基礎的 Project 檔案，例如 MPP 與 XML。  
- **How long does the implementation take?** 基本版本檢查大約需要 5‑10 分鐘。  
- **Is a license required?** 評估可使用免費試用版；正式環境需購買商業授權。

## 什麼是 Aspose Tasks Java 教學？
`Aspose.Tasks` Java 教學是一個簡潔、實作導向的指南，示範如何以程式方式與 Microsoft Project 資料互動。它說明如何讀取、修改與分析專案資訊，而無需在伺服器上安裝 Microsoft Project。此外，還涵蓋載入檔案、存取屬性與儲存變更，讓開發人員能有效自動化專案管理任務。

## 為何使用 Aspose.Tasks 來判斷專案版本？
Aspose.Tasks 在任何支援 Java 的作業系統上執行時，提供 **exact version metadata** 與 **last‑saved timestamps**。它能在標準 2.5 GHz CPU 上於 2 秒內處理最多 **500 頁** 的檔案，因而非常適合批次自動化與大規模遷移情境。

## 前置條件
1. **Java Development Kit (JDK)** – 版本 8 或更新。  
2. **Aspose.Tasks for Java JAR** – 從 [website](https://releases.aspose.com/tasks/java/) 下載，並將其加入專案的 classpath。  
3. **MS Project file** – XML 為基礎的 Project 檔案（例如 `input.xml`），您想要檢查的檔案。  

> **Pro tip:** 將 Project 檔案存放在專屬的 `data` 資料夾中，以保持路徑整潔並避免意外覆寫。

## 匯入套件
First, import the essential Aspose.Tasks classes:

```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
```

## 如何設定專案目錄
為了正確定位專案檔案，請在應用程式結構中建立專屬目錄，並將所有輸入檔案存放於其中。這樣可保持程式碼整潔，避免載入檔案時的路徑相關錯誤。使用清晰的變數名稱來表示目錄路徑，可為絕對路徑或相對於專案根目錄的路徑。

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```

將 `"Your Data Directory"` 替換為 `input.xml` 所在的絕對或相對路徑。

## 如何載入專案
`Project` 是 Aspose.Tasks 的主要物件，代表記憶體中的 Microsoft Project 檔案，讓您存取所有專案屬性與集合。建立 `Project` 實例後，您可以查詢其欄位、遍歷工作項，或在將檔案儲存回磁碟前修改資料。

```java
Project project = new Project(dataDir + "input.xml");
```

如果您的檔案名稱不同，請相應調整 `"input.xml"`。

## 如何判斷專案版本
`Prj.SAVE_VERSION` 是一個屬性，表示儲存檔案的 Microsoft Project 版本號碼。`Prj.LAST_SAVED` 是一個屬性，儲存檔案最後一次儲存的日期與時間。`Prj.SAVE_VERSION` 會回傳儲存檔案的 Microsoft Project 應用程式的數值版本（例如，12 代表 Project 2010）。`Prj.LAST_SAVED` 提供最近一次儲存操作的精確日期與時間。

```java
//Display project version property
System.out.println("Project Version : " + project.get(Prj.SAVE_VERSION));
System.out.println("Last Saved : " + project.get(Prj.LAST_SAVED));
```

這些值讓您能以程式方式強制執行特定版本的業務規則或產生稽核報告。

## 如何顯示結果
取得版本與最後儲存資訊後，通常會將其輸出至主控台或日誌檔案。使用 `System.out.println` 顯示這些值，並依需要格式化日期。這可確認擷取成功，並在開發或自動化腳本中提供即時回饋。

```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```

## 常見問題與解決方案
| 問題 | 原因 | 解決方法 |
|-------|--------|-----|
| `NullPointerException` on `project.get(...)` | 找不到檔案或路徑不正確 | 驗證 `dataDir` 與檔案名稱；測試時使用絕對路徑。 |
| Unexpected version number (e.g., 0) | 載入非 Project XML 檔案 | 確保檔案是有效的 Microsoft Project 檔案（MPP/XML）。 |
| License exception | 在生產環境使用未授權的試用版 | 套用您的 Aspose.Tasks 授權 (`License license = new License(); license.setLicense("Aspose.Tasks.lic");`). |

## 常見問答

**Q: 我可以將 Aspose.Tasks 與其他程式語言一起使用嗎？**  
A: 是的，Aspose.Tasks 支援 .NET、Java 以及 C++ 等多種語言。

**Q: Aspose.Tasks 適用於大規模專案嗎？**  
A: 絕對適用；它能在幾秒鐘內處理數百頁的專案，且不需將整個檔案載入記憶體。

**Q: 我可以使用 Aspose.Tasks 自訂專案資料嗎？**  
A: 可以，您能透過 API 修改工作項、資源、行事曆以及任何其他專案元素。

**Q: Aspose.Tasks 需要安裝 Microsoft Project 嗎？**  
A: 不需要，該函式庫可獨立運作，無需在主機上安裝 Microsoft Project。

**Q: Aspose.Tasks 有技術支援嗎？**  
A: 有，您可以在 Aspose.Tasks 論壇 [here](https://forum.aspose.com/c/tasks/15) 取得協助。

**Q: 我如何取得其他專案屬性（例如作者、公司）？**  
A: 使用 `project.get(Prj.AUTHOR)` 或 `project.get(Prj.COMPANY)`，方式與取得版本相同。

**Q: 我可以檢查 MPP（二進位）檔案的版本嗎？**  
A: 可以，Aspose.Tasks 直接載入 `.mpp` 檔案，`Prj.SAVE_VERSION` 屬性同樣適用於二進位格式。

**Q: 有辦法以程式方式將舊版專案檔升級為新版嗎？**  
A: 載入舊檔後，使用 `project.save("newfile.mpp", SaveFileFormat.MPP);` 重新儲存——Aspose.Tasks 會預設以最新格式寫入檔案。

## 結論
您現在已掌握使用 Aspose.Tasks for Java 從 MS Project 檔案取得 **how to get project version** 與 **retrieve last saved date** 的方法。將這些程式碼片段整合至自動化流程、報告工具或遷移工具中，確保您始終了解所處理的 Project 版本。

---

**最後更新：** 2026-05-31  
**測試環境：** Aspose.Tasks for Java 24.11  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [使用 Aspose.Tasks for Java 設定 MS Project 的專案開始日期](/tasks/java/project-properties/write-project-info/)
- [使用 Aspose.Tasks for Java 讀取 Microsoft Project 資料庫](/tasks/java/project-data-reading/read-project-database/)
- [使用 Aspose.Tasks for Java 將專案另存為範本、CSV 與文字檔](/tasks/java/project-file-operations/save-csv-text-template/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}