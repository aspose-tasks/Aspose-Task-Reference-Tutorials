---
date: 2026-11-19
description: 了解如何使用 Aspose.Tasks 在 Java 中建立自訂行事曆。本指南將示範如何定義工作日、設定工作時間，以及以程式方式修改 MS
  Project 行事曆。
images:
- /java/calendars/og-image.png
keywords:
- create custom calendar java
- define working days ms project
- set working hours ms project
- aspose.tasks java calendar
- ms project calendar manipulation
lastmod: 2026-11-19
linktitle: 行事曆
og_description: 了解如何使用 Aspose.Tasks 在 Java 中建立自訂行事曆。精通定義工作日、設定工作時間，以及高效地修改 MS Project
  行事曆。
og_image_alt: Guide to creating custom calendars in MS Project using Aspose.Tasks
  for Java
og_title: 如何使用 Aspose.Tasks 在 Java 中建立自訂行事曆
schemas:
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to create custom calendar Java using Aspose.Tasks. This guide
    shows you how to define working days, set working hours, and modify MS Project
    calendars programmatically.
  headline: How to create custom calendar Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes. Aspose.Tasks lets you set start and finish times individually for
      Monday through Sunday.
    question: Can I define different working hours for each weekday?
  - answer: After defining weekdays, you can add exceptions (dates) to mark holidays
      or custom non‑working periods.
    question: How do I handle holidays or non‑working days?
  - answer: Absolutely. You can retrieve a `WeekDay` object from an existing calendar
      and add it to another calendar instance.
    question: Is it possible to copy a weekday definition from one calendar to another?
  - answer: No. Changes are applied directly to the in‑memory `Project` object; just
      save the project when you’re done.
    question: Do I need to reload the project after updating weekdays?
  - answer: All recent versions (20.10 and later) support full weekday APIs. We recommend
      using the latest stable release for best performance.
    question: Which Aspose.Tasks version is required for weekday manipulation?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- calendars
- Aspose.Tasks
- Java project management
- MS Project integration
- working days
title: 如何使用 Aspose.Tasks 在 Java 中建立自訂行事曆
url: /zh-hant/java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 行事曆

## 介紹

如果你是一位想要 **create custom calendar Java** 解決方案的 Java 開發人員，你已經來對地方了。本中心彙集了所有 Aspose.Tasks for Java 教學，示範如何 **define working days MS Project**、**set working hours MS Project**，以及以程式方式調整行事曆設定。無論你是要建立全新的排程引擎，或是擴充現有的計畫，精通這些 API 都能讓你精確掌控工作日模式、假期與自訂班次——完全不需要開啟 MS Project 介面。

## 快速解答
- **定義工作日的主要目的為何？**  
  告訴 MS Project 哪些天是工作日以及它們的工作時間。  
- **哪個程式庫在 Java 中處理工作日定義？**  
  Aspose.Tasks for Java 提供流暢的行事曆操作 API。  
- **我需要授權嗎？**  
  免費評估授權可用於測試；正式環境需購買商業授權。  
- **我可以為不同團隊定義多個行事曆嗎？**  
  可以 — 每個專案可以包含多個行事曆，且每個行事曆都有自己的工作日設定。  
- **有可供開始的範例專案嗎？**  
  以下連結的「Define Weekdays in Calendar」教學包含可直接執行的範例。

## 如何建立自訂行事曆（Java）？

載入專案、建立或取得行事曆、加入工作日定義，然後儲存檔案——只需幾個 API 呼叫。此方法省去手動 UI 步驟，讓您能在數十個專案中自動化建立行事曆，並確保整個組織的工作日模式保持一致。

## 什麼是 Project 類別？

`Project` 類別是用於載入、編輯和儲存 MS Project 檔案的核心物件。它包含任務、資源和行事曆的集合，提供方法讓您以程式方式讀取和修改專案的每個面向。使用此類別，您可以存取專案的行事曆集合、調整工作時間，並將變更寫回 MPP 或 XML 檔案。

## 如何在 MS Project 行事曆中定義工作日？

`Project` 類別代表一個 MS Project 檔案，並提供對其資料結構的存取。`Calendar` 物件儲存工作時間定義與例外。使用 `new Project("myproject.mpp")` 載入專案，取得（或建立）`Calendar` 物件，然後呼叫 `calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))`。此行程式碼會建立一個星期一的工作日條目，工作 8 小時。對其他天重複此步驟，最後使用 `project.save("updated.mpp")` 儲存專案。此簡潔模式讓您只需少量 API 呼叫即可定義、修改或刪除工作日，免除手動 UI 操作。

