---
date: 2025-12-31
description: 了解如何設定專案開始日期、寫入專案資訊，並使用 Aspose.Tasks for Java 將專案儲存為 XML。
linktitle: Write Project Info in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks for Java 在 MS Project 中設定專案開始日期
url: /zh-hant/java/project-properties/write-project-info/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 MS Project 中使用 Aspose.Tasks for Java 設定專案開始日期

## 簡介
在本教學中，您將學習如何 **設定專案開始日期**，以及使用 Aspose.Tasks for Java 撰寫其他 MS Project 資訊。無論您是自動化專案排程、產生報告，或將 Project 資料整合至更大的系統，程式化控制開始日期都能讓您精確掌握時間線。我們將逐步說明每個步驟——從環境設定到將更新後的專案儲存為 XML 檔案——讓您立即能運用這些技巧。

## 快速解答
- **什麼是操作專案的主要類別？** 來自 Aspose.Tasks 函式庫的 `Project`。  
- **如何設定專案開始日期？** 使用 `project.set(Prj.START_DATE, <date>)`。  
- **我也可以設定狀態日期嗎？** 可以，使用 `project.set(Prj.STATUS_DATE, <date>)`。  
- **應使用哪種格式匯出專案？** 使用 `SaveFileFormat.Xml` 以 XML 格式儲存。  
- **在正式環境使用是否需要授權？** 需要有效的 Aspose.Tasks 授權才能取得完整功能。

## 什麼是 **設定專案開始日期**？
設定專案開始日期即定義所有排程任務開始的日曆日期。它是任務工期、相依性與關鍵路徑等計算的基準點。透過程式化設定此日期，可確保多個專案檔案之間的一致性，並避免手動輸入錯誤。

## 為什麼使用 Aspose.Tasks for Java 來寫入專案資訊？
- **完整 API 覆蓋：** 可讀取、修改與寫入每個 Project 屬性，無需安裝 Microsoft Project。  
- **跨平台：** 可在 Windows、Linux 與 macOS 上執行。  
- **自動化就緒：** 非常適合批次處理、CI 流程或即時產生專案排程的後端服務。

## 先決條件
在開始之前，請確保您已具備：

1. **Java Development Kit (JDK)** – 任意較新版本（建議 8 以上）。  
2. **Aspose.Tasks for Java 函式庫** – 從 [here](https://releases.aspose.com/tasks/java/) 下載。  
3. **IDE** – 如 IntelliJ IDEA、Eclipse，或您喜愛的 Java 編輯器。  

## 匯入套件
First, import the necessary packages in your Java project:
```java
import com.aspose.tasks.*;
import java.util.Calendar;
```

## 步驟 1：設定資料目錄
Define the directory where your project data will be stored.
```java
String dataDir = "Your Data Directory";
```

## 步驟 2：建立 Project 實例
Initialize a new project instance.
```java
Project project = new Project();
```

## 步驟 3：設定專案資訊屬性
Here we set the **project start date**, schedule from start, and status date—covering the primary and secondary keywords *write project information* and *how to set status*.
```java
project.set(Prj.SCHEDULE_FROM_START, new NullableBool(true));
java.util.Calendar cal = java.util.Calendar.getInstance();
cal.set(2014, Calendar.JULY, 10);
project.set(Prj.START_DATE, cal.getTime());
project.set(Prj.CURRENT_DATE, cal.getTime());
project.set(Prj.STATUS_DATE, cal.getTime());
```

## 步驟 4：將專案儲存為 XML
Finally, persist the updated project file. This demonstrates the secondary keyword **save project as xml**.
```java
project.save(dataDir + "project3.xml", SaveFileFormat.Xml);
```

## 常見問題與解決方案
| 問題 | 原因 | 解決方法 |
|------|------|----------|
| **開始日期不正確** | Java 中的月份是從零開始計算的。 | 如範例所示，使用 `Calendar.JULY`（或將月份索引加 1）。 |
| **檔案未儲存** | `dataDir` 不存在或沒有寫入權限。 | 事先建立目錄或選擇可寫入的路徑。 |
| **授權警告** | 未使用授權會在輸出檔案加上浮水印。 | 在建立 `Project` 物件前套用有效的 Aspose.Tasks 授權。 |

## 常見問答
### Q: 我可以使用 Aspose.Tasks for Java 讀取 MS Project 檔案嗎？
A: 是的，Aspose.Tasks for Java 提供強大的功能，可讀寫 MS Project 檔案。

### Q: Aspose.Tasks for Java 是否相容於不同版本的 MS Project？
A: 當然，Aspose.Tasks for Java 支援多種 MS Project 版本，確保不同檔案格式之間的相容性。

### Q: Aspose.Tasks for Java 試用版有什麼限制嗎？
A: 雖然試用版讓您體驗函式庫的功能，但會有一些限制，例如輸出檔案會加上浮水印。

### Q: 我該如何取得 Aspose.Tasks for Java 的支援？
A: 您可前往 Aspose.Tasks 社群論壇取得協助，連結在 [here](https://forum.aspose.com/c/tasks/15)。

### Q: 我可以購買 Aspose.Tasks for Java 的臨時授權嗎？
A: 可以，提供短期使用的臨時授權。您可從 [here](https://purchase.aspose.com/temporary-license/) 取得。

## 結論
您現在已學會如何使用 Aspose.Tasks for Java **設定專案開始日期**、寫入必要的專案資訊，並 **將專案儲存為 XML**。這些基礎構件讓您能自動化專案管理工作流程、產生一致的排程，並將 MS Project 資料整合至 Java 應用程式中。

---

**最後更新：** 2025-12-31  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}