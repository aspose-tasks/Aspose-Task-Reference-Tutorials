---
title: 在 Aspose.Tasks 中建立 MS Project 任務基線
linktitle: 在 Aspose.Tasks 中建立任務基線
second_title: Aspose.Tasks Java API
description: 了解如何使用 Aspose.Tasks 在 Java 中建立 Microsoft Project 任務基線，Aspose.Tasks 是一個用於輕鬆管理專案資料的強大函式庫。
weight: 11
url: /zh-hant/java/task-baselines/create-task-baseline/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中建立 MS Project 任務基線

## 介紹
在本教程中，我們將深入研究使用 Aspose.Tasks for Java 建立 Microsoft Project 任務基線的過程。 Aspose.Tasks 是一個功能強大的 Java 程式庫，可讓開發人員使用 Microsoft Project 文件，而無需安裝 Microsoft Project。透過 Aspose.Tasks，您可以輕鬆操作專案數據，包括任務、資源和日曆，以簡化專案管理任務。
## 先決條件
在我們開始之前，請確保您符合以下先決條件：
1. Java 開發工具包 (JDK)：Aspose.Tasks for Java 需要在您的系統上安裝 JDK。您可以從 Oracle 網站下載並安裝 JDK。
2.  Aspose.Tasks for Java 函式庫：從下列位置下載 Aspose.Tasks for Java 函式庫：[下載連結](https://releases.aspose.com/tasks/java/)假如。

## 導入包
若要開始在 Java 專案中使用 Aspose.Tasks，請匯入必要的套件：
```java
import com.aspose.tasks.BaselineType;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import java.util.ArrayList;
import java.util.List;
```

## 第 1 步：建立專案對象
```java
Project project = new Project();
```
首先，建立一個新的`Project`目的。該物件代表您將使用的 Microsoft Project 檔案。
## 第 2 步：為專案新增任務
```java
Task task = project.getRootTask().getChildren().add("Task");
```
使用`getRootTask()`方法，存取專案的根任務，然後使用以下命令向其新增任務`add()`方法。在括號內提供任務的名稱。
## 步驟 3：為指定任務設定基線
```java
List<Task> myList = new ArrayList<Task>();
project.setBaseline(BaselineType.Baseline, (Iterable<Task>) myList);
```
若要為特定任務設定基線，請建立任務清單 (`myList`在本例中）並用您要為其設定基線的任務填充它。然後，使用`setBaseline()`方法，指定基線類型和任務清單。
## 第 4 步：為整個專案設定基線
```java
project.setBaseline(BaselineType.Baseline);
```
或者，您可以透過簡單地呼叫來為整個專案設定基線`setBaseline()`指定基線類型的方法。

## 結論
在本教學中，我們探討如何使用 Aspose.Tasks for Java 建立 Microsoft Project 任務基準。透過執行上述步驟，您可以有效率地管理專案資料並輕鬆簡化專案管理任務。
## 常見問題解答
### 我可以在未安裝 Microsoft Project 的情況下使用 Aspose.Tasks for Java 嗎？
是的，Aspose.Tasks for Java 允許您使用 Microsoft Project 文件，而無需在系統上安裝 Microsoft Project。
### Aspose.Tasks for Java 是否與不同版本的 Microsoft Project 相容？
是的，Aspose.Tasks for Java 支援各種版本的 Microsoft Project，確保不同環境之間的相容性。
### 我可以使用 Aspose.Tasks for Java 操作專案資源嗎？
當然，Aspose.Tasks for Java 提供了操作專案資源的強大功能，包括根據需要新增、更新和刪除資源。
### Aspose.Tasks for Java是否支援設定任務依賴關係？
是的，您可以使用 Aspose.Tasks for Java 輕鬆設定任務依賴關係，讓您能夠在專案中建立任務順序。
### Aspose.Tasks for Java 是否提供技術支援？
是的，您可以透過以下方式存取 Aspose.Tasks for Java 的技術支援：[支援論壇](https://forum.aspose.com/c/tasks/15)，您可以在其中提出問題並尋求社區和 Aspose 支援人員的協助。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
