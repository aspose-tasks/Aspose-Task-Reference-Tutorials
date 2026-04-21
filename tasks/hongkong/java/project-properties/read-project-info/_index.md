---
date: 2025-12-31
description: 學習如何使用 Aspose.Tasks for Java 讀取專案資訊，包括從開始的排程。快速了解如何在 Java 中提取專案屬性。
linktitle: Read Project Info with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks for Java 從 Microsoft Project 讀取專案資訊
url: /zh-hant/java/project-properties/read-project-info/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.Tasks for Java 讀取 Microsoft Project 的專案資訊

## 介紹
如果您需要 **如何讀取專案** 的詳細資訊，例如開始日期、結束日期或行事曆設定，直接從 Microsoft Project 檔案中取得，Aspose.Tasks for Java 提供了一個乾淨、以程式碼為先的方式。在本教學中，您將會看到 **如何讀取專案** 的中繼資料、了解 **從開始的專案排程**，以及學會擷取其他關鍵屬性——全部只需幾行 Java 程式碼。

## 快速回答
- **Aspose.Tasks for Java 有什麼功能？** 它讓您在未安裝 Microsoft Project 的情況下，以程式方式存取 Microsoft Project 檔案（MPP、XML 等）。  
- **哪個屬性可判斷排程是否以開始為基礎？** `Prj.SCHEDULE_FROM_START` – 為 true 表示以開始為基礎排程，false 表示以結束為基礎。  
- **我可以在 Java 中擷取專案屬性嗎？** 可以，您可以讀取開始日期、結束日期、目前日期、狀態日期以及行事曆名稱。  
- **開發時需要授權嗎？** 評估期間可使用免費暫時授權；正式上線須購買完整授權。  
- **需要哪個版本的 Java？** 需要 Java 8 或更高版本，且在 classpath 中加入 Aspose.Tasks JAR。

## 前置條件
在開始之前，請確保您已具備：

1. **Java 開發環境** – 已安裝並設定 JDK 8 或更新版本。  
2. **Aspose.Tasks for Java** – 從[官方網站](https://releases.aspose.com/tasks/java/)下載最新程式庫。  

## 匯入套件
要與專案檔互動，請匯入 Aspose.Tasks 的核心命名空間：

```java
import com.aspose.tasks.*;
```

## 步驟說明

### 步驟 1：定義資料目錄
設定包含 `.mpp` 檔案的資料夾路徑。將佔位符替換為您機器上的實際路徑。

```java
String dataDir = "Your Data Directory";
```

### 步驟 2：載入專案檔案
建立 `Project` 例項，載入您想要檢查的 Microsoft Project 檔案。

```java
Project project = new Project(dataDir + "ReadProjectInfo.mpp");
```

### 步驟 3：判斷專案排程基礎
檢查排程是依據專案開始日期還是結束日期計算。這是 **如何讀取專案** 排程資訊的核心。

```java
if (project.get(Prj.SCHEDULE_FROM_START).getValue()) {
    System.out.println("Project Start Date: " + project.get(Prj.START_DATE));
} else {
    System.out.println("Project Finish Date: " + project.get(Prj.FINISH_DATE));
}
```

> **專業提示：** `Prj.SCHEDULE_FROM_START` 會回傳布林值；`true` 代表 *專案排程以開始為基礎*。

### 步驟 4：取得其他專案排程資訊
除了開始/結束日期外，您常常還需要目前日期、狀態日期以及與專案相關的行事曆。這示範了 **read project properties java** 的實際應用。

```java
String strSchdl = (project.get(Prj.SCHEDULE_FROM_START).getValue()) ? "Project Start Date" : "Project Finish Date";
System.out.println("Project Schedule From: " + strSchdl);
System.out.println("Current Date: " + project.get(Prj.CURRENT_DATE));
System.out.println("Status Date: " + project.get(Prj.STATUS_DATE));
System.out.println("Calendar: " + project.get(Prj.CALENDAR).getName());
```

## 常見問題與解決方案
| 問題 | 原因 | 解決方法 |
|------|------|----------|
| `NullPointerException` 發生於 `project.get(Prj.CALENDAR)` | 專案檔缺少預設行事曆。 | 確認 MPP 檔案已定義行事曆，或加入 `null` 檢查。 |
| 日期顯示為 `null` | 專案檔受損或缺少日期欄位。 | 在 Microsoft Project 中驗證來源檔案後再處理。 |
| 編譯錯誤：`cannot find symbol Prj` | Aspose.Tasks JAR 未加入 classpath。 | 將 `aspose-tasks-xx.jar` 加入專案的建置路徑。 |

## 常見問答

### Q: Aspose.Tasks for Java 能否支援所有版本的 Microsoft Project 檔案？
A: 能，Aspose.Tasks for Java 支援多種 Microsoft Project 檔案版本，包括 MPP 與 XML 格式。

### Q: Aspose.Tasks for Java 相容於所有 Java 開發環境嗎？
A: Aspose.Tasks for Java 相容於大多數 Java 開發環境，提供彈性的整合方式。

### Q: Aspose.Tasks for Java 是否提供除讀取資訊之外的專案資料操作功能？
A: 當然，Aspose.Tasks for Java 提供廣泛的功能，可進行專案資料的編輯、儲存與匯出等操作。

### Q: 我可以使用 Aspose.Tasks for Java 自動化擷取專案資訊嗎？
A: 可以，Aspose.Tasks for Java 透過完整的 API 支援自動化，讓資料擷取與分析流程更順暢。

### Q: 是否有 Aspose.Tasks for Java 使用者的社群論壇或支援渠道？
A: 有，您可以在 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 找到資源並與社群互動。

### Q: 如何在不載入整個工作樹的情況下讀取 Java 中的專案屬性？
A: 使用 `Project.get` 方法搭配所需的 `Prj` 列舉值，即可只取得指定的中繼資料，降低記憶體使用。

### Q: 在擷取屬性時，處理大型 MPP 檔案的最佳做法是什麼？
A: 以*唯讀*模式載入專案 (`new Project(filePath, LoadOptions)`) 並僅查詢必要的屬性，以避免高記憶體消耗。

## 結論
依照本指南，您現在已掌握 **如何讀取專案** 的資訊，包括排程來源、日期與行事曆細節，並可透過 Aspose.Tasks for Java 在應用程式中自動化報表、客製化儀表板與智慧決策，無需手動操作 Microsoft Project。

---

**最後更新：** 2025-12-31  
**測試環境：** Aspose.Tasks for Java 24.10  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}