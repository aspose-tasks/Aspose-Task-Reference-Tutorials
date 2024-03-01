---
title: Aspose.Tasks 任務逾時
linktitle: Aspose.Tasks 任務逾時
second_title: Aspose.Tasks Java API
description: 使用 Aspose.Tasks for Java 探索專案任務中高效率的加班管理。輕鬆簡化追蹤和資源分配。
type: docs
weight: 23
url: /zh-hant/java/task-properties/overtimes-in-tasks/
---
## 介紹
管理專案任務中的加班對於專案經理和團隊領導至關重要，以確保準確的追蹤和資源分配。 Aspose.Tasks for Java 提供了一個強大的解決方案來處理專案管理中與加班相關的方面。在本教程中，我們將探討如何利用 Aspose.Tasks 有效管理和分析專案任務中的加班情況。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
- Java 開發環境：確保您的電腦上設定了 Java 開發環境。
-  Aspose.Tasks for Java：下載並安裝 Aspose.Tasks 函式庫。您可以找到該庫及其文檔[這裡](https://reference.aspose.com/tasks/java/).
- 專案文件：準備一個專案文件（例如，TaskOvertimes.mpp）以便在教程中使用。
## 導入包
在您的 Java 專案中，匯入必要的 Aspose.Tasks 套件以利用其功能。新增以下導入語句：
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```
## 第 1 步：建立一個新項目
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//建立一個新項目
Project project = new Project(dataDir + "TaskOvertimes.mpp");
```
## 第 2 步：迭代任務並列印加班詳細信息
```java
for (Task tsk : project.getRootTask().getChildren()) {
    System.out.println("Overtime Cost: " + tsk.get(Tsk.OVERTIME_COST));
    System.out.println("Overtime Work: " + tsk.get(Tsk.OVERTIME_WORK).toString());
    System.out.println("Percent Complete: " + tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println("Percent Work Complete: " + tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println("Physical Percent Complete: " + tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
    //設定完成百分比
    tsk.set(Tsk.PERCENT_COMPLETE, 100);
}
```
請依照以下步驟有效地利用 Aspose.Tasks for Java 來管理和分析專案任務中的加班情況。您可以根據您的特定專案需求隨意客製化程式碼。
## 結論
Aspose.Tasks for Java 簡化了專案任務中的加班管理，為開發人員提供了一套強大的工具。透過遵循本指南，您可以將 Aspose.Tasks 無縫整合到您的 Java 專案中，確保高效的專案管理。
## 常見問題解答
### Aspose.Tasks適合大型專案管理嗎？
是的，Aspose.Tasks 旨在處理各種規模的項目，從小型項目到大型複雜項目。
### 我可以將 Aspose.Tasks 與其他 Java 框架整合嗎？
絕對地！ Aspose.Tasks 與其他 Java 框架無縫集成，增強了其在專案開發中的多功能性。
### 使用 Aspose.Tasks 是否有任何許可注意事項？
是的，您可以找到許可詳細資訊並取得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
### 我可以在哪裡尋求協助或討論與 Aspose.Tasks 相關的問題？
參觀[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)與社區互動並尋求支持。
### Aspose.Tasks 有免費試用版嗎？
是的，您可以存取免費試用版[這裡](https://releases.aspose.com/).