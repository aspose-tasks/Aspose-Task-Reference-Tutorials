---
date: 2026-02-28
description: 學習如何使用 Aspose.Tasks for Java 取得以分鐘、天、小時、週及月為單位的持續時間。提供詳細指南與程式碼範例。
linktitle: Task Duration in Different Units with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks 取得不同單位的持續時間
url: /zh-hant/java/task-properties/task-duration-different-units/
weight: 32
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何以不同單位取得持續時間（Aspose.Tasks）

## 介紹
了解 **how to get duration** 對於任何專案管理工作流程都是核心部分。無論您需要以分鐘進行精細追蹤，或以月份進行高層規劃，Aspose.Tasks for Java 都能讓轉換變得簡單。在本教學中，我們將逐步說明如何取得任務的持續時間（分鐘、天、時、週、月），並解釋在實務專案中每個單位的使用情境。

## 快速解答
- **“how to get duration”是什麼意思？** 這是取得任務時間跨度並將其轉換為所需單位的過程。  
- **哪個 API 方法執行轉換？** `Task.get(Tsk.DURATION).convert(TimeUnitType.<Unit>)`.  
- **執行程式碼是否需要授權？** 免費試用可用於測試；正式環境需購買商業授權。  
- **可以轉換為自訂單位嗎？** 您可以串接轉換或使用 `TimeSpan` 進行自訂計算。  
- **程式碼是否相容於 Java 17？** 是的，Aspose.Tasks 支援 Java 8 及更新版本。

## 什麼是 Aspose.Tasks 中的 “how to get duration”？
Aspose.Tasks 會將任務的長度儲存為 `Duration` 物件。透過呼叫 `convert` 方法並指定 `TimeUnitType`（Minute、Hour、Day、Week、Month），即可取得相同的基礎值，以所需單位表示。此彈性讓您能產生報表、執行計算，或將資料輸入其他系統，而無需手動計算。

## 為什麼使用 Aspose.Tasks 進行持續時間轉換？
- **Accuracy:** 自動處理行事曆例外、工作時間與非標準行事曆。  
- **Performance:** 單行轉換避免迴圈或自訂解析。  
- **Portability:** 在 Windows、Linux 與 macOS 環境中皆表現相同。  
- **Integration:** 無縫整合至已使用 Aspose.Tasks 的現有 Java 應用程式。

## 前置條件
在開始編寫程式碼之前，請確保您已具備以下條件：

- 已安裝 Java Development Kit (JDK)
- Aspose.Tasks for Java 程式庫。您可於 [此處](https://releases.aspose.com/tasks/java/) 下載
- 具備 Java 程式設計的基本概念

## 匯入套件
在您的 Java 專案中，加入 Aspose.Tasks 程式庫。於程式碼開頭加入以下匯入語句：

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```

## 步驟 1：設定專案
在您喜愛的 IDE（IntelliJ、Eclipse、VS Code 等）中建立新的 Java 專案，並將 Aspose.Tasks JAR 加入專案的 classpath。這可確保上述類別在編譯時可用。

## 步驟 2：讀取專案範本
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Read MS Project template file
String fileName = dataDir + "project.xml";
// Read the input file as Project
Project project = new Project(fileName);
```

將 `"Your Document Directory"` 替換為實際存放 `.xml` 或 `.mpp` 專案檔的資料夾路徑。

## 步驟 3：取得任務
```java
// Get a task to calculate its duration in different formats
Task task = project.getRootTask().getChildren().getById(1);
```

`getById(1)` 會取得 ID 為 1 的任務。請依需要調整 ID，以取得檔案中其他任務。

## 步驟 4：以分鐘為單位的持續時間 – 如何取得分鐘單位的持續時間？
```java
// Get the duration in Minutes
double mins = task.get(Tsk.DURATION).convert(TimeUnitType.Minute).toDouble();
```

`mins` 變數現在保存以分鐘表示的任務長度。

## 步驟 5：以天為單位的持續時間 – 如何取得天單位的持續時間？
```java
// Get the duration in Days
double days = task.get(Tsk.DURATION).convert(TimeUnitType.Day).toDouble();
```

當您在報告或資源分配上需要以天為粒度時，請使用此值。

## 步驟 6：以小時為單位的持續時間 – 如何取得小時單位的持續時間？
```java
// Get the duration in Hours
double hours = task.get(Tsk.DURATION).convert(TimeUnitType.Hour).toDouble();
```

小時單位適用於工時表，或在您想將一天拆分為工作班次時使用。

## 步驟 7：以週為單位的持續時間 – 如何取得週單位的持續時間？
```java
// Get the duration in Weeks
double weeks = task.get(Tsk.DURATION).convert(TimeUnitType.Week).toDouble();
```

週單位常用於高階甘特圖或里程碑規劃。

## 步驟 8：以月為單位的持續時間 – 如何取得月單位的持續時間？
```java
// Get the duration in Months
double months = task.get(Tsk.DURATION).convert(TimeUnitType.Month).toDouble();
```

月單位的持續時間有助於將專案階段與財務期間對齊。

## 常見問題與解決方案
| 症狀 | 可能原因 | 解決方法 |
|---------|--------------|-----|
| `task` 上的 `NullPointerException` | 任務 ID 錯誤或缺少子項目 | 使用 `project.getRootTask().getChildren()` 確認任務 ID 是否存在 |
| 非預期值（例如 0） | 專案使用包含非工作日的自訂行事曆 | 確保專案的行事曆正確定義，或使用 `project.getCalendar()` 進行檢查 |
| 轉換結果為小數週 | 週的計算依據專案預設的週長（通常為 5 天） | 若需日曆週，請乘以 5，或調整行事曆設定 |

## 常見問與答
### Q: 我可以在任何 Java IDE 中使用 Aspose.Tasks for Java 嗎？
A: 可以，Aspose.Tasks for Java 相容於任何 Java 整合開發環境 (IDE)。

### Q: 如何取得 Microsoft Project 檔案中任務的 ID？
A: 您可以手動檢視專案檔，或呼叫 `project.getRootTask().getChildren()` 並遍歷集合以讀取每個任務的 `ID`。

### Q: Aspose.Tasks 適合處理大型專案嗎？
A: 絕對適合。Aspose.Tasks 專為有效處理包含數千個任務與資源的專案而設計。

### Q: 我可以在哪裡找到更多文件？
A: 請前往 [文件](https://reference.aspose.com/tasks/java/) 取得完整的 API 參考、程式碼範例與最佳實踐指南。

### Q: 我可以在購買前試用 Aspose.Tasks for Java 嗎？
A: 可以，您可透過 [免費試用](https://releases.aspose.com/) 來評估其功能。

---

**Last Updated:** 2026-02-28  
**Tested With:** Aspose.Tasks for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}