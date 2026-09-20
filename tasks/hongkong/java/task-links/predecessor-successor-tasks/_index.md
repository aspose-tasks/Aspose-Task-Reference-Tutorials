---
date: 2026-09-20
description: 了解如何使用 Aspose.Tasks for Java 管理專案工作依賴關係。本指南將示範如何新增 predecessor links、列印
  task names，以及有效設定 task dependencies。
keywords:
- project task dependencies
- how to add predecessor
- java project management
- manage task dependencies
- print task names
lastmod: 2026-09-20
linktitle: 使用 Aspose.Tasks for Java 管理專案工作依賴關係
og_description: 了解如何使用 Aspose.Tasks for Java 管理專案工作依賴關係。本指南將示範如何新增 predecessor links、列印
  task names，以及有效設定 task dependencies。
og_image_alt: Guide showing how to manage project task dependencies with Aspose.Tasks
  Java API
og_title: 使用 Aspose.Tasks for Java 管理專案工作依賴關係
schemas:
- author: Aspose
  dateModified: '2026-09-20'
  description: Learn how to manage project task dependencies using Aspose.Tasks for
    Java. This guide shows you how to add predecessor links, print task names, and
    set task dependencies efficiently.
  headline: Manage project task dependencies via Aspose.Tasks for Java
  type: TechArticle
- description: Learn how to manage project task dependencies using Aspose.Tasks for
    Java. This guide shows you how to add predecessor links, print task names, and
    set task dependencies efficiently.
  name: Manage project task dependencies via Aspose.Tasks for Java
  steps:
  - name: initialize the project object
    text: Create a new instance of the `Project` class and provide the path to your
      project file (e.g., `"project.mpp"`).
  - name: access task links
    text: Retrieve all task links from the project using the `getTaskLinks()` method.
  - name: iterate through task links
    text: Use a loop to iterate through each task link in the collection and print
      information about the predecessor and successor tasks.
  - name: add a new predecessor link (optional)
    text: If you need to create a new dependency, instantiate a `TaskLink`, set its
      `PredecessorTaskUid`, `SuccessorTaskUid`, and `LinkType`, then add it to the
      project's link collection. Repeat these steps as needed for your specific project
      requirements.
  type: HowTo
