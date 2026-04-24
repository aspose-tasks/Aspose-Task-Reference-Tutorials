---
date: 2026-04-24
description: 學習如何使用 Aspose.Tasks for Java 將 Primavera XML 匯入 MS Project，實現無縫的資料交換與提升專案管理。
keywords:
- aspose tasks java
- import xml ms project
- java read project
- java project xml
linktitle: 在 Aspose.Tasks 中從 Primavera 讀取專案
second_title: Aspose.Tasks Java API
title: aspose tasks java – 將 Primavera XML 讀入 MS Project
url: /zh-hant/java/project-management/read-primavera/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 從 Primavera 讀取 MS Project（使用 Aspose.Tasks for Java）

## 介紹
在當今節奏快速的專案管理領域，您常常需要在 Primavera P6 與 Microsoft Project 之間搬移排程而不遺失任何細節。本教學示範 **如何讀取 Primavera XML** 檔案並使用 **aspose tasks java** 匯入至 MS Project。完成本指南後，您將能將 Primavera 專屬的工作項目屬性拉入 Java 應用程式，提供單一真實來源以供分析、報告或進一步自動化。

## 快速解答
- **Aspose.Tasks for Java 有什麼功能？** 它能讀寫多種專案檔案格式，包括 Primavera XML 與 Microsoft Project (MPP)。  
- **需要授權嗎？** 免費試用可用於評估；正式使用需購買授權。  
- **支援哪個 Java 版本？** 需要 Java 8 或更高版本。  
- **除了 Primavera XML，還能匯入其他格式嗎？** 可以，aspose tasks java 亦支援 MPP、XML 等多種格式。  
- **此方法適用於大型企業專案嗎？** 絕對適合——Aspose.Tasks 為高效能、企業級情境而設計。

## aspose tasks java – 讀取 Primavera XML
讀取 Primavera XML 意指解析 Oracle Primavera P6 匯出的 XML，以取得專案排程資料——工作項目、工期、資源以及 Primavera 專屬屬性，讓其他工具（如 Microsoft Project）得以使用。

## 為何使用 Aspose.Tasks for Java 讀取 Primavera XML？
- **完整保真度：** 所有 Primavera 專屬屬性皆被保留。  
- **無外部相依性：** 純 Java 函式庫，無需安裝 Primavera 或 MS Project。  
- **可擴充性：** 能有效處理含千項工作的大型專案。  
- **跨平台：** 支援 Windows、Linux 與 macOS。

