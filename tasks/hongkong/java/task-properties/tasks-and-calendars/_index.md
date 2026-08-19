---
date: 2026-02-28
description: 學習如何使用 Aspose.Tasks for Java 為專案新增任務並建立任務行事曆——一個功能強大的專案管理函式庫。
linktitle: Tasks and Calendars in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks for Java 為專案新增任務並管理行事曆
url: /zh-hant/java/task-properties/tasks-and-calendars/
weight: 33
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks for Java 中新增任務至專案並管理行事曆

## 介紹
準備好 **add task to project** 並讓您的行程完美對齊了嗎？在本指南中，我們將逐步說明建立任務、將其附加至自訂行事曆，以及運用 Aspose.Tasks——業界領先的 **java project management library**。完成後，您將確切了解如何以 **create task calendar java** 方式建立任務行事曆，讓您對專案時間表擁有精細的控制。

## 快速解答
- **What is the primary purpose?** 新增任務至專案並將其關聯至自訂行事曆。  
- **Which library should I use?** Aspose.Tasks for Java – 完整功能的專案管理 API。  
- **Do I need a license?** 可使用免費試用版；正式環境需購買商業授權。  
- **What JDK version is required?** Java 8 或以上。  
- **How long does implementation take?** 基本情境通常在 15 分鐘內完成。

## 什麼是 “add task to project”？
將任務新增至專案，即是在 Project 物件內建立工作項目，並定義其屬性（持續時間、開始日期、行事曆等）。此操作是任何以排程為核心的應用程式的基礎構件。

## 為什麼要使用 Java 專案管理函式庫？
像 Aspose.Tasks 這樣的專用函式庫會為您處理複雜的 MS‑Project 檔案格式、資源平衡與行事曆計算。它讓您免於重新發明輪子，並確保與業界標準工具的相容性。

## 前置條件
在開始本教學之前，請確保已具備以下前置條件：
- Java Development Kit (JDK)：確保系統已安裝 Java。  
- Aspose.Tasks 函式庫：下載並在專案中加入 Aspose.Tasks 函式庫。您可於[此處](https://releases.aspose.com/tasks/java/)取得函式庫。

## 匯入套件
在您的 Java 專案中，匯入 Aspose.Tasks 所需的套件：

```java
import com.aspose.tasks.Calendar;
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
```

## 步驟 1：設定專案
首先建立一個新的 Java 專案，並將 Aspose.Tasks JAR 加入建置路徑。如此即可使用完整的 API。

## 步驟 2：如何 add task to project
建立一個新的 `Project` 實例，並新增一個名為 **Task1** 的根層級任務。此範例示範核心的 “add task to project” 操作。

```java
Project project = new Project();
Task tsk = project.getRootTask().getChildren().add("Task1");
```

## 步驟 3：如何 create task calendar java
在專案中加入標準行事曆。行事曆用來定義工作日、假日及其他排程規則。

```java
Calendar cal = project.getCalendars().add("TaskCal1");
```

## 步驟 4：將任務關聯至行事曆
將先前建立的任務連結至新行事曆，使其排程遵循該行事曆的工作時間。

```java
tsk.set(Tsk.CALENDAR, cal);
```

*提示：* 針對每個需要的額外任務與行事曆重複上述步驟。您亦可使用 `Calendar` API 自訂行事曆例外（例如非工作日）。

## 常見問題與解決方案
- **Task not reflecting calendar changes:** 確認在修改行事曆後呼叫 `project.updateStructure()`。  
- **NullPointerException on `set` call:** 請確認行事曆已成功加入專案後再進行指派。  
- **Incorrect dates after import/export:** 使用 `project.save("output.mpp")` 並重新開啟，以確認資料已正確保存。

## 常見問答
### 如何下載 Aspose.Tasks for Java？
前往[此連結](https://releases.aspose.com/tasks/java/)下載函式庫。

### 在哪裡可以找到 Aspose.Tasks 的文件？
於[此處](https://reference.aspose.com/tasks/java/)瀏覽文件。

### 是否提供免費試用？
是的，您可於[此處](https://releases.aspose.com/)取得免費試用。

### 如何取得 Aspose.Tasks 支援？
加入[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)社群以獲得支援。

### 是否可以購買 Aspose.Tasks 授權？
是的，您可於[此處](https://purchase.aspose.com/buy)購買授權。

**其他問答**

**Q: 我可以使用 Aspose.Tasks 讀取現有的 Microsoft Project 檔案嗎？**  
A: 當然可以。`Project` 類別可直接載入 `.mpp` 與 `.xml` 檔案。

**Q: 此函式庫是否支援每個專案多個行事曆？**  
A: 支援。您可以依需求建立任意數量的 `Calendar` 物件，並將其指派給不同的任務。

## 結論
恭喜！您已成功學會如何 **add task to project**、建立自訂行事曆，並透過 Aspose.Tasks for Java 將兩者連結。這個強大的組合讓您能快速打造穩健且具排程感知的應用程式。

---

**最後更新：** 2026-02-28  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---