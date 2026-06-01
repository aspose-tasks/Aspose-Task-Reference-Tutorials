---
date: 2026-01-13
description: 學習如何建立自訂屬性、載入 Microsoft Project 檔案、在 Java 中設定數值，並使用 Aspose.Tasks for
  Java 將專案儲存為 XML。
linktitle: Handle Extended Resource Attributes in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks 在 MS Project 中建立自訂屬性
url: /zh-hant/java/resource-management/extended-resource-attributes/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks 在 MS Project 中建立自訂屬性

## 介紹
在本教學中，**您將學會如何為 Microsoft Project 檔案中的資源建立自訂屬性**，使用 Aspose.Tasks for Java。我們將示範如何載入 Microsoft Project 檔案、定義一個新的數值屬性、指派值，最後將專案另存為 XML。完成後，您將擁有一個清晰、可實作的範例，能套用到您自己的專案管理解決方案中。

## 快速回答
- **「自訂屬性」是什麼意思？**  
  由使用者自行定義的欄位，可為資源或工作儲存額外資訊（例如：年齡、技能等級）。  
- **哪個函式庫負責此功能？**  
  Aspose.Tasks for Java 提供流暢的 API 來建立與管理自訂屬性。  
- **需要授權嗎？**  
  評估期間可使用免費暫時授權；正式上線則需完整授權。  
- **可以設定數值嗎？**  
  可以 – 使用 `setNumericValue` 搭配 `BigDecimal`（例如 `30.5345`）。  
- **專案如何儲存？**  
  可使用 `SaveFileFormat.Xml` 將修改後的檔案另存為 XML。

## 什麼是自訂屬性？
**自訂屬性**（亦稱延伸屬性）是您可以在 Microsoft Project 中為資源或工作新增的額外欄位。它讓您能記錄內建欄位未涵蓋的資料，例如員工年齡、認證等級或任何業務特定指標。

## 為什麼要在 MS Project 中建立自訂屬性？
- **依組織需求調整專案資料**。  
- **透過儲存可查詢的值，提升進階報表功能**。  
- **以程式方式套用相同的屬性定義，確保多個專案的一致性**。

## 前置條件
在開始之前，請確保您已具備以下環境：

1. **Java 開發環境** – 已安裝 JDK 8 以上版本。  
2. **Aspose.Tasks for Java** – 從 [here](https://releases.aspose.com/tasks/java/) 下載最新版本。  
3. **IDE** – Eclipse、IntelliJ IDEA 或任何支援 Java 的開發工具。  

## 步驟說明

### 匯入套件
首先，匯入您將使用的 Aspose.Tasks 類別。這些類別提供處理專案、資源與延伸屬性的核心功能。

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

### 第一步：定義資料目錄
設定來源專案檔所在的資料夾，以及輸出檔案的寫入位置。

```java
String dataDir = "Your Data Directory";
```

### 第二步：載入 Microsoft Project 檔案
建立 `Project` 實例，載入既有檔案。這一步即 **載入 Microsoft Project 檔案**，讓您取得完整內容的存取權。

```java
Project prj = new Project(dataDir + "ResourceWithExtAttribs.xml");
```

### 第三步：定義自訂屬性
我們將建立一個名為 **Age** 的數值屬性。API 會先檢查定義是否已存在，若不存在則建立新定義。

```java
ExtendedAttributeDefinition myNumber1 = prj.getExtendedAttributes().getById((int) ExtendedAttributeTask.Number1);
if (myNumber1 == null) {
    myNumber1 = ExtendedAttributeDefinition.createResourceDefinition(ExtendedAttributeResource.Number1, "Age");
    prj.getExtendedAttributes().add(myNumber1);
}
```

### 第四步：在 Java 中設定數值
為特定資源建立屬性實例，並使用 `setNumericValue` 指派數值。此步驟示範 **set numeric value java** 的實作方式。

```java
ExtendedAttribute number1Resource = myNumber1.createExtendedAttribute();
number1Resource.setNumericValue(BigDecimal.valueOf(30.5345));
```

### 第五步：新增資源並附加自訂屬性
新增一筆名稱為 **R1** 的資源，並將先前建立的自訂屬性附加至該資源。

```java
Resource rsc = prj.getResources().add("R1");
rsc.getExtendedAttributes().add(number1Resource);
```

### 第六步：將專案另存為 XML
最後，透過儲存動作將變更寫入檔案。這是 **save project as xml** 步驟，會產生更新後的 XML 表示。

```java
prj.save(dataDir + "project5.xml", SaveFileFormat.Xml);
```

### 第七步：顯示結果
列印友善的確認訊息，讓您知道流程已順利完成且未發生錯誤。

```java
System.out.println("Process completed Successfully");
```

依照上述步驟，您已成功 **建立自訂屬性**、載入 Microsoft Project 檔案、以 Java 設定數值，並將專案另存為 XML。

## 常見問題與技巧
- **屬性 ID 衝突**：建立新定義前務必使用 `getById` 檢查，以避免重複 ID。  
- **精度處理**：`BigDecimal` 能保留小數精度，請避免使用 `float` 或 `double` 來儲存精確值。  
- **檔案路徑**：使用絕對路徑或在 IDE 中設定工作目錄，避免發生 `FileNotFoundException`。  

## 常見問答

**Q: 我可以同時為工作建立自訂屬性嗎？**  
A: 可以 – 定義屬性時使用 `ExtendedAttributeTask` 取代 `ExtendedAttributeResource`。

**Q: 能一次加入多個自訂屬性嗎？**  
A: 完全可以。為每個屬性建立獨立的 `ExtendedAttributeDefinition` 物件，然後分別附加至目標資源或工作。

**Q: 專案可以儲存成哪些格式？**  
A: Aspose.Tasks 支援 XML、MPP，以及 PDF、HTML 等多種格式。本範例使用 `SaveFileFormat.Xml`。

**Q: 開發版需要授權嗎？**  
A: 評估用的暫時授權已足夠。正式上線時則需完整授權。

**Q: 之後要如何讀取自訂屬性值？**  
A: 使用 `resource.getExtendedAttributes()` 迭代取得已附加的屬性，並透過 `getNumericValue()` 或 `getTextValue()` 取得其值。

## 結論
使用 Aspose.Tasks for Java 在 Microsoft Project 中建立 **自訂屬性** 的流程相當直接：載入專案、定義屬性、設定值、附加至資源，最後儲存檔案。此方法讓您能以程式方式擴充專案資料模型，提升報表深度並加強與業務流程的整合。

---

**最後更新：** 2026-01-13  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}