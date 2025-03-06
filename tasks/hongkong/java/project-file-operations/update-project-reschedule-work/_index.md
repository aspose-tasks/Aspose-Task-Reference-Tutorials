---
title: 在 Aspose.Tasks 中更新和重新安排 MS 項目
linktitle: 在 Aspose.Tasks 中更新專案並重新安排未完成的工作
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 以程式設計方式更新和重新排程 MS Project 檔案。
weight: 23
url: /zh-hant/java/project-file-operations/update-project-reschedule-work/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中更新和重新安排 MS 項目

## 介紹
Microsoft Project 是一種廣泛使用的專案管理軟體，可讓使用者有效地管理任務、資源和時間表。 Aspose.Tasks for Java 提供了一組強大的 API 來以程式設計方式操作 Microsoft Project 檔案。在本教程中，我們將學習如何使用 Aspose.Tasks for Java 更新 MS Project 檔案並重新安排未完成的工作。
## 先決條件
在我們開始之前，請確保您具備以下條件：
1. 您的系統上安裝了 Java 開發工具包 (JDK)。
2.  Java 函式庫的 Aspose.Tasks。您可以從以下位置下載：[這裡](https://releases.aspose.com/tasks/java/).
3. 對 Java 程式語言有基本的了解。

## 導入包
首先，在 Java 程式碼中匯入必要的套件：
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
## 第 1 步：設定項目
初始化一個新的 Project 物件並在其中定義任務及其持續時間和依賴性。
```java
String dataDir = "Your Data Directory";
Project project = new Project();
//定義任務及其持續時間
//…
//定義任務依賴關係
//…
//保存初始專案狀態
project.save(dataDir + "not_updated.xml", SaveFileFormat.Xml);
```
## 第 2 步：更新專案工作
更新專案工作以將其標記為在特定日期之前完成。
```java
Calendar cal = Calendar.getInstance();
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.updateProjectWorkAsComplete(cal.getTime(), false);
//儲存更新的項目
project.save(dataDir + "updated.xml", SaveFileFormat.Xml);
```
## 第 3 步：重新安排未完成的工作
重新安排任何未完成的工作在指定日期之後開始。
```java
cal.set(2014, Calendar.JANUARY, 28, 17, 0, 0);
project.rescheduleUncompletedWorkToStartAfter(cal.getTime());
//儲存重新安排的項目
project.save(dataDir + "rescheduled.xml", SaveFileFormat.Xml);
```

## 結論
在本教程中，我們學習如何使用 Aspose.Tasks for Java 更新 MS Project 檔案並重新安排未完成的工作。這在專案時間表需要根據進度或變化的優先順序進行調整的情況下特別有用。

## 常見問題解答
### Q：Aspose.Tasks for Java 可以處理複雜的專案結構嗎？
答：是的，Aspose.Tasks for Java 提供了強大的 API 來有效地管理任務、相依性、資源和其他專案元素。
### Q：Aspose.Tasks for Java 有試用版嗎？
答：是的，您可以從以下位置獲得免費試用[這裡](https://releases.aspose.com/).
### Q：如何獲得 Aspose.Tasks for Java 的支援？
答：您可以訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)如有任何幫助或疑問。
### Q：我可以購買 Aspose.Tasks for Java 的臨時授權嗎？
答：是的，可以購買臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
### Q：在哪裡可以找到 Aspose.Tasks for Java 的詳細文件？
答：可以參考文檔[這裡](https://reference.aspose.com/tasks/java/)取得全面的指南和 API 參考。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
