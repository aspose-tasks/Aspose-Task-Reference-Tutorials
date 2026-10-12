---
date: 2026-10-10
description: 了解如何在 Aspose.Tasks 中新增擴充屬性、使用評估函數，並使用此 Java 專案管理函式庫產生專案報告。
keywords:
- how to add extended attribute
- add custom field task
- java project management library
lastmod: 2026-10-10
linktitle: 支援 Aspose.Tasks 公式中的評估函數
og_description: 了解如何在 Aspose.Tasks 中新增擴充屬性、使用評估函數，並使用此 Java 專案管理函式庫產生專案報告。
og_image_alt: Aspose.Tasks Java tutorial showing how to add extended attribute and
  use evaluation functions
og_title: 如何在 Aspose.Tasks 公式中新增擴充屬性
schemas:
- author: Aspose
  dateModified: '2026-10-10'
  description: Learn how to add extended attribute in Aspose.Tasks, use evaluation
    functions, and generate project reports with this Java project management library.
  headline: How to add extended attribute in Aspose.Tasks formulas
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks for Java supports evaluation of a wide range of MS Project
      functions, allowing for complex calculations within Java applications.
    question: Can Aspose.Tasks for Java handle complex MS Project formulas?
  - answer: Yes, Aspose.Tasks for Java supports various versions of Microsoft Project
      files, including MPP, MPT, and XML formats.
    question: Is Aspose.Tasks for Java compatible with different versions of Microsoft
      Project files?
  - answer: Yes, you can download a free trial version of Aspose.Tasks for Java from
      the website [Aspose.Tasks for Java purchase page](https://purchase.aspose.com/buy).
    question: Can I try Aspose.Tasks for Java before purchasing?
  - answer: You can get support from the Aspose.Tasks community forum [Aspose.Tasks
      community forum](https://forum.aspose.com/c/tasks/15).
    question: How can I get support for Aspose.Tasks for Java?
  - answer: Yes, you can obtain a temporary license for testing purposes from the
      Aspose website [Aspose temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Is there a temporary license available for Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- add extended attribute
- java project management library
- Aspose.Tasks
- evaluation functions
- custom field task
title: 如何在 Aspose.Tasks 公式中新增擴充屬性
url: /zh-hant/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 公式中新增延伸屬性

## 介紹
Aspose.Tasks for Java 是一個 **Java 專案管理函式庫**，讓您透過在 Java 中建立 `Project` 物件並直接在程式碼內評估 Microsoft Project 函式來產生專案報告。透過嵌入這些公式，您可以執行複雜的計算、產生自訂報告，並在不離開開發環境的情況下自動化專案分析。在本教學中，我們將示範如何建立專案物件、加入延伸屬性，並使用評估函式 **add custom field task** 資料。

## 快速解答
- **What does “create project object java” mean?** 它會建立一個記憶體中的 `Project` 實例，您可以以程式方式操作它。  
- **Which library is required?** 需要 Aspose.Tasks for Java（從官方網站下載）。  
- **Do I need a license?** 生產環境必須使用臨時或完整的 Aspose.Tasks 授權；亦提供免費試用版。  
- **Can I use custom fields?** 是的，您可以 **add extended attribute** 到工作項，並將其視為自訂欄位。  
- **Is this compatible with all Project file formats?** Aspose.Tasks 支援 3 種主要格式（MPP、MPT、XML）以及超過 50 種其他輸入/輸出格式。

## 前置條件
在開始之前，請確保您已具備：

1. **Java Development Environment** – JDK 8 以上，並配合 IntelliJ IDEA 或 Eclipse 等 IDE。  
2. **Aspose.Tasks for Java Library** – 從 [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/) 下載並加入專案。

## 匯入套件
將 Aspose.Tasks 命名空間加入您的 Java 類別，以便操作專案、工作項與延伸屬性：

```java
import com.aspose.tasks.*;
```

## 產生專案報告 – create project object java
`Project` 類別在記憶體中表示一個 Microsoft Project 檔案，提供工作項、資源與自訂資料的存取。實例化此類別即可取得一個容納所有專案元素的容器。

```java
Project project = new Project();
```

上述程式碼 **creates project object java**，起始為空白且可供自訂。

## 如何新增延伸屬性
`ExtendedAttributeDefinition` 類別定義可附加於工作項的自訂欄位。若要新增延伸屬性，請以 `Number` 類型建立此類別的實例，指定別名（例如 “Sine”），將其加入專案的 `ExtendedAttributes` 集合，然後再連結至需要此自訂欄位的每個工作項。

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

此處我們 **add extended attribute** 類型為 `Number`、名稱為 “Sine”，並將其關聯至工作項。

## 將延伸屬性加入專案
將屬性定義註冊至專案，使每個工作項都能參照它。

```java
project.getExtendedAttributes().add(attr);
```

## 建立新任務
`Task` 代表專案中的一個工作項，且可包含自訂欄位。

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## 將自訂欄位任務加入專案
將先前定義的延伸屬性連結至新建立的工作項，為該工作項賦予可在公式或計算中使用的自訂 “Sine” 欄位。

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

現在工作項已擁有可在公式或計算中使用的自訂 “Sine” 欄位，這也是以程式方式 **add custom field task** 資料的方式。

## 為什麼使用評估函式？
評估函式允許您直接在 Aspose.Tasks 中嵌入原生 Microsoft Project 公式（例如 `Sin([Start])`），即時執行計算而無需外部處理。這樣可將所有專案邏輯集中於一處，減少資料同步錯誤，並加速報告產生。Aspose.Tasks 支援超過 100 種 MS Project 函式的評估，提供完整的計算引擎於 Java 中。

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| **Formula returns `NaN`** | 確認自訂欄位類型與預期的數值類型相符。 |
| **Extended attribute not visible** | 確保在建立工作項之前已將屬性定義加入專案。 |
| **License exception** | 安裝臨時或完整的 **Aspose.Tasks license**；試用模式可能限制某些功能。 |
| **Missing temporary license** | 從 Aspose 官方網站取得 **temporary Aspose license**。 |

## 常見問答

**Q: Aspose.Tasks for Java 能處理複雜的 MS Project 公式嗎？**  
A: 能，Aspose.Tasks for Java 支援廣泛的 MS Project 函式評估，讓您在 Java 應用程式中執行複雜計算。

**Q: Aspose.Tasks for Java 與不同版本的 Microsoft Project 檔案相容嗎？**  
A: 能，Aspose.Tasks for Java 支援多種 Microsoft Project 檔案版本，包括 MPP、MPT 與 XML 格式。

**Q: 我可以在購買前先試用 Aspose.Tasks for Java 嗎？**  
A: 能，您可從網站的 [Aspose.Tasks for Java purchase page](https://purchase.aspose.com/buy) 下載免費試用版。

**Q: 如何取得 Aspose.Tasks for Java 的支援？**  
A: 您可於 Aspose.Tasks 社群論壇取得協助，網址為 [Aspose.Tasks community forum](https://forum.aspose.com/c/tasks/15)。

**Q: 是否提供 Aspose.Tasks for Java 的臨時授權？**  
A: 能，您可從 Aspose 官方網站的 [Aspose temporary license page](https://purchase.aspose.com/temporary-license/) 取得測試用的臨時授權。

## 結論
透過本教學，您已學會 **create project object**、**add extended attribute**，並利用評估函式自動 **generate project report**。接下來，您可以在此基礎上擴展，建構更豐富的專案分析、客製化儀表板或自動排程工具——全部由 Aspose.Tasks for Java 提供動力。

---

**Last Updated:** 2026-10-10  
**Tested With:** Aspose.Tasks for Java 24.10  
**Author:** Aspose

## 相關教學

- [Custom columns and extended attributes in Java project management](/tasks/java/project-management/extended-attributes/)
- [Read Extended Task Attributes with Aspose.Tasks for Java](/tasks/java/task-properties/extended-task-attributes/)
- [How to Use Aspose.Tasks for Java – Add Extended Attributes to Resource Assignments](/tasks/java/resource-assignments/add-extended-attributes/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}