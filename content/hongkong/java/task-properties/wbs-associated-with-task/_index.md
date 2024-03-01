---
title: 與 Aspose.Tasks 中的任務關聯的 WBS
linktitle: 與 Aspose.Tasks 中的任務關聯的 WBS
second_title: Aspose.Tasks Java API
description: 使用 Aspose.Tasks for Java 掌握 WBS - 學習讀取和重新編號任務 WBS 程式碼。提升專案管理效率！
type: docs
weight: 36
url: /zh-hant/java/task-properties/wbs-associated-with-task/
---
## 介紹
歡迎來到 Aspose.Tasks for Java 的專案管理世界！在本教程中，我們將深入研究與使用 Aspose.Tasks for Java 的任務相關的工作分解結構 (WBS) 的複雜性。無論您是經驗豐富的開發人員還是新手，本指南都將協助您了解有效管理 WBS 程式碼的要點。
## 先決條件
在我們深入學習本教程之前，請確保您具備以下先決條件：
- 您的電腦上安裝了 Java 開發工具包 (JDK)。
-  Aspose.Tasks for Java 程式庫下載並新增到您的專案中。你可以從[這裡](https://releases.aspose.com/tasks/java/).
## 導入包
確保導入必要的套件來啟動您的專案：
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
讓我們先閱讀與任務相關的 WBS 代碼。按著這些次序：
## 第 1 步：載入項目
```java
Project project = new Project("Your Document Directory" + "input.mpp");
```
## 第二步：收集任務
```java
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## 第 3 步：解析與定制
```java
for (Task tsk : collector.getTasks()) {
    System.out.println(tsk.get(Tsk.WBS));
    System.out.println(tsk.get(Tsk.WBS_LEVEL));
    tsk.set(Tsk.WBS, "custom wbs");
}
```
此程式碼片段讀取並自訂與專案中的任務關聯的 WBS 程式碼。
## 重新編號任務 WBS 代碼
現在，讓我們探討如何將任務的 WBS 代碼重新編號：
## 第 1 步：載入項目
```java
Project project = new Project("Your Document Directory" + "RenumberExample.mpp");
```
## 第 2 步：選擇所有任務
```java
List<Task> tasks = (List<Task>) project.getRootTask().selectAllChildTasks();
```
## 步驟3：輸出初始WBS程式碼
```java
System.out.println("WBS codes before: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
## 步驟 4：重新編號 WBS 代碼
```java
List<Integer> listIds = new ArrayList<>();
listIds.add(1);
listIds.add(2);
listIds.add(3);
project.renumberWBSCode(listIds);
```
## 步驟 5：輸出更新的 WBS 程式碼
```java
System.out.println("\nWBS codes after: ");
for (Task task : tasks) {
    System.out.println("\"" + task.get(Tsk.WBS) + "\"" + "; ");
}
```
透過執行這些步驟，您將有效地為專案中的任務重新編號 WBS 代碼。
## 結論
恭喜！您已經成功學習如何使用 Aspose.Tasks for Java 來處理 WBS 程式碼。這些知識將使您能夠有效地管理和自訂專案的任務層次結構。
## 常見問題解答
### Q：在哪裡可以找到 Aspose.Tasks for Java 的文檔？
答：文檔已提供[這裡](https://reference.aspose.com/tasks/java/).
### Q：如何下載 Aspose.Tasks for Java？
答： 你可以下載[這裡](https://releases.aspose.com/tasks/java/).
### Q：Aspose.Tasks for Java 是否有免費試用版？
答：是的，您可以免費試用[這裡](https://releases.aspose.com/).
### Q：在哪裡可以獲得 Aspose.Tasks for Java 的支援？
答：訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)為了支持。
### Q：我可以取得 Aspose.Tasks for Java 的臨時授權嗎？
答：是的，獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).