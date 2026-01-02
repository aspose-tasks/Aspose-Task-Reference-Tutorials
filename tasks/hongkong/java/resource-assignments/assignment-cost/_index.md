---
date: 2026-01-02
description: 學習如何使用 Aspose.Tasks for Java 計算成本差異並執行專案成本管理。逐步指南，說明如何處理指派成本、已執行的預算成本工作以及排程差異的計算。
linktitle: Handle Assignment Cost in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks 計算成本差異與管理指派成本
url: /zh-hant/java/resource-assignments/assignment-cost/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks 計算成本差異並管理指派成本

## Introduction
有效地 **calculate cost variance** 是堅實 *project cost management* 的基石。無論您是追蹤小團隊還是大型企業計畫，了解計畫與實際支出的差異，讓您能及早作出明智決策。在本教學中，我們將示範如何使用 **Aspose.Tasks for Java** 讀取指派成本、計算成本差異，並檢視相關指標，如已執行的預算成本工作（budgeted cost work performed）以及排程差異計算（schedule variance calculation）。

## Quick Answers
- **What does “calculate cost variance” mean?** 它衡量已執行工作之賺取價值與實際成本之間的差異。  
- **Which API property gives the cost variance?** `Asn.CV` 於 `ResourceAssignment` 物件上。  
- **Do I need a license to run the sample?** 免費試用可用於評估；正式環境需購買授權。  
- **What project file formats are supported?** 支援 MPP、XML、MPX 等多種格式。  
- **Is any special configuration required?** 只需將 Aspose.Tasks JAR 加入 classpath 並載入專案檔案即可。

## Prerequisites
在開始撰寫程式碼之前，請確保您已具備：

1. **Java Development Kit (JDK)** – 已安裝 8 版或以上。  
2. **Aspose.Tasks for Java Library** – 從 [website](https://releases.aspose.com/tasks/java/) 下載。  
3. 具備基本的 Java 語法與 Maven/Gradle 專案設定知識。

## Import Packages
First, import the necessary classes in your Java source file:

```java
import com.aspose.tasks.*;
import java.math.BigDecimal;
```

## Step 1: Load the Project File
Create a `Project` instance that points to your existing Microsoft Project file:

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "project.mpp");
```

## Step 2: Iterate Through Resource Assignments
Now we’ll loop over every `ResourceAssignment` to read cost‑related fields and **calculate cost variance**. This also shows how to retrieve the *actual cost of work* and the *budgeted cost work performed*.

```java
for (ResourceAssignment ra : project.getResourceAssignments()) {
    // Assignment cost (total planned cost)
    System.out.println("Assignment Cost: " + ra.get(Asn.COST));
    
    // Actual cost of work performed (ACWP)
    System.out.println("Actual Cost of Work Performed: " + ra.get(Asn.ACWP));
    
    // Cost Variance (CV) – the primary metric we want to calculate
    System.out.println("Cost Variance (CV): " + ra.get(Asn.CV));
    
    // Budgeted Cost of Work Performed (BCWP) – also known as earned value
    System.out.println("Budgeted Cost of Work Performed: " + ra.get(Asn.BCWP));
    
    // Budgeted Cost of Work Scheduled (BCWS)
    System.out.println("Budgeted Cost of Work Scheduled: " + ra.get(Asn.BCWS));
    
    // Schedule Variance (SV) – useful for schedule variance calculation
    System.out.println("Schedule Variance (SV): " + ra.get(Asn.SV));
}
```

### Why These Fields Matter
- **`Asn.COST`** – 您為此指派規劃的總成本。  
- **`Asn.ACWP`** – 已執行工作的 *Actual cost of work*。  
- **`Asn.CV`** – **calculate cost variance** 的結果（`BCWP - ACWP`）。  
- **`Asn.BCWP`** – 代表 *budgeted cost work performed*，是賺值分析的關鍵輸入。  
- **`Asn.SV`** – 協助您執行 *schedule variance calculation*，以判斷工作是提前或落後。

## Common Pitfalls & Tips
- **Null values:** 某些指派可能未填寫成本資料。執行算術運算前務必先檢查 `null`。  
- **Currency handling:** 成本以 `BigDecimal` 儲存。如需特定位數的小數，請使用 `setScale`。  
- **Performance:** 對於極大型專案，建議使用過濾條件 (`project.getResourceAssignments().where(...)`) 以減少迭代開銷。

## Conclusion
透過 Aspose.Tasks for Java，您可以輕鬆 **calculate cost variance**、監控 *actual cost of work*，同時關注 *budgeted cost work performed* 與 *schedule variance*。此類洞察提升 *project cost management* 的智慧，協助您在預算與時程上皆保持在軌。

## FAQ's
### Q: Can I use Aspose.Tasks for Java to calculate resource assignment costs dynamically?
A: Yes, you can calculate assignment costs dynamically using Aspose.Tasks for Java API.  
### Q: Is Aspose.Tasks for Java compatible with all project file formats?
A: Aspose.Tasks for Java supports various project file formats, including MPP, XML, and MPX.  
### Q: How can I get support for Aspose.Tasks for Java?
A: You can get support by visiting the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) or contacting Aspose support directly.  
### Q: Can I try Aspose.Tasks for Java before purchasing?
A: Yes, you can download a free trial from the [website](https://releases.aspose.com/).  
### Q: Do I need a temporary license for using Aspose.Tasks for Java in a trial?
A: No, a temporary license is not required for trial usage. However, it's recommended for production environments.

## Frequently Asked Questions

**Q: How do I export the calculated cost variance to an Excel report?**  
A: After iterating through assignments, you can use Aspose.Cells to write the values into a spreadsheet, mapping each assignment’s ID to its CV.

**Q: Is it possible to filter assignments by a specific resource before calculating variance?**  
A: Yes, you can use `project.getResourceAssignments().where(ra -> ra.getResource().getUid() == desiredResourceId)` to limit the loop.

**Q: What does a negative cost variance indicate?**  
A: A negative CV means the actual cost (ACWP) exceeds the earned value (BCWP), signaling an overrun that should be investigated.

**Q: Can I update the cost fields programmatically and then save the project?**  
A: Absolutely. Use `ra.set(Asn.COST, new BigDecimal("1500"))` and then call `project.save("updated.mpp")`.

**Q: Does Aspose.Tasks automatically handle currency conversion?**  
A: The library stores raw numeric values; you must apply any required conversion logic yourself before presentation.

---

**Last Updated:** 2026-01-02  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}