---
date: 2026-03-29
description: 了解如何使用 Aspose.Tasks for Java 重新排程未完成的工作、更新專案工作，並將 MS Project 檔案另存為 XML。
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 重新排程未完成的工作並使用 Aspose.Tasks 更新 MS Project 檔案
url: /zh-hant/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 重新排程未完成工作並使用 Aspose.Tasks 更新 MS Project 檔案

## 簡介
Microsoft Project 是一款廣泛使用的專案管理工具，可協助團隊規劃任務、分配資源與追蹤時間表。Aspose.Tasks for Java 為開發人員提供功能豐富的 API，以程式方式操作 Microsoft Project 檔案。在本教學中，您將學習如何 **更新專案工作**、**重新排程未完成工作**，以及使用 Aspose.Tasks for Java 以 XML 格式 **儲存 MS Project 檔案**。

## 快速解答
- **「重新排程未完成工作」是什麼意思？** 它會將任何剩餘的任務工作移至選定日期之後開始，已完成的部分保持不變。  
- **哪個方法可將工作標記為完成？** `project.updateProjectWorkAsComplete(date, false)`。  
- **如何保存變更？** 使用 `project.save(<path>, SaveFileFormat.Xml)`。  
- **生產環境是否需要授權？** 是的，商業使用必須擁有有效的 Aspose.Tasks 授權。  
- **支援哪個 Java 版本？** 完全支援 Java 8 及更高版本。

## 什麼是「重新排程未完成工作」？
重新排程未完成工作會調整所有尚未完成任務的開始日期，將它們推遲至指定的截止日期之後開始。當專案時間表因延遲或範圍變更而需要調整時，這非常有用。

## 為何使用 Aspose.Tasks 來更新專案工作與重新排程任務？
- **細緻的控制：** 直接設定工作完成百分比與日期。  
- **不需 UI：** 可自動化大量更新多個專案檔案。  
- **跨平台：** 可在任何執行 Java 的系統上運作。  
- **保持資料完整性：** 所有相依性、限制條件與資源皆保持一致。

## 先決條件
在開始之前，請確保您具備以下條件：
1. 已在系統上安裝 Java Development Kit (JDK)。  
2. Aspose.Tasks for Java 程式庫。您可從 [here](https://releases.aspose.com/tasks/java/) 下載。  
3. 具備 Java 程式語言的基本了解。

## 匯入套件
首先，在您的 Java 程式碼中匯入必要的套件：
```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## 步驟 1：設定專案
初始化一個新的 `Project` 物件，定義任務、設定持續時間並建立相依性。這會建立我們稍後將更新與重新排程的基線專案。
```java
String dataDir = "Your Data Directory";
Project project = new Project();
// Define tasks and their durations
// ...
// Define task dependencies
// ...
// Save the initial project state
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```

## 步驟 2：更新專案工作
將工作標記為在特定日期之前已完成。此步驟示範 **更新專案工作** 操作，通常是重新排程之前的第一個動作。
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## 步驟 3：重新排程未完成工作
現在，我們將任何剩餘（未完成）的工作移至相同截止日期之後開始。這就是核心的 **重新排程未完成工作** 功能。
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## 結論
在本教學中，我們說明了如何使用 Aspose.Tasks for Java **更新專案工作**、**重新排程未完成工作**，以及 **以 XML 格式儲存 MS Project 檔案**。當需要根據實際進度或變更的業務優先順序調整專案時間表時，這些功能相當重要。

## 常見問題
### Q：Aspose.Tasks for Java 能處理複雜的專案結構嗎？
A：是的，Aspose.Tasks for Java 提供強大的 API，能有效管理任務、相依性、資源及其他專案元素。

### Q：Aspose.Tasks for Java 有提供試用版嗎？
A：是的，您可從 [here](https://releases.aspose.com/) 取得免費試用版。

### Q：如何取得 Aspose.Tasks for Java 的支援？
A：您可前往 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 取得協助或詢問問題。

### Q：我可以購買 Aspose.Tasks for Java 的臨時授權嗎？
A：是的，臨時授權可於 [here](https://purchase.aspose.com/temporary-license/) 購買。

### Q：在哪裡可以找到 Aspose.Tasks for Java 的詳細文件？
A：您可參考文件 [here](https://reference.aspose.com/tasks/java/) 取得完整指南與 API 參考。

## 其他常見問題

**Q：如何確保儲存的檔案相容於較舊版本的 Microsoft Project？**  
A：使用 `SaveFileFormat.Xml` 儲存專案；XML 在各版本的 Project 中廣泛支援。

**Q：我可以只重新排程部分任務而非整個專案嗎？**  
A：可以，您可以遍歷特定任務，並在計算新開始日期後呼叫 `task.setStart(date)`。

**Q：重新排程未完成工作時，資源分配會發生什麼變化？**  
A：資源指派會自動調整以符合新的任務開始日期，保持分配邏輯。

**Q：是否能以程式方式撤銷重新排程操作？**  
A：您可以重新載入原始專案檔（或備份）以還原變更。

**Q：Aspose.Tasks 是否支援儲存為其他格式，例如 .mpp？**  
A：當然。使用 `SaveFileFormat.MPP` 可儲存為原生 Microsoft Project 格式。

---

**Last Updated:** 2026-03-29  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}