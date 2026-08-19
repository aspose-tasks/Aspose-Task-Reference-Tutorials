---
date: 2026-02-26
description: 學習如何使用 Aspose.Tasks for Java 拆分任務完成日期並管理專案時間表。本指南展示如何有效地拆分任務。
linktitle: Split Task Finish Date in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 管理專案時間表 – 在 Aspose.Tasks 中拆分任務完成日期
url: /zh-hant/java/task-properties/split-task-finish-date/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中拆分任務完成日期

## 簡介
有效地 **管理專案時間表** 是成功交付專案的基石。當任務的持續時間變更時，必須重新計算其完成日期以保持排程的準確性。在本教學中，我們將示範如何使用 Aspose.Tasks for Java **拆分任務** 完成日期，讓您精確掌控專案的時間線。

## 快速解答
- **拆分任務完成日期有什麼作用？** 它讓您能夠計算任意持續時間的結束日期，協助即時調整排程。  
- **需要哪個函式庫？** Aspose.Tasks for Java（可從官方網站下載）。  
- **開發時需要授權嗎？** 測試可使用臨時授權，正式環境需購買完整授權。  
- **可以與任何專案行事曆一起使用嗎？** 可以，API 會使用專案的行事曆來遵循工作日與假日。  
- **需要多少行程式碼？** 少於十行即可取得任意持續時間的完成日期。

## 在 Aspose.Tasks 中，「管理專案時間表」是什麼意思？
管理專案時間表是指確保每個任務的開始與完成日期與整體排程同步，並考量行事曆、資源與任務相依性。精確的完成日期計算對於實際的預測與利害關係人的信心至關重要。

## 為什麼要拆分任務的完成日期？
- **彈性：** 快速了解不同工時分配對交付的影響。  
- **風險評估：** 在不更改原始計畫的情況下評估「假設」情境。  
- **資源規劃：** 使任務持續時間與團隊容量及行事曆限制相匹配。

## 先決條件
在開始之前，請確保您具備以下條件：
- 具備 Java 程式設計的基礎知識。  
- 已安裝 Aspose.Tasks for Java 函式庫。您可在[此處](https://releases.aspose.com/tasks/java/)下載。  
- 已設置 Java 開發環境。

## 匯入套件
首先在您的 Java 專案中加入必要的套件：

```java
import com.aspose.tasks.*;
```

## 步驟 1：尋找要拆分的任務
在專案中定位您想要拆分的任務：

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Read project
String projectName = dataDir + "SplitTask.mpp";
Project project = new Project(projectName);
Task splitTask = project.getRootTask().getChildren().getByUid(1);
```

## 步驟 2：取得專案行事曆
取得專案行事曆以進行精確的日期計算：

```java
Calendar calendar = project.get(Prj.CALENDAR);
```

## 步驟 3：以不同持續時間計算任務完成日期
現在，針對不同的持續時間計算任務的完成日期。

### 步驟 3.1：持續時間 8 小時
```java
System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 8 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 8d));
```

*將上述程式碼重複使用於不同持續時間，依需求調整小時數，以觀察每次變更對完成日期的影響。*

## 常見問題與解決方案
- **行事曆參考錯誤：** 請確保取得專案的行事曆 (`project.get(Prj.CALENDAR)`) 而非新建行事曆。  
- **任務 UID 錯誤：** UID 必須對應實際存在的任務，否則 `getByUid` 會回傳 `null`，導致 `NullPointerException`。  
- **時區不匹配：** API 依照行事曆的時區運作；若結果異常，請檢查系統預設時區。

## 結論
精通透過拆分任務完成日期來 **管理專案時間表** 的技巧，對於有效的專案管理至關重要。Aspose.Tasks for Java 簡化了此流程，讓您輕鬆優化排程。

## 常見問答
### Q1：如何下載 Aspose.Tasks for Java？
A1：您可在[此處](https://releases.aspose.com/tasks/java/)下載。

### Q2：在哪裡可以找到 Aspose.Tasks 的文件？
A2：請參考[此處](https://reference.aspose.com/tasks/java/)的文件。

### Q3：如何取得 Aspose.Tasks 的臨時授權？
A3：可在[此處](https://purchase.aspose.com/temporary-license/)取得臨時授權。

### Q4：在哪裡可以取得 Aspose.Tasks 的支援？
A4：請前往[此處](https://forum.aspose.com/c/tasks/15)的支援論壇。

### Q5：可以購買 Aspose.Tasks 嗎？
A5：是的，您可在[此處](https://purchase.aspose.com/buy)購買。

## 其他常見問題

**Q：我可以將此技巧與自訂行事曆一起使用嗎？**  
A：當然可以。只需將 `project.get(Prj.CALENDAR)` 替換為您自訂的 `Calendar` 實例。

**Q：此方法是否會考慮非工作日？**  
A：會，計算完成日期時會套用行事曆的工作時間定義。

**Q：是否有辦法取得小數小時（例如 3.5 小時）的完成日期？**  
A：將 `double` 值（如 `3.5d`）傳入 `getTaskFinishDateFromDuration`；API 會處理小數持續時間。

**Q：如何格式化輸出日期？**  
A：使用 `java.time.format.DateTimeFormatter` 於返回的 `Date` 物件上，即可依您偏好的格式顯示。

---

**最後更新：** 2026-02-26  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}