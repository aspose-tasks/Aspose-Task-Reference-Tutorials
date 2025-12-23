---
date: 2025-12-23
description: 了解如何使用 Aspose.Tasks for Java 更新 MS Project 檔案並重新排程未完成的工作。亦可參閱如何儲存 MS
  Project XML。
linktitle: Update Project and Reschedule Uncompleted Work in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks 更新 MS Project 並重新排程工作
url: /zh-hant/java/project-file-operations/update-project-reschedule-work/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 更新 MS Project 並使用 Aspose.Tasks 重新排程工作

## Introduction
Microsoft Project 是一個廣泛使用的專案管理工具，協助團隊規劃、追蹤並準時交付工作。當排程變更時，您通常需要以程式方式 **更新 MS Project** 檔案——將工作標記為完成、移動剩餘任務，並保持專案基線的準確性。Aspose.Tasks for Java 為您提供乾淨、型別安全的 API，讓您不必開啟 GUI 就能完成這些操作。在本教學中，您將看到如何更新專案、將工作標記為截至特定日期已完成，然後 **如何重新排程仍在等待的 MS Project 工作**。

## Quick Answers
- **「更新 MS Project」是什麼意思？** 它會將任務標記為截至給定日期已完成，並將變更寫回檔案。  
- **我可以自動重新排程剩餘工作嗎？** 可以——使用 `rescheduleUncompletedWorkToStartAfter` 將未完成的任務向前推移。  
- **儲存的檔案格式為何？** 範例將專案儲存為 XML (`SaveFileFormat.Xml`)。  
- **執行程式碼是否需要授權？** 開發階段可使用免費試用版；正式環境需購買商業授權。  
- **需要哪個 Java 版本？** JDK 8 或以上。

## What is “update MS Project” in code?
在程式碼中更新專案是指以程式方式變更任務的日期、工期或完成百分比，並將這些變更寫入檔案。Aspose.Tasks 提供如 `updateProjectWorkAsComplete` 的方法，根據您提供的參考 `Date` 來套用變更。

## Why use Aspose.Tasks for Java to update MS Project?
- **無需 UI 依賴** – 可在大量檔案上自動執行批次變更。  
- **高保真度** – 函式庫保留所有原生 Project 資料（資源、行事曆、自訂欄位）。  
- **跨平台** – 可在 Windows、Linux 或 macOS 上執行相同程式碼。  
- **儲存 MS Project XML** – 您可以將更新後的專案匯出為廣受支援的 XML 格式，以供後續工具使用。

## Prerequisites
1. 已安裝 Java Development Kit (JDK)。  
2. Aspose.Tasks for Java 函式庫 – 可從 [here](https://releases.aspose.com/tasks/java/) 下載。  
3. 具備 Java 語法與物件導向概念的基本認識。

## Import Packages
First, import the necessary Aspose.Tasks classes and Java utilities:

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

## Step 1: Set up the Project
建立一個新的 `Project` 實例，定義幾個範例任務、設定其工期，並建立相依關係。接著將初始狀態儲存，以便觀察前後變化。

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

## Step 2: Update Project Work
將工作標記為截至特定截止日期已完成。這即是 **更新 MS Project** 的核心——API 會自動調整任務進度與日期。

```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
// Save the updated project
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```

## Step 3: Reschedule Uncompleted Work
在標記完成的工作之後，通常需要將剩餘任務向前推移。以下呼叫會將所有未完成的工作移至同一截止日期之後開始，實際上說明了 **如何重新排程 MS Project**。

```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
// Save the rescheduled project
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## Common Issues and Solutions
| 問題 | 原因 | 解決方法 |
|-------|--------|-----|
| 任務未顯示更新的日期 | 專案以不同格式（例如 `.mpp`）儲存 | 使用 `SaveFileFormat.Xml` 以保留 XML 結構。 |
| `updateProjectWorkAsComplete` 看似未執行任何操作 | 參考日期早於專案開始日期 | 確保 `Calendar` 日期位於專案時間軸內。 |
| 重新排程的任務重疊 | 未套用行事曆或資源平衡 | 套用 `Project` 行事曆，或在重新排程後手動使用 `Task.setStart`。 |

## Frequently Asked Questions (Extended)

**Q: Aspose.Tasks for Java 能處理複雜的專案結構嗎？**  
A: 可以，Aspose.Tasks for Java 提供強大的 API，能有效管理任務、相依關係、資源及其他專案元素。

**Q: 是否有 Aspose.Tasks for Java 的試用版可供下載？**  
A: 有，您可從 [here](https://releases.aspose.com/) 取得免費試用版。

**Q: 如何取得 Aspose.Tasks for Java 的支援？**  
A: 您可前往 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 尋求協助或提問。

**Q: 是否可以購買 Aspose.Tasks for Java 的臨時授權？**  
A: 可以，臨時授權可於 [here](https://purchase.aspose.com/temporary-license/) 購買。

**Q: 在哪裡可以找到 Aspose.Tasks for Java 的詳細文件？**  
A: 您可參考文件 [here](https://reference.aspose.com/tasks/java/) 取得完整指南與 API 參考。

## Conclusion
在本教學中，我們完整示範了 **更新 MS Project** 檔案、將工作標記為完成，並說明 **如何重新排程 MS Project** 中仍未完成的任務的整個流程。將專案儲存為 XML 可保留與其他工具的相容性，並留下清晰的變更稽核紀錄。您可使用這些模式在大型專案組合中自動調整排程、整合至 CI 流程，或建立自訂報表儀表板。

---

**最後更新：** 2025-12-23  
**測試環境：** Aspose.Tasks for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}