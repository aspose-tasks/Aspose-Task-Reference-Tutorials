---
date: 2026-02-13
description: 學習如何透過在 Java 中建立專案物件、加入延伸屬性，並使用 Aspose.Tasks 的評估函式來產生專案報告。
linktitle: Support Evaluation Functions in Aspose.Tasks Formulas
second_title: Aspose.Tasks Java API
title: 產生專案報告 – 建立 Java 專案物件
url: /zh-hant/java/formulas/evaluation-functions/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 支援 Aspose.Tasks 公式中的評估函式

## 簡介
Aspose.Tasks for Java 讓您透過在 Java 中建立 **project object** 來 **generate project report**，並直接在程式碼內評估 Microsoft Project 函式。透過嵌入這些公式，您可以執行複雜計算、產生自訂報表，並自動化專案分析，而無需離開開發環境。本教學將逐步說明如何建立 project object、加入延伸屬性，並使用評估函式來 **add custom field task** 資料。

## 快速回答
- **What does “create project object java” mean?** 它會建立一個記憶體中的 `Project` 實例，讓您可以以程式方式操作。  
- **Which library is required?** Aspose.Tasks for Java（從官方網站下載）。  
- **Do I need a license?** 生產環境需要臨時或正式的 Aspose.Tasks 授權；亦提供免費試用版。  
- **Can I use custom fields?** 可以——您可以 **add extended attribute** 至工作項，並將其視為自訂欄位。  
- **Is this compatible with all Project file formats?** Aspose.Tasks 支援 MPP、MPT 與 XML 格式。

## 前置條件
在開始之前，請確保您已具備以下條件：

1. **Java Development Environment** – JDK 8 以上，並搭配 IntelliJ IDEA 或 Eclipse 等 IDE。  
2. **Aspose.Tasks for Java Library** – 從 [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/) 下載並加入專案中。

## 匯入套件
在 Java 類別中加入 Aspose.Tasks 命名空間，以便操作專案、工作項與延伸屬性：

```java
import com.aspose.tasks.*;
```

## 產生專案報表 – 建立 Project Object Java
建立一個新的 `Project` 物件。此物件將作為所有工作項、資源與自訂資料的容器。

```java
Project project = new Project();
```

上述程式碼 **creates project object java**，會產生一個空的專案物件，隨時可供自訂。

## 如何新增延伸屬性
定義一個延伸屬性，用於儲存每個工作項的自訂數值資料（例如正弦值）。

```java
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(CustomFieldType.Number, ExtendedAttributeTask.Number1, "Sine");
```

此處我們 **add extended attribute**，類型為 `Number`，名稱為「Sine」，並將其關聯至工作項。

## 將延伸屬性加入專案
將屬性定義註冊至專案，使每個工作項皆可參考它。

```java
project.getExtendedAttributes().add(attr);
```

## 建立新工作項
在專案的根工作項下新增一個名稱為「Task」的簡易工作項。

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## 將延伸屬性關聯至工作項
將先前定義的延伸屬性連結至新建立的工作項。

```java
ExtendedAttribute a = attr.createExtendedAttribute();
task.getExtendedAttributes().add(a);
```

現在該工作項擁有自訂的「Sine」欄位，您可以在公式或計算中使用。這也是以程式方式 **add custom field task** 資料的方式。

## 為何使用評估函式？
在 Aspose.Tasks 公式中嵌入 MS Project 函式，可讓您：

- 在不使用外部工具的情況下，即時執行計算（例如 `Sin([Start])`）。  
- 將所有專案邏輯集中於單一且易於維護的程式碼庫中。  
- 產生即時反映資料變動的動態報表，協助您自動 **generate project report**。

## 常見問題與解決方案
| Issue | Solution |
|-------|----------|
| **Formula returns `NaN`** | 確認自訂欄位類型與預期的數值類型相符。 |
| **Extended attribute not visible** | 確保在建立工作項 **之前** 已將屬性定義加入專案。 |
| **License exception** | 安裝臨時或正式的 **Aspose.Tasks license**；試用模式可能限制某些功能。 |
| **Missing temporary license** | 從 Aspose 官方網站取得 **temporary Aspose license**。 |

## 常見問與答

**Q: Aspose.Tasks for Java 能處理複雜的 MS Project 公式嗎？**  
A: 可以，Aspose.Tasks for Java 支援評估各種 MS Project 函式，讓您在 Java 應用程式中執行複雜計算。

**Q: Aspose.Tasks for Java 是否相容於不同版本的 Microsoft Project 檔案？**  
A: 可以，Aspose.Tasks for Java 支援多種版本的 Microsoft Project 檔案，包括 MPP、MPT 與 XML 格式。

**Q: 我可以在購買前試用 Aspose.Tasks for Java 嗎？**  
A: 可以，您可從網站 [here](https://purchase.aspose.com/buy) 下載 Aspose.Tasks for Java 的免費試用版。

**Q: 如何取得 Aspose.Tasks for Java 的支援？**  
A: 您可於 Aspose.Tasks 社群論壇 [here](https://forum.aspose.com/c/tasks/15) 獲得協助。

**Q: 是否提供 Aspose.Tasks for Java 的臨時授權？**  
A: 可以，您可從 Aspose 官方網站 [here](https://purchase.aspose.com/temporary-license/) 取得測試用的臨時授權。

## 結論
透過上述步驟，您已學會如何 **create project object**、**add extended attribute**，並利用評估函式自動 **generate project report**。現在您可以在此基礎上擴充，打造更完整的專案分析、客製化儀表板或自動排程工具——全部由 Aspose.Tasks for Java 提供支援。

---

**最後更新：** 2026-02-13  
**測試環境：** Aspose.Tasks for Java 24.10  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}