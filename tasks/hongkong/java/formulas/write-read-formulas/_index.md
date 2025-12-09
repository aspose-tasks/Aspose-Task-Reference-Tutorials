---
date: 2025-12-07
description: 學習如何儲存專案檔案、編寫與讀取 MS Project 公式，以及使用 Aspose.Tasks for Java 新增自訂欄位公式。
linktitle: Save Project File & Write Formulas in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 儲存專案檔案並使用 Aspose.Tasks 撰寫 MS Project 公式
url: /zh-hant/java/formulas/write-read-formulas/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 儲存專案檔案並使用 Aspose.Tasks 撰寫 MS Project 公式

## 簡介
在專案管理領域，有效的資料處理至關重要。Aspose.Tasks for Java 是一套強大的解決方案，可協助操作與擷取 Microsoft Project 檔案中的資料。它提供的一項強大功能是能夠寫入與讀取 MS Project 公式。**您還將學習在套用公式後如何 *save project file*，**確保變更能持久保存以供未來分析。本教學將指引您如何利用此功能提升專案管理工作。

## 快速解答
- **「save project file」會做什麼？** 它會將所有記憶體中的變更寫回磁碟上的 .mpp 檔案。  
- **我可以新增自訂欄位公式嗎？** 可以——您可以建立自訂欄位，並指派如「double task cost」的公式。  
- **執行程式碼需要授權嗎？** 免費試用可用於評估；正式環境需購買商業授權。  
- **哪個 IDE 最適合？** 任何 Java IDE（IntelliJ IDEA、Eclipse、VS Code）皆可編譯範例。  
- **API 是否相容最新的 MS Project 版本？** Aspose.Tasks 支援所有近期的 .mpp 格式。

## 什麼是 Aspose.Tasks 中的「save project file」？
儲存專案檔案指的是將 `Project` 物件目前的狀態——包括工作、資源以及任何自訂公式——寫入實體的 Microsoft Project 檔案（`.mpp`）。在您修改資料（例如新增自訂欄位或變更工作成本）後，必須執行此操作。

## 為什麼要新增自訂欄位並建立自訂欄位公式？
新增自訂欄位可為未被預設欄位涵蓋的額外資訊提供彈性容器。透過附加公式（例如 **double task cost**），您可以自動化計算、減少手動錯誤，並確保排程資料的一致性。

## 先決條件
在開始本教學之前，請確保具備以下條件：

1. **Java Development Kit (JDK)** – 已在您的機器上安裝 Java 8 或更高版本。  
2. **Aspose.Tasks for Java** – 從 [here](https://releases.aspose.com/tasks/java/) 下載並安裝。  
3. **Integrated Development Environment (IDE)** – 選擇您偏好的 Java 開發環境（IntelliJ IDEA、Eclipse、VS Code 等）。  

## 匯入套件
首先，將必要的套件匯入您的 Java 專案：

```java
import com.aspose.tasks.*;
import java.io.IOException;
import java.math.BigDecimal;
import java.util.Objects;
```

## 步驟 1：設定資料目錄
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
```
定義存放 MS Project 檔案的資料夾。這裡將載入來源檔案，之後再 **save project file**。

## 步驟 2：載入專案檔案
```java
Project project = new Project(dataDir + "project.mpp");
```
將現有的 Microsoft Project 檔案載入 `Project` 物件，以便讀取或修改其內容。

## 步驟 3：新增自訂欄位並建立自訂欄位公式
```java
project.set(Prj.NEW_TASKS_ARE_MANUAL, new NullableBool(false));
ExtendedAttributeDefinition attr = ExtendedAttributeDefinition.createTaskDefinition(
        CustomFieldType.Text, ExtendedAttributeTask.Text1, "Custom");
attr.setAlias("Double Costs");
attr.setFormula("[Cost]*2");   // This formula doubles the task cost
project.getExtendedAttributes().add(attr);
```
在此步驟中，我們 **add custom field** 「Double Costs」並 **create custom field formula**，將工作 `[Cost]` 乘以 2，實現 **double task cost**。`setFormula` 方法會直接將計算寫入專案檔案。

## 步驟 4：新增工作並設定成本
```java
Task task = project.getRootTask().getChildren().add("Task");
task.set(Tsk.COST, BigDecimal.valueOf(100));
```
建立新工作，並將基礎成本設定為 `100`。當專案儲存時，自訂欄位會因公式自動顯示 `200`。

## 步驟 5：儲存專案檔案
```java
project.save(dataDir + "saved.mpp", SaveFileFormat.Mpp);
```
最後，**save project file**，將所有修改寫入 `saved.mpp`。

## 常見問題與解決方案
| 問題 | 原因 | 解決方法 |
|------|------|----------|
| **Formula not applied** | Custom field not added to the project’s `ExtendedAttributes` collection. | Ensure `project.getExtendedAttributes().add(attr);` is executed before saving. |
| **File not found** | Incorrect `dataDir` path. | Verify the directory string ends with a path separator (`/` or `\\`). |
| **Cost appears as 0** | Task cost not set before saving. | Call `task.set(Tsk.COST, ...)` before `project.save`. |

## 常見問答
**Q: Aspose.Tasks 是否相容所有版本的 MS Project？**  
A: 是的，Aspose.Tasks 支援廣泛的 MS Project 版本，從較舊的 .mpp 格式到最新發行版皆可。

**Q: 我可以將 Aspose.Tasks 整合到現有的 Java 專案嗎？**  
A: 當然可以。API 設計為可無縫整合，只需將 Aspose.Tasks JAR 加入專案的 classpath 即可。

**Q: 我能建立的公式類型有什麼限制？**  
A: 此函式庫支援大多數原生 MS Project 公式語法，包括算術、邏輯與內建函式。較複雜的自訂函式可能需要另行處理。

**Q: Aspose.Tasks 支援多平台部署嗎？**  
A: 支援，該函式庫可在任何支援 Java 的平台上執行，包含 Windows、Linux 與 macOS。

**Q: 我要如何取得 Aspose.Tasks 的技術支援？**  
A: 前往 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 取得社群協助，或在擁有商業授權時提交支援工單。

## 結論
本教學說明了如何 **save project file**、**add custom field**，以及 **create a custom field formula** 以 **double task cost**，使用 Aspose.Tasks for Java。依循這些步驟，您可自動化計算、豐富專案資料，並確保所有變更持久保存，以供未來報告與分析使用。

---

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}