---
date: 2026-08-29
description: 了解如何在 Aspose.Tasks for Java 中設定連結類型並管理工作項目相依性，透過一步一步的教學。
keywords:
- how to set link
- Aspose.Tasks link types
- Java task dependencies
lastmod: 2026-08-29
linktitle: 如何在 Aspose.Tasks for Java 中設定連結類型
og_description: 了解如何在 Aspose.Tasks for Java 中設定連結類型並管理工作項目相依性。為開發人員提供的一步一步指南。
og_image_alt: Screenshot of Aspose.Tasks Java code setting task link types
og_title: 如何在 Aspose.Tasks for Java 中設定連結類型
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to set link types and manage task dependencies with Aspose.Tasks
    for Java in a step‑by‑step tutorial.
  headline: How to Set Link Types in Aspose.Tasks for Java
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks integrates with standard Java SE, Java EE, and Android
      development kits without additional dependencies.
    question: Is Aspose.Tasks compatible with different Java environments?
  - answer: Absolutely. The `TaskLinkType` enum provides four standard types, and
      you can combine them with lag values to model complex schedules.
    question: Can I customize link types based on my project requirements?
  - answer: Refer to the [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/)
      for in‑depth guidance, API reference, and code samples.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to acquire a temporary license for testing purposes.
    question: How can I obtain a temporary license for Aspose.Tasks?
  - answer: Join the Aspose.Tasks community on the [support forum](https://forum.aspose.com/c/tasks/15)
      for assistance and discussions.
    question: Where can I get support for Aspose.Tasks‑related queries?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- task link
title: 如何在 Aspose.Tasks for Java 中設定連結類型
url: /zh-hant/java/task-links/define-link-type/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks for Java 中設定連結類型

## 簡介
如果你想了解 **如何設定連結**，在專案中 *管理工作項目相依性*，你來對地方了。在本教學中，我們將示範如何建立新專案、加入工作項目，並使用 Aspose.Tasks for Java 定義連結類型（Start‑to‑Start、Finish‑to‑Start 等）。完成後，你將能自信地自訂任務關係以符合實務排程需求，並了解 API 如何處理多達 10,000 個工作項目的大型計畫。

## 快速答案
- **哪個類別代表相依性？** `TaskLink` 是模型兩個工作項目之間連結的核心物件。  
- **哪個列舉定義關係類型？** `TaskLinkType`（例如 `StartToStart`、`FinishToStart`）。  
- **我可以讀取既有的連結類型嗎？** 可以 – 迭代 `Project.getTaskLinks()` 並呼叫 `getLinkType()`。  
- **執行此程式碼需要授權嗎？** 測試可使用臨時授權；正式環境需購買完整授權。  
- **此程式碼相容於 Java 8+ 嗎？** 完全相容 – Aspose.Tasks 支援 Java 8 至 Java 21，涵蓋 13 個主要版本。

## 什麼是任務連結？

**任務連結** 用於在專案排程中模型兩個工作項目之間的相依性。  
你可以建立、修改或刪除 `TaskLink`，以反映前置‑後置關係，讓排程器自動計算開始與結束日期。

## 為什麼使用 Aspose.Tasks 連結類型？

Aspose.Tasks 支援 **30+ 輸入與輸出格式**，且可在不將整個檔案載入記憶體的情況下處理包含 **多達 10,000 個工作項目** 的專案。此量化能力確保即使是企業級的大型計畫也能快速執行，且函式庫保留 Microsoft Project 的所有功能，如自訂欄位與資源指派。

## 先決條件
- **Java 開發環境** – 已安裝並設定 JDK 8 或更新版本。  
- **Aspose.Tasks 函式庫** – 從 [download link](https://releases.aspose.com/tasks/java/) 下載最新 JAR。  
- **文件目錄** – 在本機建立資料夾，用於存放範例專案檔案。

## 匯入套件
我們先匯入必要的 Aspose.Tasks 類別，讓 IDE 能辨識稍後將使用的 API 呼叫。

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskLink;
import com.aspose.tasks.TaskLinkCollection;
import com.aspose.tasks.TaskLinkType;
```

## 如何在 Aspose.Tasks for Java 中設定連結類型？

載入全新的 `Project` 實例，新增兩個工作項目，然後以所需的 `TaskLinkType` 建立 `TaskLink`。此兩步驟模式讓你在一次呼叫中定義四種標準相依性之一。`Project` 代表整個專案檔案與其排程。`Task` 是專案內的單一工作項目。`TaskLink` 連接前置工作項目與後置工作項目。`TaskLinkType` 為列舉，指定關係類型（Start‑to‑Start、Finish‑to‑Start 等）。

### 步驟 1：設定連結類型
`TaskLink` 代表兩個工作項目之間的相依性，而 `TaskLinkType` 列舉可能的關係類型，例如 `StartToStart`。在此步驟中，我們建立全新專案、加入兩個工作項目，並使用 **Start‑to‑Start** 關係將它們連結。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";

Project project = new Project();
Task pred = project.getRootTask().getChildren().add("Task 1");
Task succ = project.getRootTask().getChildren().add("Task 2");
TaskLink link = project.getTaskLinks().add(pred, succ);
link.setLinkType(TaskLinkType.StartToStart);
```

> **專業提示：** 你可以將 `StartToStart` 替換為 `FinishToStart`、`StartToFinish` 或 `FinishToFinish`，視需要 **管理工作項目相依性** 而定。

### 步驟 2：取得連結類型
`Project.getTaskLinks()` 會回傳排程中所有 `TaskLink` 物件的集合。透過迭代此集合，你可以讀取每個連結的 `TaskLinkType`，並驗證已正確保存的關係。

```java
Project project = new Project(dataDir + "project.xml");
TaskLinkCollection allLinks = project.getTaskLinks();
for (TaskLink tskLink : allLinks) {
    System.out.println(tskLink.getLinkType());
}
```

主控台將輸出 `StartToStart`、`FinishToStart` 等值，以確認先前設定的連結類型。

## 常見問題與解決方案
- **加入連結時發生 NullPointerException** – 確保在建立 `TaskLink` 前，已將前置與後置工作項目加入專案。  
- **儲存後連結類型不正確** – 設定連結類型後，務必呼叫 `project.save("output.mpp")`（或其他支援格式）以持久化變更。  
- **找不到授權** – 將 Aspose.Tasks 授權檔放入專案的 classpath，並以 `License license = new License(); license.setLicense("Aspose.Tasks.Java.lic");` 載入。

## 常見問答

**Q: Aspose.Tasks 是否相容於不同的 Java 環境？**  
A: 是的，Aspose.Tasks 可與標準 Java SE、Java EE 以及 Android 開發套件整合，無需額外相依性。

**Q: 我可以依專案需求自訂連結類型嗎？**  
A: 當然可以。`TaskLinkType` 列舉提供四種標準類型，你亦可結合延遲值來建模複雜排程。

**Q: 哪裡可以找到 Aspose.Tasks for Java 的詳細文件？**  
A: 請參考 [Aspose.Tasks for Java documentation](https://reference.aspose.com/tasks/java/) 取得深入指引、API 參考與程式碼範例。

**Q: 如何取得 Aspose.Tasks 的臨時授權？**  
A: 前往 [temporary license page](https://purchase.aspose.com/temporary-license/) 取得測試用的臨時授權。

**Q: 哪裡可以取得 Aspose.Tasks 相關問題的支援？**  
A: 加入 Aspose.Tasks 社群的 [support forum](https://forum.aspose.com/c/tasks/15) 以獲得協助與討論。

**Q: 專案儲存後可以變更連結類型嗎？**  
A: 可以。載入專案、取得 `TaskLink`、呼叫 `setLinkType()` 設定新列舉值，然後再次儲存專案。

**Q: Aspose.Tasks 是否支援讀取 Microsoft Project (MPP) 檔案？**  
A: 支援。使用 `new Project("file.mpp")` 即可載入 MPP 檔，並如同上述 XML 範例般操作其任務連結。

---

**最後更新：** 2026-08-29  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose

## 相關教學

- [在 Aspose.Tasks 中建立跨專案任務連結](/tasks/java/task-links/create-cross-project-task-link/)
- [設定專案開始日期及管理父子任務於 Aspose.Tasks](/tasks/java/task-properties/parent-child-tasks/)
- [載入 MPP 檔案（Java）- 使用 Aspose.Tasks 管理專案屬性](/tasks/java/project-management/default-properties/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}