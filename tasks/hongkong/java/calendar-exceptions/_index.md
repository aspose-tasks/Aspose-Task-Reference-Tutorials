---
date: 2026-08-18
description: 輕鬆建立自訂日曆例外、整合 MS Project 日曆，並在 Java 專案中使用 Aspose.Tasks 管理、定義、處理及取得日曆例外。簡化專案工作流程，提高專案管理效率。
keywords:
- create calendar exceptions
- manage project calendar
- set nonworking days
- modify ms project calendar
lastmod: 2026-08-18
linktitle: 日曆例外
og_description: 了解如何使用 Aspose.Tasks 在 Java 中建立日曆例外、管理專案日曆及設定非工作日。開發人員快速指南。
og_image_alt: Developer guide showing Java code to create calendar exceptions with
  Aspose.Tasks
og_title: 如何使用 Aspose.Tasks for Java 建立日曆例外
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Effortlessly create custom calendar exceptions, integrate MS Project
    calendar, and manage, define, handle & retrieve calendar exceptions in Java projects
    with Aspose.Tasks. Streamline project workflows for efficient project management.
  headline: How to create calendar exceptions with Aspose.Tasks for Java
  type: TechArticle
- description: Effortlessly create custom calendar exceptions, integrate MS Project
    calendar, and manage, define, handle & retrieve calendar exceptions in Java projects
    with Aspose.Tasks. Streamline project workflows for efficient project management.
  name: How to create calendar exceptions with Aspose.Tasks for Java
  steps:
  - name: Load the project file.
    text: Load the project file.
  - name: Retrieve or create a `Calendar` instance.
    text: Retrieve or create a `Calendar` instance.
  - name: Define the exception’s date range and working time.
    text: Define the exception’s date range and working time.
  - name: (Optional) Configure recurrence for annual holidays.
    text: (Optional) Configure recurrence for annual holidays.
  - name: Save the project.
    text: Save the project.
  type: HowTo
- questions:
  - answer: Yes. Use the add‑remove and define‑weekdays APIs to update the calendar,
      then re‑save the project file.
    question: Can I modify calendar exceptions after a project is already published?
  - answer: Absolutely. The “handle occurrences” tutorial covers how to set up recurring
      patterns.
    question: Does Aspose.Tasks support recurring exceptions (e.g., every first Monday
      of the month)?
  - answer: Assign the calendar to the project’s default calendar or explicitly set
      it on each task’s `Calendar` property.
    question: How do I ensure my custom calendar is used by all tasks in the project?
  - answer: Yes. Retrieve each calendar, combine their exceptions programmatically,
      and then assign the merged calendar to the target project.
    question: Is it possible to merge calendars from multiple MS Project files?
  - answer: All features are available in the current stable release of Aspose.Tasks
      for Java (2025.x).
    question: What version of Aspose.Tasks is required for these features?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendar exceptions
- Aspose.Tasks
- Java project scheduling
title: 如何使用 Aspose.Tasks for Java 建立日曆例外
url: /zh-hant/java/calendar-exceptions/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks for Java 建立行事曆例外

## 介紹

`Aspose.Tasks` 是一個 Java 函式庫，可程式化建立、操作與轉換 Microsoft Project 檔案。在本教學中，您將學習如何 **建立行事曆例外**——自訂的非工作期間，可覆寫專案的預設行事曆。對工作日與非工作日的精確控制對於準確的排程預測、資源分配以及符合區域假期至關重要。完成本指南後，您還將了解如何 **將 MS Project 行事曆整合**到您的 Java 應用程式中，並取得或修改其例外設定。

## 快速解答
- **我可以達成什麼？** 在 Java 專案中建立、修改與取得自訂的行事曆例外。  
- **需要哪個函式庫？** Aspose.Tasks for Java（最新穩定版）。  
- **需要授權嗎？** 是的，正式使用時需要有效的 Aspose.Tasks 授權。  
- **可以處理 MS Project 檔案嗎？** 當然可以——您能匯入、編輯與匯出 MS Project 行事曆資料。  
- **需要任何特殊設定嗎？** 只需將 Aspose.Tasks JAR 加入 classpath，並匯入相關類別即可。

## 如何在 Aspose.Tasks for Java 中建立自訂行事曆例外？

`Project` 類別代表一個 Microsoft Project 檔案，並提供對其內容的存取。  
`Calendar` 物件定義專案的工作與非工作時間。  
`addException()` 方法會在行事曆中新增一個例外。

使用 `Project project = new Project("example.mpp")` 載入目標專案，取得其 `Calendar` 物件，並以所需的日期範圍與工作時間設定呼叫 `addException()`。此兩步驟模式會立即建立新例外，並在您儲存專案時持久化。若為重複假期，請在儲存前於例外上設定 `RecurrencePattern`。

以此方式建立行事曆例外可讓您精確 **設定非工作日**，無論是一次性停工還是年度假期。例外加入後，您可以呼叫 `project.save("updated.mpp")` 將變更寫回磁碟。

### 步驟概覽
1. 載入專案檔案。  
2. 取得或建立 `Calendar` 實例。  
3. 定義例外的日期範圍與工作時間。  
4. (可選) 為年度假期設定重複規則。  
5. 儲存專案。

