---
date: 2026-01-20
description: 學習如何使用 Aspose.Tasks for Java 連結專案以及跨專案連結任務，並依循逐步指南建立跨專案任務連結。
linktitle: Create Cross-Project Task Link in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何連結專案：在 Aspose.Tasks 中建立跨專案任務連結
url: /zh-hant/java/task-links/create-cross-project-task-link/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何連結專案：在 Aspose.Tasks 中建立跨專案工作項目連結

## 如何使用 Aspose.Tasks 連結專案
在當今節奏快速的專案管理環境中，了解 **如何連結專案** 對於保持多個計畫同步至關重要。Aspose.Tasks for Java 為您提供強大的 API 以建立跨專案工作項目連結，讓您只需幾行程式碼即可 **在專案之間連結工作項目**。在本教學中，您將學習具體步驟、查看所需的程式碼片段，並了解此技術如何顯著提升團隊成員之間的協作。

## 快速答覆
- **主要好處是什麼？** 在不同的專案檔案之間無縫同步相依的工作項目。  
- **需要哪個函式庫？** Aspose.Tasks for Java（最新版本）。  
- **需要授權嗎？** 生產環境使用需具備有效的 Aspose.Tasks 授權。  
- **實作需要多少分鐘？** 基本連結大約需要 10–15 分鐘。  
- **可以在不同檔案格式之間連結工作項目嗎？** 可以 — API 支援 MPP、XML 以及其他格式。  

## 先決條件
在開始之前，請確保您已準備好以下項目：

- 具備 Java 程式設計的實務知識。  
- 已安裝 Aspose.Tasks for Java。您可從 [Aspose.Tasks for Java 釋出頁面](https://releases.aspose.com/tasks/java/) 下載。  
- 基本了解專案管理概念，如工作項目相依性與彙總工作項目。  

## 匯入套件
首先，匯入您需要的類別。這樣即可存取 Aspose.Tasks 的核心功能：

```java
import com.aspose.tasks.NullableBool;
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkType;
import com.aspose.tasks.Tsk;
```

## 步驟 1：設定環境
確保您的機器已安裝 Java，且已將 Aspose.Tasks JAR 加入專案的 classpath。此步驟對於程式碼能順利編譯且不產生錯誤至關重要。

## 步驟 2：建立 Project 實例
建立一個全新的 `Project` 物件，用於保存工作項目與連結：

```java
Project project = new Project();
```

## 步驟 3：新增彙總工作項目
彙總工作項目作為您將要連結的工作項目的容器。稍後檢視專案時，可使結構更為清晰：

```java
Task summary = project.getRootTask().getChildren().add("Summary Task");
```

## 步驟 4：新增外部工作項目
現在新增一個外部工作項目，指向另一個專案檔案中的工作項目。這是跨專案連結的「來源」端：

```java
Task t2 = summary.getChildren().add("External Task");
t2.set(Tsk.EXTERNAL_TASK_PROJECT, "ExternalProject.mpp");
t2.set(Tsk.EXTERNAL_ID, 1);
t2.set(Tsk.IS_EXTERNAL_TASK, true);
t2.set(Tsk.IS_MANUAL, new NullableBool(false));
t2.set(Tsk.IS_SUMMARY, false);
```

## 步驟 5：新增本地工作項目
建立將與外部工作項目連結的本地工作項目。這是關係的「目標」端：

```java
Task t = summary.getChildren().add("Task");
```

## 步驟 6：建立工作項目連結
在外 `true`，即告訴 Aspose.Tasks 此連結跨越兩個不同的專案檔案：

```java
TaskLink link = project.getTaskLinks().add(t2, t);
link.setCrossProject(true);
link.setLinkType(TaskLinkType.FinishToStart);
link.setCrossProjectName("ExternalProject.mpp\\1");
```

## 步驟 7：顯示結果
最後，輸出簡單的確認訊息，以確保流程已順利完成且未拋出例外：

```java
System.out.println("Process completed Successfully");
```

##間連結工作項目？
在專案之間連結工作項目可讓您：

- 在與解決方案
|------|----------|
| 找_ID` 正確無誤。 |
| 連結類型不匹配 | 確保 `TaskLinkType` 符合所需的相依關係（例如，完成至開始）。 |
| 授權例外 | 在建立 Project 實例前安裝有效的 Aspose.Tasks 授權。 |

## 常見問與答

**Q: 我工作項目中，從多個外部專案連結工作項目嗎？**  
A: 可以，您可以在同一個彙總工作項目內，依照類似流程連結來自不同外部專案的工作項目。

**Q: 如果已連結專案中的外部工作項目被修改，會發生什麼情況？**  
A: 外部工作項目的任何變更都會反映在您目前專案中的連結工作項目上。

**Q: 是否: 可以:項目數量有任何限制嗎？**  
A: 可連結的工作項目數量受限於您 Aspose.Tasks 授權的功能與限制。

## 結論
您現在已了解如何使用 Aspose.Tasks for Java **連結專案** 以及 **在專案之間連結工作項目**。透過建立跨專案工作項目連結，您可以促進更順暢的協作、減少手動同步的工作量，並使專案計畫保持一致。歡迎嘗試不同的連結類型，並探索 Aspose.Tasks 的管理工作.Tasks for Java 24.12 (latest)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}