- questions:
  - answer: Yes, simply add the Aspose.Tasks JAR to your classpath or Maven/Gradle
      dependencies.
    question: Can I use Aspose.Tasks for Java in my existing Java project?
  - answer: Yes, it supports MPP, XML, CSV, and more than 30 additional formats.
    question: Is Aspose.Tasks compatible with different project file formats?
  - answer: Obtain a temporary license from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Tasks?
  - answer: Visit the [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) for
      community support and discussions.
    question: Where can I find additional support for Aspose.Tasks?
  - answer: Yes, download a free trial from the [Aspose free trial page](https://releases.aspose.com/).
    question: Can I download a free trial of Aspose.Tasks for Java?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- project task dependencies
- Aspose.Tasks
- Java project management
title: 使用 Aspose.Tasks for Java 管理專案工作依賴關係
url: /zh-hant/java/task-links/predecessor-successor-tasks/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks for Java 管理專案工作相依性

## 介紹
Project task dependencies 是任何實際排程的支柱，讓您能夠模擬哪項工作必須完成才能開始另一項工作。在本教學中，您將學習如何使用 Aspose.Tasks for Java 管理 **project task dependencies**，包括如何新增前置工作連結、列印工作名稱，以及以程式方式設定工作相依性。

## 快速解答
- **What is the first step?** 將您的 MPP 檔案載入至 `Project` 物件。  
- **How do you add a predecessor?** 建立 `TaskLink` 並設定其 `PredecessorTaskUid` 與 `SuccessorTaskUid`。  
- **Can you list all links?** 使用 `project.getTaskLinks()` 並遍歷集合。  
- **Do I need a license?** 臨時授權可用於評估；正式使用需購買完整授權。  
- **Which Java version is supported?** 支援 Java 8 或更高版本。

## 什麼是 project task dependencies？
project task dependencies 定義兩個工作之間的邏輯關係，例如 Finish‑to‑Start 或 Start‑to‑Start，並決定工作必須執行的順序。透過建立這些連結，排程會自動遵守實務限制，防止工作重疊，並確保下游工作僅在其前置條件滿足時才開始。

## 為何使用 Aspose.Tasks for Java？
Aspose.Tasks for Java 支援超過三十種專案檔案格式，包括最新的 Microsoft Project 版本，且可在不將整個文件載入記憶體的情況下處理高達兩 GB 的檔案。此高效能功能讓您能夠操作大型排程、產生報告，並有效執行批次更新，十分適合企業級專案管理解決方案。

## 前置條件
- Java 開發環境：機器上已安裝 Java 8 或更新版本。  
- Aspose.Tasks for Java 程式庫：從 [Aspose.Tasks for Java download page](https://releases.aspose.com/tasks/java/) 下載並安裝 Aspose.Tasks 程式庫。  
- 整合開發環境 (IDE)：Eclipse、IntelliJ IDEA，或您偏好的任何 Java 相容 IDE。

## 匯入套件
您需要匯入可進行專案操作的核心類別。

`Project` 類別是載入與儲存 Microsoft Project 檔案的入口點。  
`TaskLink` 類別則代表兩個工作之間的相依性。

## 如何在兩個工作之間新增前置連結？
建立 `TaskLink` 實例，指定前置工作的 UID 與後續工作的 UID，選擇適當的 `TaskLinkType`（例如 Finish‑to‑Start），然後將連結加入專案的工作連結集合。加入後，排程會立即反映新的相依關係。

### 步驟 1：初始化專案物件
建立 `Project` 類別的新實例，並提供您的專案檔案路徑（例如 `"project.mpp"`）。

```java
import com.aspose.tasks.*;
```

### 步驟 2：存取工作連結
使用 `getTaskLinks()` 方法從專案中取得所有工作連結。

```java
String dataDir = "Your Document Directory";
Project project = new Project(dataDir + "project.mpp");
```

### 步驟 3：遍歷工作連結
使用迴圈遍歷集合中的每個工作連結，並列印前置工作與後續工作的資訊。

```java
TaskLinkCollection allinks = project.getTaskLinks();
```

### 步驟 4：新增前置連結（可選）
如果需要建立新相依性，請實例化 `TaskLink`，設定其 `PredecessorTaskUid`、`SuccessorTaskUid` 與 `LinkType`，然後將其加入專案的連結集合。

```java
for (TaskLink tsklnk : allinks) {
    System.out.println("Predecessor " + tsklnk.getPredTask().get(Tsk.NAME));
    System.out.println("Successor " + tsklnk.getSuccTask().get(Tsk.NAME));
}
```

根據您的專案需求，重複上述步驟。

## 常見問題與解決方案
- **Missing predecessor after adding a link** – 確認已呼叫 `project.updateTaskLinks()`（或儲存後重新載入），以刷新內部圖形。  
- **Performance slowdown on large files** – 在批次操作前使用 `project.setReadOnly(true)` 以減少記憶體開銷。  
- **Incorrect link type** – 確認使用正確的 `TaskLinkType` 列舉值（例如 `FinishToStart`），以符合排程邏輯。

## 常見問答

**Q: 我可以在現有的 Java 專案中使用 Aspose.Tasks for Java 嗎？**  
A: 可以，只需將 Aspose.Tasks JAR 加入您的 classpath 或 Maven/Gradle 依賴即可。

**Q: Aspose.Tasks 是否相容於不同的專案檔案格式？**  
A: 是的，它支援 MPP、XML、CSV，以及超過 30 種其他格式。

**Q: 我該如何取得 Aspose.Tasks 的臨時授權？**  
A: 可從 [temporary license page](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

**Q: 我可以在哪裡找到 Aspose.Tasks 的其他支援？**  
A: 前往 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 取得社群支援與討論。

**Q: 我可以下載 Aspose.Tasks for Java 的免費試用版嗎？**  
A: 可以，從 [Aspose free trial page](https://releases.aspose.com/) 下載免費試用版。

---

**最後更新：** 2026-09-20  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose

## 相關教學

- [在 Aspose.Tasks 中建立專案管理工作相依性](/tasks/java/task-links/create-task-link/)
- [設定專案開始日期與管理父子工作於 Aspose.Tasks](/tasks/java/task-properties/parent-child-tasks/)
- [使用 Aspose.Tasks for Java 讀取與設定工作優先順序](/tasks/java/task-properties/handle-priorities/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}