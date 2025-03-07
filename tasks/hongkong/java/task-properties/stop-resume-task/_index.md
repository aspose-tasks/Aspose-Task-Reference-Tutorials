---
title: 在 Aspose.Tasks 中停止和恢復任務
linktitle: 在 Aspose.Tasks 中停止和恢復任務
second_title: Aspose.Tasks Java API
description: 透過我們有關停止和復原任務的逐步指南來探索 Aspose.Tasks for Java 的強大功能。無縫增強專案管理！
weight: 30
url: /zh-hant/java/task-properties/stop-resume-task/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中停止和恢復任務

## 介紹
在 Java 開發領域，有效管理任務是專案執行的重要面向。 Aspose.Tasks for Java 以其強大的功能提供了處理任務的強大解決方案。在本教程中，我們將深入研究一項特定功能 - 停止和恢復任務。透過遵循此逐步指南，您將能夠將此功能無縫整合到您的 Java 專案中。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
- 對 Java 程式設計有基本的了解。
- 在您的系統上安裝了 Java 開發工具包 (JDK)。
- Aspose.Tasks for Java 程式庫下載並新增到您的專案中。您可以從以下位置獲取它：[這裡](https://releases.aspose.com/tasks/java/).
## 導入包
要開始該過程，請確保將必要的套件匯入到您的 Java 專案中：
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
import java.util.GregorianCalendar;
```
## 第 1 步：初始化
首先初始化您的專案並建立一個`ChildTasksCollector`實例來收集所有任務。
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "Software Development.mpp");
ChildTasksCollector collector = new ChildTasksCollector();
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## 第 2 步：設定最短日期
定義最短日期來過濾需要停止或復原的任務。
```java
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
```
## 第 3 步：停止和恢復任務
迭代任務，檢查並列印停止和恢復日期。
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
在您的 Java 專案中重複這些步驟，以使用 Aspose.Tasks for Java 無縫整合停止和復原功能。
## 結論
在本教程中，我們探索了使用 Aspose.Tasks for Java 停止和復原任務的過程。透過執行上述步驟，您可以增強專案管理能力並簡化任務執行。
## 經常問的問題
### Aspose.Tasks for Java適合大型專案嗎？
絕對地！ Aspose.Tasks for Java 旨在處理不同規模的項目，確保效率和可靠性。
### 我可以自訂停止和恢復任務的日期嗎？
是的，所提供的範例允許根據您的專案要求靈活設定最短日期。
### 在哪裡可以找到 Aspose.Tasks for Java 的其他支援？
參觀[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)以獲得社區支持和討論。
### Aspose.Tasks for Java 是否有免費試用版？
是的，您可以訪問[免費試用](https://releases.aspose.com/)在購買前探索功能。
### 如何取得 Aspose.Tasks for Java 的臨時授權？
您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/)用於測試目的。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
