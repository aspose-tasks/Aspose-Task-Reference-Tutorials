---
date: 2026-03-03
description: 學習如何使用 Aspose.Tasks for Java 建立專案任務（Java）並管理任務備註。請遵循此一步一步的指南，快速且有效地新增任務備註。
linktitle: Task Notes Management in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 建立專案任務（Java）– 使用 Aspose.Tasks 的任務備註
url: /zh-hant/java/task-properties/task-notes/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立專案任務 Java – 任務備註與 Aspose.Tasks

## 介紹
Aspose.Tasks for Java 提供一個強大的解決方案，讓您 **create project task java** 物件並管理相關的備註。在本教學中，我們將深入探討如何使用 Aspose.Tasks for Java 高效處理任務備註。無論您是資深開發者還是剛入門，本分步指南都會帶領您順利完成新增與取得任務備註的流程。

## 快速解答
- **我可以使用 Aspose.Tasks 管理什麼？** Project tasks, resources, schedules, and task notes.  
- **如何設定備註？** Use the `Tsk.NOTES_RTF` field on a `Task` object.  
- **支援哪種備註格式？** Rich Text Format (RTF) is fully supported.  
- **我需要授權嗎？** A free trial works for development; a commercial license is required for production.  
- **需要哪個 Java 版本？** JDK 8 or higher.

## 前置條件
在開始本教學之前，請確保您已具備以下前置條件：
- 已在電腦上安裝 Java Development Kit (JDK)。
- 已下載並設定 Aspose.Tasks for Java 程式庫。您可於此處下載 [here](https://releases.aspose.com/tasks/java/)。
- 具備基本的 Java 程式設計概念。

## 匯入套件
確保在您的 Java 專案中已匯入必要的套件：
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## 如何建立 Project Task Java
### 步驟 1：建立專案與任務
首先，您需要建立一個新的 `Project` 實例，並在其根節點加入任務。這是 **create project task java** 物件的基礎步驟。
```java
Project project = new Project();
Task task = project.getRootTask().getChildren().add("Task");
```

## 如何新增任務備註
### 步驟 2：以 RTF 格式設定備註
現在任務已建立，您可以附加備註。以下範例示範了 **how to add task notes** 於富文字格式 (RTF) 中的做法。
```java
String rtf = "{\\rtf1\\ansi\\ansicpg1252\\deff0\\deflang1033{\\fonttbl{\\f0\\fnil\\fcharset134 SimSun;}{\\f1\\fnil\\fcharset0 Calibri;}}\r\n"
        + "{\\*\\generator Msftedit 5.41.21.2510;}\\viewkind4\\uc1\\pard\\sa200\\sl276\\slmult1\\lang9\\f0\\fs22\\'d4\\'e7\\'c9\\'cf\\'ba\\'c3\\f1\\par\r\n"
        + "}\r\n"
        + "; // 早上好";
task.set(Tsk.NOTES_RTF, rtf);
```

### 步驟 3：取得並顯示備註
為了驗證備註是否正確儲存，讀取 `NOTES_RTF` 欄位並將其輸出。
```java
System.out.println("Notes RTF: " + task.get(Tsk.NOTES_RTF));
```

## 常見問題與解決方案
- **備註顯示亂碼：** Ensure the RTF string is correctly escaped and uses proper Unicode encoding.  
- **存取任務時出現 NullPointerException：** Verify that the task was added to the project hierarchy before setting notes.  
- **授權例外錯誤：** Use a valid license file or trial version; otherwise, Aspose may throw a licensing error.  

## 常見問答
### 我可以免費使用 Aspose.Tasks for Java 嗎？
Yes, you can download a free trial [here](https://releases.aspose.com/).

### 我在哪裡可以找到詳細文件？
Refer to the documentation [here](https://reference.aspose.com/tasks/java/).

### 如何取得 Aspose.Tasks for Java 的支援？
Visit the support forum [here](https://forum.aspose.com/c/tasks/15).

### 是否提供臨時授權？
Yes, you can obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).

### 我該從哪裡購買 Aspose.Tasks for Java？
You can buy the product [here](https://purchase.aspose.com/buy).

#### Additional Q&A
**Q: 我可以將備註儲存為純文字而非 RTF 嗎？**  
A: Yes, you can use the `Tsk.NOTES` field for plain‑text notes, but RTF preserves formatting.

**Q: 任務儲存後可以更新備註嗎？**  
A: Absolutely. Call `task.set(Tsk.NOTES_RTF, newRtf)` and then save the project.

**Q: Aspose.Tasks 支援多語言備註嗎？**  
A: Yes, as long as the RTF string is encoded correctly (UTF‑8) and the appropriate fonts are available.

## 結論
在 Aspose.Tasks for Java 中管理任務備註相當簡單，只要您了解 **how to create project task java** 物件並附加 RTF 備註。現在您已掌握必要的程式碼片段，可在 Java 應用程式中新增、取得與排除任務備註的問題。

---

**最後更新：** 2026-03-03  
**測試環境：** Aspose.Tasks for Java 24.11 (latest)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}