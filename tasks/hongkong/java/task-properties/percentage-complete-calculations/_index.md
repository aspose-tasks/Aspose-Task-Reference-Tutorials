---
date: 2026-02-23
description: 探索 Aspose.Tasks for Java，簡化專案管理，並學習如何計算任務百分比及有效追蹤進度。
linktitle: Percentage Complete Calculations for Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 專案管理 Java：使用 Aspose.Tasks 的任務完成百分比
url: /zh-hant/java/task-properties/percentage-complete-calculations/
weight: 25
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 專案管理 Java：使用 Aspose.Tasks 計算工作完成百分比

## 介紹
歡迎閱讀我們關於 **project management java**，使用 Aspose.Tasks for Java 的完整教學。本教學將教您如何讀取 Microsoft Project 檔案、計算已完成工作量，並取得每個工作項目的精確進度百分比。掌握這些計算可讓您即時向利害關係人報告，確保專案如期進行。

## 快速回答
- **哪個函式庫負責在 Java 中處理 Microsoft Project 檔案？** Aspose.Tasks for Java。  
- **哪個屬性顯示整體進度？** `Tsk.PERCENT_COMPLETE`。  
- **如何讀取 .mpp 檔案？** 使用 `new Project(filePath)` 載入。  
- **我可以計算已完成的工作量嗎？** 可以，使用 `Tsk.PERCENT_WORK_COMPLETE`。  
- **正式環境需要授權嗎？** 必須使用有效的 Aspose.Tasks 授權。

## 什麼是 Project Management Java？
Project management java 指的是使用基於 Java 的工具與函式庫（如 Aspose.Tasks）以程式方式建立、讀取與操作專案排程。此方式可實現自動化報表、客製化儀表板，並與現有的 Java 應用程式無縫整合。

## 為什麼使用 Aspose.Tasks 計算工作百分比？
- **精確的進度追蹤** – 直接取得原生 Project 欄位，免除手動解析。  
- **完整的 .mpp 支援** – 直接讀取、編輯與儲存 Microsoft Project 檔案。  
- **可擴充的自動化** – 在秒級內處理成千上萬的工作項目，適合大型投資組合。  
- **跨平台** – 可在任何 Java 執行環境上執行，從桌面到雲端服務皆適用。

## 前置條件
開始之前，請確保您已具備：

- 已安裝 **Java Development Kit (JDK)**（Java 8 或更新版本）。  
- **Aspose.Tasks for Java** 函式庫 – 可從 [this link](https://releases.aspose.com/tasks/java/) 下載。  
- 一個範例 Microsoft Project 檔案（例如 *Software Development.mpp*），並放置於已知目錄下。

## 匯入套件
首先，匯入您需要的類別。此程式碼片段應加入任何使用 Aspose.Tasks 的 Java 類別中。

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.TaskCollection;
import com.aspose.tasks.Tsk;
```

### 步驟 1：設定文件目錄
定義包含 *.mpp* 檔案的資料夾。將佔位符替換為您機器上的實際路徑。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### 步驟 2：載入專案檔案
建立 `Project` 實例並載入 Microsoft Project 檔案。此步驟 **讀取 Microsoft Project 檔案**，讓您可以存取其工作項目。

```java
Project project = new Project(dataDir + "Software Development.mpp");
```

### 步驟 3：取得工作項目集合
取得根工作項目，然後取得其子工作項目。此集合代表專案中所有的最高層工作項目。

```java
TaskCollection alTasks = project.getRootTask().getChildren();
```

### 步驟 4：列印百分比完成值
遍歷每個工作項目，顯示三個關鍵進度指標：

- **Percentage Complete** – 整體工作進度。  
- **Percentage Work Complete** – 基於工作量的進度。  
- **Physical Percentage Complete** – 物理進度（若已設定）。

```java
for (Task tsk : alTasks) {
    System.out.println(tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println(tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println(tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
}
```

對每個需要監控的工作項目執行此迴圈。輸出將為您提供 **如何取得每項工作進度** 的清晰快照。

## 常見使用情境
- **儀表板報表**：擷取百分比並輸入 BI 工具。  
- **自動化警示**：當工作項目的 `PERCENT_COMPLETE` 低於門檻時觸發通知。  
- **資源平衡**：根據 `PERCENT_WORK_COMPLETE` 調整指派，以維持排程的現實性。

## 疑難排解與技巧
- **空值**：確保專案檔案實際包含您查詢的欄位；某些較舊的 .mpp 檔案可能缺少 `PHYSICAL_PERCENT_COMPLETE`。  
- **效能**：對於非常大型的專案，考慮分頁讀取 `TaskCollection` 或依工作項目 ID 篩選，以降低記憶體使用量。  
- **授權錯誤**：若看到授權警告，請在建立 `Project` 物件之前先載入有效的 Aspose.Tasks 授權檔案。

## 常見問題

**Q: 在哪裡可以找到 Aspose.Tasks 的文件說明？**  
A: 文件說明可於 [here](https://reference.aspose.com/tasks/java/) 取得。

**Q: 如何下載 Aspose.Tasks for Java 函式庫？**  
A: 您可於 [here](https://releases.aspose.com/tasks/java/) 下載。

**Q: 有提供免費試用嗎？**  
A: 有，您可於 [here](https://releases.aspose.com/) 取得免費試用。

**Q: 在哪裡可以獲得 Aspose.Tasks 的支援？**  
A: 請前往支援論壇 [here](https://forum.aspose.com/c/tasks/15)。

**Q: 如何取得臨時授權？**  
A: 您可於 [here](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

**其他問答**

**Q: 可以不使用 Aspose.Tasks 計算工作百分比嗎？**  
A: 您可以自行解析 .mpp 二進位檔，但 Aspose.Tasks 提供可靠且完整支援的 API，能處理所有邊緣情況。

**Q: Aspose.Tasks 支援讀取 Project Online 檔案嗎？**  
A: 支援，只要檔案以 .mpp 格式匯出，即可載入。

---

**最後更新：** 2026-02-23  
**測試環境：** Aspose.Tasks for Java 24.11（最新）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}