---
date: 2026-06-10
description: 了解如何在 Java 中建立擴充屬性、載入 Microsoft Project 檔案、設定數值，並使用 Aspose.Tasks for
  Java 將專案儲存為 XML。
keywords:
- create extended attribute java
- custom attribute Aspose.Tasks
- Java project management
linktitle: 處理 Aspose.Tasks 中的擴充資源屬性
schemas:
- author: Aspose
  dateModified: '2026-06-10'
  description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  headline: How to create extended attribute in Java with Aspose.Tasks
  type: TechArticle
- description: Learn how to create extended attribute in Java, load a Microsoft Project
    file, set numeric values, and save the project as XML using Aspose.Tasks for Java.
  name: How to create extended attribute in Java with Aspose.Tasks
  steps:
  - name: Define Data Directory
    text: '`Paths` is a utility class that provides methods to obtain a file system
      path in a platform‑independent way.'
  - name: Load Microsoft Project File
    text: '`Project` represents a Microsoft Project file in memory, allowing read
      and write access to its contents.'
  - name: Define the Custom Attribute
    text: '`ExtendedAttributeDefinition` defines the schema of a new custom field
      that can be attached to resources or tasks.'
  - name: Set Numeric Value in Java
    text: '`ExtendedAttributeResource` holds the value of a custom attribute for a
      specific resource instance.'
  - name: Add Resource and Attach the Custom Attribute
    text: '`Resource` models a project resource such as a person, equipment, or material.'
  - name: Save Project as XML
    text: '`SaveFileFormat` enumerates the supported output formats for saving a project,
      including XML.'
  - name: Display Result
    text: '`System.out.println` prints a line of text to the standard console output.'
  type: HowTo
- questions:
  - answer: Yes – use `ExtendedAttributeTask` instead of `ExtendedAttributeResource`
      when defining the attribute schema.
    question: Can I create custom attributes for tasks as well as resources?
  - answer: Absolutely. Create separate `ExtendedAttributeDefinition` objects for
      each attribute and attach them to the desired resources or tasks.
    question: Is it possible to add multiple custom attributes at once?
  - answer: Aspose.Tasks supports XML, MPP, PDF, HTML, and more than 30 additional
      formats. In this example we used `SaveFileFormat.Xml`.
    question: What formats can I save the project in?
  - answer: A temporary evaluation license is sufficient for testing. For any production
      deployment, a full commercial license is required.
    question: Do I need a license for development builds?
  - answer: Call `resource.getExtendedAttributes()` and iterate over the collection;
      retrieve the stored value with `getNumericValue()` or `getTextValue()`.
    question: How do I read back the custom attribute values later?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: 如何在 Java 中使用 Aspose.Tasks 建立擴充屬性
url: /zh-hant/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中使用 Aspose.Tasks 建立擴充屬性

## 介紹
在本實作指南中，您將 **在 Java 中建立擴充屬性** 以用於 Microsoft Project 檔案，使用 Aspose.Tasks。我們將示範如何載入既有專案、定義新的數值屬性、將值指派給資源，最後以 XML 檔案儲存變更。完成後，您將擁有可在任何基於 Java 的專案管理解決方案中直接使用的可重用程式碼範本。

## 快速解答
- **什麼是擴充屬性？**  
  使用者自訂欄位（例如：年齡、技能等級），用來為資源或工作項存放額外資料。  
- **哪個 API 用來建立？**  
  Aspose.Tasks for Java 提供 `ExtendedAttributeDefinition` 類別，用於定義與管理自訂屬性。  
- **需要授權嗎？**  
  開發階段可使用臨時評估授權；正式上線須購買完整授權。  
- **可以儲存數字嗎？**  
  可以 – 使用 `setNumericValue(BigDecimal)` 來指派精確的十進位值。  
- **如何永久保存變更？**  
  呼叫 `project.save("output.xml", SaveFileFormat.Xml)` 即可將更新後的專案寫入 XML 格式。

## 什麼是自訂屬性？
**自訂屬性**（亦稱為擴充屬性）是您可以在 Microsoft Project 的資源或工作項中新增的額外欄位。它讓您能捕捉內建欄位未涵蓋的資料，例如員工年齡、認證等級，或任何業務特定指標。

## 為什麼要在 Java 中建立擴充屬性？
在 Java 中建立擴充屬性可讓您以程式方式豐富專案資料，確保檔案間的一致性，並支援自動化報表。只要定義一次屬性，即可套用至任意數量的資源或工作項，省時減錯。

