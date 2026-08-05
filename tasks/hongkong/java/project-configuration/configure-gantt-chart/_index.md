---
date: 2026-02-13
description: 了解如何在 Aspose.Tasks Java 中建立新活動、設定資料目錄，並將專案儲存為 MPP。本一步一步的指南亦涵蓋自訂表格欄位。
linktitle: How to Create New Activity & Set Data Directory Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何建立新活動及設定 Aspose.Tasks 資料目錄
url: /zh-hant/java/project-configuration/configure-gantt-chart/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何建立新活動與設定資料目錄 Aspose.Tasks

## 簡介
在本教學中，您將學習**如何設定資料目錄**、**如何建立新活動**，以及在使用 Java 的 Aspose.Tasks 專案中配置甘特 MS Project 圖表視圖時**將專案另存為 MPP**。Aspose.Tasks 是一個功能強大的 Java API，讓您能以程式方式操作 Microsoft Project 檔案。完成本指南後，您將能**自訂表格欄位**、調整資料目錄，並以您需要的方式視覺化專案。

## 快速解答
- **第一步是什麼？** 設定您的專案檔案所在的資料目錄路徑。  
- **需要哪個函式庫？** Aspose.Tasks for Java（可從官方網站下載）。  
- **我可以加入自訂屬性嗎？** 可以——您可以定義延伸屬性並在甘特圖中顯示它們。  
- **測試需要授權嗎？** 可取得臨時授權供評估使用。  
- **哪個 IDE 最適合？** 任何 Java IDE（IntelliJ IDEA、Eclipse、NetBeans）皆可使用。

## 什麼是「設定資料目錄」以及為何重要？
設定資料目錄可告訴 Aspose.Tasks 在哪裡讀寫專案檔案。若路徑不正確，API 將找不到您的 `.mpp` 檔案，導致 FileNotFound 錯誤。於程式碼開頭定義此目錄，可使後續工作流程保持整潔且可重複執行。

## 為何在甘特圖中自訂表格欄位？
自訂表格欄位可讓您直接在甘特視圖中顯示額外資訊——例如自訂屬性、資源資料或專案特定備註——使圖表對利害關係人更具資訊性，並減少在多份報告之間切換的需求。

## 如何建立新活動？
建立新活動（工作）是建構或更新專案排程的核心操作之一。透過程式方式加入工作，您可以自動產生複雜的專案計畫、整合其他系統的資料，或在不需手動編輯的情況下批次套用變更。

## 先決條件
1. **Java Development Kit (JDK)** – 任意近期版本（8 以上）。  
2. **Aspose.Tasks Library** – 從[此處](https://releases.aspose.com/tasks/java/)下載。  
3. **IDE** – IntelliJ IDEA、Eclipse，或您偏好的任何 Java 相容編輯器。

## 匯入套件
首先，匯入 Aspose.Tasks 命名空間，以便使用其類別：

```java
import com.aspose.tasks.*;
```

## 步驟說明

### 步驟 1：設定資料目錄
定義包含您的專案檔案的資料夾。這就是本教學所聚焦的**設定資料目錄**步驟。

```java
String dataDir = "Your Data Directory";
```

將 `"Your Data Directory"` 替換為 `project.mpp` 所在資料夾的絕對路徑。

### 步驟 2：載入專案檔案
透過載入現有的 Microsoft Project 檔案，建立 `Project` 實例。

```java
Project project = new Project(dataDir + "project.mpp");
```

### 步驟 3：加入新活動
在專案的根目錄插入新工作（活動）。此範例示範如何以程式方式**建立新活動**。

```java
Task task = project.getRootTask().getChildren().add("New Activity");
```

### 步驟 4：定義自訂屬性
建立自訂屬性定義，以便之後附加至工作。

```java
ExtendedAttributeDefinition text1Definition = ExtendedAttributeDefinition.createTaskDefinition(ExtendedAttributeTask.Text1, null);
project.getExtendedAttributes().add(text1Definition);
```

### 步驟 5：將自訂屬性加入工作
將新定義的屬性指派給您先前建立的工作。

```java
task.getExtendedAttributes().add(text1Definition.createExtendedAttribute("Activity attribute"));
```

### 步驟 6：自訂表格 – **自訂表格欄位**
將自訂屬性作為欄位加入甘特圖表格，並設定寬度、標題與對齊方式。

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
將變更持久化為可在 Microsoft Project 開啟的新檔案。此步驟**將專案另存為 MPP**。

```java
project.save("saved.mpp", SaveFileFormat.Mpp);
```

## 常見問題與解決方案
| 問題 | 發生原因 | 解決方式 |
|------|----------|----------|
| **FileNotFoundException** 載入專案時 | **設定資料目錄** 路徑不正確或缺少結尾的斜線。 | 確認 `dataDir` 指向正確的資料夾，並加入正確的檔案分隔符（`/` 或 `\\`）。 |
| 自訂屬性在甘特圖中未顯示 | 表格欄位被加入了錯誤的索引，或欄寬過小。 | 確保 `table.getTableFields().add(3, attrField);` 使用有效的索引，並視需要調整 `setWidth`。 |
| 儲存時發生 LicenseException | 未為正式使用套用有效授權。 | 在呼叫 `project.save()` 前套用臨時或永久授權。 |

## 常見問答

**Q: 我可以在其他程式語言中使用 Aspose.Tasks 嗎？**  
A: 可以，Aspose.Tasks 支援多種程式語言，包括 .NET、Java 與 C++。

**Q: 是否提供 Aspose.Tasks 的免費試用？**  
A: 有，您可從[此處](https://releases.aspose.com/)下載免費試用版。

**Q: 我可以在哪裡取得 Aspose.Tasks 的支援？**  
A: 您可在 [Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)取得支援並提出問題。

**Q: 我要如何購買 Aspose.Tasks 授權？**  
A: 您可從[此處](https://purchase.aspose.com/buy)購買授權。

**Q: 測試時需要臨時授權嗎？**  
A: 需要，您可從[此處](https://purchase.aspose.com/temporary-license/)取得臨時授權。

## 結論
您現在已學會如何**設定資料目錄**、**建立新活動**、定義並附加自訂屬性，以及在使用 Aspose.Tasks for Java 的甘特圖視圖中**自訂表格欄位**的同時**將專案另存為 MPP**。這些步驟讓您完整掌控專案資料的呈現方式，使甘特圖更具資訊性，並符合利害關係人的需求。

---

**最後更新：** 2026-02-13  
**測試環境：** Aspose.Tasks Java 24.12（最新）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}