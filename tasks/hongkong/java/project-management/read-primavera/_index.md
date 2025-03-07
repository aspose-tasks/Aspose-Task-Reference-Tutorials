---
title: 使用 Aspose.Tasks for Java 讀取 Primavera 的 MS 項目
linktitle: 在 Aspose.Tasks 中讀取 Primavera 的項目
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 從 Primavera XML 無縫讀取 MS Project 檔案。提高您的專案管理效率。
weight: 20
url: /zh-hant/java/project-management/read-primavera/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks for Java 讀取 Primavera 的 MS 項目

## 介紹
在專案管理中，不同軟體平台之間的互通性對於無縫工作流程至關重要。 Aspose.Tasks for Java 提供了從 Primavera XML 讀取 Microsoft Project 檔案的強大功能。本教學將引導您完成使用 Aspose.Tasks for Java 從 Primavera 讀取 MS Project 檔案的過程，從而使您能夠有效地檢查任務的 Primavera 特定屬性。
## 先決條件
在繼續之前，請確保您已安裝並設定以下先決條件：
1. Java 開發工具包 (JDK)：確保您的系統上安裝了 JDK。
2.  Aspose.Tasks for Java：從下列位置下載並安裝 Aspose.Tasks for Java：[這裡](https://releases.aspose.com/tasks/java/).

## 導入包
```java
import com.aspose.tasks.PrimaveraReadOptions;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeDelta;
```
## 第 1 步：設定資料目錄
```java
String dataDir = "Your Data Directory";
```
確保更換`"Your Data Directory"`與資料目錄的實際路徑。
## 步驟 2： 從 Primavera XML 讀取項目
```java
PrimaveraReadOptions options = new PrimaveraReadOptions();
options.setProjectUid(3883);
Project project = new Project(dataDir + "PrimaveraProject.xml", options);
```
確保更換`"PrimaveraProject.xml"`與您的 Primavera XML 檔案的實際名稱。
## 第 3 步：迭代任務並檢索 Primavera 特定屬性
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
此程式碼循環存取專案中的每個任務，列印相關的 Primavera 特定屬性。

## 結論
在本教學中，您學習如何使用 Aspose.Tasks for Java 從 Primavera XML 讀取 MS Project 檔案。此功能可跨不同平台無縫整合和分析專案數據，從而提高整體專案管理效率。
## 常見問題解答
### Q：我可以使用 Aspose.Tasks for Java 修改任務的 Primavera 特定屬性嗎？
答：是的，Aspose.Tasks for Java 提供 API 來根據需要修改任務的 Primavera 特定屬性。
### Q：Aspose.Tasks for Java 支援讀取其他專案檔案格式嗎？
答：是的，Aspose.Tasks for Java 支援讀取各種專案檔案格式，包括 MPP、XML 和 Primavera XML。
### Q：Aspose.Tasks for Java 適合企業級專案管理應用程式嗎？
答：當然，Aspose.Tasks for Java 提供了強大的功能和可擴充性，使其適合企業級專案管理應用程式。
### Q：我可以使用 Aspose.Tasks for Java 從 Primavera 專案中提取資源資訊嗎？
答：是的，Aspose.Tasks for Java 可讓您從 Primavera 專案中提取資源資訊以及任務詳細資訊。
### Q：在哪裡可以找到 Aspose.Tasks for Java 的其他支援或文件？
答：您可以找到全面的文檔並訪問論壇以獲得有關[Aspose.Tasks for Java 文檔](https://reference.aspose.com/tasks/java/)頁。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
