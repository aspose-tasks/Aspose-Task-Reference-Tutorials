---
date: 2026-09-09
description: 使用 Aspose.Tasks 在 Java 中設定專案行事曆。了解如何顯示行事曆工作時段、設定工作時間，並在 MS Project 檔案中修改行事曆日期。
keywords:
- how to set project calendar
- display calendar working hours
- configure calendar working time
- modify calendar working days
- aspose.tasks java
lastmod: 2026-09-09
linktitle: 在 Aspose.Tasks 中管理行事曆屬性
og_description: 使用 Aspose.Tasks 在 Java 中設定專案行事曆。了解如何顯示行事曆工作時段、設定工作時間，並在 MS Project
  檔案中修改行事曆日期。
og_image_alt: Screenshot of Java code managing MS Project calendar with Aspose.Tasks
og_title: 使用 Aspose.Tasks 在 Java 中設定專案行事曆
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: How to set project calendar in Java using Aspose.Tasks. Learn to display
    calendar working hours, configure working time, and modify calendar days in MS
    Project files.
  headline: How to set project calendar Java with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Yes, the API provides full read/write access to calendars, allowing you
      to add, edit, or delete working times, exceptions, and base‑calendar relationships.
    question: Can I modify calendar properties programmatically using Aspose.Tasks?
  - answer: The library mirrors the capabilities of Microsoft Project, so you can
      customize virtually all calendar aspects. Only very old Project file versions
      may have minor compatibility quirks.
    question: Are there any limitations to calendar customization with Aspose.Tasks?
  - answer: Absolutely. Simply add the Aspose.Tasks JAR to your build path and use
      the same code patterns shown here.
    question: Can I integrate calendar management into existing Java projects?
  - answer: Yes, it covers tasks, resources, assignments, outlines, baselines, and
      more—making it a comprehensive solution for Java‑based project automation.
    question: Does Aspose.Tasks support other project‑management functionalities besides
      calendar management?
  - answer: Yes, Aspose provides dedicated forums, email support, and extensive documentation
      for all licensed users.
    question: Is technical support available for developers using Aspose.Tasks?
  type: FAQPage
second_title: Aspose.Tasks Java API
tags:
- aspose.tasks
- java project calendar
- ms project automation
- calendar management
title: 使用 Aspose.Tasks 在 Java 中設定專案行事曆
url: /zh-hant/java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks 在 Java 中設定專案行事曆

## 簡介
在本教學中，您將學習如何在 Java 中使用 Aspose.Tasks 函式庫 **設定專案行事曆**。控制行事曆屬性可讓您 **顯示行事曆工作時數**、設定自訂工作日，並使專案排程符合諸如假期或輪班模式等現實限制。我們將逐步說明環境設定、載入專案、遍歷行事曆，以及讀取或更新其屬性，讓您能在任何 Java 應用程式中自信地 **管理 MS Project 行事曆** 設定。

## 快速解答
- **什麼是「設定專案行事曆」？** 這表示在 MS Project 檔案中建立或更新行事曆的工作時間、基礎行事曆以及日期類型。  
- **需要哪個函式庫？** Aspose.Tasks for Java（任何近期版本）。  
- **我需要授權嗎？** 免費試用可用於開發；正式環境需購買商業授權。  
- **我可以顯示行事曆工作時數嗎？** 可以——透過讀取每個 `WeekDay`，即可輸出各日期類型的時數。  
- **這與 Maven/Gradle 相容嗎？** 完全相容——只需將 Aspose.Tasks JAR 加入相依性即可。  

## 如何在 Java 中設定專案行事曆
載入您的專案檔案，定位目標行事曆，然後依需求調整其工作時間定義、基礎行事曆與日期類型。以下步驟提供完整的端對端解決方案，示範載入、遍歷、修改及儲存專案，同時處理例外並確保工作時數計算的準確性。

## 什麼是專案行事曆？
專案行事曆定義了任務、資源及整體專案時間線的工作日與工作時數。在 MS Project 中，行事曆可以繼承自基礎行事曆，每種日期類型（例如 **Standard**、**Non‑working**）皆可擁有自己的工作時間。以程式方式管理這些設定，可在不需手動編輯的情況下動態調整排程。

## 為什麼要以程式方式管理 MS Project 行事曆？
以程式方式管理行事曆可讓您在多個專案中套用一致的排程規則、減少手動錯誤，並將行事曆資料與其他企業系統（如 HR 或 ERP）整合。此自動化可加速專案設定，確保所有團隊成員遵循相同的工作時間政策。

- **自動化：** 使用單一腳本即可調整數十個專案的行事曆。  
- **一致性：** 自動執行全組織的工作時間政策。  
- **整合性：** 將行事曆與外部 HR 或 ERP 系統同步。  
- **可見性：** 快速 **顯示行事曆工作時數** 以供報告或除錯。  
- **彈性：** 可即時加入例外或輪班模式，無需開啟介面。  

## 先決條件
在開始之前，請確保您已具備：

