---
date: 2026-02-28
description: 了解如何使用 Aspose.Tasks for Java 來管理任務時間分段資料，下載程式庫，免費試用，並簡化專案追蹤。
linktitle: Task Timephased Data in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks 管理任務時間相位資料（Java）
url: /zh-hant/java/task-properties/task-timephased-data/
weight: 34
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks 進行任務時間相位資料管理

## 介紹
如果你正尋找 **how to use Aspose** 以緊密掌控專案排程，你來對地方了。精確追蹤任務時間相位資料是成功專案管理的基石，而 Aspose.Tasks for Java 為你提供自動化此流程的工具。在本教學中，我們將逐步示範完整的端對端範例，說明如何使用 Aspose.Tasks 建立專案、指派資源、設定基線，最後取得並顯示時間相位資料。

## 快速回答
- **What does “timephased data” mean?** 它是依時間間隔（天、週、月）細分的資料，顯示在專案時間線上工作的量、成本或剩餘工作量。  
- **Which library provides this capability?** Aspose.Tasks for Java。  
- **Do I need a license to run the sample?** 免費試用版可用於開發；正式環境需購買授權。  
- **What Java version is required?** Java 8 或以上。  
- **Can I export the results to Excel?** 可以 – 你可以遍歷 `TimephasedData` 集合，將值寫入任何需要的格式。

## 什麼是任務時間相位資料？
任務時間相位資料表示在專案行事曆的每個時間切片中，為任務排定的工作（或成本）量。它讓你能看出工作分配情況、發現資源過度配置，並比較計畫與實際進度。

## 為什麼使用 Aspose.Tasks 來管理時間相位資料？
- **Full control** – 以程式方式建立、修改與查詢時間相位資訊，無需開啟 Microsoft Project。  
- **Cross‑platform** – 可在任何支援 Java 的作業系統上執行。  
- **No COM dependencies** – 適用於伺服器端自動化。  
- **Rich API** – 原生支援基線、工作輪廓與自訂欄位。

## 前置條件
在深入程式碼之前，請確保你已具備以下條件：

- **Java Development Environment** – 已安裝 JDK 8 以上，且已設定 `JAVA_HOME`。  
- **Aspose.Tasks for Java Library** – 下載並將 Aspose.Tasks 程式庫加入專案中。你可於[此處](https://releases.aspose.com/tasks/java/)取得程式庫。  
- **Document Directory** – 你的機器上用於讀寫範例專案檔 (`project.xml`) 的資料夾。

## 匯入套件
在 Java 專案中，匯入必要的 Aspose.Tasks 類別：

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimephasedData;
import com.aspose.tasks.TimephasedDataType;
import com.aspose.tasks.Tsk;
import com.aspose.tasks.WorkContourType;
import java.math.BigDecimal;
import java.util.Date;
import java.util.List;
```

## 步驟 1：設定專案開始日期
```java
Project project = new Project(dataDir + "project.xml");
// Additional code for package imports
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, 7, 17, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
```
*Explanation:* 我們建立一個 `Project` 實例，將 `Calendar` 初始化為所需的開始日期，並將其指派給專案的 `START_DATE` 屬性。

## 步驟 2：定義任務與資源
```java
Task task = project.getRootTask().getChildren().add("Task");
Resource rsc = project.getResources().add("Rsc");
rsc.set(Rsc.STANDARD_RATE, BigDecimal.valueOf(10));
rsc.set(Rsc.OVERTIME_RATE, BigDecimal.valueOf(15));
```
*Explanation:* 在根任務下新增一個名為 **Task** 的新任務。我們同時建立一個名為 **Rsc** 的資源，並設定其標準與加班費率。

## 步驟 3：設定任務工期
```java
task.set(Tsk.DURATION, project.getDuration(6));
```
*Explanation:* 此任務的工期設定為 **6 天**。

## 步驟 4：指派資源給任務
```java
ResourceAssignment assn = project.getResourceAssignments().add(task, rsc);
```
*Explanation:* 前述建立的資源透過 `ResourceAssignment` 連結至此任務。

## 步驟 5：設定資源指派
```java
Date d = new Date(0);
assn.set(Asn.STOP, new Date(0));
assn.set(Asn.RESUME, new Date(0));
assn.set(Asn.WORK_CONTOUR, WorkContourType.BackLoaded);
```
*Explanation:* 我們設定指派的停止與恢復日期（使用佔位值），並套用 **Back‑Loaded** 工作輪廓，使工作量在指派的後期較多。

## 步驟 6：設定基線
```java
project.setBaseline(BaselineType.Baseline);
```
*Explanation:* 設定基線可讓你之後比較計畫值與實際值。

## 步驟 7：更新任務完成度
```java
task.set(Tsk.PERCENT_COMPLETE, 50);
```
*Explanation:* 任務被標記為 **50 % 完成**，這會影響剩餘工作量的計算。

## 步驟 8：取得時間相位資料
```java
List<TimephasedData> td = assn.getTimephasedData(assn.get(Asn.START), assn.get(Asn.FINISH), TimephasedDataType.AssignmentRemainingWork).toList();
```
*Explanation:* 此呼叫取得指派的 **remaining work**，依專案的時間間隔分段。

## 步驟 9：顯示時間相位資料
```java
System.out.println(td.size());
System.out.println(td.get(0).getValue());
// Additional code for displaying other values
```
*Explanation:* 我們僅列印時間相位項目的數量與第一筆的值。實務上，你會遍歷此清單，並將資料匯出至報表或 UI。

## 常見問題與解決方案
- **NullPointerException on `getTimephasedData`** – 確保在呼叫此方法前已設定指派的 `START` 與 `FINISH` 日期。  
- **Incorrect work contour** – 檢查所選的 `WorkContourType` 是否符合你的排程策略；`BackLoaded` 只是多種選項之一。  
- **Baseline not reflecting changes** – 記得在定義任務、資源與指派之後，再呼叫 `project.setBaseline`。

## 常見問答
### Q: 我可以在任何 Java 專案中使用 Aspose.Tasks for Java 嗎？
A: 可以，Aspose.Tasks for Java 相容於任何基於 Java 的專案。

### Q: 我可以在哪裡取得 Aspose.Tasks for Java 的額外支援？
A: 前往 [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) 取得支援與討論。

### Q: 是否提供 Aspose.Tasks for Java 的免費試用？
A: 有，您可於[此處](https://releases.aspose.com/)試用免費版。

### Q: 我該如何取得 Aspose.Tasks for Java 的臨時授權？
A: 您可於[此處](https://purchase.aspose.com/temporary-license/)取得臨時授權。

### Q: 我可以在哪裡購買 Aspose.Tasks for Java？
A: 您可於[此處](https://purchase.aspose.com/buy)購買 Aspose.Tasks for Java。

**最後更新：** 2026-02-28  
**測試環境：** Aspose.Tasks for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}