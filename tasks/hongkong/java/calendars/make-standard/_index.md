---
date: 2025-12-03
description: 學習如何使用 Aspose.Tasks 在 Java 中建立日曆。本分步指南將向您展示如何建立標準的 MS Project 日曆、加入標準日曆，以及有效運用
  Aspose.Tasks。
linktitle: Make Standard Calendar in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何建立行事曆 – 在 Aspose.Tasks 中製作標準行事曆
url: /zh-hant/java/calendars/make-standard/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何建立行事曆 – 在 Aspose.Tasks 中製作標準行事曆

## 介紹
在本教學中，您將學習如何使用 Aspose.Tasks for Java 函式庫為 Microsoft Project 檔案 **建立行事曆** 物件。我們會一步步示範建立標準的 MS Project 行事曆、將其設為預設（標準）行事曆，並儲存專案檔。完成本指南後，您即可在任何基於 Java 的專案管理解決方案中整合行事曆建立功能。

## 快速答覆
- **「標準行事曆」是什麼意思？** 它是未指定自訂行事曆的工作項目所使用的預設工作時間定義。  
- **需要哪個函式庫？** Aspose.Tasks for Java（「如何使用 Aspose」的部分）。  
- **需要授權嗎？** 開發階段可使用免費試用版；正式上線需購買商業授權。  
- **產生的檔案格式為何？** 基於 XML 的 Microsoft Project 檔案（`.xml`）。  
- **實作大約需要多久？** 基本行事曆約 5‑10 分鐘即可完成。

## Microsoft Project 中的標準行事曆是什麼？
**標準行事曆** 定義了專案的預設工作日與工作時段。當您新增標準行事曆後，所有未指定特定行事曆的工作項目都會遵循此排程。

## 為什麼使用 Aspose.Tasks 來建立行事曆？
Aspose.Tasks 提供純 Java API，讓您在不安裝 Microsoft Project 的情況下操作 Project 檔案。這對於伺服器端自動化、CI 流程，或任何需要以程式方式 **建立 MS Project 行事曆** 物件的 Java 應用程式而言，都是理想選擇。

## 前置條件
在開始之前，請確保以下項目已就緒：

### Java Development Kit (JDK) 安裝
從 Oracle 官方網站或 OpenJDK 發行版下載並安裝最新的 JDK。

### Aspose.Tasks for Java 函式庫
從 [下載頁面](https://releases.aspose.com/tasks/java/) 取得函式庫，並將 JAR 加入專案的 classpath。

## 匯入套件
本教學只需匯入一個套件：

```java
import com.aspose.tasks.*;
```

## 步驟說明

### 步驟 1：設定資料目錄
定義產生的專案檔要儲存的位置。

```java
String dataDir = "Your Data Directory";
```

將 `"Your Data Directory"` 替換為您機器上的絕對路徑（例如 `C:/Projects/Output/`）。

### 步驟 2：建立 Project 實例
建立一個新的、空的 Project 物件，用來保存行事曆。

```java
Project project = new Project();
```

### 步驟 3：定義並設為標準行事曆
新增一個名為 **「My Cal」** 的行事曆，並將其提升為專案的標準行事曆。

```java
Calendar cal1 = project.getCalendars().add("My Cal");
Calendar.makeStandardCalendar(cal1);
```

> **小技巧：** `makeStandardCalendar` 方法會自動將提供的行事曆標記為專案的預設行事曆，這正是您想要 **加入標準行事曆** 功能時所需要的。

### 步驟 4：儲存專案
將專案（含新行事曆）持久化為 XML 檔案。

```java
project.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

如果需要其他 Project 版本，可改變檔名或格式（`SaveFileFormat.Pp`）。

### 步驟 5：顯示完成訊息
提供視覺提示，表示流程已順利完成且未發生錯誤。

```java
System.out.println("Process completed Successfully");
```

## 常見問題與解決方案
| 問題 | 原因 | 解決方式 |
|------|------|----------|
| **找不到檔案** | `dataDir` 指向不存在的資料夾 | 建立該資料夾或改用絕對路徑 |
| **授權例外** | 生產環境未使用有效的 Aspose.Tasks 授權 | 透過 `License license = new License(); license.setLicense("Aspose.Tasks.lic");` 載入授權檔 |
| **行事曆為空** | 忘記加入工作時間定義 | 如需自訂時段，使用 `cal1.getWeekDays().add(WeekDay.DayType.Monday)` 等方式加入 |

## 常見問答

**Q: Aspose.Tasks 是否相容所有版本的 Microsoft Project？**  
A: 是，Aspose.Tasks 支援從 2000 版到最新版本的多種 Microsoft Project 版本。

**Q: 我可以進一步自訂行事曆設定嗎？**  
A: 當然可以！您可以使用 `WeekDay` 與 `WorkingTime` 類別修改工作日、加入例外，並定義特定的工作時段。

**Q: Aspose.Tasks 適合企業級應用嗎？**  
A: 完全適合。此函式庫設計用於高效能、可擴充的環境，並提供對大型 Project 檔案的完整支援。

**Q: Aspose.Tasks 是否提供開發者技術支援？**  
A: 有，Aspose 提供專屬論壇、票務支援以及豐富的文件，協助您快速解決問題。

**Q: 我可以先試用 Aspose.Tasks 再決定是否購買嗎？**  
A: 可以，您可在[官方網站](https://purchase.aspose.com/buy)下載免費試用版，完整體驗所有功能後再作決定。

## 結論
現在您已掌握如何在 Aspose.Tasks for Java 中 **建立行事曆** 物件、將其設為標準行事曆，並儲存最終的 Project 檔案。此功能讓您能自動化專案排程、統一工作時段，並將 Microsoft Project 資料直接整合至 Java 應用程式中。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2025-12-03  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

---