## 什麼是 WeekDay 物件？

`WeekDay` 物件代表行事曆中單一星期天的條目。它記錄該天是否為工作日、該天的工作時間區間，以及預設行為的旗標。您可以附加一個或多個 `WorkingTime` 區間以模擬分段班次，將該天設定為非工作日，或從父行事曆繼承預設值。

## 如何定義 MS Project 的工作日？

透過將 `WeekDay` 物件加入行事曆的 `WeekDays` 集合來定義工作日。每個 `WeekDay` 指定該天是否為工作日以及被視為工作時間的時間範圍。例如，要將星期六設定為半天，加入一個只有單一 `WorkingTime`（10:00 至 14:00）的 `WeekDay`。API 會自動更新專案的排程計算。

## 如何設定 MS Project 的工作時間？

為每個 `WeekDay` 建立一個或多個 `WorkingTime` 區間來設定工作時間。`WorkingTime` 需要傳入開始小時、開始分鐘、結束小時與結束分鐘。您可以為同一天指派多個區間以模擬分段班次（例如 08:00‑12:00 與 13:00‑17:00）。設定完所有工作日後，呼叫 `project.save(...)` 以持久化變更。

## 為何使用 Aspose.Tasks for Java 來定義工作日？

- **完整的 API 控制** – 無 UI 限制；您可以以程式方式建立、修改或刪除工作日條目。  
- **跨平台** – 可在任何相容 JVM 的環境執行，從桌面應用程式到雲端服務皆適用。  
- **精確度** – 為每個工作日設定不同的工作時間，加入假期例外，並在多個專案間同步行事曆。  
- **效能** – 可處理含 500+ 工作項目與 100+ 週行事曆的專案，且不需載入完整 UI，在標準 2.5 GHz 伺服器上轉換時間低於 2 秒（根據 Aspose 基準測試的量化聲明）。  
- **廣泛的格式支援** – Aspose.Tasks 支援超過 30 種行事曆相關 API，且可匯入/匯出超過 20 種檔案格式，讓您輕鬆整合現有的專案資料管線。

## 前置條件
- 已安裝 Java 8 或更新版本。  
- Aspose.Tasks for Java 程式庫（從 Aspose 官方網站下載或透過 Maven/Gradle 加入）。  
- 有效的 Aspose.Tasks 授權（評估授權可用於學習）。  

## 在 Aspose.Tasks 中管理 MS Project 行事曆屬性

釋放在 Java 中使用 Aspose.Tasks 管理 MS Project 行事曆屬性的全部潛能。我們的教學將帶您深入行事曆管理的細節，提供客製化與最佳化的寶貴見解。從調整工作時間到定義特殊日期，您將全面掌握。

準備好掌控您的專案時間表了嗎？[Explore the tutorial here](./properties/)

## 使用 Aspose.Tasks 建立 MS Project 行事曆

輕鬆簡化您的專案管理，使用 Aspose.Tasks for Java 建立 MS Project 行事曆。我們的教學簡化了流程，確保您能設定符合專案獨特需求的行事曆。邁出高效專案規劃與組織的第一步。

準備好輕鬆建立行事曆了嗎？[Check out the tutorial](./create/)

## 使用 Aspose.Tasks 定義行事曆的工作日

使用 Aspose.Tasks for Java 客製化您的 MS Project 行事曆。本教學指導您如何調整工作日與時間，提供成功專案管理所需的彈性。讓您的行事曆為您服務。

準備好輕鬆定義工作日了嗎？[Get started here](./define-weekdays/)

在這些教學中，您將發現更多主題，包括工作時間提取、標準行事曆建立、讀取工作週以及將行事曆更新為 MPP 格式。每個教學都精心設計，提供實用知識，確保您能直接將所學應用於 Java 專案。

## 使用 Aspose.Tasks 從行事曆取得工作時間

簡化您的專案管理任務，使用 Aspose.Tasks for Java 從 MS Project 行事曆提取工作時間。本教學為您提供有效率地最佳化專案時間表的技能。

準備好輕鬆提取工作時間了嗎？[Explore the tutorial](./working-hours/)

