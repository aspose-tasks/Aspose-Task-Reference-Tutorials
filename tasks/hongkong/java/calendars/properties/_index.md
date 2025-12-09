---
date: 2025-12-04
description: 了解如何在 Java 中使用 Aspose.Tasks 設定專案行事曆並管理 MS Project 行事曆屬性。一步一步的指南，展示行事曆工作時間並自訂排程。
linktitle: Manage Calendar Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks for Java 設定專案行事曆
url: /zh-hant/java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks for Java 設定專案日曆

## 介紹
在本教學中，您將學會如何使用 Aspose.Tasks for Java 程式化 **設定專案日曆**。控制日曆屬性可讓您 **顯示日曆工作時段**、自訂工作日，並使您的專案排程符合實際限制。我們將逐步說明——從環境設定到遍歷日曆並讀取其屬性——讓您能在應用程式中自信地管理 MS Project 日曆。

## 快速回答
- **「設定專案日曆」是什麼意思？** 代表在 MS Project 檔案中建立或更新日曆的工作時間、基礎日曆與日類型。  
- **需要哪個程式庫？** Aspose.Tasks for Java（任意近期版本）。  
- **需要授權嗎？** 開發階段可使用免費試用版；正式上線需購買商業授權。  
- **可以顯示日曆工作時段嗎？** 可以——讀取每個 `WeekDay` 後即可輸出各日類型的工作時段。  
- **支援 Maven/Gradle 嗎？** 完全支援——只要將 Aspose.Tasks JAR 加入相依性即可。

## 什麼是專案日曆？
專案日曆定義了任務、資源與整體專案時間線的工作日與工作時段。在 MS Project 中，日曆可以繼承自基礎日曆，每種日類型（例如 **Standard**、**Non‑working**）皆可設定獨立的工作時間。以程式方式管理這些設定，可在不手動編輯的情況下動態調整排程。

## 為什麼要以程式方式管理 MS Project 日曆？
- **自動化：** 只需一支腳本即可在多個專案間調整日曆。  
- **一致性：** 強制執行全公司統一的工作時間政策。  
- **整合性：** 與外部系統（HR、ERP）同步日曆。  
- **可見性：** 快速 **顯示日曆工作時段**，方便報表或除錯。

## 前置需求
在開始之前，請確保您已具備：

- **Java Development Kit (JDK) 8+** 已安裝且設定 `JAVA_HOME`。  
- **Aspose.Tasks Java** 程式庫，請從 [下載頁面](https://releases.aspose.com/tasks/java/) 取得。將 JAR 加入專案的 classpath 或 Maven/Gradle 相依性中。

## 匯入套件
首先，匯入本教學中將會使用的 Aspose.Tasks 核心類別：

```java
import com.aspose.tasks.*;
```

## 步驟 1：設定資料目錄
定義存放專案檔案的資料夾。將佔位符替換為您機器上的實際路徑。

```java
String dataDir = "Your Data Directory";
```

## 步驟 2：定義時間單位
工作時間以毫秒為單位。定義可重複使用的常數可提升程式可讀性。

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## 步驟 3：載入專案資料
透過載入現有的 MS Project XML 檔案（`.xml` 或 `.mpp`）建立 `Project` 實例，從而取得檔案中所有日曆的存取權。

```java
Project project = new Project(dataDir + "project.xml");
```

## 步驟 4：遍歷日曆並顯示工作時段
現在，我們會遍歷每個日曆，印出其唯一識別碼、名稱、基礎日曆，以及各日類型的工作時段。此範例同時示範 **如何設定專案日曆** 以及 **如何顯示日曆工作時段**。

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

### 程式碼說明
- **過濾未命名的日曆**（某些內部日曆的 `name` 為 `null`）。  
- **印出 UID 與名稱**——方便日後辨識。  
- **顯示基礎日曆**——若為「Self」表示該日曆本身即為基礎日曆，否則顯示繼承的日曆名稱。  
- **遍歷每個 `WeekDay`**，計算並輸出總工作時數（workingTime` 以毫秒為單位，需除以 `OneHour`）。

## 常見問題與解決方案
| 問題 | 原因 | 解決方式 |
|-------|--------|-----|
| `NullPointerException` 發生於 `cal.getBaseCalendar()` | 該日曆本身即為基礎日曆（`isBaseCalendar()` 回傳 `true`）。 | 如範例所示使用三元運算子 (`cal.isBaseCalendar() ? "Self" : ...`)。 |
| 工作時段未輸出 | 專案檔使用不同的時間單位（ticks）。 | 檢查檔案格式；Aspose.Tasks 會正規化為毫秒，但請確保載入正確的檔案類型。 |
| 找不到 `project.xml` | `dataDir` 路徑錯誤。 | 使用絕對路徑或 `Paths.get(dataDir, "project.xml").toString()`。 |

## 常見問答

**Q: 可以使用 Aspose.Tasks 程式化修改日曆屬性嗎？**  
A: 可以，API 提供完整的讀寫存取，您可以新增、編輯或刪除工作時間、例外與基礎日曆關係。

**Q: Aspose.Tasks 在日曆自訂方面有什麼限制？**  
A: 此程式庫與 Microsoft Project 的功能相同，幾乎可以自訂所有日曆項目。僅極舊的 Project 檔案版本可能會有少量相容性問題。

**Q: 能否將日曆管理整合到現有的 Java 專案中？**  
A: 完全可以。只要將 Aspose.Tasks JAR 加入建置路徑，並使用本教學中的程式碼模式即可。

**Q: Aspose.Tasks 除了日曆管理，還支援其他專案管理功能嗎？**  
A: 支援，包括任務、資源、指派、概覽、基線等，是 Java 專案自動化的完整解決方案。

**Q: 開發者使用 Aspose.Tasks 是否有技術支援？**  
A: 有，Aspose 提供專屬論壇、電子郵件支援以及完整文件，供所有授權使用者使用。

## 結論
透過本指南，您已掌握 **如何設定專案日曆**、讀取並 **顯示日曆工作時段**，以及如何在任何 Java 應用程式中整合這些功能。這讓您能自動化排程調整、落實一致的工作政策，並打造更完整的專案管理解決方案。

---

**最後更新：** 2025-12-04  
**測試環境：** Aspose.Tasks for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}