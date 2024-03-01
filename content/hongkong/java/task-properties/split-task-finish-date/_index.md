---
title: Aspose.Tasks 中的分割任務完成日期
linktitle: Aspose.Tasks 中的分割任務完成日期
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks for Java 輕鬆分割任務完成日期。透過準確的時間表加強專案管理。
type: docs
weight: 28
url: /zh-hant/java/task-properties/split-task-finish-date/
---
## 介紹
在專案管理中，了解任務時間表對於成功完成專案至關重要。 Aspose.Tasks for Java 提供了強大的功能來有效地操作專案任務。在本教學中，我們將深入研究使用 Aspose.Tasks 分割任務完成日期，以幫助您有效管理專案時程。
## 先決條件
在我們開始之前，請確保您具備以下條件：
- Java 程式設計的基礎知識。
- 安裝了 Java 函式庫的 Aspose.Tasks。你可以下載它[這裡](https://releases.aspose.com/tasks/java/).
- Java開發環境搭建完畢。
## 導入包
首先在您的 Java 專案中包含必要的套件：
```java
import com.aspose.tasks.*;
```
## 第 1 步：找到拆分任務
找到您要在專案中拆分的任務：
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//閱讀項目
String projectName = dataDir + "SplitTask.mpp";
Project project = new Project(projectName);
Task splitTask = project.getRootTask().getChildren().getByUid(1);
```
## 第 2 步：尋找專案日曆
擷取專案日曆以進行準確的日期計算：
```java
Calendar calendar = project.get(Prj.CALENDAR);
```
## 步驟 3：計算不同持續時間的任務完成日期
現在，計算不同持續時間的任務完成日期：
## 步驟 3.1：8 小時的持續時間
```java
System.out.println("Start Date: " + splitTask.get(Tsk.START) + "\n+ Duration 8 hours\nFinish Date: " + calendar.getTaskFinishDateFromDuration(splitTask, 8d));
```
針對不同的持續時間重複上述程式碼，並據此調整時間。
## 結論
掌握操縱任務完成日期的藝術對於有效的專案管理至關重要。 Aspose.Tasks for Java 簡化了這個過程，讓您可以毫不費力地簡化專案時程。
## 常見問題解答
### Q1: 如何下載 Aspose.Tasks for Java？
 A1：可以下載[這裡](https://releases.aspose.com/tasks/java/).
### Q2：在哪裡可以找到 Aspose.Tasks 的文件？
 A2：參考文檔[這裡](https://reference.aspose.com/tasks/java/).
### Q3：如何取得 Aspose.Tasks 的臨時授權？
 A3：獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
### Q4：我可以在哪裡尋求 Aspose.Tasks 的支援？
 A4：造訪支援論壇[這裡](https://forum.aspose.com/c/tasks/15).
### Q5：我可以購買Aspose.Tasks嗎？
 A5: 是的，您可以購買[這裡](https://purchase.aspose.com/buy).