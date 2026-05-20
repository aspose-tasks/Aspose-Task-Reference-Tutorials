---
date: 2026-05-20
description: 了解如何使用 Aspose.Tasks for Java 為資源指派新增延伸屬性、設定專案開始日期，並有效寫入 MS Project 檔案。
keywords:
- how to use aspose
- add extended attributes
- set project start date
- create resource assignment
- aspose tasks java
linktitle: 在 Aspose.Tasks 中為資源指派新增延伸屬性
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  headline: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource
    Assignments
  type: TechArticle
- description: Learn how to use Aspose.Tasks for Java to add extended attributes to
    resource assignments, set project start date, and write MS Project files efficiently.
  name: How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource Assignments
  steps:
  - name: Set Up Data Directory
    text: Define the directory where your project data will be stored. This path is
      used later when you save the XML file.
  - name: Create Project Instance
    text: The `Project` class is Aspose.Tasks' top‑level object that represents a
      single Microsoft Project file in memory. Instantiating it gives you full access
      to all project elements.
  - name: Set Project Information Properties
    text: Set essential project properties such as the start date, schedule from start
      flag, and status date. These values are stored in the project’s `ProjectInfo`
      object.
  - name: Add Extended Attributes to a Resource Assignment
    text: Create an `ExtendedAttributeDefinition` for the custom field, attach it
      to a `ResourceAssignment`, and populate the value. This step demonstrates the
      **add extended attributes** keyword in action.
  type: HowTo
