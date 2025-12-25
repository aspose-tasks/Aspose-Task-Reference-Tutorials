---
date: 2025-12-25
description: 學習如何使用 Aspose.Tasks for Java 篩選 MPP 檔案，並自訂篩選條件，以簡化您的專案管理工作流程。
linktitle: How to Filter MPP Files Using Aspose.Tasks for Java
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks for Java 篩選 MPP 檔案
url: /zh-hant/java/project-management/filter-data/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks for Java 篩選 MPP 檔案

## 簡介
If you’re working with Microsoft Project files (.mpp) in a Java application, you’ll often need to **filter** tasks, resources, or assignments to focus on the data that really matters. In this tutorial we’ll walk through **how to filter mpp** files programmatically with Aspose.Tasks for Java, and show you how to **customize filter criteria** to fit your project‑specific reporting needs. By the end, you’ll have a clear, step‑by‑step example you can drop straight into your own codebase.

## 快速解答
- **「filter mpp」是什麼意思？** It refers to extracting a subset of project data based on defined conditions.  
- **哪個函式庫負責此功能？** Aspose.Tasks for Java provides a rich API for creating and applying filters.  
- **我需要授權嗎？** A free trial works for development; a commercial license is required for production.  
- **我可以篩選任務、資源和指派嗎？** Yes – each entity type has its own filter collection.  
- **需要 Java 8 或以上版本嗎？** Aspose.Tasks supports Java 8 and later versions.

## 什麼是 Java 中的「how to filter mpp」？
Filtering an MPP file means using the Aspose.Tasks API to define criteria (such as task start date, cost, or custom fields) and then retrieving only the items that meet those rules. This helps you generate focused reports, automate status checks, or integrate project data with other systems.

## 為什麼要自訂篩選條件？
Every project has its own priorities. By **customizing filter criteria**, you can isolate high‑risk tasks, overdue items, or resources that exceed budget, making your project dashboards more actionable and your code more reusable.

## 先決條件
Before you begin, make sure you have:

1. **Java Development Kit (JDK)** – version 8 or newer.  
2. **Aspose.Tasks for Java** – download it from the [download page](https://releases.aspose.com/tasks/java/).  
3. **An IDE** – IntelliJ IDEA, Eclipse, or NetBeans will work fine.  

## 匯入套件
Begin by importing the necessary classes into your Java project:

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

## 逐步指南

### 步驟 1：設定專案
First, create a `Project` instance that points to the MPP file you want to work with.

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "Project2003.mpp");
```

### 步驟 2：取得篩選器
Aspose.Tasks stores predefined filters (e.g., “All Tasks”, “Critical Tasks”). Grab the one you need by index or name.

```java
Filter filter = project.getTaskFilters().toList().get(1);
```

> **專業提示：** If you prefer a named filter, use `project.getTaskFilters().getByName("My Custom Filter")`.

### 步驟 3：存取篩選條件
Now that you have the `Filter` object, you can inspect its criteria rows and the logical operation (AND/OR) that combines them.

```java
System.out.println(filter.getCriteria().getCriteriaRows().size());
System.out.println(filter.getCriteria().getOperation());
```

### 步驟 4：取得條件細節
Each criteria row contains a test (e.g., “Equals”, “GreaterThan”) and the field it applies to (e.g., “Start”, “Cost”).

```java
FilterCriteria criteria1 = filter.getCriteria().getCriteriaRows().get(0);
System.out.println(criteria1.getTest());
System.out.println(criteria1.getField());
```

### 步驟 5：遍歷條件列
Complex filters can have nested criteria. Here we walk through a second‑level group of criteria.

```java
FilterCriteria criteria2 = filter.getCriteria().getCriteriaRows().get(1);
System.out.println(criteria2.getOperation());
System.out.println(criteria2.getCriteriaRows().size());
```

### 步驟 6：列印條件資訊
Finally, output the details of each nested criterion so you can verify the filter logic.

```java
FilterCriteria criteria21 = criteria2.getCriteriaRows().get(0);
System.out.println(criteria21.getTest());
System.out.println(criteria21.getField());
FilterCriteria criteria22 = criteria2.getCriteriaRows().get(1);
System.out.println(criteria22.getTest());
System.out.println(criteria22.getField());
```

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| **在存取篩選器時發生 NullPointerException** | Ensure the project file actually contains task filters; you can add a filter programmatically if needed. |
| **欄位名稱不正確** | Use `ItemType` enums (e.g., `ItemType.Task`) to avoid typos. |
| **篩選結果為空** | Verify the test operators and values match the data in your MPP file. |

## 常見問答
### Q: Aspose.Tasks for Java 是否相容於不同版本的 Microsoft Project 檔案？
A: 是，Aspose.Tasks for Java 支援各種版本的 Microsoft Project 檔案，確保在專案管理任務中的相容性與彈性。

### Q: 我可以根據特定專案需求自訂篩選條件嗎？
A: 當然可以！Aspose.Tasks for Java 允許您依照專案的獨特需求調整篩選條件，實現目標資料的操作與分析。

### Q: Aspose.Tasks for Java 是否適用於小型與大型專案？
A: 是的，無論您管理的是小規模專案或是龐大的專案組合，Aspose.Tasks for Java 都提供所需的可擴充性與效能。

### Q: Aspose.Tasks for Java 是否提供完整的文件與支援資源？
A: 當然！您可參考[文件](https://reference.aspose.com/tasks/java/)取得詳細指南與 API 參考；此外，也可在 Aspose.Tasks 社群論壇尋求協助。

### Q: 我可以在購買前先體驗 Aspose.Tasks for Java 的功能嗎？
A: 當然可以！您可從[網站](https://releases.aspose.com/)取得免費試用，親自體驗 Aspose.Tasks for Java 的功能與效能。

## 常見問題

**問：如何以程式方式建立全新的篩選器？**  
答：Use `project.getTaskFilters().add(new Filter("My Filter"))` and then define its `FilterCriteria` collection.

**問：我可以將篩選器套用於資源而非任務嗎？**  
答：Yes – use `project.getResourceFilters()` to work with resource‑specific filters.

**問：是否可以使用 OR 邏輯結合多個篩選器？**  
答：You can create a parent `FilterCriteria` with the `Operation` set to `OR` and add individual criteria as children.

**問：Aspose.Tasks 是否支援對自訂欄位進行篩選？**  
答：Absolutely. Custom fields are treated like any other field; reference them by their `CustomField` enum value.

**問：在大型 MPP 檔案上執行篩選會產生什麼效能影響？**  
答：Filtering is performed in memory and is generally fast, but for extremely large projects consider loading only required sections using `ProjectReader`.

---

**最後更新：** 2025-12-25  
**測試版本：** Aspose.Tasks for Java 24.10  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}