## 在 Aspose.Tasks 中管理行事曆例外
[了解如何在 Aspose.Tasks for Java 中高效新增與移除行事曆例外](./add-remove/)。在專案管理中，彈性是關鍵。Aspose.Tasks 讓您輕鬆管理行事曆例外，從而動態調整專案時間表。本教學提供逐步指南，確保您能有效掌握流程。探索如何輕鬆提升您的專案管理工作流程。

## 使用 Aspose.Tasks 定義行事曆例外的工作日
[精通在 Java 專案中為行事曆例外定義工作日的技巧](./define-weekdays/)。精確的專案排程需要細緻的注意。使用 Aspose.Tasks，您可以精確定義行事曆例外的工作日，確保專案無縫符合特定時間表。本教學提供優化排程的知識，讓您掌控專案時間線。

## 使用 Aspose.Tasks 處理行事曆例外的發生次數
[有效處理 Java 專案中的行事曆例外](./handle-occurrences/)。專案管理是一個動態過程，常需因應不可預見的情況進行調整。Aspose.Tasks 讓您能有效處理行事曆例外，提供精簡的專案管理方式。透過本詳細教學，輕鬆學會管理專案不確定性。

## 使用 Aspose.Tasks 取得行事曆例外
[了解如何使用 Aspose.Tasks for Java 從 MS Project 取得行事曆例外](./retrieve/)。使用 Aspose.Tasks 無縫將行事曆例外整合至您的專案管理流程。本教學逐步說明如何取得行事曆例外，確保順暢且高效地整合至您的專案中。發揮 Aspose.Tasks 的力量，提升您的專案管理能力。

## 如何將 MS Project 行事曆與 Aspose.Tasks 整合？

`Project` 類別載入 Microsoft Project 檔案，揭露其行事曆與其他專案資料。使用 `new Project("source.mpp")` 匯入現有的 MS Project 檔案；函式庫會自動載入其預設行事曆及任何自訂例外。您可以在儲存回磁碟前讀取、修改或合併這些例外。此方法讓您能以程式方式 **修改 MS Project 行事曆** 資料，無需在 MS Project UI 手動編輯。

## 常見使用情境
- **假期排程** – 將國定假日定義為多個專案的非工作日。  
- **輪班工作** – 為採用非標準排程的團隊設定自訂工作週。  
- **專案階段門檻** – 阻止在特定期間排程工作，例如維護窗口。  
- **舊版遷移** – 從較舊的 MS Project 檔案匯入行事曆，並以程式方式調整。

## 提示與最佳實踐
- **專業提示：** 在新增例外前，務必先取得現有行事曆，以避免重複。  
- **警告：** 變更已指派給任務的行事曆可能導致任務日期移動；修改後請重新計算排程。  
- **效能：** 將多筆例外更新批次處理於單一交易，以減少檔案 I/O 開銷。Aspose.Tasks 可處理高達 500 MB 的檔案，且不需將整個文件載入記憶體，在一般伺服器硬體上每秒處理超過 50 個與行事曆相關的 API 呼叫。

## 行事曆例外教學
### [管理 Aspose.Tasks 行事曆例外](./add-remove/)
了解如何在 Aspose.Tasks for Java 中高效新增與移除行事曆例外。輕鬆提升專案管理工作流程。

### [使用 Aspose.Tasks 定義行事曆例外的工作日](./define-weekdays/)
了解如何在 Java 專案中使用 Aspose.Tasks 為行事曆例外定義工作日，以達到精確的專案排程。

### [使用 Aspose.Tasks 處理行事曆例外的發生次數](./handle-occurrences/)
了解如何在 Java 專案中使用 Aspose.Tasks for Java 有效處理行事曆例外。立即簡化您的專案管理流程。

### [使用 Aspose.Tasks 取得行事曆例外](./retrieve/)
了解如何使用 Aspose.Tasks for Java 從 MS Project 取得行事曆例外。逐步教學，實現無縫整合。

## 常見問題

**Q: 我可以在專案已發佈後修改行事曆例外嗎？**  
A: 是的。使用 add‑remove 和 define‑weekdays API 更新行事曆，然後重新儲存專案檔案。

**Q: Aspose.Tasks 支援重複例外嗎（例如，每月第一個星期一）？**  
A: 絕對支援。「處理發生次數」教學說明如何設定重複模式。

**Q: 我如何確保我的自訂行事曆被專案中的所有任務使用？**  
A: 將行事曆指派給專案的預設行事曆，或明確設定於每個任務的 `Calendar` 屬性上。

**Q: 是否可以合併多個 MS Project 檔案的行事曆？**  
A: 可以。取得每個行事曆，程式化合併其例外，然後將合併後的行事曆指派給目標專案。

**Q: 需要哪個版本的 Aspose.Tasks 才能使用這些功能？**  
A: 所有功能皆在目前的 Aspose.Tasks for Java 穩定版 (2025.x) 中提供。

---

**最後更新：** 2026-08-18  
**測試環境：** Aspose.Tasks for Java 24.11  
**作者：** Aspose

## 相關教學

- [建立專案行事曆 Aspose – 定義行事曆例外的工作日](/tasks/java/calendar-exceptions/define-weekdays/)
- [使用 Aspose.Tasks 取得行事曆例外 – Aspose.Tasks Java 教學](/tasks/java/calendar-exceptions/retrieve/)
- [建立 Aspose for Java 行事曆例外](/tasks/java/calendar-exceptions/add-remove/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}