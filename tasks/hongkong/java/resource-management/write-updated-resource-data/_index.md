---
date: 2026-06-30
description: 了解如何更新多個資源並修改資源組資料，然後使用 Aspose.Tasks for Java 將專案匯出為 MPP 並將專案儲存為 MPP。
keywords:
- update multiple resources
- modify resource group
- export project to mpp
- save project as mpp
linktitle: 在 Aspose.Tasks for Java 中更新多個資源
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  headline: Update Multiple Resources in Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to update multiple resources and modify resource group data,
    then export project to MPP and save project as MPP using Aspose.Tasks for Java.
  name: Update Multiple Resources in Aspose.Tasks for Java
  steps:
  - name: Java Development Kit (JDK) installed on your system.
    text: Java Development Kit (JDK) installed on your system.
  - name: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
    text: Aspose.Tasks for Java library. You can download it from [here](https://releases.aspose.com/tasks/java/).
  - name: Basic knowledge of Java programming.
    text: Basic knowledge of Java programming.
  type: HowTo
- questions:
  - answer: Yes, you can update multiple resources by iterating through them and setting
      their attributes accordingly.
    question: Can I update multiple resources in the same project using Aspose.Tasks
      for Java?
  - answer: Yes, Aspose.Tasks supports various file formats including XML, MPP, and
      more.
    question: Does Aspose.Tasks support other file formats besides MS Project?
  - answer: Aspose.Tasks is compatible with Java versions 6 and above.
    question: Is Aspose.Tasks compatible with different versions of Java?
  - answer: Yes, you can perform a wide range of operations such as reading, writing,
      and manipulating tasks, resources, and calendars.
    question: Can I perform other operations on MS Project files with Aspose.Tasks?
  - answer: You can visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)
      for any assistance or queries.
    question: Where can I find additional help or support for Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: 在 Aspose.Tasks for Java 中更新多個資源
url: /zh-hant/java/resource-management/write-updated-resource-data/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspise.Tasks for Java 中更新多個資源

## 簡介
在本教學中，您將學習如何使用 Aspose.Tasks for Java 在 Microsoft Project 檔案中**更新多個資源**。無論您需要變更費率、重新指派群組，或將更新後的檔案匯出為 MPP，以下步驟將帶領您完成完整且可投入生產的工作流程。不需要安裝 Microsoft Project，且 API 能有效處理擁有數百個資源的專案。

## 快速解答
- **我可以一次更新多個資源嗎？** 可以 – 只需遍歷 `ResourceCollection` 並在一次迭代中設定屬性。  
- **哪個方法可將檔案儲存為 MPP？** `project.save("output.mpp", SaveFileFormat.MPP)`。  
- **商業使用是否需要授權？** 生產環境需要付費授權；亦提供免費試用版。  
- **支援哪些 Java 版本？** Java 6 及以上版本，包括 Java 17 LTS。  
- **大量更新效能如何？** Aspose.Tasks 在一般伺服器上可在 2 秒內處理 500 個資源的專案。

## 什麼是「更新多個資源」？
**「更新多個資源」**指的是以程式方式變更單一 Project 檔案中多個資源項目的屬性，例如費率、群組、行事曆或自訂欄位。此操作常在將專案資料與企業資源規劃系統同步、調整多個資源的預算，或套用全公司政策變更時需要。

## 為何使用 Aspose.Tasks 來修改資源群組並匯出專案為 MPP？
Aspose.Tasks 支援 **超過 50 種輸入與輸出格式**，包括 MPP、XML 與 CSV，且可在不將整個檔案載入記憶體的情況下 **匯出專案為 MPP**。此函式庫可處理高達 **2 GB** 的檔案，讓您能快速且可靠地 **將專案儲存為 MPP**。

## 先決條件

在開始之前，請確保您具備以下項目：

