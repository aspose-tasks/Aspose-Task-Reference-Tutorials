---
date: 2026-02-20
description: 探索如何使用 Aspose.Tasks for Java 向專案新增任務並管理工期。了解如何設定工期以及如何輕鬆轉換工期。
linktitle: Manage Durations of Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 將工作新增至專案並使用 Aspose.Tasks 管理工期
url: /zh-hant/java/task-properties/manage-durations/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 新增任務至專案並使用 Aspose.Tasks 管理工期

## 介紹
在本教學中，您將學習 **如何將任務新增至專案**，以及使用 Aspose.Tasks for Java 來控制其工期。無論您是建立全新的專案規劃工具，或是擴充現有解決方案，掌握任務工期的處理對於精確排程與報告皆相當重要。

## 快速解答
- **「將任務新增至專案」是什麼意思？** 它會在專案的根節點或特定的彙總任務下建立一個新的任務物件。  
- **哪個類別代表工期？** `com.aspose.tasks.Duration`。  
- **如何設定工期？** 使用 `task.set(Tsk.DURATION, project.getDuration(value, TimeUnitType))`。  
- **我可以將工期轉換成其他單位嗎？** 可以，呼叫 `duration.convert(TimeUnitType.Hour)` 或其他任意的 `TimeUnitType`。  
- **正式環境需要授權嗎？** 商業使用需具備有效的 Aspose.Tasks 授權。

## 什麼是「將任務新增至專案」？
將任務新增至專案表示建立一個 `Task` 物件，並將其附加到專案的任務階層中。此操作是您之後才能為該任務定義工作、資源或工期的第一步。

## 為何要管理任務工期？
精確的工期能驅動實際的時間表、資源配置與關鍵路徑分析。使用 Aspose.Tasks，您可以以程式方式設定、讀取、轉換與調整工期，全面掌控專案排程。

## 前置條件
在開始之前，請確保您具備以下條件：

- Java Development Kit (JDK)：確保您的機器已安裝 Java。您可以在[此處](https://www.oracle.com/java/technologies/javase-downloads.html)下載。  
- Aspose.Tasks 程式庫：下載並將 Aspose.Tasks 程式庫加入您的專案。您可以在[此處](https://releases.aspose.com/tasks/java/)取得。

## 匯入套件
在您的 Java 專案中，匯入使用 Aspose.Tasks 所需的套件：
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## 步驟 1：設定您的專案
```java
// Create a new project
Project project = new Project();
```

## 步驟 2：新增任務（將任務新增至專案）
```java
// Add a new task to the project
Task task = project.getRootTask().getChildren().add("Task");
```

## 如何設定工期
現在任務已存在，您可以定義其長度。預設情況下，工期以天為單位表示。

## 步驟 3：取得並轉換任務工期
```java
// Get task duration in days (default time unit)
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
// Convert duration to hours time unit
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```

## 如何轉換工期
`convert` 方法讓您將 `Duration` 從一個 `TimeUnitType` 轉換為另一個（例如，天 → 小時，週 → 天）。

## 步驟 4：將任務工期更新為 1 週
```java
// Increase task duration to 1 week
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```

## 步驟 5：縮短任務工期
```java
// Decrease task duration
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```

透過上述步驟，您已成功 **將任務新增至專案**，並使用 Aspose.Tasks for Java 管理其工期。

## 常見陷阱與技巧
- **陷阱：** 在進行算術運算前忘記先轉換工期，可能導致結果不正確。請務必使用 `duration.getTimeUnit()` 來確認單位。  
- **技巧：** 使用 `project.getDuration(value, TimeUnitType)` 直接建立所需單位的工期，而非之後再轉換。  
- **陷阱：** 設定負值工期會拋出例外。請務必驗證輸入值。

## 結論
本指南說明了如何 **將任務新增至專案**、讀取其預設工期、**設定工期**，以及 **將工期轉換** 為不同的時間單位。您現在可以將這些技巧整合到更大型的排程應用程式中，以實現精確的專案規劃。

## 常見問答
### Aspose.Tasks 是否相容所有 Java 版本？
Aspose.Tasks 相容於 Java 6 及之後的版本。

### 我可以在商業專案中使用 Aspose.Tasks 嗎？
可以，您可於個人或商業專案中使用 Aspose.Tasks。請前往[此處](https://purchase.aspose.com/buy)了解授權細節。

### 我可以在哪裡取得更多支援與資源？
請造訪 [Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15) 取得社群支援與討論。

### 如何取得測試用的臨時授權？
您可在[此處](https://purchase.aspose.com/temporary-license/)取得測試與評估用的臨時授權。

### 是否提供 Aspose.Tasks 的免費試用？
可以，您可於[此處](https://releases.aspose.com/)取得免費試用，先行體驗 Aspose.Tasks 後再決定是否購買。

## 常見問題

**Q: 如何在已設定工期後變更任務的工期？**  
A: 先使用 `task.get(Tsk.DURATION)` 取得目前的工期，進行修改（例如 `add`、`subtract` 或 `convert`），再以 `task.set(Tsk.DURATION, newDuration)` 設回。

**Q: 我可以以分鐘為單位設定工期嗎？**  
A: 可以，呼叫 `project.getDuration(value, TimeUnitType.Minute)` 時使用 `TimeUnitType.Minute`。

**Q: 變更工期是否會自動更新任務的開始與結束日期？**  
A: 只有在專案的排程模式設定為自動時才會自動更新。否則，您可能需要使用 `project.calculateCriticalPath()` 重新計算排程。

**Q: 是否可以將工期以原始數值取得？**  
A: 呼叫 `duration.getTimeSpan()` 可取得目前時間單位下的數值。

**Q: 若我減去的時間超過目前工期會發生什麼事？**  
A: API 會拋出 `ArgumentOutOfRangeException`。請務必驗證結果工期仍為正值。

---

**Last Updated:** 2026-02-20  
**Tested With:** Aspose.Tasks for Java (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}