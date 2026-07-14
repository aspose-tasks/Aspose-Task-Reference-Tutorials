---
date: 2026-07-14
description: 了解如何停止 Java 資源指派、管理資源指派，並在本分步指南中查看使用 Aspose.Tasks for Java 的範例。
keywords:
- stop resource assignment java
- Aspose.Tasks Java
- resource assignment management
- project scheduling Java
lastmod: 2026-07-14
linktitle: 在 Aspose.Tasks 中停止與恢復資源指派
og_description: 使用 Aspose.Tasks 停止 Java 資源指派。本教學說明如何暫停與恢復指派、處理日期，以及在不使用 Microsoft
  Project 的情況下整合 API。
og_image_alt: Guide to stop and resume resource assignments in Aspose.Tasks for Java
og_title: 停止資源指派（Java） – Aspose.Tasks 指南
schemas:
- author: Aspose
  dateModified: '2026-07-14'
  description: Learn how to stop resource assignment java, manage resource assignments,
    and view examples using Aspose.Tasks for Java in this step‑by‑step guide.
  headline: How to Stop Resource Assignment Java – Resume with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Use `ra.set(Asn.STOP, yourDateObject);` where `yourDateObject` is a `java.util.Date`.
    question: How do I programmatically set a stop date for an assignment?
  - answer: The API does not enforce chronological order; however, the scheduler will
      treat the assignment as active only after the later of the two dates, so you
      should validate dates yourself.
    question: What happens if the resume date is earlier than the stop date?
  - answer: Yes, iterate through `prj.getResourceAssignments()` and check `ra.get(Asn.STOP)
      != null`.
    question: Can I filter assignments to only those that have a stop date set?
  - answer: Set the stop date to `null` with `ra.set(Asn.STOP, null);` and then save
      the project.
    question: Is it possible to remove a stop date once set?
  - answer: Absolutely. The `Asn` enum provides constants for all assignment fields,
      such as `Asn.START`, `Asn.FINISH`, etc.
    question: Does Aspose.Tasks support other date‑related fields like start, finish,
      or actual start?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- stop resource assignment
- Aspose.Tasks
- Java project scheduling
- resource management
title: 如何停止資源指派（Java） – 以 Aspose.Tasks 繼續
url: /zh-hant/java/resource-assignments/stop-resume-assignment/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何停止資源指派（Java） – 使用 Aspose.Tasks 重新啟動

## 簡介
在本教學中，您將學習 **how to stop resource assignment java**，並稍後使用 Aspose.Tasks for Java 重新啟動它。Aspose.Tasks 是一個功能強大的 Java API，可讓您讀寫 Microsoft Project 檔案、操作排程，並控制資源指派——完全不需要安裝 Microsoft Project。我們將逐步說明每個步驟，解釋每行程式碼的意義，並分享可在實務專案計畫中應用的實用技巧。

## 快速答覆
- **What does “stop assignment” mean?** 它將資源指派標記為自特定停止日期起暫時不活躍。  
- **Can I resume the same assignment later?** 可以，透過在同一指派上設定重新啟動日期。  
- **Do I need Microsoft Project to use this API?** 不需要，Aspose.Tasks 可獨立於 Microsoft Project 使用。  
- **Which Java version is required?** 建議使用 Java 8 或更高版本。  
- **Where can I download the library?** 從官方的 Aspose.Tasks Java 下載頁面取得。

## 如何停止資源指派（Java）？
載入您的專案，找到目標 `ResourceAssignment`，設定 `STOP` 日期，必要時設定 `RESUME` 日期，然後儲存檔案。此流程會在指定期間暫停工作，並在重新啟動日期後自動重新啟用，讓您能精確控制資源行事曆，無需手動編輯檔案。

## 在 Aspose.Tasks 中，「how to stop assignment」是什麼意思？
停止指派會告訴排程器在 **stop date** 之後（直到 **resume date**，若有）忽略分配給資源的工作。這在處理假期、設備停機或任何資源不應被視為活躍的期間時非常有用。

## 為什麼使用 Aspose.Tasks 來管理資源指派？
Aspose.Tasks 讓您以程式方式控制指派日期，省去手動編輯並降低錯誤風險。它支援 **50 多種輸入與輸出格式**，且能處理 **多達 10,000 個工作**的專案，同時因為採用串流資料而將記憶體使用量控制在 200 MB 以下，而非一次載入整個檔案。此 API 可在任何支援 Java 的作業系統上執行，提供跨平台的彈性。

