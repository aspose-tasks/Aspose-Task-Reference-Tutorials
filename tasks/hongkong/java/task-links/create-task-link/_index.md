---
date: 2026-01-20
description: 學習如何使用 Aspose.Tasks for Java 連結任務。此分步指南將向您展示如何有效地建立任務連結。
linktitle: Create Task Link in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何在 Aspose.Tasks for Java 中連結任務
url: /zh-hant/java/task-links/create-task-link/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中連結任務

## 簡介
連結任務是建立真實專案排程的核心部分，了解 **如何連結任務** 與 Aspose.Tasks for Java 可為您節省數小時的手動工作。在本教學中，您將逐步說明如何 **建立任務連結** 物件、設定前置‑後繼關係，並驗證結果——全部以清晰、可執行的程式碼示範。

## 快速解答
- **任務連結的主要類別是什麼？** `TaskLink` obtained via `project.getTaskLinks()`
- **執行範例是否需要授權？** A temporary license works for testing; a full license is required for production.
- **哪個 Maven 套件包含 Aspose.Tasks？** `com.aspose:aspose-tasks`
- **我可以連結超過兩個任務嗎？** Yes, add multiple `TaskLink` instances for complex dependencies.
- **設定需要多長時間？** Less than 10 minutes for a basic link.

## 先決條件
在深入之前，請確保您已具備以下條件：

- **Java 開發環境** – 已安裝 JDK 8 或更新版本。
- **Aspose.Tasks 程式庫** – 下載並整合 Aspose.Tasks for Java 程式庫，可於 [此處](https://releases.aspose.com/tasks/java/) 取得。

## 匯入套件
首先，匯入 Aspose.Tasks 命名空間，以便操作專案、任務與連結。

```java
import com.aspose.tasks.*;
```

## 步驟 1：設定文件目錄
定義專案檔案所在位置。此路徑讓 Aspose.Tasks 能找到來源的 MPP 檔案。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

## 步驟 2：初始化專案與任務
建立 `Project` 實例並新增兩個簡單任務。實務上會加入許多任務，但對於基本連結而言已足夠。

```java
Project project = new Project(dataDir + "project5.mpp");
Task pred = project.getRootTask().getChildren().add("Task 1");
Task succ = project.getRootTask().getChildren().add("Task 2");
```

## 步驟 3：建立任務連結
使用 `getTaskLinks()` 集合建立連結，使 **Task 1** 成為 **Task 2** 的前置任務。這正是 **如何連結任務** 的核心。

```java
TaskLink link = project.getTaskLinks().add(pred, succ);
```

## 步驟 4：顯示結果
列印確認訊息。於正式環境中，您可能會記錄連結 ID 或將更新後的專案寫回磁碟。

```java
// Display the result of the conversion.
System.out.println("Task Link Creation Process Completed Successfully");
```

### 為何建立任務連結？
- **相依性管理** – 根據前置限制自動計算開始/結束日期。
- **清晰可視化** – 甘特圖呈現真實的任務關係。
- **降低風險** – 在規劃階段即防止排程衝突。

### 常見陷阱與技巧
- **缺少授權** – 若未持有有效授權，API 會以評估模式執行，可能會加入浮水印。
- **路徑錯誤** – 確認 `dataDir` 以檔案分隔符 (`/` 或 `\`) 結尾，以免發生 `FileNotFoundException`。
- **多重連結** – 新增多個連結時，請驗證每個前置‑後繼配對，避免形成循環相依。

## 結論
透過上述步驟，您現在已了解如何使用 Aspose.Tasks for Java **連結任務**，並見到 **建立任務連結** 的實作範例。歡迎自行擴充程式碼：加入延遲時間、變更連結類型（FS、SS、FF、SF），或遍歷任務集合以建立複雜排程。若遇到問題，請參考 [Aspose.Tasks 文件](https://reference.aspose.com/tasks/java/) 或在 [Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15) 向社群求助。

## 常見問答
### Q: 我可以將 Aspose.Tasks for Java 與其他 Java 框架一起使用嗎？
A: 可以，Aspose.Tasks 可無縫整合至各種 Java 框架，提升其彈性。

### Q: 在購買程式庫前，有提供免費試用嗎？
A: 有，您可透過 [免費試用](https://releases.aspose.com/) 先行體驗功能，再決定是否購買。

### Q: 如何取得 Aspose.Tasks for Java 的臨時授權？
A: 可於 [此處](https://purchase.aspose.com/temporary-license/) 取得臨時授權，用於測試與評估。

### Q: 是否有可供參考的範例專案？
A: 有，請查閱文件以取得完整的範例專案與程式碼片段。

### Q: 推薦的 Aspose.Tasks for Java 購買方式是什麼？
A: 請前往 [購買頁面](https://purchase.aspose.com/buy) 取得授權，並了解各種授權方案。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-01-20  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose