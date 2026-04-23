---
date: 2026-02-07
description: 學習如何使用 Aspose.Tasks 設定專案行事曆（Java）並管理 MS Project 行事曆屬性。一步一步的指南，展示行事曆工作時間並自訂排程。
linktitle: Manage Calendar Properties in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何在 Java 中使用 Aspose.Tasks 設定專案行事曆
url: /zh-hant/java/calendars/properties/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks 設定 Java 專案行事曆

## 介紹
在本教學中，您將學會如何使用 Aspose.Tasks for Java 程式化 **設定專案行事曆 (Java)**。控制行事曆屬性可讓您 **顯示行事曆工作時段**、自訂工作日，並將專案排程與實際限制相匹配。我們會一步步說明——從環境設定、遍歷行事曆到讀取其屬性——讓您能在應用程式中自信地 **管理 MS Project 行事曆** 設定。

## 快速答覆
- **「設定專案行事曆」是什麼意思？** 即在 MS Project 檔案中建立或更新行事曆的工作時間、基礎行事曆與日期類型。  
- **需要哪個程式庫？** Aspose.Tasks for Java（任意近期版本）。  
- **需要授權嗎？** 開發階段可使用免費試用版；正式上線需購買商業授權。  
- **可以顯示行事曆工作時段嗎？** 可以——讀取每個 `WeekDay` 後即可輸出各日期類型的時段。  
- **支援 Maven/Gradle 嗎？** 完全支援——將 Aspose.Tasks JAR 加入相依性即可。

## 如何設定專案行事曆 Java
本節直接回應主要關鍵字。我們將說明 **設定專案行事曆 Java** 的具體步驟、修改行事曆工作日，以及以 Java 方式 **計算工作時數**。

## 什麼是專案行事曆？
專案行事曆定義了任務、資源與整體專案時間表的工作日與工作時段。在 MS Project 中，行事曆可以繼承自基礎行事曆，每種日期類型（例如 **Standard**、**Non‑working**）皆可擁有自己的工作時間。以程式方式管理這些設定，可在不手動編輯的情況下動態調整排程。

## 為什麼要以程式方式管理 MS Project 行事曆？
- **自動化：** 只需一支腳本即可在多個專案間調整行事曆。  
- **一致性：** 強制執行全公司統一的工作時間政策。  
- **整合性：** 與外部系統（HR、ERP）同步行事曆。  
- **可見性：** 快速 **顯示行事曆工作時段** 以供報表或除錯使用。  
- **彈性：** 可即時 **修改行事曆工作日** 或新增例外。

## 前置條件
在開始之前，請確保您已具備：

- 已安裝 **Java Development Kit (JDK) 8+**，且設定 `JAVA_HOME`。  
- 已從[下載頁面](https://releases.aspose.com/tasks/java/)取得 **Aspose.Tasks for Java** 程式庫，並將 JAR 加入專案的 classpath 或 Maven/Gradle 相依性。

## 匯入套件
首先，匯入本教學中會使用的 Aspose.Tasks 核心類別：

```java
import com.aspose.tasks.*;
```

## 步驟 1：設定資料目錄
定義存放專案檔案的資料夾。將佔位符替換為您機器上的實際路徑。

```java
String dataDir = "Your Data Directory";
```

## 步驟 2：定義時間單位
工作時間以毫秒為單位。使用可重用的常數可讓程式碼更易讀，並協助您 **準確計算 Java 工作時數**。

```java
long OneSec = 1000; // 1000 milliseconds
long OneMin = 60 * OneSec;
long OneHour = 60 * OneMin;
```

## 步驟 3：載入專案資料
建立 `Project` 實例，載入既有的 MS Project XML 檔案（`.xml` 或 `.mpp`），以取得檔案中所有行事曆的存取權。

```java
Project project = new Project(dataDir + "project.xml");
```

## 以 Java 遍歷行事曆
現在我們會遍歷每個行事曆，印出其唯一識別碼、名稱、基礎行事曆，以及各日期類型的工作時段。此範例同時示範 **如何設定專案行事曆 Java** 的值與 **顯示行事曆工作時段**。

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
- **過濾未命名的行事曆**（某些內部行事曆的 `name` 可能為 `null`）。  
- **印出 UID 與名稱**——方便日後辨識行事曆。  
- **顯示基礎行事曆**——若為自身則顯示 “Self”，否則顯示繼承的行事曆名稱。  
- **遍歷每個 `WeekDay`**，計算並輸出總工作時數（`workingTime` 以毫秒為單位，需除以 `OneHour`）。

## 常見問題與解決方案
| 問題 | 原因 | 解決方式 |
|------|------|----------|
| `NullPointerException` 發生於 `cal.getBaseCalendar()` | 行事曆本身即為基礎行事曆（`isBaseCalendar()` 為 `true`）。 | 如範例所示使用三元運算子 (`cal.isBaseCalendar() ? "Self" : ...`)。 |
| 沒有顯示工作時段 | 專案檔使用不同的時間單位（ticks）。 | 確認檔案格式；Aspose.Tasks 會正規化為毫秒，但請確保載入正確的檔案類型。 |
| 找不到 `project.xml` | `dataDir` 路徑不正確。 | 使用絕對路徑或 `Paths.get(dataDir, "project.xml").toString()`。 |

## 常見問答

**Q: 可以使用 Aspose.Tasks 以程式方式修改行事曆屬性嗎？**  
A: 可以，API 提供完整的讀寫存取，讓您新增、編輯或刪除工作時間、例外與基礎行事曆關係。

**Q: Aspose.Tasks 在行事曆自訂方面有什麼限制？**  
A: 此程式庫與 Microsoft Project 的功能相同，幾乎可以自訂所有行事曆層面。僅極舊的 Project 檔案版本可能會有少量相容性問題。

**Q: 能否將行事曆管理整合到現有的 Java 專案中？**  
A: 完全可以。只要將 Aspose.Tasks JAR 加入建置路徑，並使用本教學中的程式碼模式即可。

**Q: Aspose.Tasks 是否支援除行事曆管理之外的其他專案管理功能？**  
A: 支援，涵蓋任務、資源、指派、概述、基線等多項功能，是 Java 專案自動化的完整解決方案。

**Q: 開發人員使用 Aspose.Tasks 是否有技術支援？**  
A: 有，Aspose 為所有授權使用者提供專屬論壇、電子郵件支援與完整文件。

---

**最後更新日期：** 2026-02-07  
**測試環境：** Aspose.Tasks for Java 24.12（撰寫時最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}