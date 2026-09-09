---
date: 2026-09-09
description: 了解如何使用 Aspose.Tasks for Java 識別跨專案任務。探索無縫整合、高效管理以及實際範例。
keywords:
- identify cross project tasks
- set document directory
- get task id java
lastmod: 2026-09-09
linktitle: 在 Aspose.Tasks 中識別跨專案任務
og_description: 在 Aspose.Tasks for Java 中識別跨專案任務。了解如何設定文件目錄、檢索任務 ID，並有效管理連結的專案。
og_image_alt: Screenshot of Aspose.Tasks Java API showing cross‑project task identification
og_title: 在 Aspose.Tasks 中識別跨專案任務 – Java 指南
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to identify cross project tasks using Aspose.Tasks for Java.
    Explore seamless integration, efficient management, and real‑world examples.
  headline: Identify cross project tasks in Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Tasks supports multiple languages, including Java, .NET, and
      more.
    question: Can I use Aspose.Tasks with other programming languages?
  - answer: Refer to the documentation **[here](https://reference.aspose.com/tasks/java/)**.
    question: Where can I find detailed documentation for Aspose.Tasks for Java?
  - answer: Yes, you can get a free trial **[here](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Tasks for Java?
  - answer: Obtain a temporary license **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I get temporary licensing for Aspose.Tasks?
  - answer: Visit the Aspose.Tasks support forum **[here](https://forum.aspose.com/c/tasks/15)**.
    question: Need help or have specific questions?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- Aspose.Tasks
- Java project management
- cross project tasks
- task linking
title: 在 Aspose.Tasks 中識別跨專案任務
url: /zh-hant/java/task-links/identify-cross-project-tasks/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 識別 Aspose.Tasks 中的跨專案任務

## 介紹
在本教學中，您將學習 **如何識別跨專案任務** 與 Aspose.Tasks for Java。無論您是維護相互依賴的排程組合，或是需要稽核外部相依性，以下步驟將示範如何定位參考其他專案檔案的任務、取得其識別碼，並以程式方式操作它們。

## 快速解答
- **「識別跨專案任務」是什麼意思？** 它指的是定位參考或依賴於另一個專案檔案中任務的任務。  
- **哪個方法會印出任務 ID？** 使用 `externalTask.get(Tsk.ID)` 來印出任務 ID。  
- **如何設定文件目錄？** 將資料夾路徑指派給 `String` 變數（例如 `dataDir`）。  
- **哪個屬性可依 UID 取得任務？** 呼叫 `getChildren().getByUid(yourUid)`。  
- **生產環境是否需要授權？** 是的，商業部署需要有效的 Aspose.Tasks 授權。

## 什麼是「識別跨專案任務」？
識別跨專案任務可讓您追蹤分散於多個 Microsoft Project 檔案之間的任務關係。透過定位參考或依賴外部排程的任務，您能了解工作項目在專案邊界之間的互動方式，防止重複工作，並維持正確的時間表。此功能對於任務共享或依賴外部排程的大型投資組合尤為重要。

## 為什麼使用 Aspose.Tasks for Java？
Aspose.Tasks for Java 支援 **超過 50 種輸入與輸出格式**（包括 MPP、MPX、XML 與 CSV），且能在不將整個檔案載入記憶體的情況下處理 **多達 10,000 個任務** 的專案。此函式庫可在任何相容 JVM 的平台上執行，無需安裝 Microsoft Project，並提供完整的 API 以存取 ID、UID、外部 ID 與連結中繼資料。

## 前置條件
- 具備可運作的 Java 開發環境（JDK 8 或以上）。  
- 已安裝 Aspose.Tasks for Java。您可於 **[此處](https://releases.aspose.com/tasks/java/)** 下載。  
- 若計畫在生產環境執行程式碼，需具備有效的 Aspose.Tasks 授權檔案。

## 匯入套件
`Project` 類別代表 Microsoft Project 檔案，`Task` 代表單一任務，而 `Tsk` 提供任務欄位常數。  
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## 步驟 1：設定文件目錄
`dataDir` 字串保存包含您 `.mpp` 檔案的資料夾路徑。  
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

## 步驟 2：載入外部專案
`Project externalProject` 會載入指定的外部專案檔案以供檢查。  
```java
Project externalProject = new Project(dataDir + "External.mpp");
```

## 步驟 3：依 UID 取得外部任務
`externalProject.getChildren().getByUid(uid)` 會使用唯一識別碼從外部專案的任務集合中取得任務。  
```java
Task externalTask = externalProject.getRootTask().getChildren().getByUid(1);
```

## 步驟 4：印出任務 ID（主要使用情境）
`externalTask.get(Tsk.ID)` 會回傳 Aspose.Tasks 為該任務指派的內部 ID。  
```java
System.out.println(externalTask.get(Tsk.ID).toString());
```

## 步驟 5：印出原始（外部）任務 ID
`externalTask.get(Tsk.ExternalID)` 會取得來源專案檔案中定義的任務原始 ID。  
```java
System.out.println(externalTask.get(Tsk.EXTERNAL_ID).toString());
```

對於需要跨專案追蹤的其他任務，請重複上述步驟。

## 常見問題與技巧
- **路徑錯誤** – 確認 `dataDir` 以正確的檔案分隔符結尾（`/` 或 `\\`）。  
- **找不到 UID** – 確認 UID 存在於外部專案中；可使用 `externalProject.getRootTask().getChildren().size()` 列出可用的 UID。  
- **授權例外** – 缺少或無效的授權會在執行時拋出授權例外。  
- **大型專案** – 對於超過 5,000 個任務的專案，建議使用帶有 `LoadOptions` 標誌的 `ProjectReader` 以串流資料並降低記憶體使用量。

## 常見問答

**Q: 我可以將 Aspose.Tasks 與其他程式語言一起使用嗎？**  
A: 可以，Aspose.Tasks 支援多種語言，包括 Java、.NET 等。

**Q: 哪裡可以找到 Aspose.Tasks for Java 的詳細文件？**  
A: 請參考文件 **[此處](https://reference.aspose.com/tasks/java/)**。

**Q: 是否提供 Aspose.Tasks for Java 的免費試用？**  
A: 可以，您可於 **[此處](https://releases.aspose.com/)** 取得免費試用。

**Q: 如何取得 Aspose.Tasks 的臨時授權？**  
A: 請於 **[此處](https://purchase.aspose.com/temporary-license/)** 取得臨時授權。

**Q: 需要協助或有特定問題嗎？**  
A: 請造訪 Aspose.Tasks 支援論壇 **[此處](https://forum.aspose.com/c/tasks/15)**。

---

**最後更新：** 2026-09-09  
**測試環境：** Aspose.Tasks for Java 24.11（撰寫時的最新版本）  
**作者：** Aspose

## 相關教學

- [在 Aspose.Tasks 中建立專案管理任務相依性](/tasks/java/task-links/create-task-link/)
- [在 Aspose.Tasks 中設定專案開始日期與管理父子任務](/tasks/java/task-properties/parent-child-tasks/)
- [建立 MPP 專案 Java – 使用 Aspose.Tasks 變更任務進度](/tasks/java/task-properties/change-progress/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}