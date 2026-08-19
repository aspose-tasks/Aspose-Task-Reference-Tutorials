---
date: 2026-02-26
description: 學習如何在 Aspose.Tasks for Java 中恢復任務和停止任務，包括按日期篩選任務，以實現精確的項目控制。
linktitle: How to Resume Task and Stop Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何在 Aspose.Tasks 中恢復任務與停止任務
url: /zh-hant/java/task-properties/stop-resume-task/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中恢復任務與停止任務

## 介紹
如果您正在構建基於 Java 的專案管理解決方案，常會需要 **暫停** 任務，之後再 **繼續**。Aspose.Tasks for Java 內建停止與恢復任務的屬性，讓這件事變得簡單。在本教學中，您將學會 **如何程式化地恢復任務** 以及 **如何程式化地停止任務**，同時也會看到 **如何依日期篩選任務**，只處理排程中相關的項目。

## 快速回答
- **「停止」任務是什麼意思？** 會設定停止日期，之後的工作將暫停。  
- **如何恢復已停止的任務？** 為任務指定一個晚於停止日期的恢復日期即可。  
- **可以限制操作的日期範圍嗎？** 可以——使用最小日期來篩選任務。  
- **需要哪個版本的函式庫？** 任意近期的 Aspose.Tasks for Java 版本（API 穩定）。  
- **開發時需要授權嗎？** 測試可使用免費試用版，正式環境需購買授權。

## 什麼是 Aspose.Tasks 中的「如何恢復任務」？
恢復任務即在 `Task` 物件上提供 **RESUME** 日期。當專案引擎計算排程時，工作會從該日期起繼續。這在資源不可用或外部依賴中斷時特別有用。

## 為什麼要使用停止/恢復功能？
- **掌控時間線**：在不刪除任務的情況下暫停工作。  
- **報表更精確**：在甘特圖中顯示真實的開始/結束日期。  
- **自動化便利**：結合日期篩選一次更新多筆任務。

## 前置條件
在開始之前，請確保您已具備：

- 扎實的 Java 基礎。  
- 已在電腦上安裝 JDK。  
- 已將 Aspose.Tasks for Java 函式庫加入專案（可從 [here](https://releases.aspose.com/tasks/java/) 下載）。

## 匯入套件
首先，將需要的類別匯入，以便操作專案與任務。

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
import java.util.GregorianCalendar;
```

## 步驟 1：初始化 Project 與 Collector
建立指向 MPP 檔案的 `Project` 實例，並設定 `ChildTasksCollector` 以收集層級中的所有任務。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "Software Development.mpp");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

## 步驟 2：定義最小日期以作篩選
若只想處理具有實際停止或恢復日期的任務，請定義一個 **最小日期**。這是 *依日期篩選任務* 技巧的核心。

```java
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
```

## 步驟 3：遍歷、檢查並顯示停止/恢復值
現在遍歷收集到的任務，套用 **如何停止任務** 的邏輯，並印出日期。程式碼同時示範了透過讀取 `RESUME` 屬性 **如何恢復任務**。

```java
for (Task tsk : collector.getTasks()) {
    if (tsk.get(Tsk.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.STOP).toString());
    }
    if (tsk.get(Tsk.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(tsk.get(Tsk.RESUME).toString());
    }
}
```

> **專業提示：** 將 `System.out.println` 呼叫換成您自己的邏輯（例如更新日期、寫入檔案日誌，或修改任務物件），即可真正 *停止* 或 *恢復* 任務。

## 常見問題與解決方案
| 問題 | 原因 | 解決方式 |
|------|------|----------|
| `NullPointerException` 發生在 `tsk.get(Tsk.STOP)` | 任務未設定停止日期。 | 在呼叫 `.before(minDate)` 前先檢查是否為 `null`。 |
| 設定後日期仍顯示為 `NA` | 最小日期設定過近。 | 使用較早的 `minDate` 或移除篩選條件。 |
| 儲存的 MPP 檔未反映變更 | 修改後未儲存專案。 | 在更新任務後呼叫 `project.save("output.mpp");`。 |

## 常見問答

### Aspose.Tasks for Java 適合大型專案嗎？
絕對適合！Aspose.Tasks for Java 設計能處理不同規模的專案，保證效能與可靠性。

### 我可以自訂停止與恢復任務的日期嗎？
可以，範例中提供的方式允許您依專案需求彈性設定最小日期。

### 哪裡可以取得 Aspose.Tasks for Java 的其他支援？
請前往 [Aspose.Tasks Forum](https://forum.aspose.com/c/tasks/15) 取得社群支援與討論。

### 有提供 Aspose.Tasks for Java 的免費試用嗎？
有，您可透過 [free trial](https://releases.aspose.com/) 先行體驗功能，再決定是否購買。

### 如何取得 Aspose.Tasks for Java 的臨時授權？
您可在此處取得臨時授權 [here](https://purchase.aspose.com/temporary-license/) 以供測試使用。

**其他問答**

**Q: 如何為任務設定新的停止日期？**  
A: 使用 `tsk.set(Tsk.STOP, new Date(...));`，之後儲存專案。

**Q: 能否以特定範圍而非僅最小日期來篩選任務？**  
A: 可以——同時比較 `before` 與 `after` 以符合您的起始與結束日期。

**Q: 更改停止/恢復日期後 API 會自動重新計算排程嗎？**  
A: 更改日期後，呼叫 `project.calculateCriticalPath();` 以重新整理排程。

## 結論
本指南說明了如何使用 Aspose.Tasks for Java **恢復任務** 與 **停止任務**，並提供了 **依日期篩選任務** 的實用方法。將這些程式碼片段整合到您的應用程式，即可精細掌控專案時間線，並自動化排程調整，提升開發效率與可靠性。

---

**最後更新：** 2026-02-26  
**測試環境：** Aspose.Tasks for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}