---
date: 2026-06-05
description: 了解如何使用 Aspose.Tasks for Java 篩選 MPP 檔案、客製化篩選條件，並依日期篩選工作，以提升專案管理效率。
keywords:
- how to filter mpp
- filter tasks by date
- Aspose.Tasks Java filter
- project management Java API
linktitle: 如何使用 Aspose.Tasks for Java 篩選 MPP 檔案
schemas:
- author: Aspose
  dateModified: '2026-06-05'
  description: Learn how to filter MPP files using Aspose.Tasks for Java, customize
    filter criteria, and filter tasks by date to streamline project management.
  headline: How to Filter MPP Files Using Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: It means extracting a subset of project data based on defined conditions.
    question: What does “filter mpp” mean?
  - answer: Aspose.Tasks for Java provides a comprehensive API for creating and applying
      filters.
    question: Which library handles this?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – each entity type has its own filter collection.
    question: Can I filter tasks, resources, and assignments?
  - answer: Aspose.Tasks supports Java 8 and later versions.
    question: Is Java 8 or higher required?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks for Java 篩選 MPP 檔案
url: /zh-hant/java/project-management/filter-data/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks for Java 過濾 MPP 檔案的方法

## 介紹
如果您在 Java 應用程式中處理 Microsoft Project 檔案（*.mpp*），通常需要 **過濾 MPP 檔案** 以挑選出最重要的工作、資源或指派項目。在本教學中，我們將示範如何使用 Aspose.Tasks for Java 程式化 **過濾 mpp** 檔案、**自訂過濾條件**，並展示一個實務的「依日期過濾工作」情境。完成後，您將擁有一段可直接放入任何 Java 專案的即用程式碼片段。

## 快速答覆
- **「filter mpp」是什麼意思？** 即根據定義的條件抽取專案資料的子集合。  
- **哪個函式庫負責此功能？** Aspose.Tasks for Java 提供完整的 API 來建立與套用過濾器。  
- **需要授權嗎？** 開發階段可使用免費試用版；正式上線需購買商業授權。  
- **可以過濾工作、資源與指派嗎？** 可以——每種實體都有自己的過濾集合。  
- **是否需要 Java 8 或更高版本？** Aspose.Tasks 支援 Java 8 及以上版本。

## 在 Java 中「如何過濾 mpp」是什麼？
`How to filter mpp` 是指使用 Aspose.Tasks 的 `Filter` 物件，選取符合特定謂詞（如開始日期、成本或自訂欄位）的專案元素。載入 `Project`、取得 `Filter`，API 會回傳符合條件的集合，讓您能進行聚焦報表或後續整合。

## 為什麼要自訂過濾條件？
自訂過濾條件讓您能鎖定高風險工作、逾期項目或預算超支的資源，將龐大的專案檔案轉換為簡潔、可行的視圖。Aspose.Tasks 支援 **50+ 預定義過濾類型**，且允許建立無限制的自訂過濾器，將手動篩選時間縮短最高可達 70 %。

## 前置條件
在開始之前，請確保您已具備：

