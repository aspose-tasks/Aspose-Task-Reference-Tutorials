---
title: 在 Aspose.Tasks 中管理任務的持續時間
linktitle: 在 Aspose.Tasks 中管理任務的持續時間
second_title: Aspose.Tasks Java API
description: 探索 Aspose.Tasks for Java 並學習輕鬆管理任務持續時間。按照我們的逐步指南進行有效的專案規劃和執行。
weight: 20
url: /zh-hant/java/task-properties/manage-durations/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中管理任務的持續時間

## 介紹
Aspose.Tasks for Java 提供了一個強大的解決方案來有效管理專案任務和工期。在本教程中，我們將探索如何使用 Aspose.Tasks 管理任務的持續時間，引導您完成每個步驟。無論您是經驗豐富的開發人員還是初學者，本指南都將幫助您掌握在專案中處理任務持續時間的要點。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
-  Java 開發工具包 (JDK)：確保您的電腦上安裝了 Java。你可以下載它[這裡](https://www.oracle.com/java/technologies/javase-downloads.html).
- Aspose.Tasks 庫：下載 Aspose.Tasks 庫並將其包含在您的專案中。你可以找到圖書館[這裡](https://releases.aspose.com/tasks/java/).
## 導入包
在您的 Java 專案中，匯入使用 Aspose.Tasks 所需的套件：
```java
import com.aspose.tasks.Duration;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TimeUnitType;
import com.aspose.tasks.Tsk;
```
## 第 1 步：設定您的項目
```java
//建立一個新項目
Project project = new Project();
```
## 第 2 步：新增任務
```java
//新增任務
Task task = project.getRootTask().getChildren().add("Task");
```
## 第 3 步：取得並轉換任務持續時間
```java
//取得任務持續時間（以天為單位）（預設時間單位）
Duration duration = task.get(Tsk.DURATION);
System.out.println("Duration equals 1 day: " + duration.toString().equals("1 day"));
//將持續時間轉換為小時時間單位
duration = duration.convert(TimeUnitType.Hour);
System.out.println("Duration equals 8 hrs: " + duration.toString().equals("8 hrs"));
```
## 步驟 4：將任務持續時間更新為 1 週
```java
//將任務持續時間增加至 1 週
task.set(Tsk.DURATION, project.getDuration(1, TimeUnitType.Week));
System.out.println("Duration equals 1 wk: " + task.get(Tsk.DURATION).toString().equals("1 wk"));
```
## 第 5 步：減少任務持續時間
```java
//減少任務持續時間
task.set(Tsk.DURATION, task.get(Tsk.DURATION).subtract(0.5));
System.out.println("Duration equals 0.5 wks: " + task.get(Tsk.DURATION).toString().equals("0.5 wks"));
```
透過執行這些步驟，您已成功管理 Aspose.Tasks for Java 專案中任務的持續時間。
## 結論
在本教程中，我們介紹了使用 Aspose.Tasks for Java 管理任務持續時間的基礎知識。現在，您可以自信地將這些技術融入您的專案中，以實現有效的任務工期管理。
## 常見問題解答
### Aspose.Tasks 與所有 Java 版本相容嗎？
Aspose.Tasks 與 Java 6 及更高版本相容。
### 我可以將 Aspose.Tasks 用於商業項目嗎？
是的，您可以將 Aspose.Tasks 用於個人和商業專案。訪問[這裡](https://purchase.aspose.com/buy)了解許可詳細資訊。
### 我可以在哪裡找到額外的支援和資源？
參觀[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)以獲得社區支持和討論。
### 我如何獲得用於測試目的的臨時許可證？
您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/)用於測試和評估。
### Aspose.Tasks 是否有免費試用版？
是的，您可以免費試用[這裡](https://releases.aspose.com/)在購買之前探索 Aspose.Tasks。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
