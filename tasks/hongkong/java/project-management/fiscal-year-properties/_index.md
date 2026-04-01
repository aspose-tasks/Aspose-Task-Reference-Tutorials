---
date: 2026-04-01
description: 學習如何使用 Aspose.Tasks for Java 儲存 XML、設定財政年度，並將 MPP 轉換為 XML。逐步指南，附程式碼範例。
keywords:
- how to save xml
- how to set fiscal
- convert mpp to xml
linktitle: 如何在 Aspose.Tasks 中儲存 XML 及管理財政年度
second_title: Aspose.Tasks Java API
title: 如何在 Aspose.Tasks 中儲存 XML 及管理會計年度
url: /zh-hant/java/project-management/fiscal-year-properties/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何儲存 XML 及管理 Aspose.Tasks 中的財政年度

## 簡介
如果您需要 **how to save xml** 從 Microsoft Project 資料產生的檔案，Aspose.Tasks for Java 為您提供一個乾淨且免授權費的解決方案。在本教學中，我們將示範如何載入 MPP 檔案、顯示財政年度資訊、設定財政年度屬性，最後 **how to save xml** 輸出。您還會看到如何 **how to set fiscal** 細節以及 **how to convert mpp** 檔案，而無需開啟 Microsoft Project。

## 快速解答
- **什麼是 Aspose.Tasks 中的「manage fiscal year」？** 它讓您定義財政年度的起始月份，並為專案啟用財政年度編號。
- **如何設定財政年度起始月份？** 使用 `Prj.FY_START_DATE` 屬性搭配 `Month` 列舉值（例如 `Month.JULY`）。
- **我可以載入 MPP 檔案嗎？** 是的，只需使用指向 *.mpp* 檔案的路徑建立 `Project` 實例。
- **如何將 MPP 轉換為 XML？** 在設定任何所需屬性後，呼叫 `project.save(..., SaveFileFormat.Xml)`。
- **我需要授權嗎？** 可使用免費試用版；在正式環境中需購買商業授權。

## 什麼是專案檔案中的「manage fiscal year」？
管理財政年度表示為您的專案設定用於財務報告的行事曆。這包括設定財政年度的起始月份，並可選擇啟用財政年度編號，這會影響日期的計算方式以及在報告中的顯示。

## 為何使用 Aspose.Tasks 處理財政年度？
- **不需要 Microsoft Project** – 直接在 Java 中處理專案檔案。
- **完整控制** – 程式化設定財政年度起始、啟用編號，並轉換格式。
- **強大 API** – 能可靠處理大型 MPP 檔案，並順暢匯出 XML。

## 先決條件
在開始之前，請確保您具備以下條件：
1. 已在系統上安裝 Java Development Kit (JDK)。  
2. Aspose.Tasks for Java JAR – 從 [here](https://releases.aspose.com/tasks/java/) 下載，並將其加入專案的 classpath。

## 匯入套件
要開始使用，請在 Java 原始檔案中匯入必要的類別：
```java
import com.aspose.tasks.*;
```

## 如何載入 MPP 檔案並顯示財政年度資訊
以下我們將此流程分解為清晰的編號步驟。

### 步驟 1：載入專案檔案
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
在此我們 **load an MPP file** (`project.mpp`) 從指定目錄載入。這是任何與財政年度相關操作的第一步。

### 步驟 2：顯示財政年度屬性
```java
//Display fiscal year properties
System.out.println("Fiscal Year Start Date : " + project.get(Prj.FY_START_DATE));
System.out.println("Fiscal Year Numbering : " + project.get(Prj.FISCAL_YEAR_START));
```
`Prj.FY_START_DATE` 與 `Prj.FISCAL_YEAR_START` 屬性讓您 **display fiscal year** 細節，回答「目前的財政設定為何？」的問題。

### 步驟 3：設定財政年度起始並啟用編號
```java
//Create a project instance
Project prj = new Project();
//Set fiscal year properties
prj.set(Prj.FY_START_DATE, Month.JULY);
prj.set(Prj.FISCAL_YEAR_START, new NullableBool(true));
//Save the project as XML project file
prj.save(dataDir + "savedProject.xml", SaveFileFormat.Xml);
```
在此步驟我們 **how to set fiscal** 設定：
- `Month.JULY` 定義財政年度的起始月份。  
- `NullableBool(true)` 開啟財政年度編號。  
- 最後，使用 `SaveFileFormat.Xml` **converted MPP to XML** 專案。

### 步驟 4：確認操作
```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```
簡單的主控台訊息會確認財政年度已設定，且檔案已儲存。

## 為何這很重要
將專案儲存為 XML 可提供可攜帶的文字型表示，便於解析、版本控制或與其他系統整合。當財政年度設定正確時，下游的財務報告與儀表板將與貴組織的會計期間保持一致。

## 常見使用情境
- **財務報告** – 在匯出至 BI 工具前，將專案排程與財政行事曆對齊。
- **資料遷移** – 將舊版 *.mpp* 檔案轉換為 XML，以匯入雲端專案管理平台。
- **自動稽核** – 以程式方式驗證每個專案使用正確的財政起始月份。

## 故障排除技巧與常見陷阱
| 問題 | 解決方案 |
|-------|----------|
| **Incorrect month value** | 確認使用 `Month` 列舉（例如 `Month.JANUARY`）。 |
| **File not found** | 確認 `dataDir` 指向正確的資料夾，且檔名相符。 |
| **Saving fails** | 檢查目標目錄的寫入權限，並確認支援 `SaveFileFormat`。 |
| **Fiscal year not reflected in XML** | 儲存後，開啟 XML 並確認 `<FiscalYearStart>` 與 `<FiscalYearNumbering>` 節點包含預期的值。 |

## 常見問與答

**Q: 我可以使用 Aspose.Tasks for Java 來操作其他專案屬性嗎？**  
A: 可以，Aspose.Tasks 提供完整功能，管理除財政年度設定之外的各種專案屬性。

**Q: Aspose.Tasks for Java 是否相容於不同的專案檔案格式？**  
A: 是的，它支援包括 MPP、XML 等多種格式。

**Q: 若在使用 Aspose.Tasks for Java 時遇到問題，該如何取得支援？**  
A: 您可以在 Aspose.Tasks 社群的 [forum](https://forum.aspose.com/c/tasks/15) 尋求協助，或直接聯絡他們的支援團隊。

**Q: Aspose.Tasks 是否提供免費試用版？**  
A: 是的，您可從 [here](https://releases.aspose.com/) 取得 Aspose.Tasks 的免費試用版。

**Q: 我該從哪裡購買 Aspose.Tasks for Java 的授權？**  
A: 您可從 [here](https://purchase.aspose.com/buy) 購買 Aspose.Tasks for Java 的授權。

## 結論
在 Aspose.Tasks for Java 中管理財政年度屬性相當簡單。依照上述步驟，您即可自信地 **how to save xml**、**load mpp file**、**display fiscal year**、**set fiscal year** 與 **convert mpp to xml**。運用這些技巧，讓您的專案排程與組織的財務行事曆保持一致，並產生可供下游處理的可攜帶 XML 表示。

---

**最後更新：** 2026-04-01  
**測試環境：** Aspose.Tasks for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}