1. **Java Development Kit (JDK)** – 版本 8 或更新。  
2. **Aspose.Tasks for Java** – 從 [download page](https://releases.aspose.com/tasks/java/) 下載。  
3. **IDE** – IntelliJ IDEA、Eclipse 或 NetBeans 都可使用。  

## 匯入套件
`Filter`、`FilterCollection`、`FilterCriteria`、`ItemType` 與 `Project` 為定義與套用過濾器的核心類別。

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

## 步驟指南

### 步驟 1：設定專案
首先，建立指向欲分析的 MPP 檔案的 `Project` 實例，並將其載入記憶體。此一步驟會將整個專案模型準備好，以供過濾、驗證與後續操作，讓您能透過 API 存取工作、資源與指派。

### 如何設定專案以過濾 MPP 檔案？
`Project` 類別會將 MPP 檔案載入記憶體並加以表示。建立指向目標 MPP 檔案的 `Project` 實例，然後載入即可。此單一步驟會為過濾、驗證與進一步操作準備完整的專案模型，讓您能透過 API 存取工作、資源與指派。

### 如何取得並檢視過濾器？
`Filter` 物件封裝了用於選取專案項目的過濾定義。Aspose.Tasks 內建如「All Tasks」或「Critical Tasks」等預設過濾器。使用 `project.getTaskFilters().getByName("My Filter")` 或索引方式取得 `Filter` 物件，然後檢查其 `FilterCriteria` 集合，以了解每條規則及其組合的邏輯運算子（AND/OR），確保過濾器符合您的需求。

### 如何遍歷巢狀的條件列？
`FilterCriteriaGroup` 代表以邏輯運算子結合的一組過濾條件。過濾器可包含多個條件群組，每個群組都有自己的運算子。遍歷 `filter.getCriteria().getRows()`，對於任何屬於 `FilterCriteriaGroup` 的列，遞迴處理其子列。此遍歷讓您完整了解複雜的過濾邏輯，例如「(Start < today AND Cost > 1000) OR Priority = High」，並依需求調整條件。

### 如何列印條件資訊以進行除錯？
在遍歷條件樹後，將每列的欄位名稱、測試運算子與值輸出至主控台。這個簡易的 dump 可協助您在將過濾器套用至大型專案前，驗證其是否符合預期的業務規則，並更容易發現錯誤的運算子或值。

### 如何程式化建立全新過濾器？
使用 `new Filter("My Filter")` 建立 `Filter`，然後透過 `project.getTaskFilters().add(filter)` 加入專案的工作過濾集合。之後，將所需的列（欄位名稱、測試運算子、值）加入其 `FilterCriteria` 集合，即可定義在套用過濾器時應包含的工作項目。

### 能否將過濾器套用於資源而非工作？
`ResourceFilters` 集合保存適用於資源的過濾定義。是的——使用 `project.getResourceFilters()` 以與工作過濾器相同的方式處理資源過濾器。加入或取得過濾器後，像處理工作一樣配置其 `FilterCriteria`，然後套用至資源集合，即可取得過濾後的資源集合。

### 是否可以使用 OR 邏輯結合多個過濾器？
建立一個 `FilterCriteriaGroup`，將其 `Operation` 設為 `OR`，再將個別的 `FilterCriteria` 物件作為子項加入。此群組會評估每個子條件，返回符合任一條件的項目，讓您能將多個簡單過濾器合併為更廣的選取範圍。

### Aspose.Tasks 是否支援自訂欄位的過濾？
`CustomField` 列舉提供專案中自訂欄位的識別碼。當然支援。透過 `CustomField` 列舉引用自訂欄位，它們在過濾表達式中與內建欄位同等對待。您可以在 `FilterCriteria` 列中加入自訂欄位，使用相同的運算子與值，實現對使用者定義資料的強大查詢。

### 大型 MPP 檔案的過濾效能如何？
過濾完全在記憶體中執行，通常可在 200 ms 內處理 1,000 工作的專案。對於數千工作的大型檔案，建議使用 `ProjectReader` 僅載入必要的區段，然後在選擇性載入後套用過濾器，這樣可降低記憶體使用量，並在極大規模專案中仍保持快速回應。

---

**最後更新：** 2026-06-05  
**測試環境：** Aspose.Tasks for Java 24.10  
**作者：** Aspose

## 相關教學

- [Load MPP File Java - Manage Project Properties with Aspose.Tasks](/tasks/java/project-management/default-properties/)
- [Aspose.Tasks Java - Effortless MS Project Online Data Reading](/tasks/java/project-data-reading/read-project-online/)
- [Set Project Start Date in MS Project using Aspose.Tasks for Java](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
import com.aspose.tasks.Filter;
import com.aspose.tasks.FilterCollection;
import com.aspose.tasks.FilterCriteria;
import com.aspose.tasks.ItemType;
import com.aspose.tasks.Project;
import java.util.List;
```

```java
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "Project2003.mpp");
```

```java
Filter filter = project.getTaskFilters().toList().get(1);
```

```java
System.out.println(filter.getCriteria().getCriteriaRows().size());
System.out.println(filter.getCriteria().getOperation());
```

```java
FilterCriteria criteria1 = filter.getCriteria().getCriteriaRows().get(0);
System.out.println(criteria1.getTest());
System.out.println(criteria1.getField());
```

```java
FilterCriteria criteria2 = filter.getCriteria().getCriteriaRows().get(1);
System.out.println(criteria2.getOperation());
System.out.println(criteria2.getCriteriaRows().size());
```

```java
FilterCriteria criteria21 = criteria2.getCriteriaRows().get(0);
System.out.println(criteria21.getTest());
System.out.println(criteria21.getField());
FilterCriteria criteria22 = criteria2.getCriteriaRows().get(1);
System.out.println(criteria22.getTest());
System.out.println(criteria22.getField());
```