---
title: 在 Aspose.Tasks 中管理關鍵任務和工作驅動任務
linktitle: 在 Aspose.Tasks 中管理關鍵任務和工作驅動任務
second_title: Aspose.Tasks Java API
description: 使用 Aspose.Tasks 輕鬆管理 Java 專案中的關鍵和需要大量精力的任務。下載該庫並增強您的專案管理能力。
weight: 14
url: /zh-hant/java/task-properties/critical-effort-driven-tasks/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中管理關鍵任務和工作驅動任務

在快節奏的專案管理世界中，有效處理關鍵和需要付出努力的任務對於成功完成專案至關重要。 Aspose.Tasks for Java 提供了一個強大的解決方案來無縫管理這些任務。在本教程中，我們將指導您完成使用 Aspose.Tasks for Java 處理專案中的關鍵任務和工作驅動型任務的過程。
## 先決條件
在我們深入學習本教程之前，請確保您具備以下先決條件：
- Aspose.Tasks for Java Library：從以下位置下載並安裝該程式庫：[Aspose.Tasks for Java 文檔](https://reference.aspose.com/tasks/java/).
- Java 開發工具包 (JDK)：確保您的系統上安裝了 Java。
- 整合開發環境 (IDE)：使用您首選的 IDE 進行 Java 開發。
- 專案文件：準備一個 XML 格式的專案文件，用於演示。
## 導入包
在您的 Java 專案中，匯入必要的套件以利用 Aspose.Tasks for Java 的功能：
```java
import com.aspose.tasks.ChildTasksCollector;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskUtils;
import com.aspose.tasks.Tsk;
```
現在，讓我們將每個步驟分解為一個綜合指南：
## 步驟 1： 使用 ChildTasksCollector 收集任務
創建一個`ChildTasksCollector`使用實例從根任務收集所有任務`TaskUtils.apply`。這可確保您可以存取專案內的所有任務。
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "project.xml");
//建立一個 ChildTasksCollector 實例
ChildTasksCollector collector = new ChildTasksCollector();
//使用 TaskUtils 從 RootTask 收集所有任務
TaskUtils.apply(project.getRootTask(), collector, 0);
```
## 第 2 步：迭代收集的任務
使用 a 解析所有收集到的任務`for`環形。對於每項任務，確定它是否是努力驅動的和關鍵的，並列印相應的狀態。
```java
//解析所有收集的任務
for (Task tsk : collector.getTasks()) {
    String strED = tsk.get(Tsk.IS_EFFORT_DRIVEN) != null ? "EffortDriven" : "Non-EffortDriven";
    String strCrit = tsk.get(Tsk.IS_CRITICAL) != null ? "Critical" : "Non-Critical";
    System.out.println(strED);
    System.out.println(strCrit);
}
```
透過執行這些步驟，您可以使用 Aspose.Tasks for Java 有效管理專案中的關鍵任務和工作驅動型任務。
## 結論
總之，Aspose.Tasks for Java 使 Java 開發人員能夠有效地管理專案管理中的關鍵任務和工作驅動型任務。憑藉其易於使用的特性和強大的功能，處理複雜的專案場景變得輕而易舉。
## 經常問的問題
### Q：我可以在 Windows 和 Linux 環境中使用 Aspose.Tasks for Java 嗎？
是的，Aspose.Tasks for Java 是獨立於平台的，可以在 Windows 和 Linux 環境中使用。
### Q：Aspose.Tasks for Java 是否有免費試用版？
是的，您可以免費試用 Aspose.Tasks for Java[這裡](https://releases.aspose.com/).
### Q：在哪裡可以找到 Aspose.Tasks for Java 的支援？
參觀[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)以獲得社區支持和討論。
### Q：如何取得 Aspose.Tasks for Java 的臨時授權？
您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
### Q：哪裡可以購買 Aspose.Tasks for Java？
您可以從以下位置購買 Aspose.Tasks for Java[購買頁面](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
