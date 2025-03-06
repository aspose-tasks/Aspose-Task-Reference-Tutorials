---
title: 掌握Aspose.Tasks中的任務屬性
linktitle: 在 Aspose.Tasks 中讀取和寫入任務的常規屬性
second_title: Aspose.Tasks Java API
description: 探索 Aspose.Tasks for Java 在輕鬆管理任務屬性方面的強大功能。使用我們的逐步指南輕鬆閱讀和寫作。
weight: 26
url: /zh-hant/java/task-properties/read-write-general-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 掌握Aspose.Tasks中的任務屬性

## 介紹
使用 Aspose.Tasks 釋放 Java 任務管理的全部潛力。在本綜合指南中，我們將深入研究使用 Aspose.Tasks for Java 讀取和寫入任務的一般屬性。無論您是經驗豐富的開發人員還是初學者，本教學都將為您提供輕鬆操作任務屬性的技能。
## 先決條件
在我們深入學習本教程之前，請確保您具備以下先決條件：
- 您的系統上安裝了 Java 開發工具包 (JDK)。
- 下載並設定了 Aspose.Tasks for Java 函式庫。你可以找到下載鏈接[這裡](https://releases.aspose.com/tasks/java/).
- 程式碼編輯器，例如 IntelliJ IDEA 或 Eclipse。
## 導入包
首先，在您的 Java 專案中匯入必要的套件。此步驟可確保您可以存取 Aspose.Tasks 功能。這是一個指導您的片段：
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```
## 讀取任務的一般屬性
## 第 1 步：建立任務
首先在您的專案中建立一個任務。這涉及設定任務名稱、開始日期和其他相關詳細資訊。這是一個例子：
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
Project project = new Project();
Task task = project.getRootTask().getChildren().add("Task1");
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2013, Calendar.JULY, 17, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
task.set(Tsk.NAME, "new name");
```
## 第 2 步：讀取任務屬性
現在您已經建立了一個任務，讓我們檢索並顯示其常規屬性。下面的程式碼片段完成了這個任務：
```java
//讀取任務的一般屬性
Project prj = new Project(dataDir + "project.xml");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(prj.getRootTask(), collector, 0);
for (Task tsk : collector.getTasks()) {
    System.out.println("Task Id:" + tsk.get(Tsk.ID));
    System.out.println("Task Uid: " + tsk.get(Tsk.UID));
    System.out.println("Task Name: " + tsk.get(Tsk.NAME));
    System.out.println("Task Start: " + tsk.get(Tsk.START));
    System.out.println("Task Finish: " + tsk.get(Tsk.FINISH));
}
```
## 編寫任務的一般屬性
## 第 3 步：載入專案並建立收集器
若要寫入常規屬性，請載入現有項目並設定`ChildTasksCollector`：
```java
Project prj = new Project(dataDir + "project.xml");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(prj.getRootTask(), collector, 0);
```
## 步驟4：解析並顯示屬性
最後，解析收集到的任務並顯示它們的屬性：
```java
for (Task tsk : collector.getTasks()) {
    System.out.println("Task Id:" + tsk.get(Tsk.ID));
    System.out.println("Task Uid: " + tsk.get(Tsk.UID));
    System.out.println("Task Name: " + tsk.get(Tsk.NAME));
    System.out.println("Task Start: " + tsk.get(Tsk.START));
    System.out.println("Task Finish: " + tsk.get(Tsk.FINISH));
}
```
恭喜！您已使用 Aspose.Tasks for Java 成功讀取和寫入任務的常規屬性。
## 結論
在本教程中，我們探索了使用 Aspose.Tasks for Java 無縫操作任務屬性的基本步驟。透過掌握這些技術，您可以提高 Java 開發技能並簡化專案中的任務管理。
## 常見問題解答
### Aspose.Tasks 與 Java 11 相容嗎？
是的，Aspose.Tasks 與 Java 11 及更高版本相容。
### 我可以將 Aspose.Tasks 用於商業項目嗎？
絕對地！ Aspose.Tasks 是個人和商業專案的強大工具。訪問[這裡](https://purchase.aspose.com/buy)探索許可證選項。
### 我如何獲得用於測試目的的臨時許可證？
獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/)用於測試和評估。
### 在哪裡可以找到 Aspose.Tasks 的社區支援？
加入社群討論：[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)尋求幫助和合作。
### 有沒有範例項目可供參考？
瀏覽文件的範例部分[這裡](https://reference.aspose.com/tasks/java/)用於範例專案和程式碼片段。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