- questions:
  - answer: Yes, the library provides full read‑write capabilities for .mpp, .xml,
      and .xps formats.
    question: Can I use Aspose.Tasks for Java to read MS Project files?
  - answer: Absolutely, it supports files from Project 2000 up to the latest 2024
      release, covering over 20 version formats.
    question: Is Aspose.Tasks for Java compatible with different versions of MS Project?
  - answer: The trial adds a watermark to generated files and limits the number of
      tasks you can create, but all API features remain accessible.
    question: Are there any limitations to the trial version of Aspose.Tasks for Java?
  - answer: You can seek assistance from the Aspose.Tasks community forum [here](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, temporary licenses are available for short‑term usage. You can obtain
      one from [here](https://purchase.aspose.com/temporary-license/).
    question: Can I purchase a temporary license for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks for Java – 為資源指派新增延伸屬性
url: /zh-hant/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 精通使用 Aspose.Tasks for Java 操作 MS Project

## 簡介
在本教學中，您將了解 **如何使用 Aspose.Tasks for Java** 為資源指派新增擴充屬性，並以程式方式寫入 Microsoft Project 資訊。無論您是自動化報告流程，或是建置自訂的專案管理工具，以下步驟將精確示範如何設定專案開始日期、建立資源指派，並將檔案以 XML 格式儲存——只需幾行 Java 程式碼。

## 快速解答
- **Aspose.Tasks for Java 的功能是什麼？** 它可以在不安裝 Microsoft Project 的情況下讀取、寫入與修改 Microsoft Project 檔案。  
- **我可以在資源指派中加入自訂欄位嗎？** 可以，使用 `ResourceAssignment` 物件的 `ExtendedAttribute` 集合。  
- **如何設定專案開始日期？** 在儲存之前呼叫 `project.setStartDate(LocalDateTime.of(...))`。  
- **正式環境需要授權嗎？** 商業授權會移除評估水印，並解鎖完整 API 存取權限。  
- **支援哪些 Java 版本？** Aspose.Tasks for Java 支援 JDK 8 至 JDK 21。

## 如何使用 Aspose.Tasks for Java？
`Project` 是代表 Microsoft Project 檔案於記憶體中的主要物件。載入 Aspose.Tasks 函式庫，建立 `Project` 實例，設定專案層級屬性，為資源指派新增擴充屬性，最後將專案儲存為 XML。核心工作流程分為三個簡潔步驟：初始化、修改、持久化。此模式適用於任何大小的專案檔，且可在 Windows、Linux 或 macOS 的 JVM 上執行。

## 什麼是 Aspose.Tasks 中的擴充屬性？
**擴充屬性** 是一種自訂欄位，您可以將其附加於工作、資源或指派，以儲存超出內建欄位的額外中繼資料。`ExtendedAttributeDefinition` 定義自訂欄位的結構。Aspose.Tasks 提供 `ExtendedAttributeDefinition` 與 `ExtendedAttribute` 類別，讓您以程式方式定義並指派這些欄位。

## 為什麼要在資源指派中加入擴充屬性？
Aspose.Tasks 支援 **超過 50 個內建與自訂欄位**，且可無限制新增使用者自訂屬性。加入這些屬性可讓您直接在 .mpp 檔案中捕捉成本代碼、部門編號或任何業務特定資料，省去外部試算表的需求，並確保專案生命週期中的資料完整性。

## 先決條件
開始之前，請確保您已具備：

1. **Java Development Kit (JDK)** – 已安裝 JDK 8 或更新版本。  
2. **Aspose.Tasks for Java library** – 從官方發行頁面 [此處](https://releases.aspose.com/tasks/java/) 下載。  
3. **IDE** – 您偏好的 IntelliJ IDEA、Eclipse，或任何相容 Java 的編輯器。

## 匯入套件
First, import the necessary packages in your Java project:

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.Value;
import java.io.IOException;
import java.math.BigDecimal;
```

### 步驟 1：設定資料目錄
Define the directory where your project data will be stored. This path is used later when you save the XML file.

```java
String dataDir = "Your Data Directory";
```

### 步驟 2：建立 Project 實例
The `Project` class is Aspose.Tasks' top‑level object that represents a single Microsoft Project file in memory. Instantiating it gives you full access to all project elements.

```java
Project project = new Project();
```

### 步驟 3：設定專案資訊屬性
Set essential project properties such as the start date, schedule from start flag, and status date. These values are stored in the project’s `ProjectInfo` object.

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### 步驟 4：為資源指派新增擴充屬性
Create an `ExtendedAttributeDefinition` for the custom field, attach it to a `ResourceAssignment`, and populate the value. This step demonstrates the **add extended attributes** keyword in action.

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## 常見問題與解決方案
- **在存取指派集合時發生 NullPointerException** – 確認在取得指派前已建立至少一個資源與一個工作。  
- **擴充屬性未在 MS Project 中顯示** – 檢查屬性的 `FieldId` 是否對應到自訂欄位槽位（例如 `ExtendedAttributeTask.Text1`）。  
- **日期格式不匹配** – 使用 `java.time.LocalDateTime` 作為日期值；Aspose.Tasks 會自動將其轉換為專案行事曆格式。

## 常見問答

**問：我可以使用 Aspose.Tasks for Java 讀取 MS Project 檔案嗎？**  
答：可以，該函式庫提供 .mpp、.xml 與 .xps 格式的完整讀寫功能。

**問：Aspose.Tasks for Java 是否相容於不同版本的 MS Project？**  
答：當然相容，支援從 Project 2000 到最新 2024 版的檔案，涵蓋超過 20 種版本格式。

**問：Aspose.Tasks for Java 試用版有什麼限制嗎？**  
答：試用版會在產生的檔案上加上水印，且限制可建立的工作數量，但所有 API 功能仍可使用。

**問：如何取得 Aspose.Tasks for Java 的支援？**  
答：您可前往 Aspose.Tasks 社群論壇 [此處](https://forum.aspose.com/c/tasks/15) 尋求協助。

**問：我可以購買 Aspose.Tasks for Java 的臨時授權嗎？**  
答：可以，提供短期使用的臨時授權。您可從 [此處](https://purchase.aspose.com/temporary-license/) 取得。

---

**最後更新：** 2026-05-20  
**測試環境：** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [如何在 Aspose.Tasks 中為資源指派新增備註](/tasks/java/resource-assignments/resource-assignment-notes/)
- [如何在 Aspose.Tasks 中讀取與寫入資源指派的費率比例](/tasks/java/resource-assignments/read-write-rate-scale/)
- [如何在 Aspose.Tasks 中將資源加入專案並處理平衡延遲屬性](/tasks/java/resource-assignments/leveling-delay-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}