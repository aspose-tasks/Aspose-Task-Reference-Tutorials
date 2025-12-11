---
date: 2025-12-09
description: 學習如何在 Aspose.Tasks 使用 Java 設定資料目錄並配置甘特圖檢視。本指南亦示範如何自訂表格欄位以及一步一步配置 Java
  甘特圖專案。
linktitle: Set Data Directory for Gantt Chart View in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 在 Aspose.Tasks 中設定甘特圖檢視的資料目錄
url: /zh-hant/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 設定 Gantt 圖表檢視的資料目錄於 Aspose.Tasks

## 簡介
在本教學中，您將學習 **如何設定資料目錄**，以及在 Aspose.Tasks 專案中使用 Java 配置 Gantt MS Project 圖表檢視。Aspose.Tasks 是一套功能強大的 Java API，讓您能以程式方式操作 Microsoft Project 檔案。完成本指南後，您將能 **自訂表格欄位**、調整資料目錄，並以您需要的方式呈現專案。

## 快速解答
- **第一步是什麼？** 設定專案檔案所在的資料目錄路徑。  
- **需要哪個函式庫？** Aspose.Tasks for Java（可從官方網站下載）。  
- **可以加入自訂屬性嗎？** 可以——您可以定義延伸屬性並在 Gantt 圖表中顯示。  
- **測試需要授權嗎？** 可使用臨時授權進行評估。  
- **哪個 IDE 最適合？** 任何 Java IDE（IntelliJ IDEA、Eclipse、NetBeans）皆可。

## 什麼是「設定資料目錄」以及為何重要？
設定資料目錄告訴 Aspose.Tasks 從哪裡讀寫專案檔案。若路徑不正確，API 無法找到 `.mpp` 檔案，會導致 FileNotFound 錯誤。於程式碼開頭定義此目錄，可使後續工作流程更清晰且易於重複執行。

## 為什麼要在 Gantt 圖表中自訂表格欄位？
自訂表格欄位讓您能直接在 Gantt 檢視中顯示額外資訊——例如自訂屬性、資源資料或專案特定備註。這可提升圖表對利害關係人的資訊價值，減少在多份報表之間切換的需求。

## 先決條件
在開始之前，請確保您已具備：

1. **Java Development Kit (JDK)** – 任意近期版本（8 以上）。  
2. **Aspose.Tasks Library** – 從 [此處](https://releases.aspose.com/tasks/java/) 下載。  
3. **IDE** – IntelliJ IDEA、Eclipse，或任何您慣用的 Java 編輯器。

## 匯入套件
首先，匯入 Aspose.Tasks 命名空間，以便使用其類別：

```java
import com.aspose.tasks.*;
```

## 逐步指南

### 步驟 1：設定資料目錄
定義包含專案檔案的資料夾。這就是本教學聚焦的 **設定資料目錄** 步驟。

```java
String dataDir = "Your Data Directory";
```

將 `"Your Data Directory"` 替換為存放 `project.mpp` 的資料夾絕對路徑。

### 步驟 2：載入專案檔案
透過載入現有的 Microsoft Project 檔案，建立 `Project` 實例。

```java
Project project = new Project(dataDir + "project.mpp");
```

### 步驟 3：新增活動
在專案根目錄插入一個新任務（活動）。

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### 步驟 4：定義自訂屬性
建立自訂屬性定義，以便之後附加至任務。

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### 步驟 5：將自訂屬性加入任務
將剛才定義的屬性指派給您建立的任務。

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### 步驟 6：自訂表格 – **customize table fields**
將自訂屬性作為欄位加入 Gantt 圖表的表格，並設定寬度、標題與對齊方式。

```java
TableField attrField = new TableField();
attrField.setField(Field.TaskText1);
attrField.setWidth(20);
attrField.setTitle("Custom attribute");
attrField.setAlignTitle(HorizontalStringAlignment.Center);
attrField.setAlignData(HorizontalStringAlignment.Center);
Table table = project.getTables().toList().get(0);
table.getTableFields().add(3, attrField);
```

### 步驟 7：儲存專案
將變更寫入新檔案，以便在 Microsoft Project 中開啟。

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## 常見問題與解決方案
| 問題 | 發生原因 | 解決方法 |
|------|----------|----------|
| **FileNotFoundException** 在載入專案時 | **設定資料目錄** 路徑不正確或缺少結尾的斜線。 | 確認 `dataDir` 指向正確的資料夾，並加入正確的檔案分隔符（`/` 或 `\\`）。 |
| 自訂屬性在 Gantt 檢視中未顯示 | 表格欄位加入的索引錯誤或欄寬過小。 | 確認 `table.getTableFields().add(3, attrField);` 使用有效索引，並依需要調整 `setWidth`。 |
| LicenseException 在儲存時 | 未為正式使用套用有效授權。 | 在呼叫 `project.save()` 前套用臨時或永久授權。 |

## 常見問答

**Q: 可以在其他程式語言中使用 Aspose.Tasks 嗎？**  
A: 可以，Aspose.Tasks 支援多種程式語言，包括 .NET、Java 與 C++。

**Q: Aspose.Tasks 有免費試用嗎？**  
A: 有，您可從 [此處](https://releases.aspose.com/) 下載免費試用版。

**Q: 在哪裡可以取得 Aspose.Tasks 的支援？**  
A: 可於 [Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15) 提問與尋求協助。

**Q: 如何購買 Aspose.Tasks 的授權？**  
A: 請前往 [此處](https://purchase.aspose.com/buy) 購買。

**Q: 測試時需要臨時授權嗎？**  
A: 需要，您可從 [此處](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

## 結論
您現在已學會如何 **設定資料目錄**、新增活動、定義並附加自訂屬性，以及在 Gantt 圖表檢視中 **自訂表格欄位**，全部透過 Aspose.Tasks for Java 完成。這些步驟讓您能完全掌控專案資料的呈現方式，使 Gantt 圖表更具資訊性且符合利害關係人的需求。

---

**最後更新：** 2025-12-09  
**測試環境：** Aspose.Tasks Java 24.12（最新版）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}