## 先決條件
在開始之前，請確保您已具備：

- 已安裝 Java Development Kit (JDK) 8 或更新版本。  
- 已下載 Aspose.Tasks for Java 函式庫。您可從 [here](https://releases.aspose.com/tasks/java/) 下載。  
- 基本的 Java 程式設計知識。

## 匯入套件
`Project`、`ResourceAssignment` 與 `Asn` 類別位於 `com.aspose.tasks` 命名空間。請在來源檔案的頂部匯入它們：

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
import java.util.Calendar;
import java.util.GregorianCalendar;
import java.util.Objects;
```

## 步驟 1：載入專案檔案
`Project` 類別是 Aspose.Tasks 的頂層物件，代表記憶體中的單一 Microsoft Project 檔案。建立實例即會載入檔案，並讓您存取工作、資源與指派。

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
// Load the project file
Project prj = new Project(dataDir + "ResourceAssignmentVariance.mpp");
```

## 步驟 2：遍歷資源指派
`ResourceAssignment` 物件會顯示所有與指派相關的欄位。我們設定 **minimum date** 以過濾佔位日期，然後遍歷每個指派。此模式是檢查或修改的標準 *resource assignment example*。

```java
// Define minimum date
java.util.Date minDate = new GregorianCalendar(2000, Calendar.JANUARY, 1).getTime();
// Iterate through resource assignments
for (ResourceAssignment ra : prj.getResourceAssignments()) {
```

## 步驟 3：檢查停止與重新啟動日期
在此區塊中，我們檢查每個指派的 `STOP` 與 `RESUME` 欄位。若日期早於我們的 `minDate`，則視為未設定（`"NA"`）；否則印出實際日期。此邏輯對正確 **manage resource assignments** 至關重要。

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

## 常見問題與解決方案
- **Null dates** – `ra.get(Asn.STOP)` 可能回傳 `null`。在呼叫 `.before(minDate)` 前加入 null 檢查以防止錯誤。  
- **Incorrect file path** – 確認 `dataDir` 以適合您作業系統的路徑分隔符（`/` 或 `\\`）結尾。  
- **Version mismatch** – 使用最新的 Aspose.Tasks for Java 版本，以避免缺少列舉值。

## 常見問與答

**Q: 如何以程式方式為指派設定停止日期？**  
A: 使用 `ra.set(Asn.STOP, yourDateObject);`，其中 `yourDateObject` 為 `java.util.Date`。

**Q: 如果重新啟動日期早於停止日期會發生什麼情況？**  
A: API 不會強制時間順序；然而，排程器僅在兩個日期中較晚的那一天之後才視指派為活躍，因此您應自行驗證日期。

**Q: 我可以只篩選出已設定停止日期的指派嗎？**  
A: 可以，遍歷 `prj.getResourceAssignments()` 並檢查 `ra.get(Asn.STOP) != null`。

**Q: 設定後可以移除停止日期嗎？**  
A: 使用 `ra.set(Asn.STOP, null);` 將停止日期設為 `null`，然後儲存專案。

**Q: Aspose.Tasks 是否支援其他與日期相關的欄位，如開始、完成或實際開始？**  
A: 當然。`Asn` 列舉提供所有指派欄位的常數，例如 `Asn.START`、`Asn.FINISH` 等。

## 結論
透過上述步驟，您現在已了解 **how to stop resource assignment java**，能檢查停止/重新啟動日期，並在需要時重新啟動指派。此功能讓您能更精確地 **manage resource assignments**，尤其在資源休假或設備停機等情境下。歡迎擴充此範例以更新日期、產生報表，或整合至您自己的排程邏輯中。

---

**最後更新：** 2026-07-14  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose

## 相關教學

- [在 Aspose.Tasks 中建立資源指派](/tasks/java/resource-assignments/create-resource-assignments/)
- [如何計算成本差異並管理指派成本（Aspose.Tasks）](/tasks/java/resource-assignments/assignment-cost/)
- [如何在 Aspose.Tasks 中為資源指派新增備註](/tasks/java/resource-assignments/resource-assignment-notes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}