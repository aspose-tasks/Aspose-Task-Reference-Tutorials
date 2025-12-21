---
date: 2025-12-21
description: 學習如何使用 Aspose.Tasks for Java 建立專案並為新任務設定 MS Project 屬性，包括如何將專案儲存為 XML
  以及自訂任務屬性。
linktitle: Set Attributes for New Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何建立專案 – 使用 Aspose.Tasks 設定新任務屬性
url: /zh-hant/java/project-file-operations/set-attributes-new-tasks/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何建立專案 – 使用 Aspose.Tasks 設定新工作屬性

## Introduction
在本綜合指南中，您將了解 **如何建立專案** 檔案並為新工作設定 Microsoft Project 屬性，使用 Aspose.Tasks Java 函式庫。我們將逐步說明，從準備開發環境到將專案儲存為 XML 檔案，讓您輕鬆 **自訂工作屬性** 並簡化專案管理工作流程。

## Quick Answers
- **此教學涵蓋什麼內容？** 為新工作設定預設開始日期並將專案儲存為 XML。  
- **需要哪個函式庫？** Aspose.Tasks for Java。  
- **是否需要授權？** 開發階段可使用免費試用版；正式環境需購買商業授權。  
- **我可以變更其他工作預設值嗎？** 可以，Aspose.Tasks 允許您修改多項工作層級的預設值。  
- **使用的輸出格式為何？** XML（SaveFileFormat.Xml）。

## What is a Project in Aspose.Tasks?
在 Aspose.Tasks 中，*專案* 是一個物件模型，對應 Microsoft Project 檔案。它儲存工作、資源、行事曆及其他排程資料，讓您能以程式方式讀取、修改與產生專案檔案。

## Why Set Task Defaults?
設定如新工作開始日期等預設值，可確保整個計畫的一致性。這樣可免除手動更新每個工作，降低排程錯誤的風險。

## Prerequisites
1. **Java 開發環境** – 已安裝 Java 8 或以上版本。  
2. **Aspose.Tasks for Java** – 從 [download link](https://releases.aspose.com/tasks/java/) 下載。  
3. **IDE** – Eclipse、IntelliJ IDEA 或任何相容 Java 的編輯器。

## Import Packages
```java
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.TaskStartDateType;
```

## How to Create Project – Set New Task Attributes
### Step 1: Define the Data Directory
```java
String dataDir = "Your Data Directory";
```
將 `"Your Data Directory"` 替換為您希望儲存輸出檔案的絕對路徑。

### Step 2: Create a Project Instance
```java
Project prj = new Project();
```
此程式碼會建立一個空的專案，供您進一步自訂。

### Step 3: Set New Task Property
```java
prj.set(Prj.NEW_TASK_START_DATE, TaskStartDateType.CurrentDate);
```
上述程式碼告訴 Aspose.Tasks，將 **當前日期** 設為之後新增任何工作的開始日期。

### Step 4: Save the Project
```java
prj.save(dataDir + "project1.xml", SaveFileFormat.Xml);
```
此處我們 **將專案儲存為 XML**，這是一種廣泛支援的交換與後續處理格式。

### Step 5: Display Result
```java
System.out.println("Project file generated Successfully");
```
簡單的主控台訊息會確認檔案已成功建立且未發生錯誤。

## How to Set Task Attributes
如何設定工作屬性  
除了開始日期外，您還可以使用 `Prj` 列舉修改其他預設工作設定，例如持續時間、行事曆與優先順序。此彈性讓您 **自訂工作屬性**，以符合組織的標準。

## How to Save Project as XML
如何將專案儲存為 XML  
以 XML 儲存可保留完整的專案結構，同時讓檔案可供人類閱讀。這非常適合與其他工具整合、版本控制或自動化流程。

## Common Issues and Solutions
- **資料夾路徑無效** – 請確保資料夾已存在且應用程式具備寫入權限。  
- **找不到授權** – 在建立 `Project` 物件之前先載入 Aspose.Tasks 授權，以避免評估水印。  
- **開始日期異常** – 確認在設定後沒有其他程式碼覆寫 `Prj.NEW_TASK_START_DATE`。

## FAQ's
### Q: 我可以使用 Aspose.Tasks for Java 來操作既有的專案檔案嗎？
A: 可以，Aspose.Tasks for Java 提供廣泛功能，可讀取、修改並以各種格式儲存既有專案檔案。

### Q: 我在哪裡可以找到更多 Aspose.Tasks for Java 的文件與資源？
A: 您可於 [Aspose.Tasks for Java documentation page](https://reference.aspose.com/tasks/java/) 查看相關文件與資源。

### Q: 是否提供 Aspose.Tasks for Java 的免費試用？
A: 有，您可從 [here](https://releases.aspose.com/) 下載 Aspose.Tasks for Java 的免費試用版。

### Q: 我如何取得 Aspose.Tasks for Java 的臨時授權？
A: 可於 [temporary license page](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

### Q: 若有任何與 Aspose.Tasks for Java 相關的問題，我該向哪裡尋求支援？
A: 您可在 [Aspose.Tasks for Java support forum](https://forum.aspose.com/c/tasks/15) 獲得支援並與社群互動。

**Additional Q&A**

**Q: 我可以在建立專案後變更預設開始日期嗎？**  
A: 可以，您可在新增工作之前的任何時刻呼叫 `prj.set(Prj.NEW_TASK_START_DATE, ...)` 來變更。

**Q: 將專案儲存為 XML 會影響大型專案的效能嗎？**  
A: XML 為文字格式，檔案大小可能較二進位格式大，但對於大多數一般規模的專案仍保持快速。

**Q: 還有其他可以全域設定的工作預設值嗎？**  
A: 當然可以——如 `NEW_TASK_DURATION`、`NEW_TASK_COST`、`NEW_TASK_PRIORITY` 等屬性亦可透過 `Prj` 列舉設定。

## Conclusion
結論  
您現在已學會如何使用 Aspose.Tasks for Java **建立專案** 檔案、為新工作設定預設開始日期，並 **將專案儲存為 XML**。掌握這些步驟後，您可以輕鬆 **自訂工作屬性**，以符合任何專案管理情境，提升一致性並節省寶貴時間。

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}