## 前置條件
在開始之前，請確保您具備以下項目：
1. **Java Development Kit (JDK)** – 已安裝 Java 8 或更新版本。  
2. **Aspose.Tasks for Java** – 從 [here](https://releases.aspose.com/tasks/java/) 下載。  
3. 需要讀取的 Primavera XML 檔案（例如 `PrimaveraProject.xml`）。

## 如何使用 Aspose.Tasks 讀取 Java 專案檔案？
以下提供逐步說明，帶您完成整個流程。

### 匯入套件
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```

### 步驟 1：設定資料目錄
```java
String dataDir = "Your Data Directory";
```
將 `"Your Data Directory"` 替換為 Primavera XML 檔案所在的絕對路徑。

### 步驟 2：從 Primavera XML 讀取專案
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
將 `"PrimaveraProject.xml"` 更新為實際的 Primavera 匯出檔名。

### 步驟 3：遍歷工作項目並取得 Primavera 專屬屬性
```java
for (Task task : project.enumerateAllChildTasks()) {
    System.out.println("Task '" + task.getName() + "'");
    
    if (task.isSummary()) {
        System.out.println("WBS Sequence number: " + task.getPrimaveraProperties().getSequenceNumber());
    } else {
        System.out.println("Task ActivityId: " + task.getPrimaveraProperties().getActivityId());
    }
    
    System.out.println("Activity Type: " + task.getPrimaveraProperties().getActivityType());
    System.out.println("Duration Type: " + task.getPrimaveraProperties().getDurationType());
    System.out.println("Percent Complete Type: " + task.getPrimaveraProperties().getPercentCompleteType());
    System.out.println("Original Duration: " + TimeDelta.fromMilliseconds(task.getDuration().getTimeSpan()).getTotalHours());
    System.out.println("At Complete Duration: " +
            (TimeDelta.fromMilliseconds(task.getActualDuration().getTimeSpan()).getTotalHours() + TimeDelta.fromMilliseconds(task.getRemainingDuration().getTimeSpan()).getTotalHours()));
    System.out.println("Duration % Complete: " + task.getPrimaveraProperties().getDurationPercentComplete());
    System.out.println("Physical % Complete: " + task.getPrimaveraProperties().getPhysicalPercentComplete());
    
    System.out.println("Task RemainingEarlyStart: " + task.getPrimaveraProperties().getRemainingEarlyStart());
    System.out.println("Task RemainingEarlyFinish: " + task.getPrimaveraProperties().getRemainingEarlyFinish());
    
    System.out.println("Actual costs:");
    System.out.println(task.getPrimaveraProperties().getActualExpenseCost() + ", "
                    + task.getPrimaveraProperties().getActualLaborCost() + ", "
                    + task.getPrimaveraProperties().getActualMaterialCost() + ", "
                    + task.getPrimaveraProperties().getActualNonlaborCost() + ", Total: "
                    + task.getPrimaveraProperties().getActualTotalCost());
    
    System.out.println("Labor Units:");
    System.out.println(task.getPrimaveraProperties().getActualLaborUnits() + ", " +
            task.getPrimaveraProperties().getActualNonLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingLaborUnits() + ", " +
            task.getPrimaveraProperties().getRemainingNonLaborUnits());
    
    System.out.println("Units % Complete: " + task.getPrimaveraProperties().getUnitsPercentComplete());
}
```
此迴圈會列印每個工作項目的 Primavera 專屬細節，例如 Activity ID、WBS 序列、工期類型、成本細分等。

## 常見問題與解決方案
- **檔案未找到錯誤：** 請確認 `dataDir` 以路徑分隔符（`/` 或 `\\`）結尾，且 XML 檔名正確。  
- **缺少 Primavera 屬性：** 請確保 XML 已匯出所有必要欄位；較舊的 Primavera 版本可能會遺漏某些屬性。  
- **大型檔案效能問題：** 建議為包含數萬工作項目的專案增加 JVM 堆積大小（如 `-Xmx2g` 或更高）。

## 常見問答
### Q：我可以使用 Aspose.Tasks for Java 修改工作項目的 Primavera 專屬屬性嗎？
A：可以，Aspose.Tasks for Java 提供 API 讓您依需求修改 Primavera 專屬屬性。

### Q：Aspose.Tasks for Java 支援讀取其他專案檔案格式嗎？
A：支援，包括 MPP、XML 以及 Primavera XML 等多種格式。

### Q：Aspose.Tasks for Java 適用於企業級專案管理應用程式嗎？
A：絕對適合，Aspose.Tasks for Java 提供強大功能與可擴充性，適用於企業級專案管理。

### Q：我能使用 Aspose.Tasks for Java 從 Primavera 專案中提取資源資訊嗎？
A：可以，Aspose.Tasks for Java 允許您從 Primavera 專案中提取資源資訊及工作項目細節。

### Q：在哪裡可以找到 Aspose.Tasks for Java 的其他支援或文件？
A：您可於 [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/) 頁面取得完整文件與論壇支援。

## 結論
您現在已學會 **如何讀取 primavera xml** 檔案，並使用 **aspose tasks java** 將詳細工作項目資訊匯入 Java 應用程式。此功能彌合 Primavera 與 Microsoft Project 之間的鴻溝，提供跨平台的完整可視性，提升整體專案管理效率。

---

**Last Updated:** 2026-04-24  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}