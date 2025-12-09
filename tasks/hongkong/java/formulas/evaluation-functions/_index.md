---
date: 2025-12-09
description: 學習如何使用 Java 建立 Project 物件，並在 Aspose.Tasks 公式中支援評估函式。了解如何為任務建立擴充屬性。
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: 建立專案物件 Java – 支援 Aspose.Tasks 中的評估功能
url: /zh-hant/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 公式中支援評估函式

## 介紹
Aspose.Tasks for Java 讓您 **建立 project object java** 實例，並直接在 Java 程式碼中評估 Microsoft Project 函式。透過嵌入這些公式，您可以執行複雜計算、產生自訂報表，並在不離開開發環境的情況下自動化專案分析。本教學將逐步說明整個流程——從設定專案物件到新增可保存自訂資料的延伸屬性。

## 快速答覆
- **「create project object java」是什麼意思？** 它會在記憶體中建立一個 `Project` 實例，讓您以程式方式操作。  
- **需要哪個程式庫？** Aspose.Tasks for Java（從官方網站下載）。  
- **需要授權嗎？** 生產環境必須使用臨時或正式授權；亦提供免費試用版。  
- **可以使用自訂欄位嗎？** 可以——您能定義並將延伸屬性附加至工作。  
- **是否相容所有 Project 檔案格式？** Aspose.Tasks 支援 MPP、MPT 與 XML 格式。

## 前置條件
在開始之前，請確保您已具備：

1. **Java 開發環境** – JDK 8 以上，並使用 IntelliJ IDEA 或 Eclipse 等 IDE。  
2. **Aspose.Tasks for Java 程式庫** – 從 [Aspose.Tasks for Java 下載頁面](https://releases.aspose.com/tasks/java/) 下載並加入專案。

## 匯入套件
在 Java 類別中加入 Aspose.Tasks 命名空間，以便操作專案、工作與延伸屬性：

```java
import com.aspose.tasks.*;
```

## 步驟 1：建立 Project Object Java
建立一個新的 `Project` 物件。此物件將作為所有工作、資源與自訂資料的容器。

```java
Project project = new Project();
```

上述程式碼 **creates project object java**，建立一個空白且可供自訂的專案實例。

## 步驟 2：如何建立延伸屬性
定義一個延伸屬性，用於儲存每個工作之自訂數值資料（例如正弦值）。

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

此處 **create extended attribute** 為類型 `Number`、名稱為「Sine」的屬性，並將其關聯至工作。

## 步驟 3：將延伸屬性加入專案
將屬性定義註冊到專案，使每個工作都能參照它。

```java
project.getExtendedAttributes().add(attr);
```

## 步驟 4：建立新工作
在專案的根工作下新增一個簡單的工作，名稱為「Task」。

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## 步驟 5：將延伸屬性關聯至工作
將先前定義的延伸屬性連結到新建立的工作。

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

現在此工作已擁有自訂的「Sine」欄位，您可以在公式或計算中使用它。

## 為什麼要使用評估函式？
在 Aspose.Tasks 公式中嵌入 MS Project 函式，可讓您：

- 即時執行計算（例如 `Sin([Start])`），無需外部工具。  
- 將所有專案邏輯集中於單一、易於維護的程式碼庫。  
- 產生即時反映資料變更的動態報表。

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| **公式回傳 `NaN`** | 確認自訂欄位類型與預期的數值類型相符。 |
| **延伸屬性未顯示** | 確保在建立工作 **之前** 已將屬性定義加入專案。 |
| **授權例外** | 安裝臨時或正式授權；試用模式可能限制某些功能。 |

## 常見問答

**Q: Aspose.Tasks for Java 能處理複雜的 MS Project 公式嗎？**  
A: 能，Aspose.Tasks for Java 支援廣泛的 MS Project 函式，讓您在 Java 應用程式中執行複雜計算。

**Q: Aspose.Tasks for Java 是否相容不同版本的 Microsoft Project 檔案？**  
A: 能，Aspose.Tasks for Java 支援多種 Microsoft Project 檔案版本，包括 MPP、MPT 與 XML 格式。

**Q: 我可以在購買前試用 Aspose.Tasks for Java 嗎？**  
A: 可以，您可從網站 [此處](https://purchase.aspose.com/buy) 下載免費試用版。

**Q: 如何取得 Aspose.Tasks for Java 的支援？**  
A: 您可前往 Aspose.Tasks 社群論壇 [此處](https://forum.aspose.com/c/tasks/15) 取得協助。

**Q: 是否提供 Aspose.Tasks for Java 的臨時授權？**  
A: 有，您可從 Aspose 網站 [此處](https://purchase.aspose.com/temporary-license/) 取得測試用的臨時授權。

---

**最後更新：** 2025-12-09  
**測試環境：** Aspose.Tasks for Java 24.10  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}