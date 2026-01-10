---
date: 2026-01-10
description: 學習如何停止指派、管理資源指派，並在 Aspose.Tasks for Java 中查看資源指派範例，本分步教學將為您說明。
linktitle: Stop and Resume Resource Assignments in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何在 Aspose.Tasks 中停止指派並恢復資源指派
url: /zh-hant/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中停止指派並恢復資源指派

## Introduction
在本教學中，**您將了解如何停止指派**，以及稍後使用 Aspose.Tasks for Java 重新啟動它。Aspose.Tasks 是一個功能強大的 Java API，讓您能讀取專案檔案的 Java 格式，操作 Microsoft Project 資料，並在未安裝 Microsoft Project 的情況下管理資源指派。我們將逐步說明每一步，解釋每行程式碼的意義，並提供您可套用於實務專案的實用技巧。

## Quick Answers
- **「停止指派」是什麼意思？** 它會將資源指派標記為自特定停止日期起暫時不活動。  
- **我可以稍後恢復相同的指派嗎？** 可以，透過在同一指派上設定恢復日期。  
- **使用此 API 是否需要 Microsoft Project？** 不需要，Aspose.Tasks 可獨立於 Microsoft Project 使用。  
- **需要哪個版本的 Java？** 建議使用 Java 8 或更高版本。  
- **在哪裡可以下載此函式庫？** 請前往官方 Aspose.Tasks Java 下載頁面。

## 在 Aspose.Tasks 中「如何停止指派」是什麼意思？
停止指派會告訴排程器在 **停止日期** 之後（若有設定恢復日期則至 **恢復日期**）忽略分配給資源的工作。這在處理假期、設備停機或任何資源不應被視為活躍的期間時非常有用。

## 為什麼使用 Aspose.Tasks 來管理資源指派？
- **不需要 Microsoft Project** – 可直接處理 .mpp 檔案。  
- **完整的日期控制** – 您可以以程式方式檢查停止日期、恢復日期，並進行調整。  
- **跨平台** – 可在任何支援 Java 的作業系統上執行。  
- **豐富的 API** – 提供 *資源指派範例*，您可以擴充以進行自訂報告。

## 先決條件
在開始之前，請確保您已具備以下項目：

- 已在系統上安裝 Java Development Kit (JDK)。  
- 已下載 Aspose.Tasks for Java 函式庫。您可從 [此處](https://releases.aspose.com/tasks/java/) 下載。  
- 具備基本的 Java 程式設計知識。  

## 匯入套件
首先，讓我們在 Java 專案中匯入必要的套件：

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## 步驟 1：載入專案檔案
```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

此處我們 **讀取 Java 專案檔案** 格式（`.mpp`），並建立一個 `Project` 物件，讓我們能存取所有專案資料，包括資源指派。

## 步驟 2：遍歷資源指派
```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

我們設定一個 **最小日期** 以過濾佔位日期，然後遍歷每個指派。這是常見的 *資源指派範例* 模式，適用於需要檢查或修改指派的情況。

## 步驟 3：檢查停止與恢復日期
```java
    // Check stop date
    if (ra.get(Asn.STOP).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.STOP));
    }
    // Check resume date
    if (ra.get(Asn.RESUME).before(minDate)) {
        System.out.println("NA");
    } else {
        System.out.println(ra.get(Asn.RESUME));
    }
}
```

在此區塊中，我們 **檢查每個指派的停止日期** 與 **檢查恢復日期**。若日期早於我們的 `minDate`，則視為未設定（`"NA"`）；否則印出實際日期。此邏輯對於正確 **管理資源指派** 至關重要。

## 常見問題與解決方案
- **空值日期** – `ra.get(Asn.STOP)` 可能回傳 `null`。在呼叫 `.before(minDate)` 前加入空值檢查以防止錯誤。  
- **檔案路徑不正確** – 確認 `dataDir` 以適合您作業系統的路徑分隔符（`/` 或 `\\`）結尾。  
- **版本不匹配** – 使用最新的 Aspose.Tasks for Java 版本，以避免缺少列舉值。  

## 常見問答
### 我可以在未安裝 Microsoft Project 的情況下使用 Aspose.Tasks 嗎？
是的，Aspose.Tasks 讓您能在系統上未安裝 Microsoft Project 的情況下處理 Microsoft Project 檔案。

### 我可以在哪裡找到更多文件？
您可在 [此處](https://reference.aspose.com/tasks/java/) 找到詳細文件。

### 是否提供免費試用？
是的，您可在 [此處](https://releases.aspose.com/) 取得免費試用。

### 若遇到問題，我該如何取得支援？
您可在社群 [此處](https://forum.aspose.com/c/tasks/15) 取得支援。

### 我可以購買臨時授權嗎？
是的，您可在 [此處](https://purchase.aspose.com/temporary-license/) 購買臨時授權。

## 常見問題

**問：如何以程式方式為指派設定停止日期？**  
答：使用 `ra.set(Asn.STOP, yourDateObject);`，其中 `yourDateObject` 為 `java.util.Date` 物件。

**問：如果恢復日期早於停止日期會發生什麼？**  
答：API 不會強制時間順序；然而，排程器僅在兩個日期較晚者之後才視指派為活躍，因此您需自行驗證日期。

**問：我可以只篩選出已設定停止日期的指派嗎？**  
答：可以，遍歷 `prj.getResourceAssignments()` 並檢查 `ra.get(Asn.STOP) != null`。

**問：設定後的停止日期可以移除嗎？**  
答：將停止日期設為 `null`（`ra.set(Asn.STOP, null);`），然後儲存專案即可。

**問：Aspose.Tasks 是否支援其他與日期相關的欄位，如開始、結束或實際開始？**  
答：當然支援。`Asn` 列舉提供所有指派欄位的常數，例如 `Asn.START`、`Asn.FINISH` 等。

## 結論
透過上述步驟，您現在已了解 **如何停止指派**、檢查停止/恢復日期，並在需要時重新啟動指派。此功能讓您能更精確地 **管理資源指派**，尤其在資源假期或設備停機等情境下。歡迎擴充此範例以更新日期、產生報告，或整合至您自己的排程邏輯中。

---

**最後更新：** 2026-01-10  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}