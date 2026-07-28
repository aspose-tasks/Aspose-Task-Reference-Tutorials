---
date: 2026-02-05
description: 學習如何將假期加入日曆、將日曆指派給專案，並使用 Aspose.Tasks for Java 將 MS Project 檔案儲存為 MPP。
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 將假期加入行事曆並以 MPP 格式儲存（使用 Aspose.Tasks）
url: /zh-hant/java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 為日曆新增假期並以 Aspose.Tasks 儲存為 MPP

## 介紹

在現代專案管理中，您常常需要 **將假期新增至日曆** 檔案、建立 **MS Project 日曆**，然後以原生 MPP 格式分享排程。無論是整合多個來源的時間線，或是遷移舊有資料，程式化產生日曆都能消除手動錯誤並加快交付速度。本教學將帶您完整了解如何在 MS Project 中建立日曆、以假期自訂、**將日曆指派給專案**，最後使用 Aspose.Tasks Java API **將專案轉換為 MPP**。

## 快速回答
- **本教學涵蓋什麼內容？** 將假期新增至日曆、將日曆指派給專案，並使用 Aspose.Tasks for Java 將結果儲存為 MPP 檔案。  
- **需要授權嗎？** 開發階段可使用免費試用版；正式上線需購買商業授權。  
- **需要哪個 Java 版本？** Java 8 或以上 (JDK 8+)。  
- **可以自訂日曆嗎？** 可以——您可以新增工作時間、例外與假期。  
- **實作大約需要多久？** 基本日曆約 10‑15 分鐘即可完成。  

## 什麼是「建立 MS Project 日曆」？

建立 MS Project 日曆指的是以程式方式定義工作日、工作時段與例外（如假期），這些設定會影響 Microsoft Project 檔案內的工作排程。透過 Aspose.Tasks，您可以 **java create project calendar**、修改它，且無需開啟 Microsoft Project UI 即可將變更寫入檔案。

## 為什麼要使用 Aspose.Tasks 完成此任務？

- **完整的 .NET/Java 相容性** – 可在任何支援 Java 的平台上執行。  
- **不需 COM 或 Office 安裝** – 非常適合伺服器端自動化與 **automate schedule generation**。  
- **功能豐富的 API** – 支援所有日曆屬性，包括自訂工作週與假期。  
- **直接輸出 MPP** – 您可以 **save project as MPP**，無需中間轉換。

## 前置條件

1. **Java Development Kit (JDK) 8+** – 確認 `java -version` 顯示 1.8 或更新版本。  
2. **Aspose.Tasks for Java** – 從 [Aspose website](https://releases.aspose.com/tasks/java/) 下載最新 JAR。  
3. **IDE** – IntelliJ IDEA、Eclipse 或您慣用的編輯器。  
4. **基本的 Java 知識** – 熟悉類別、方法與檔案 I/O。

## 如何為日曆新增假期

以下將逐步說明從環境設定到最終產出 MPP 檔案的完整流程。程式碼區塊保持原樣，說明文字已擴充說明。

### 步驟 1：匯入必要的套件

首先，將 Aspose.Tasks 類別與 Java 工具類別匯入作用域。

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### 步驟 2：設定資料目錄

定義輸入範本與輸出檔案的存放位置。請將佔位符替換為您機器上的實際路徑。

```java
String dataDir = "Your Data Directory";
```

### 步驟 3：定義輸入與輸出檔案名稱

我們會載入既有的 MPP 檔（或空白專案），並將結果寫入新檔案。

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### 步驟 4：載入專案並新增日曆

從來源檔案建立 `Project` 實例，並新增一個名為 **「Calendar 1」** 的日曆。

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### 步驟 5：自訂日曆（可選）

如果需要特定的工作時間、假期或例外，呼叫您自己的輔助方法。範例使用 `GetTestCalendar` 作為佔位。

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **專業提示：** 您可以直接操作 `cal1.getWeekDays()` 來設定每週各日的工作時段，或使用 `cal1.getExceptions()` **將假期新增至日曆**。

### 步驟 6：將日曆指派給專案

告訴專案使用新建立的日曆進行所有排程計算。

```java
project.set(Prj.CALENDAR, cal1);
```

### 步驟 7：將專案儲存為 MPP

現在使用 `SaveFileFormat.Mpp` 選項 **convert project to MPP**，將專案儲存為 MPP 檔。

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### 步驟 8：確認成功完成

簡單的主控台訊息會告訴您流程已順利結束，且未發生錯誤。

```java
System.out.println("Process completed Successfully");
```

## 常見使用情境

- **自動化排程產生**，適用於週期性專案（例如每週衝刺）。  
- **將舊有 CSV 或 Excel 日曆遷移** 至功能完整的 MS Project 檔案。  
- **伺服器端報表**，讓 Web 服務即時回傳 MPP 檔案。

## 疑難排解與常見陷阱

| 問題 | 原因 | 解決方案 |
|------|------|----------|
| `NullPointerException` on `project.save` | `dataDir` 指向不存在的資料夾 | 確保目錄存在，或以程式方式建立它。 |
| 日曆未套用至工作項目 | 工作項目仍參考預設日曆 | 在設定 `Prj.CALENDAR` 後，若先前已覆寫，亦需更新每個工作項目的 `Task.CALENDAR`。 |
| 輸出檔案為 0 KB | 缺少寫入權限 | 以適當的檔案系統權限執行 JVM，或選擇可寫入的路徑。 |

## 常見問與答

**Q:** Aspose.Tasks for Java 是否相容於不同版本的 MS Project？  
**A:** 是的，Aspose.Tasks for Java 支援廣泛的 MS Project 版本，從 Project 2007 到最新發行版，確保無縫相容。

**Q:** 我可以依照特定專案需求自訂日曆嗎？  
**A:** 當然可以。您可以定義工作日、設定自訂工作週、加入假期，甚至在同一專案檔中建立多個日曆。

**Q:** Aspose.Tasks for Java 是否提供疑難排解與協助支援？  
**A:** 有，您可以在 Aspose.Tasks 社群論壇 [here](https://forum.aspose.com/c/tasks/15) 取得協助。

**Q:** 是否有 Aspose.Tasks for Java 的免費試用版？  
**A:** 有，完整功能的免費試用版可在 [here](https://releases.aspose.com/) 取得。

**Q:** 如何取得 Aspose.Tasks for Java 的臨時授權？  
**A:** 可透過 Aspose 官方網站的 [here](https://purchase.aspose.com/temporary-license/) 申請臨時授權。

---

**最後更新：** 2026-02-05  
**測試版本：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}