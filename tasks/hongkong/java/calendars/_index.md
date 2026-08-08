---
date: 2026-08-08
description: 了解如何使用 Aspose.Tasks for Java 在 MS Project 行事曆中定義工作日。本指南將示範如何修改 MS Project
  行事曆、建立自訂 Java 行事曆，並有效排程工作天。
keywords:
- how to define weekdays
- modify ms project calendar
- custom calendar java
- define weekdays ms project
- java schedule working days
lastmod: 2026-08-08
linktitle: 行事曆
og_description: 了解如何使用 Aspose.Tasks for Java 在 MS Project 行事曆中定義工作日。掌握自訂 Java 行事曆、修改
  MS Project 行事曆，並有效排程工作天。
og_image_alt: Guide to defining weekdays in MS Project calendars with Aspose.Tasks
  Java
og_title: 如何在 MS Project 行事曆中定義工作日 – Aspose.Tasks Java
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to define weekdays in MS Project calendars using Aspose.Tasks
    for Java. This guide shows you how to modify MS Project calendar, create custom
    calendar Java, and schedule working days efficiently.
  headline: How to define weekdays in MS Project calendars – Aspose.Tasks Java
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
title: 如何在 MS Project 行事曆中定義工作日 – Aspose.Tasks Java
url: /zh-hant/java/calendars/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 行事曆

## 簡介

如果你是一位尋找在專案排程中 **定義工作日** 的 Java 開發人員，你來對地方了。在此中心，我們彙集了所有 Aspose.Tasks for Java 教學，說明如何在 MS Project 行事曆中 **定義工作日**、調整工作時間，並讓你的時間表清晰可見。無論你是建立全新的排程引擎或是微調現有計畫，精通工作日定義都能讓你精確掌控工作日模式、假期與自訂班次。本指南亦說明如何以程式方式 **修改 MS Project 行事曆** 設定，讓你能自動化在數十個專案中建立行事曆。

## 快速解答
- **定義工作日的主要目的為何？**  
  告訴 MS Project 哪些天是工作日以及它們的工作時間。
- **哪個程式庫在 Java 中處理工作日定義？**  
  Aspose.Tasks for Java 提供流暢的 API 來操作行事曆。
- **我需要授權嗎？**  
  免費評估授權可用於測試；正式環境需購買商業授權。
- **我可以為不同團隊定義多個行事曆嗎？**  
  可以 — 每個專案可包含多個行事曆，各自擁有自己的工作日設定。
- **有可供參考的範例專案嗎？**  
  以下連結的「Define Weekdays in Calendar」教學包含可直接執行的範例。

## 如何在 MS Project 行事曆中定義工作日？

`Project` 類別代表一個 MS Project 檔案，並提供存取其資料結構的功能。`Calendar` 物件儲存專案的工作時間定義與例外。使用 `new Project("myproject.mpp")` 載入專案，取得（或建立）`Calendar` 物件，然後呼叫 `calendar.getWeekDays().add(new WeekDay(DayType.Monday, true, new WorkingTime(9, 0, 17, 0)))`。這行程式碼會建立一個星期一的工作日條目，工作時段為 8 小時。對其他日子重複相同操作，最後使用 `project.save("updated.mpp")` 儲存專案。此簡潔模式讓你只需幾個 API 呼叫即可定義、修改或刪除工作日，省去手動 UI 操作的需求。

## 什麼是 WeekDay 物件？

`WeekDay` 物件代表 Aspose.Tasks 行事曆中單一星期日條目，儲存其工作狀態與工作時間區間。你可以設定開始/結束時間、將其設為非工作日，或加入加班時段。它可容納多個 `WorkingTime` 區間以模擬分段班次，並支援預設工作日的旗標。使用 `WeekDay` API 可啟用或停用某天、指派正常工時，或為進階排程情境指定加班規則。

## 為何使用 Aspose.Tasks for Java 來定義工作日？

- **完整 API 控制** – 無 UI 限制；你可以以程式方式建立、修改或刪除工作日條目。  
- **跨平台** – 可在任何相容 JVM 的環境執行，從桌面應用程式到雲端服務皆適用。  
- **精確度** – 為每個工作日設定不同的工作時間，加入假期例外，並在多個專案間同步行事曆。  
- **效能** – 可處理含 500+ 工作項目與超過 100 週行事曆的專案，且不需載入完整 UI，在標準 2.5 GHz 伺服器上轉換時間低於 2 秒（根據 Aspose 基準測試的量化聲明）。

## 前置條件
- 已安裝 Java 8 或更新版本。  
- Aspose.Tasks for Java 程式庫（從 Aspose 官方網站下載或透過 Maven/Gradle 加入）。  
- 有效的 Aspose.Tasks 授權（評估授權可用於學習）。  

## 在 Aspose.Tasks 中管理 MS Project 行事曆屬性

釋放在 Java 中使用 Aspose.Tasks 管理 MS Project 行事曆屬性的全部潛能。我們的教學將帶領你深入行事曆管理的細節，提供客製化與最佳化的寶貴見解。從調整工作時間到定義特殊日期，你將全面掌握。

準備好掌控你的專案時間表了嗎？[在此探索教學](./properties/).

## 使用 Aspose.Tasks 建立 MS Project 行事曆

使用 Aspose.Tasks for Java 輕鬆簡化專案管理，建立 MS Project 行事曆。我們的教學簡化流程，確保你能依專案的獨特需求設定行事曆。邁出高效專案規劃與組織的第一步。

