---
date: 2025-12-28
description: 學習如何使用 Aspose.Tasks for Java 將 Primavera XML 檔案讀入 MS Project，實現無縫的資料交換與提升專案管理效能。
linktitle: Read Project from Primavera in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks for Java 將 Primavera XML 匯入 MS Project
url: /zh-hant/java/project-management/read-primavera/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 從 Primavera 讀取 MS Project 使用 Aspose.Tasks for Java

## 介紹
在現代專案管理中，於工具之間搬移資料而不遺失細節是必須的。本教學示範 **如何讀取 primavera xml** 檔案並使用 Aspose.Tasks for Java 匯入至 Microsoft Project。完成後，您將能提取 Primavera 專屬的工作屬性，讓跨平台分析變得簡單且高效。

## 快速解答
- **Aspose.Tasks for Java 的功能是什麼？** 它能讀寫多種專案檔案格式，包括 Primavera XML 與 Microsoft Project (MPP)。  
- **我需要授權嗎？** 免費試用可用於評估；正式使用則需購買授權。  
- **支援哪個 Java 版本？** 需要 Java 8 或更高版本。  
- **除了 Primavera XML，我還能讀取其他格式嗎？** 可以，Aspose.Tasks 支援 MPP、XML 以及其他多種格式。  
- **此方法適用於大型企業專案嗎？** 絕對適用——Aspose.Tasks 為高效能、企業級情境而設計。

## 什麼是讀取 primavera xml？
讀取 Primavera XML 指的是解析 Oracle Primavera P6 匯出的 XML，以取得專案排程資料——工作、工期、資源以及 Primavera 專屬屬性——使其能被其他工具（如 Microsoft Project）使用。

## 為何使用 Aspose.Tasks for Java 讀取 primavera xml？
- **完整保真度：** 所有 Primavera 專屬屬性皆被保留。  
- **無外部相依性：** 純 Java 函式庫，無需安裝 Primavera 或 MS Project。  
- **可擴充性：** 能有效處理包含數千個工作的大型專案。  
- **跨平台：** 可在 Windows、Linux 與 macOS 上執行。

## 前置條件
1. **Java Development Kit (JDK)** – 已安裝 Java 8 或更新版本。  
2. **Aspose.Tasks for Java** – 從 [here](https://releases.aspose.com/tasks/java/) 下載。  
3. 您想要讀取的 Primavera XML 檔案（例如 `PrimaveraProject.xml`）。

## 如何使用 Aspose.Tasks 讀取 Java 專案檔案？
以下是一個逐步指南，帶您完成整個流程。

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
將 `"PrimaveraProject.xml"` 更新為您 Primavera 匯出的實際檔名。

### 步驟 3：遍歷工作並取得 Primavera 專屬屬性
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
此迴圈會列印每個工作的 Primavera 專屬細節，例如 Activity ID、WBS 序列、工期類型、成本細分等。

## 常見問題與解決方案
- **檔案未找到錯誤：** 請確認 `dataDir` 以路徑分隔符（`/` 或 `\\`）結尾，且 XML 檔名正確。  
- **缺少 Primavera 屬性：** 請確保 XML 已匯出所有必要欄位；較舊的 Primavera 版本可能會遺漏某些屬性。  
- **大型檔案效能問題：** 對於包含數萬個工作的專案，可考慮增大 JVM 堆積大小（例如 `-Xmx2g` 或更高）。

## 常見問答
### Q: 我可以使用 Aspose.Tasks for Java 修改工作之 Primavera 專屬屬性嗎？
A: 可以，Aspose.Tasks for Java 提供 API 讓您依需求修改工作之 Primavera 專屬屬性。

### Q: Aspose.Tasks for Java 支援讀取其他專案檔案格式嗎？
A: 可以，Aspose.Tasks for Java 支援讀取多種專案檔案格式，包括 MPP、XML 與 Primavera XML。

### Q: Aspose.Tasks for Java 適用於企業級專案管理應用程式嗎？
A: 絕對適用，Aspose.Tasks for Java 提供強大的功能與可擴充性，適合企業級專案管理應用程式。

### Q: 我可以使用 Aspose.Tasks for Java 從 Primavera 專案中提取資源資訊嗎？
A: 可以，Aspose.Tasks for Java 允許您從 Primavera 專案中提取資源資訊及工作細節。

### Q: 我可以在哪裡找到 Aspose.Tasks for Java 的其他支援或文件？
A: 您可於 [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/) 頁面取得完整文件與論壇支援。

## 結論
您現在已學會 **如何讀取 primavera xml** 檔案，並使用 Aspose.Tasks 將詳細工作資訊匯入 Java 應用程式。此功能彌合了 Primavera 與 Microsoft Project 之間的差距，提供跨平台的完整可見性，提升整體專案管理效率。

---

**最後更新：** 2025-12-28  
**測試環境：** Aspose.Tasks for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}