- **依組織需求客製化資料** – 無需手動 Excel 處理，即可儲存任何重要指標。  
- **提升報表深度** – 之後可針對自訂欄位進行查詢，製作儀表板或分析。  
- **維持一致性** – 以程式方式在多個專案中套用相同定義，避免人工錯誤。  
- **效能測試** – 根據產品基準測試，Aspose.Tasks 可在不將整個檔案載入記憶體的情況下，處理多達 10,000 個工作項與 5,000 個資源。

## 前置條件
在開始之前，請確保您已具備：

1. **Java Development Kit** – 已安裝 JDK 8 或更新版本。  
2. **Aspose.Tasks for Java** – 從 [here](https://releases.aspose.com/tasks/java/) 下載最新發行版。  
3. **IDE** – Eclipse、IntelliJ IDEA，或任何相容的 Java 開發環境。  

## 如何在 Java 中建立擴充屬性？
載入專案、定義屬性、將其附加至資源，最後儲存檔案——只需幾個簡單步驟。以下各節將說明每一步，並提供放置實際程式碼的佔位符。

### 步驟說明

#### 匯入套件
`Project`、`ExtendedAttributeDefinition`、`ExtendedAttributeResource` 以及相關類別位於 `com.aspose.tasks` 命名空間。請在 Java 檔案頂部匯入它們。

```java
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.ExtendedAttributeDefinition;
import com.aspose.tasks.ExtendedAttributeResource;
import com.aspose.tasks.ExtendedAttributeTask;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.SaveFileFormat;
import java.math.BigDecimal;
```

#### 步驟 1：定義資料目錄
`Paths` 為工具類別，可提供平台無關的檔案系統路徑取得方法。

```java
String dataDir = "Your Data Directory";
```

#### 步驟 2：載入 Microsoft Project 檔案
`Project` 代表記憶體中的 Microsoft Project 檔案，允許讀寫其內容。

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

#### 步驟 3：定義自訂屬性
`ExtendedAttributeDefinition` 定義可附加於資源或工作項的新自訂欄位之結構。

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

#### 步驟 4：在 Java 中設定數值
`ExtendedAttributeResource` 保存特定資源實例的自訂屬性值。

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

#### 步驟 5：新增資源並附加自訂屬性
`Resource` 代表專案中的資源，如人員、設備或材料。

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

#### 步驟 6：將專案儲存為 XML
`SaveFileFormat` 列舉了支援的輸出格式，包括 XML。

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

#### 步驟 7：顯示結果
`System.out.println` 將文字列印至標準主控台輸出。

```java
System.out.println("Process completed Successfully");
```

## 常見陷阱與技巧
- **屬性 ID 衝突**：在建立新定義前，務必先呼叫 `project.getExtendedAttributes().getById(id)`，避免重複的識別碼。  
- **精度處理**：建議使用 `BigDecimal` 取代 `float`/`double`，以確保數值精確，避免報表中出現四捨五入誤差。  
- **檔案路徑可靠性**：使用 `Paths.get(...).toAbsolutePath()` 或在 IDE 中設定工作目錄，以避免 `FileNotFoundException`。

## 常見問與答

**Q: 我可以同時為工作項與資源建立自訂屬性嗎？**  
A: 可以 – 定義屬性結構時，使用 `ExtendedAttributeTask` 取代 `ExtendedAttributeResource` 即可。

**Q: 能一次新增多個自訂屬性嗎？**  
A: 完全可以。為每個屬性建立獨立的 `ExtendedAttributeDefinition` 物件，然後分別附加至目標資源或工作項。

**Q: 我可以將專案儲存為哪些格式？**  
A: Aspose.Tasks 支援 XML、MPP、PDF、HTML 等超過 30 種格式。本範例使用 `SaveFileFormat.Xml`。

**Q: 開發版需要授權嗎？**  
A: 測試時使用臨時評估授權即可。任何正式上線的部署，都必須購買完整商業授權。

**Q: 之後要如何讀取自訂屬性值？**  
A: 呼叫 `resource.getExtendedAttributes()`，遍歷集合，並使用 `getNumericValue()` 或 `getTextValue()` 取得儲存的值。

---

**最後更新：** 2026-06-10  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose

## 相關教學

- [How to Create Resources – Resource Management with Aspose.Tasks for Java](/tasks/java/resource-management/)
- [Create custom field Aspose - Handle extended attributes](/tasks/java/project-management/extended-attributes/)
- [How to Create Project – Set New Task Attributes with Aspose.Tasks](/tasks/java/project-file-operations/set-attributes-new-tasks/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}