## 在 Aspose.Tasks 中建立標準行事曆

透過 Aspose.Tasks 學習如何在 Java 中建立標準的 MS Project 行事曆。此逐步教學確保您能實作標準化的專案時間表方法。

準備好建立標準行事曆了嗎？[Check out the tutorial](./make-standard/)

## 使用 Aspose.Tasks 從 MS Project 行事曆讀取工作週

深入了解如何使用 Aspose.Tasks for Java 從 MS Project 行事曆讀取工作週。本教學提供詳細說明，讓您能有效管理專案排程。

準備好輕鬆讀取工作週了嗎？[Get started here](./read-work-weeks/)

## 使用 Aspose.Tasks 將 MS Project 行事曆更新為 MPP 格式

使用 Aspose.Tasks for Java 輕鬆將 MS Project 行事曆更新為 MPP 格式。本教學提供無縫的方式，確保您的專案資料以最佳相容性儲存於正確格式。

準備好將行事曆更新為 MPP 格式了嗎？[Explore the tutorial](./update-to-mpp/)

釋放 Aspose.Tasks for Java 的全部潛能，提升您的專案管理技能。每個教學皆針對各層次開發者設計，確保學習過程順暢。立即投入，徹底改變您的 Java 專案管理之旅！

## 行事曆教學
### [管理 MS Project 行事曆屬性於 Aspose.Tasks](./properties/)
了解如何使用 Aspose.Tasks 在 Java 中管理 MS Project 行事曆屬性。此教學提供在 Java 應用程式中操作行事曆的逐步指引。
### [使用 Aspose.Tasks 建立 MS Project 行事曆](./create/)
了解如何使用 Aspose.Tasks for Java 建立 MS Project 行事曆。輕鬆簡化專案管理。
### [使用 Aspose.Tasks 定義行事曆的工作日](./define-weekdays/)
了解如何使用 Aspose.Tasks for Java 在 MS Project 行事曆中定義工作日。輕鬆客製化工作日與時間。
### [使用 Aspose.Tasks 從行事曆取得工作時間](./working-hours/)
使用 Aspose.Tasks for Java 輕鬆從 MS Project 行事曆提取工作時間。簡化專案管理任務。
### [在 Aspose.Tasks 中建立標準行事曆](./make-standard/)
了解如何使用 Aspose.Tasks 在 Java 中建立標準的 MS Project 行事曆。透過此逐步教學提升您的專案管理能力。
### [使用 Aspose.Tasks 從 MS Project 行事曆讀取工作週](./read-work-weeks/)
了解如何使用 Aspose.Tasks for Java 從 MS Project 行事曆讀取工作週。此教學提供完整的步驟說明。
### [使用 Aspose.Tasks for Java 輕鬆將 MS Project 行事曆更新為 MPP 格式](./update-to-mpp/)
了解如何使用 Aspose.Tasks for Java 輕鬆將 MS Project 行事曆更新為 MPP 格式。

## 常見問題

**Q: 我可以為每個工作日定義不同的工作時間嗎？**  
A: 是的。Aspose.Tasks 允許您為星期一至星期日分別設定開始與結束時間。

**Q: 我該如何處理假期或非工作日？**  
A: 定義工作日後，您可以加入例外（日期）以標記假期或自訂的非工作期間。

**Q: 是否可以將工作日定義從一個行事曆複製到另一個行事曆？**  
A: 當然可以。您可以從現有行事曆取得 `WeekDay` 物件，並將其加入另一個行事曆實例。

**Q: 更新工作日後需要重新載入專案嗎？**  
A: 不需要。變更會直接套用到記憶體中的 `Project` 物件，只要在完成後儲存專案即可。

**Q: 需要哪個版本的 Aspose.Tasks 才能操作工作日？**  
A: 所有近期版本（20.10 及之後）皆支援完整的工作日 API。我們建議使用最新的穩定版以獲得最佳效能。

**最後更新：** 2026-11-19  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose

## 相關教學

- [將行事曆加入專案（使用 Aspose.Tasks for Java）](/tasks/java/calendars/create/)
- [確定工作日與工作時間（使用 Aspose.Tasks）](/tasks/java/calendars/working-hours/)
- [建立自訂行事曆例外（使用 Aspose.Tasks for Java）](/tasks/java/calendar-exceptions/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}