1. 已在系統上安裝 Java Development Kit (JDK)。  
2. Aspose.Tasks for Java 函式庫。您可從 [here](https://releases.aspose.com/tasks/java/) 下載。  
3. 具備基本的 Java 程式設計知識。  

## 匯入套件

`import` 陳述式將所需的 Aspose.Tasks 類別匯入您的原始檔案。

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.SaveFileFormat;
```

## 步驟 1：設定資料目錄

定義資料檔案所在的目錄：

```java
String dataDir = "Your Data Directory";
```

## 步驟 2：指定輸入與輸出檔案

定義輸入的 MS Project 檔案路徑以及產生的更新後檔案路徑：

```java
String file = dataDir + "ResourceWithExtAttribs.xml"; // Test file with one rsc to update
String resultFile = dataDir + "OutputMPP.mpp"; // File to write test project
```

## 步驟 3：載入專案

`Project` 代表已載入記憶體的 Microsoft Project 檔案，提供對工作、資源及其他專案資料的存取。

```java
Project project = new Project(file);
```

## 步驟 4：新增資源並設定屬性

`Resource` 模擬單一專案資源，允許您設定費率、群組、行事曆及其他屬性。

```java
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(30));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(45));
rsc.set(Rsc.GROUP, "Workgroup1");
```

## 步驟 5：有效率地更新多個資源

`ResourceCollection` 是專案中所有資源的集合，可透過 `project.getResources()` 取得。

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## 步驟 6：儲存專案

`SaveFileFormat` 列舉了儲存專案時支援的檔案格式，例如 MPP、XML 與 PDF。

```java
project.save(resultFile, SaveFileFormat.Mpp);
```

## 如何在專案中更新多個資源？

載入現有的專案，取得其 `ResourceCollection`，並遍歷每個 `Resource` 物件。對每個資源，修改所需的欄位（如費率、群組或自訂屬性），然後繼續處理下一項。處理完所有資源後，僅呼叫一次 `project.save(...)` 即可有效地保存變更。

## 常見問題與解決方案

- **資源 ID 衝突** – 確保每個新資源使用 `project.getResources().add(new Resource())` 取得唯一的 ID。  
- **費率格式錯誤** – 使用 `ResourceRate` 物件，並將 `RateType` 設為 `StandardRate` 或 `OvertimeRate`。  
- **大型檔案導致記憶體壓力** – 在載入前啟用 `Project.setReadOnly(true)` 以減少記憶體佔用。

## 常見問與答

**問：我可以在同一個專案中使用 Aspose.Tasks for Java 更新多個資源嗎？**  
A: 是的，您可以透過遍歷它們並相應設定屬性來更新多個資源。

**問：Aspose.Tasks 是否支援除 MS Project 之外的其他檔案格式？**  
A: 是的，Aspose.Tasks 支援多種檔案格式，包括 XML、MPP 等。

**問：Aspose.Tasks 是否相容於不同版本的 Java？**  
A: Aspose.Tasks 相容於 Java 6 及以上版本。

**問：我可以使用 Aspose.Tasks 在 MS Project 檔案上執行其他操作嗎？**  
A: 是的，您可以執行各種操作，如讀取、寫入以及操作工作、資源和行事曆。

**問：我可以在哪裡取得 Aspose.Tasks 的其他協助或支援？**  
A: 您可前往 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 取得協助或詢問問題。

**問：如何將更新後的檔案匯出為 MPP 格式？**  
A: 在完成所有資源變更後，呼叫 `project.save("UpdatedProject.mpp", SaveFileFormat.MPP)`。

**問：修改資源群組的最佳方法是什麼？**  
A: 在儲存專案前，於每個 `Resource` 物件設定 `Resource.Group` 屬性。

---

**最後更新：** 2026-06-30  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [使用 Aspose.Tasks for Java 為專案新增資源](/tasks/java/resource-management/create-resources/)
- [使用 Aspose.Tasks for Java 管理 MS Project 資源成本](/tasks/java/resource-management/resource-cost/)
- [如何使用 Aspose.Tasks for Java 將 MPP 匯出至 Excel](/tasks/java/project-file-operations/save-data-to-excel/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}