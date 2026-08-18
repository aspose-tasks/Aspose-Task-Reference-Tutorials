---
date: 2026-02-20
description: 學習如何使用 Aspose.Tasks for Java 設定專案開始日期並管理專案變異。本指南亦示範如何有效設定工作持續時間。
linktitle: Handle Task Variances in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 設定專案開始日期及處理任務差異 Aspose.Tasks
url: /zh-hant/java/task-properties/handle-variances/
weight: 19
---

 final output with all translations and placeholders unchanged.

Check for any missing items: Ensure we preserve all shortcodes at top and bottom.

Now produce final answer.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 設定專案開始日期與處理工作變異 Aspose.Tasks

## 介紹
在專案管理的領域中，**設定專案開始日期**是您為排程奠定堅實基礎的第一步之一。Aspose.Tasks for Java 讓此步驟以及隨後的工作變異處理變得簡單且可靠。在本教學中，您將學習如何設定專案開始日期、設定工作持續時間，並有效管理專案變異。

## 快速解答
- **設定專案開始日期的主要方法是什麼？** 使用 `project.set(Prj.START_DATE, …)` 搭配 `java.util.Calendar` 例項。  
- **哪個類別代表用於變異追蹤的基線？** `BaselineType.Baseline`。  
- **在設定基線後，我可以調整工作開始與結束日期嗎？** 可以，只需更新 `Tsk.START` 和 `Tsk.STOP`。  
- **開發使用是否需要授權？** 可取得臨時授權以供評估。  
- **哪個版本的 Aspose.Tasks 可與此程式碼相容？** 最新的 Aspose.Tasks for Java 版本。

## 什麼是 **設定專案開始日期**？
設定專案開始日期即定義所有工作日期計算的基準日。它會影響排程計算、關鍵路徑分析以及基線建立，對於精確的變異管理至關重要。

## 為何要設定專案開始日期並管理變異？
- **可預測性：** 建立可供比較實際進度的已知基線。  
- **彈性：** 允許您調整個別工作日期而不會遺失原始計畫。  
- **報告：** 產生清晰的變異報告，突顯排程延遲或提前完成的情況。  

## 前置條件
在開始之前，請確保您具備以下項目：

- Java 開發環境 – 已安裝 JDK 並備妥 IDE 或建置工具。  
- Aspose.Tasks 程式庫 – 下載程式庫 **[此處](https://releases.aspose.com/tasks/java/)**。  

## 匯入套件
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Prj;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
import java.util.Calendar;
```

## 步驟 1：設定專案
建立一個新的 `Project` 實例，用於保存所有工作與排程資訊。

```java
Project project = new Project();
```

## 步驟 2：新增工作
在根工作下新增一個工作。這將是我們之後要調整的工作項目。

```java
Task task = project.getRootTask().getChildren().add("Task");
```

## 步驟 3：設定開始日期與持續時間
定義專案的開始日期並為工作設定持續時間。此範例展示了 **設定工作持續時間** 的實作。

```java
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.FEBRUARY, 15, 8, 0, 0);
project.set(Prj.START_DATE, cal.getTime());
task.set(Tsk.DURATION, project.getDuration(2));
```

## 步驟 4：設定基線
建立基線，以便之後比較計畫日期與實際日期——這對 **管理專案變異** 至關重要。

```java
project.setBaseline(BaselineType.Baseline);
```

## 步驟 5：調整工作開始與結束日期
修改工作之開始與結束日期，以模擬變異情境。

```java
cal.set(2013, Calendar.NOVEMBER, 29, 8, 0, 0);
task.set(Tsk.START, cal.getTime());
cal.set(2013, Calendar.NOVEMBER, 27, 8, 0, 0);
task.set(Tsk.STOP, cal.getTime());
```

*隨意調整日期與持續時間，以符合您專案的具體需求。*

## 常見問題與技巧
- **必須先設定基線再調整日期。** 若先變更日期，基線將記錄已變更的排程，而非原始計畫。  
- **Calendar 的月份是從零開始計算。** 請記得 `Calendar.FEBRUARY` 代表第 1 個月，而非第 2 個月。  
- **持續時間單位：** `project.getDuration(2)` 預設建立兩天的持續時間；若需要小時或週，請調整單位。  

## 結論
透過精通 **設定專案開始日期**、**設定工作持續時間** 與 **管理專案變異**，您即可使用 Aspose.Tasks for Java 完全掌控專案排程。上述步驟提供了堅實的基礎，您可將其延伸至更複雜的情境，例如多階段專案、資源分配與自動化報告。

## 常見問答
### Aspose.Tasks 是否適用於所有專案管理需求？
Aspose.Tasks 是一套多功能工具，適用於廣泛的專案管理需求，提供彈性與強大的功能。

### 我可以將 Aspose.Tasks 整合到現有的 Java 專案中嗎？
可以，您只需依照提供的文件 **[此處](https://reference.aspose.com/tasks/java/)**，即可輕鬆將 Aspose.Tasks 整合至您的 Java 專案。

### 是否提供 Aspose.Tasks 的臨時授權？
可以，您可於 **[此處](https://purchase.aspose.com/temporary-license/)** 取得 Aspose.Tasks 的臨時授權。

### 我可以從哪裡取得 Aspose.Tasks 的支援？
若需支援與討論，請前往 Aspose.Tasks 論壇 **[此處](https://forum.aspose.com/c/tasks/15)**。

### 我可以下載 Aspose.Tasks for Java 嗎？
可以，請於 **[此處](https://releases.aspose.com/tasks/java/)** 下載最新版本的 Aspose.Tasks for Java。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-02-20  
**測試環境：** Aspose.Tasks 最新 Java 版本  
**作者：** Aspose