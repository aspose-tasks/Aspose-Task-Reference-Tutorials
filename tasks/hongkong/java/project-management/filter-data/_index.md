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
如果您在 Java 應用程式中使用 Microsoft Project 檔案 (.mpp)，通常需要對任務、資源或指派進行**篩選**，以便專注於真正重要的資料。本教學將逐步說明如何使用 Aspose.Tasks for Java 以程式方式篩選 .mpp 文件，並向您展示如何**自訂篩選條件**以滿足您專案特定的報告需求。最後，您將獲得一個清晰的逐步範例，可以直接將其應用到您自己的程式碼庫中。

## 快速解答
- **「filter mpp」是什麼意思？** 它指的是根據定義的條件提取項目資料的子集。  
- **哪個函式庫負責此功能？** Aspose.Tasks for Java 提供了豐富的 API，用於建立和套用篩選器。 
- **我需要授權嗎？** 免費試用版適用於開發階段；生產階段需要商業許可。  
- **我可以篩選任務、資源和指派嗎？** 是的－每種實體類型都有自己的過濾器集合。  
- **需要 Java 8 或以上版本嗎？** Aspose.Tasks 支援 Java 8 及更高版本。

## 什麼是 Java 中的「how to filter mpp」？
篩選 .mpp 檔案意味著使用 Aspose.Tasks API 定義篩選條件（例如任務開始日期、成本或自訂欄位），然後僅擷取符合這些規則的項目。這有助於您產生重點突出的報告、自動執行狀態檢查或將專案資料與其他系統整合。

## 為什麼要自訂篩選條件？
每個項目都有其自身的優先順序。透過**自訂篩選條件**，您可以隔離高風險任務、逾期專案或超出預算的資源，從而使您的專案儀表板更具實用性，程式碼更易於重複使用。

## 先決條件
在開始之前，請確保您已準備好以下工具：

1. **Java 開發工具包 (JDK)** – 版本 8 或更高版本。
2. **Aspose.Tasks for Java** – 請從[下載頁面](https://releases.aspose.com/tasks/java/)下載。
3. **整合開發環境 (IDE)** – IntelliJ IDEA、Eclipse 或 NetBeans 皆可。  

## 匯入套件
首先，將必要的類別匯入到您的 Java 專案中：

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
首先，建立一個指向您要處理的 MPP 檔案的 `Project` 實例。

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "Project2003.mpp");
```

### 步驟 2：取得篩選器
Aspose.Tasks 儲存了預先定義的篩選器（例如，「所有任務」、「關鍵任務」）。您可以按索引或名稱取得所需的篩選器。

```java
Filter filter = project.getTaskFilters().toList().get(1);
```

> **專業提示：** 如果您喜歡使用命名篩選器，請使用 `project.getTaskFilters().getByName("我的自訂篩選器")`。

### 步驟 3：存取篩選條件
現在您已經有了 `Filter` 對象，可以檢查其條件行以及組合這些條件的邏輯運算（AND/OR）。

```java
System.out.println(filter.getCriteria().getCriteriaRows().size());
System.out.println(filter.getCriteria().getOperation());
```

### 步驟 4：取得條件細節
每個條件行都包含一個測試（例如，「等於」、「大於」）以及它所應用的欄位（例如，「開始時間」、「成本」）。

```java
FilterCriteria criteria1 = filter.getCriteria().getCriteriaRows().get(0);
System.out.println(criteria1.getTest());
System.out.println(criteria1.getField());
```

### 步驟 5：遍歷條件列
複雜的篩選器可以包含嵌套條件。這裡我們來看看第二層條件組。

```java
FilterCriteria criteria2 = filter.getCriteria().getCriteriaRows().get(1);
System.out.println(criteria2.getOperation());
System.out.println(criteria2.getCriteriaRows().size());
```

### 步驟 6：列印條件資訊
最後，輸出每個嵌套條件的詳細信息，以便您可以驗證篩選邏輯。

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
| **在存取篩選器時發生 NullPointerException** | 請確保專案文件中確實包含任務篩選器；如果需要，可以透過程式設計方式新增篩選器。 |
| **欄位名稱不正確** | 使用 `ItemType` 枚舉（例如，`ItemType.Task`）可以避免拼字錯誤。 |
| **篩選結果為空** | 請驗證測試運算子和值是否與 MPP 檔案中的資料相符。 |

## 常見問題

**問：如何以程式方式建立全新的篩選器？**  
答：使用 `project.getTaskFilters().add(new Filter("My Filter"))`，然後定義其 `FilterCriteria` 集合。

**問：我可以將篩選器套用於資源而非任務嗎？**  
答：是的－使用 `project.getResourceFilters()` 來處理特定於資源的篩選器。

**問：是否可以使用 OR 邏輯結合多個篩選器？**  
答：您可以建立一個父級 `FilterCriteria`，並將 `Operation` 設定為 `OR`，然後新增各個條件作為子條件。

**問：Aspose.Tasks 是否支援對自訂欄位進行篩選？**  
答：當然。自訂欄位的處理方式與其他欄位相同；可以透過其 `CustomField` 枚舉值來引用它們。

**問：在大型 MPP 檔案上執行篩選會產生什麼效能影響？**  
答：過濾操作在記憶體中執行，速度通常很快，但對於非常大的項目，請考慮使用 `ProjectReader` 僅載入所需的部分。

---

**最後更新：** 2025-12-25  
**測試版本：** Aspose.Tasks for Java 24.10  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}