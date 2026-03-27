---
date: 2025-12-25
description: 學習如何使用 Aspose.Tasks for Java 管理財政年度屬性並有效載入 MPP 檔案。提供逐步說明與範例。
linktitle: Manage Fiscal Year Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 在 Aspose.Tasks 中管理財政年度屬性
url: /zh-hant/java/project-management/fiscal-year-properties/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 管理 Aspose.Tasks 中的財政年度屬性

## 簡介
Aspose.Tasks 是一個功能強大的 Java 函式庫，讓開發人員只需幾行程式碼即可 **管理財政年度** 設定、載入 MPP 檔案，並將專案資料轉換為 XML。在本教學中，您將看到如何設定財政年度屬性、顯示財政年度資訊，以及儲存結果，同時保持程式碼的乾淨與可維護性。

## 快速回答
- **在 Aspose.Tasks 中，「管理財政年度」是什麼意思？** 它讓您為專案定義財政年度的起始月份，並啟用財政年度編號。  
- **如何設定財政年度起始月份？** 使用 `Prj.FY_START_DATE` 屬性，搭配 `Month` 列舉值（例如 `Month.JULY`）。  
- **我可以載入 MPP 檔案嗎？** 可以，只需使用檔案路徑建立 `Project` 實例即可。  
- **如何將 MPP 轉換為 XML？** 在設定完所需屬性後，呼叫 `project.save(..., SaveFileFormat.Xml)`。  
- **我需要授權嗎？** 提供免費試用版；商業使用需購買授權。

## 什麼是專案檔案中的「管理財政年度」？
管理財政年度是指為您的專案設定用於財務報表的行事曆，包含設定財政年度的起始月份，並可選擇啟用財政年度編號，這會影響日期的計算與報表顯示方式。

## 為什麼使用 Aspose.Tasks 來處理財政年度？
- **不需 Microsoft Project** – 直接在 Java 中操作專案檔案。  
- **完整控制** – 程式化設定財政年度起始、啟用編號，並轉換格式。  
- **穩健 API** – 能可靠處理大型 MPP 檔案，並順暢匯出 XML。

## 先決條件
在開始之前，請確保您具備以下條件：
1. 已在系統上安裝 Java Development Kit (JDK)。  
2. Aspose.Tasks for Java JAR – 從 [here](https://releases.aspose.com/tasks/java/) 下載並加入專案的 classpath。

## 匯入套件
要開始使用，請在 Java 原始檔中匯入必要的類別：
```java
import com.aspose.tasks.*;
```

## 如何載入 MPP 檔案並顯示財政年度資訊
以下將流程分解為清晰的步驟說明。

### 步驟 1：載入專案檔案
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```
此處 **載入 MPP 檔案** (`project.mpp`) 於指定目錄。這是任何財政年度相關操作的第一步。

### 步驟 2：顯示財政年度屬性
```java
//Display fiscal year properties
System.out.println("Fiscal Year Start Date : " + project.get(Prj.FY_START_DATE));
System.out.println("Fiscal Year Numbering : " + project.get(Prj.FISCAL_YEAR_START));
```
`Prj.FY_START_DATE` 與 `Prj.FISCAL_YEAR_START` 屬性可讓您 **顯示財政年度** 詳細資訊，回答「目前的財政設定是什麼？」的問題。

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
在此步驟說明 **如何設定財政** 相關設定：
- `Month.JULY` 定義財政年度的起始月份。  
- `NullableBool(true)` 開啟財政年度編號。  
- 最後，使用 `SaveFileFormat.Xml` 將專案 **從 MPP 轉換為 XML**。

### 步驟 4：確認操作
```java
//Display result of conversion.
System.out.println("Process completed Successfully");
```
簡單的主控台訊息確認財政年度已完成設定，且檔案已成功儲存。

## 常見問題與解決方案
| Issue | Solution |
|-------|----------|
| **月份值不正確** | 確保使用 `Month` 列舉 (例如 `Month.JANUARY`)。 |
| **找不到檔案** | 確認 `dataDir` 指向正確的資料夾，且檔案名稱相符。 |
| **儲存失敗** | 檢查目標目錄的寫入權限，並確認支援 `SaveFileFormat`。 |

## 常見問答

**Q: 我可以使用 Aspose.Tasks for Java 來操作其他專案屬性嗎？**  
A: 可以，Aspose.Tasks 提供完整功能，可管理除財政年度設定之外的各種專案屬性。

**Q: Aspose.Tasks for Java 是否相容於不同的專案檔案格式？**  
A: 是的，它支援多種格式，包括 MPP、XML 等。

**Q: 若在使用 Aspose.Tasks for Java 時遇到問題，該如何取得支援？**  
A: 您可以在 Aspose.Tasks 社群的 [forum](https://forum.aspose.com/c/tasks/15) 尋求協助，或直接聯絡他們的支援團隊。

**Q: Aspose.Tasks 是否提供免費試用版？**  
A: 有的，您可從 [here](https://releases.aspose.com/) 取得 Aspose.Tasks 的免費試用版。

**Q: 我可以從哪裡購買 Aspose.Tasks for Java 的授權？**  
A: 您可於 [here](https://purchase.aspose.com/buy) 購買 Aspose.Tasks for Java 的授權。

## 結論
在 Aspose.Tasks for Java 中管理財政年度屬性相當簡單。依照上述步驟，您即可 **管理財政年度**、**載入 MPP 檔案**、**顯示財政年度** 詳情，並 **將 MPP 轉換為 XML**，確保專案排程與組織的財務行事曆保持一致。

---

**Last Updated:** 2025-12-25  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}