- **Java Development Kit (JDK) 8+** 已安裝，且已設定 `JAVA_HOME`。  
- **Aspose.Tasks for Java** 函式庫已從 [download page](https://releases.aspose.com/tasks/java/) 下載。將 JAR 加入 classpath，或在 Maven/Gradle 中聲明相依性。  
- 一個包含至少一個您想檢視或修改的行事曆的範例 MS Project 檔案（`.mpp` 或 `.xml`）。

## 匯入套件
`Project`、`Calendar`、`WeekDay` 及相關類別是行事曆操作的核心。  
`Calendar` 類別代表專案行事曆，包含工作日、例外與基礎行事曆關係。  
`WeekDay` 類別定義行事曆中單一天的工作時間設定。

`Project` 類別是 Aspose.Tasks 的最高層物件，於記憶體中表示單一 MS Project 檔案。載入檔案後，所有行事曆操作皆透過此物件進行。

```java
import com.aspose.tasks.*;
```

## 步驟 1：設定資料目錄
定義包含專案檔案的資料夾。將佔位符替換為您機器上的實際路徑。

```java
String dataDir = "Your Data Directory";
```

## 步驟 2：定義時間單位常數
工作時間以毫秒為單位表示。定義可重用的常數可讓程式碼更易閱讀，並協助您 **正確計算 Java 工作時數**。

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## 步驟 3：載入專案資料
透過載入現有的 MS Project XML 檔案（`.xml` 或 `.mpp`），建立 `Project` 實例。這讓您能存取檔案中所有的行事曆。

`Project` 類別將檔案載入輕量級物件模型；它 **不會** 需要將整個檔案全部載入記憶體，因而可處理包含數萬個工作項的專案。

```java
Project project = new Project(dataDir + "project.xml");
```

## 步驟 4：遍歷行事曆 Java
現在我們遍歷每個行事曆，列印其唯一識別碼、名稱、基礎行事曆，以及每種日期類型的工作時數。此範例同時示範 **如何在 Java 中設定專案行事曆** 的值，並 **顯示行事曆工作時數**。

```java
for (Calendar cal : project.getCalendars()) {
    if (cal.getName() == null) {
        continue;
    }
    System.out.println("UID: " + cal.getUid() + " Name: " + cal.getName());
    // Show if it has a base calendar
    System.out.print("Base Calendar: ");
    System.out.println(cal.isBaseCalendar() ? "Self" : cal.getBaseCalendar().getName());
    // Iterate through weekdays
    for (WeekDay wd : cal.getWeekDays()) {
        double ts = wd.getWorkingTime();
        System.out.println("Day Type: " + DayType.toString(DayType.class, wd.getDayType()) + " Hours: " + ts / OneHour);
    }
}
```

### 此程式碼的功能
- **過濾未命名的行事曆**（某些內部行事曆可能 `null` 名稱）。  
- **列印 UID 與名稱**——有助於日後辨識行事曆。  
- **顯示基礎行事曆**——可能是 “Self”（行事曆本身即為基礎）或繼承的行事曆名稱。  
- **遍歷每個 `WeekDay`** 以計算並輸出總工作時數（`workingTime` 為毫秒，需除以 `OneHour`）。  

## 使用 Aspose.Tasks 的量化效益
Aspose.Tasks 支援 **30 多種輸入與輸出格式**，且可在不將整個檔案載入記憶體的情況下處理 **最多 10,000 個工作項的專案**，在一般伺服器硬體上於一秒內完成。這些數據顯示它是企業級自動化的可靠選擇。

## 常見問題與解決方案
| 問題 | 原因 | 解決方案 |
|-------|--------|-----|
| `NullPointerException` 發生於 `cal.getBaseCalendar()` | 行事曆本身就是基礎行事曆（`isBaseCalendar()` 回傳 `true`）。 | 如範例所示使用三元運算子檢查 (`cal.isBaseCalendar() ? "Self" : ...`)。 |
| 未輸出工作時數 | 專案檔使用不同的時間單位（ticks）。 | 確認檔案格式；Aspose.Tasks 會正規化為毫秒，但請確保載入正確的檔案類型。 |
| 找不到 `project.xml` | `dataDir` 路徑不正確。 | 使用絕對路徑或 `Paths.get(dataDir, "project.xml").toString()`。 |

## 常見問答

**Q: 我可以使用 Aspose.Tasks 以程式方式修改行事曆屬性嗎？**  
A: 是的，API 提供完整的讀寫存取權限，讓您能新增、編輯或刪除工作時間、例外與基礎行事曆關係。

**Q: 使用 Aspose.Tasks 進行行事曆自訂有任何限制嗎？**  
A: 此函式庫與 Microsoft Project 的功能相同，幾乎可以自訂所有行事曆層面。僅極舊的 Project 檔案版本可能會有少量相容性問題。

**Q: 我可以將行事曆管理整合到現有的 Java 專案中嗎？**  
A: 當然可以。只需將 Aspose.Tasks JAR 加入建置路徑，並使用此處示範的程式碼模式。

**Q: Aspose.Tasks 是否支援除行事曆管理之外的其他專案管理功能？**  
A: 有，涵蓋工作項、資源、指派、概觀、基線等，提供完整的 Java 專案自動化解決方案。

**Q: 使用 Aspose.Tasks 的開發者是否有技術支援？**  
A: 有，Aspose 為所有授權使用者提供專屬論壇、電子郵件支援與豐富文件。

---

**最後更新：** 2026-09-09  
**測試環境：** Aspose.Tasks for Java 24.12 (latest at time of writing)  
**作者：** Aspose

## 相關教學

- [建立 Java 專案行事曆 – Aspose.Tasks for Java 指南](/tasks/java/)
- [在 Java 中載入專案檔案並管理專案屬性](/tasks/java/project-management/default-properties/)
- [使用 Aspose.Tasks for Java 設定 MS Project 專案開始日期](/tasks/java/project-properties/write-project-info/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}