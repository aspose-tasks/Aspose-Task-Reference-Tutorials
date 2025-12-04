---
date: 2025-12-03
description: 了解如何使用 Aspose.Tasks for Java 輕鬆建立 Microsoft Project 行事曆、將專案轉換為 MPP，並儲存
  MPP 檔案。
language: zh-hant
linktitle: Update Calendar to MPP Format in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks 建立 MS Project 行事曆並儲存為 MPP
url: /java/calendars/update-to-mpp/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 建立日曆 MS Project 並儲存為 MPP

## 簡介

在現代專案管理中，您常常需要 **建立日曆 MS Project** 檔案，然後以原生 MPP 格式分享。無論是整合多個來源的排程，或是遷移舊有資料，能以程式方式產生日曆可節省時間並消除手動錯誤。本教學將帶您完整了解在 MS Project 中建立日曆、客製化，最後使用 Aspose.Tasks Java API **將專案轉換為 MPP** 的過程。

## 快速回答
- **本教學涵蓋什麼內容？** 使用 Aspose.Tasks for Java 在 MS Project 中建立日曆並儲存為 MPP 檔案。  
- **需要授權嗎？** 免費試用可用於開發；正式環境需購買商業授權。  
- **需要哪個 Java 版本？** Java 8 或以上 (JDK 8+)。  
- **可以自訂日曆嗎？** 可以——您可以新增工作時間、例外與假期。  
- **實作需要多久？** 基本日曆大約 10‑15 分鐘即可完成。

## 什麼是「建立日曆 MS Project」？

建立日曆 MS Project 指的是以程式方式定義工作日、工作時數與例外，這些資訊會影響 Microsoft Project 檔案中的工作排程。使用 Aspose.Tasks，您可以在不開啟 Microsoft Project 使用者介面的情況下，建立、修改並保存這些日曆。

## 為什麼要使用 Aspose.Tasks 來完成此任務？

- **完整的 .NET/Java 相容性** – 可在任何支援 Java 的平台上執行。  
- **不需要 COM 或 Office 安裝** – 非常適合伺服器端自動化。  
- **功能豐富的 API** – 支援所有日曆屬性，包括自訂工作週與假期。  
- **直接輸出 MPP** – 您可以 **儲存專案為 MPP**，無需中間轉換。

## 先決條件

1. **Java Development Kit (JDK) 8+** – 確認 `java -version` 顯示 1.8 或更新版本。  
2. **Aspose.Tasks for Java** – 從 [Aspose 官方網站](https://releases.aspose.com/tasks/java/) 下載最新的 JAR。  
3. **IDE** – IntelliJ IDEA、Eclipse，或您偏好的任何編輯器。  
4. **基本的 Java 知識** – 熟悉類別、方法與檔案 I/O。  

## 逐步指南

### 步驟 1：匯入必要的套件

首先，將 Aspose.Tasks 類別與 Java 工具類別匯入至程式範圍內。

```java
import com.aspose.tasks.*;

import java.util.Date;
import java.util.GregorianCalendar;
```

### 步驟 2：設定資料目錄

定義輸入範本與輸出檔案的存放位置。將佔位符替換為您機器上的實際路徑。

```java
String dataDir = "Your Data Directory";
```

### 步驟 3：定義輸入與輸出檔案名稱

我們會載入既有的 MPP 檔案（或空白專案），並將結果寫入新檔案。

```java
String resultFile = "OutputMpp.mpp";
String newFile = "SampleMpp.mpp";
```

### 步驟 4：載入專案並新增日曆

從來源檔案建立 `Project` 實例，並新增名為 **「Calendar 1」** 的日曆。

```java
Project project = new Project(dataDir + newFile);
Calendar cal1 = project.getCalendars().add("Calendar 1");
```

### 步驟 5：自訂日曆（可選）

若需要特定的工作時間、假期或例外，請呼叫您自訂的輔助方法。範例使用 `GetTestCalendar` 作為佔位符。

```java
GetTestCalendar(cal1); // Additional method for customizing calendar if required
```

> **專業提示：** 您可以直接操作 `cal1.getWeekDays()`，為每週的各天設定工作時數。

### 步驟 6：將日曆指派給專案

告訴專案使用新建立的日曆進行所有排程計算。

```java
project.set(Prj.CALENDAR, cal1);
```

### 步驟 7：將專案儲存為 MPP

現在透過使用 `SaveFileFormat.Mpp` 選項儲存，即可 **將專案轉換為 MPP**。

```java
project.save(dataDir + resultFile, SaveFileFormat.Mpp);
```

### 步驟 8：確認成功完成

簡單的主控台訊息會告訴您流程已順利完成，且未發生錯誤。

```java
System.out.println("Process completed Successfully");
```

## 常見使用情境

- **自動排程產生**，適用於重複性專案（例如每週衝刺）。  
- **將舊有 CSV 或 Excel 日曆** 遷移至功能完整的 MS Project 檔案。  
- **伺服器端報表**，可讓 Web 服務按需回傳 MPP 檔案。  

## 故障排除與常見問題

| 問題 | 原因 | 解決方案 |
|------|------|----------|
| `project.save` 時發生 `NullPointerException` | `dataDir` 指向不存在的資料夾 | 確保該目錄存在，或以程式方式建立它。 |
| 日曆未套用至工作 | 工作仍參考預設日曆 | 在設定 `Prj.CALENDAR` 後，若工作已被覆寫，亦需更新每個工作之 `Task.CALENDAR`。 |
| 輸出檔案為 0 KB | 缺乏寫入權限 | 以具備適當檔案系統權限的方式執行 JVM，或選擇可寫入的路徑。 |

## 常見問題

**Q: Aspose.Tasks for Java 是否相容於不同版本的 MS Project？**  
A: 是的，Aspose.Tasks for Java 支援廣泛的 MS Project 版本，從 Project 2007 到最新版本，確保無縫相容性。

**Q: 我可以依照特定專案需求自訂日曆嗎？**  
A: 當然可以。您可以定義工作日、設定自訂工作週、加入假期，甚至在單一專案檔案中建立多個日曆。

**Q: Aspose.Tasks for Java 是否提供故障排除與協助支援？**  
A: 有的，您可在 Aspose.Tasks 社群論壇取得協助，請點擊[此處](https://forum.aspose.com/c/tasks/15)。

**Q: 是否提供 Aspose.Tasks for Java 的免費試用？**  
A: 有的，完整功能的免費試用可在[此處](https://releases.aspose.com/)取得。

**Q: 如何取得 Aspose.Tasks for Java 的臨時授權？**  
A: 可透過 Aspose 官方網站申請臨時授權，請點擊[此處](https://purchase.aspose.com/temporary-license/)。

---

**最後更新：** 2025-12-03  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}