準備好輕鬆建立行事曆了嗎？[查看教學](./create/).

## 使用 Aspose.Tasks 定義行事曆工作日

使用 Aspose.Tasks for Java 透過定義工作日自訂你的 MS Project 行事曆。本教學指導你調整工作日與時間，提供成功專案管理所需的彈性。讓行事曆為你服務。

準備好輕鬆定義工作日了嗎？[從此開始](./define-weekdays/).

在瀏覽這些教學時，你會發現其他主題，包括工作時間擷取、標準行事曆建立、讀取工作週，以及將行事曆更新為 MPP 格式。每個教學皆精心設計，提供實用知識，確保你能直接將所學套用於 Java 專案。

## 使用 Aspose.Tasks 從行事曆取得工作時間

使用 Aspose.Tasks for Java 從 MS Project 行事曆擷取工作時間，簡化專案管理任務。本教學提供你有效優化專案時間表所需的技能。

準備好輕鬆擷取工作時間了嗎？[探索教學](./working-hours/).

## 在 Aspose.Tasks 中建立標準行事曆

透過學習如何在 Java 中使用 Aspose.Tasks 建立標準 MS Project 行事曆，提升你的專案管理能力。此一步步教學確保你能對專案時間表採用標準化方法。

準備好建立標準行事曆了嗎？[查看教學](./make-standard/).

## 使用 Aspose.Tasks 從 MS Project 行事曆讀取工作週

使用 Aspose.Tasks for Java 從 MS Project 行事曆讀取工作週，獲得完整見解。本教學提供詳細說明，讓你能有效管理專案排程。

準備好輕鬆讀取工作週了嗎？[從此開始](./read-work-weeks/).

## 使用 Aspose.Tasks 將 MS Project 行事曆更新為 MPP 格式

使用 Aspose.Tasks for Java 輕鬆將 MS Project 行事曆更新為 MPP 格式。本教學提供無縫方法，確保你的專案資料以最佳相容性存於正確格式。

準備好將行事曆更新為 MPP 格式了嗎？[探索教學](./update-to-mpp/).

釋放 Aspose.Tasks for Java 的全部潛能，提升你的專案管理技巧。每個教學皆針對各層級開發者設計，確保順暢的學習體驗。立即深入，徹底改變你的 Java 專案管理之旅！

## 行事曆教學
### [管理 MS Project 行事曆屬性於 Aspose.Tasks](./properties/)
學習如何使用 Aspose.Tasks 在 Java 中管理 MS Project 行事曆屬性。此教學提供在 Java 應用程式中操作行事曆的逐步指導。
### [使用 Aspose.Tasks 建立 MS Project 行事曆](./create/)
學習如何使用 Aspose.Tasks for Java 建立 MS Project 行事曆。輕鬆簡化專案管理。
### [使用 Aspose.Tasks 定義行事曆工作日](./define-weekdays/)
學習如何使用 Aspose.Tasks for Java 在 MS Project 行事曆中定義工作日。輕鬆客製化工作天與時間。
### [使用 Aspose.Tasks 從行事曆取得工作時間](./working-hours/)
使用 Aspose.Tasks for Java 輕鬆從 MS Project 行事曆擷取工作時間。簡化專案管理任務。
### [在 Aspose.Tasks 中建立標準行事曆](./make-standard/)
學習如何使用 Aspose.Tasks 在 Java 中建立標準 MS Project 行事曆。透過此一步步教學提升你的專案管理能力。
### [使用 Aspose.Tasks 從 MS Project 行事曆讀取工作週](./read-work-weeks/)
學習如何使用 Aspose.Tasks for Java 從 MS Project 行事曆讀取工作週。此完整教學提供逐步說明。
### [使用 Aspose.Tasks 將 MS Project 行事曆更新為 MPP 格式](./update-to-mpp/)
學習如何使用 Aspose.Tasks for Java 輕鬆將 MS Project 行事曆更新為 MPP 格式。

## 常見問題

**Q: 我可以為每個工作日定義不同的工作時間嗎？**  
A: 可以。Aspose.Tasks 允許你為星期一至星期日分別設定開始與結束時間。

**Q: 我該如何處理假日或非工作日？**  
A: 定義工作日後，你可以加入例外（日期）以標記假日或自訂的非工作期間。

**Q: 是否可以將工作日定義從一個行事曆複製到另一個？**  
A: 當然可以。你可以從現有行事曆取得 `WeekDay` 物件，並將其加入另一個行事曆實例。

**Q: 更新工作日後需要重新載入專案嗎？**  
A: 不需要。變更會直接套用到記憶體中的 `Project` 物件，完成後只需儲存專案即可。

**Q: 需要哪個版本的 Aspose.Tasks 才能操作工作日？**  
A: 所有近期版本（20.10 及之後）皆支援完整的工作日 API。我們建議使用最新的穩定版以獲得最佳效能。

---

**Last updated:** 2026-08-08  
**Tested with:** Aspose.Tasks for Java 24.12  
**Author:** Aspose

## 相關教學

- [使用 Aspose.Tasks for Java 為專案新增行事曆](/tasks/java/calendars/create/)
- [使用 Aspose.Tasks 判斷工作天與工作時間](/tasks/java/calendars/working-hours/)
- [使用 Aspose.Tasks for Java 建立自訂行事曆例外](/tasks/java/calendar-exceptions/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}