---
date: 2026-01-28
description: 學習如何使用 Aspose.Tasks for Java 讀取擴充任務屬性，並有效切換自訂欄位類型。
linktitle: Read Extended Task Attributes with Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks for Java 讀取擴展任務屬性
url: /zh-hant/java/task-properties/extended-task-attributes/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks for Java 讀取擴充任務屬性

## 簡介
在本完整教學中，您將學會如何使用 Aspose.Tasks for Java 從 Microsoft Project 檔案 **讀取擴充任務屬性**。無論您是要建立報表工具、同步資料，或只是需要深入了解自訂欄位，此功能都能讓您提取專案中儲存的每一筆資訊。我們將說明必要的設定步驟、示範在處理屬性時如何切換自訂欄位類型，並提供實用技巧以避免常見陷阱。

## 快速回答
- **「讀取擴充任務屬性」是什麼意思？** 指的是擷取超出 Project 檔案預設任務屬性的自訂欄位值。  
- **哪個類別提供對這些屬性的存取？** Aspose.Tasks 中的 `ExtendedAttribute` 類別。  
- **執行程式碼需要授權嗎？** 開發階段可使用免費試用版；正式上線需購買商業授權。  
- **可以在執行時變更屬性類型嗎？** 可以 ─ 透過 `switch` 陳述式根據 `CustomFieldType` **切換自訂欄位類型**。  
- **此功能支援 Java 8 及以上版本嗎？** 完全支援，API 相容於 JDK 8+。

## 什麼是讀取擴充任務屬性？
擴充任務屬性是使用者自行定義的欄位（文字、日期、數字、旗標等），用以補足 Microsoft Project 中的標準任務屬性。Aspose.Tasks 透過每個 `Task` 物件所附帶的 `ExtendedAttribute` 集合，讓您以程式方式讀取或修改這些值。

## 為什麼要讀取擴充任務屬性？
- **完整可視性：** 瞭解利害關係人於排程中加入的自訂資料。  
- **自動化：** 填充儀表板、產生自訂報表，或將資料遷移至其他系統，免除手動匯出。  
- **彈性：** 透過適當的處理，可支援任何自訂欄位類型──文字、日期、工期、成本、旗標等。

## 先決條件
在開始之前，請確保您已具備：
- 具備 Java 程式設計的基本知識。  
- 在電腦上安裝 Java Development Kit (JDK)。  
- 使用 IntelliJ IDEA 或 Eclipse 等 IDE。  

## 匯入套件
首先匯入 Aspose.Tasks 專案所需的類別：

```java
import com.aspose.tasks.CustomFieldType;
import com.aspose.tasks.ExtendedAttribute;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
```

## 步驟 1：存取任務與擴充屬性
載入 Project 檔案並遍歷每個任務以取得其擴充屬性：

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "ReadTaskExtendedAttributes.mpp");
for (Task tsk : project.getRootTask().getChildren()) {
    for (ExtendedAttribute ea : tsk.getExtendedAttributes()) {
```

## 步驟 2：取得欄位 ID 與值 GUID
列印內部識別碼，以協助了解正在處理的自訂欄位：

```java
System.out.println(ea.getFieldId());
System.out.println(ea.getValueGuid());
```

## 步驟 3：讀取擴充任務屬性時如何切換自訂欄位類型
使用 `switch` 陳述式對 `CustomFieldType` 進行切換，以正確處理每種可能的資料類型：

```java
switch (ea.getAttributeDefinition().getCfType()) {
    case CustomFieldType.Date:
    case CustomFieldType.Start:
    case CustomFieldType.Finish:
        System.out.println(ea.getDateValue());
        break;
    case CustomFieldType.Text:
        System.out.println(ea.getTextValue());
        break;
    case CustomFieldType.Duration:
        System.out.println(ea.getDurationValue().toString());
        break;
    case CustomFieldType.Cost:
    case CustomFieldType.Number:
        System.out.println(ea.getNumericValue());
        break;
    case CustomFieldType.Flag:
        System.out.println(ea.getFlagValue());
        break;
}
```

對專案中的每個任務重複上述步驟，以探索與操作所有擴充任務屬性。

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| **返回空值 (Null)** | 確認自訂欄位在來源 .mpp 檔案中已實際填寫。 |
| **顯示類型不正確** | 確保在 `switch` 陳述式中使用正確的 `CustomFieldType`；類型不匹配會導致預設值。 |
| **大型專案效能下降** | 使用 `project.getRootTask().getChildren().stream()` 搭配適當的條件式，將任務分批處理或僅篩選所需的任務。 |

## 常見問答
### 我可以以程式方式修改擴充任務屬性嗎？
可以，您可以使用 Aspose.Tasks for Java 修改擴充任務屬性。請參考文件以取得詳細說明。

### 是否提供試用版？
是的，您可以在此取得免費試用版 [here](https://releases.aspose.com/)。

### 我可以在哪裡取得 Aspose.Tasks for Java 的支援？
如需支援，請前往 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)。

### 如何取得臨時授權？
您可以在此取得臨時授權 [here](https://purchase.aspose.com/temporary-license/)。

### 我可以從哪裡購買 Aspose.Tasks for Java 的完整版本？
您可以在此購買完整版本 [here](https://purchase.aspose.com/buy)。

---

**最後更新：** 2026-01-28  
**測試環境：** Aspose.Tasks Java API（最新穩定版）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}