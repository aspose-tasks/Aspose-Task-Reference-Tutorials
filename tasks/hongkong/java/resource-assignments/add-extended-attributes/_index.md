---
date: 2026-01-05
description: 學習如何設定專案開始日期並使用 Aspose.Tasks for Java 儲存 MS Project XML。針對 Java 開發人員的逐步指南。
linktitle: Add Extended Attributes to Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks for Java 設定專案開始日期
url: /zh-hant/java/resource-assignments/add-extended-attributes/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks for Java 設定專案開始日期

## 介紹
在本教學中，您將學習 **如何在 Microsoft Project 檔案中設定專案開始日期**，然後 **使用 Aspose.Tasks for Java 套件將其儲存為 MS Project XML**。無論您是自動化報告流程或是建構自訂的專案管理工具，掌握此任務都能節省時間並消除手動錯誤。

## 快速解答
- **設定開始日期的主要方法是什麼？** 使用 `project.set(Prj.START_DATE, …)`。
- **我應該使用哪種格式匯出檔案？** 使用 `SaveFileFormat.Xml` 以 XML 格式儲存。
- **此操作是否需要授權？** 試用版可用，但完整授權可移除浮水印。
- **建立任務後可以更改開始日期嗎？** 可以，在加入任務之前更新專案屬性。
- **這是否相容於所有 MS Project 版本？** Aspose.Tasks 支援 XML、MPP 等多種格式。

## 什麼是「設定專案開始日期」？
設定專案開始日期定義了所有任務排程計算所依據的基準行事曆。這是以程式方式建立可靠專案排程的第一步。

## 為什麼使用 Aspose.Tasks for Java？
Aspose.Tasks 提供純 Java API，能在任何平台上執行，無需安裝 Microsoft Project。它讓您快速建立、修改與匯出專案資料，非常適合伺服器端自動化。

## 前置條件
1. **Java Development Kit (JDK)** – 任意近期的 JDK 版本。  
2. **Aspose.Tasks for Java** – 從 [here](https://releases.aspose.com/tasks/java/) 下載。  
3. **IDE** – IntelliJ IDEA、Eclipse 或您偏好的 Java IDE。

## 匯入套件
首先，匯入必要的類別：

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
定義產生的檔案將儲存的位置。

```java
String dataDir = "Your Data Directory";
```

### 步驟 2：建立 Project 實例
建立一個全新的空白專案。

```java
Project project = new Project();
```

### 步驟 3：設定專案資訊屬性
此處 **設定專案開始日期** 以及相關的排程屬性。

```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

### 步驟 4：儲存 MS Project XML
將已設定好的專案匯出為 XML 檔案。

```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## 常見問題與解決方案
- **日期格式不正確：** 確保使用 `java.util.Calendar` 並在指派前呼叫 `getTime()`。  
- **檔案未儲存：** 確認 `dataDir` 指向已存在且可寫入的資料夾。  
- **授權警告：** 試用版會加入浮水印，請套用有效授權以移除。

## 常見問答

### Q: 我可以使用 Aspose.Tasks for Java 讀取 MS Project 檔案嗎？  
**A:** 可以，Aspose.Tasks for Java 提供強大的功能，支援讀取與寫入 MS Project 檔案。

### Q: Aspose.Tasks for Java 是否相容於不同版本的 MS Project？  
**A:** 絕對相容，Aspose.Tasks for Java 支援多種 MS Project 格式，確保廣泛的相容性。

### Q: Aspose.Tasks for Java 試用版有什麼限制嗎？  
**A:** 試用版允許您探索此函式庫，但會在輸出檔案中加入浮水印。

### Q: 我該如何取得 Aspose.Tasks for Java 的支援？  
**A:** 您可以在 Aspose.Tasks 社群論壇 [here](https://forum.aspose.com/c/tasks/15) 尋求協助。

### Q: 我可以購買 Aspose.Tasks for Java 的臨時授權嗎？  
**A:** 可以，提供短期使用的臨時授權。可從 [here](https://purchase.aspose.com/temporary-license/) 取得。

### Q: 以 XML 格式儲存是否會保留自訂欄位？  
**A:** 會的，使用 `SaveFileFormat.Xml` 儲存時，所有自訂屬性與擴充欄位皆會被保留。

### Q: 加入任務後我可以更改開始日期嗎？  
**A:** 可以，在儲存前的任何時間都能更新開始日期，只需再次呼叫 `project.set(Prj.START_DATE, …)` 即可。

---

**最後更新：** 2026-01-05  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}