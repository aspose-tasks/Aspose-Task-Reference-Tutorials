---
date: 2026-03-03
description: 學習如何在 Aspose.Tasks for Java 中重新編號 WBS，管理工作分解結構，並透過逐步範例高效自訂 WBS 代碼。
linktitle: WBS Associated with Task in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何在 Aspose.Tasks for Java 中重新編號 WBS
url: /zh-hant/java/task-properties/wbs-associated-with-task/
weight: 36
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks for Java 中重新編號 WBS

## 簡介
如果您需要使用 Aspose.Tasks for Java 在 Microsoft Project 檔案中 **how to renumber WBS**，您來對地方了。本教學將帶您閱讀現有的 WBS 代碼、進行自訂，然後重新編號層級，使您的專案保持有序。無論是清理舊有排程或是從頭建立新排程，掌握這些步驟都能讓您自信地 **manage work breakdown** 結構。

## 快速解答
- **What does renumbering WBS do?** 它會重新計算任務的階層編號，以反映任何結構變更。  
- **Which class performs the renumbering?** `Project.renumberWBSCode`.  
- **Do I need a license to run the code?** 在正式環境使用時，需要有效的 Aspose.Tasks 授權。  
- **Can I customize the WBS format?** 是——使用 `Task.set(Tsk.WBS, "...")` 來指派任意字串。  
- **What are the main prerequisites?** Java JDK、Aspose.Tasks for Java 程式庫，以及有效的專案檔 (.mpp)。

## 什麼是工作分解結構 (WBS)？
工作分解結構 (WBS) 是專案交付成果與任務的階層式表示。每個任務都會收到一個代碼（例如 1.2.3），以反映其在階層中的位置。當任務被新增、刪除或重新排序時，重新編號變得必須，以確保代碼保持合乎邏輯且易於閱讀。

## 為什麼要管理工作分解並自訂 WBS 代碼？
- **Clarity:** 清晰的 WBS 代碼讓利害關係人容易找到任務。  
- **Reporting:** 許多報表工具依賴一致的編號。  
- **Flexibility:** 自訂代碼讓您能將專案結構與內部標準對齊。  

## 前置條件
在深入程式碼之前，請確認您已具備以下項目：

- 已在機器上安裝 Java Development Kit (JDK)。  
- 已將 Aspose.Tasks for Java 程式庫加入您的專案。您可以從 [here](https://releases.aspose.com/tasks/java/) 取得。

## 匯入套件
確保匯入必要的套件以啟動您的專案：

```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.ArrayList;
import java.util.List;
```

## 讀取 WBS 代碼
首先，我們將讀取現有的 WBS 代碼，讓您了解正在處理的內容。

### 步驟 1：載入專案
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```

### 步驟 2：收集任務
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```

### 步驟 3：解析與自訂
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```

上述程式碼片段會列印每個任務目前的 WBS 與層級，然後示範透過指派新字串來 **customize wbs codes**。

## 重新編號任務 WBS 代碼
現在讓我們實際重新編號 WBS 階層。

### 步驟 1：載入專案（重新編號範例）
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```

### 步驟 2：選取所有任務
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```

### 步驟 3：輸出初始 WBS 代碼
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

### 步驟 4：重新編號 WBS 代碼
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```

### 步驟 5：輸出更新後的 WBS 代碼
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```

依照這些步驟，您即可有效地 **how to renumber wbs** 任意專案檔中的任務集合。

## 常見問題與解決方案
- **WBS not changing after `set` call:** 請確保您使用的是正確的任務實例，且在修改後已儲存專案。  
- **`renumberWBSCode` throws an exception:** 請確認 ID 清單與最高層任務的數量相符；否則此方法無法正確對應新編號。  
- **Missing WBS values:** 某些任務可能因從未定義 WBS 的檔案匯入而為 `null`。在列印前請使用備用值。

## 常見問與答

**Q: 我可以在哪裡找到 Aspose.Tasks for Java 的文件？**  
A: 文件可於 [here](https://reference.aspose.com/tasks/java/) 取得。

**Q: 我該如何下載 Aspose.Tasks for Java？**  
A: 您可以從 [here](https://releases.aspose.com/tasks/java/) 下載。

**Q: 是否提供 Aspose.Tasks for Java 的免費試用？**  
A: 是的，您可在 [here](https://releases.aspose.com/) 獲得免費試用。

**Q: 我可以從哪裡取得 Aspose.Tasks for Java 的支援？**  
A: 請前往 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 取得支援。

**Q: 我可以取得 Aspose.Tasks for Java 的臨時授權嗎？**  
A: 可以，請至 [here](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

**Q: 重新編號後，我可以重新命名 WBS 格式嗎？**  
A: 當然可以。呼叫 `renumberWBSCode` 後，您可以遍歷任務並使用 `task.set(Tsk.WBS, "NewFormat-" + task.get(Tsk.WBS))` 來符合您的命名慣例。

**Q: 重新編號會影響任務相依性嗎？**  
A: 不會。此方法僅更新 WBS 字串；任務連結與限制保持不變。

---

**最後更新：** 2026-03-03  
**測試環境：** Aspose.Tasks for Java 24.12 (latest)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}