---
date: 2025-12-02
description: 了解如何將行事曆加入專案、如何建立 MS Project 行事曆，以及如何使用 Aspose.Tasks for Java 將專案儲存為
  XML。
linktitle: Add Calendar to Project using Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks for Java 為專案新增行事曆
url: /zh-hant/java/calendars/create/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks for Java 為專案新增行事曆

## 介紹
在現代專案管理工作流程中，透過程式碼 **為專案新增行事曆** 能節省大量手動編輯的時間。Aspose.Tasks for Java 為開發者提供乾淨且型別安全的 API，讓您在不開啟桌面客戶端的情況下操作 Microsoft Project 檔案。本教學將教您 **如何新增行事曆**、**如何建立 MS Project 行事曆**，以及 **將專案儲存為 XML**——只需幾行 Java 程式碼。

## 快速回答
- **「為專案新增行事曆」是什麼意思？**  
  意指透過程式碼在 Microsoft Project 檔案中插入一個新的工作時間定義（行事曆）。  
- **哪個函式庫負責此功能？**  
  Aspose.Tasks for Java 提供 `Calendar` 類別與 `Project` 容器來管理行事曆。  
- **需要授權嗎？**  
  測試時可使用臨時評估授權；正式上線則需購買正式授權。  
- **可以將檔案儲存為 XML 嗎？**  
  可以——使用 `SaveFileFormat.Xml` 即可匯出為 XML 檔。  
- **前置條件是什麼？**  
  需要 Java JDK 8 以上，並在 classpath 中加入 Aspose.Tasks for Java JAR。

## 「為專案新增行事曆」是什麼？
為專案新增行事曆會建立一套自訂排程，定義工作日、假日與每日工作時數。之後可將此行事曆指派給工作、資源或整個專案，確保開始日期與工期等計算遵循所設定的工作時間。

## 為什麼使用 Aspose.Tasks for Java 來為專案新增行事曆？
- **完整控制** – 無需 UI，能在大量專案中自動化批次建立行事曆。  
- **跨版本相容** – 支援 Project 2007、2010、2013、2016 以及更新版本的檔案。  
- **不需安裝 Microsoft Project** – 可在任何伺服器或 CI 流程中執行。  
- **匯出彈性** – 可儲存為 XML、MPP 或其他支援格式。

## 前置條件
- 已安裝並設定 **Java Development Kit (JDK) 8 或更新版本**。  
- **Aspose.Tasks for Java** 函式庫 – 從[官方網站](https://releases.aspose.com/tasks/java/)下載，並將 JAR 加入專案的 classpath。  
- 任一您慣用的 IDE 或建置工具（Maven/Gradle）。

## 步驟說明

### 步驟 1：匯入所需的 Aspose.Tasks 套件
首先，將 Aspose.Tasks 類別匯入，以便操作專案與行事曆。

```java
import com.aspose.tasks.*;
```

### 步驟 2：設定資料目錄路徑
定義產生的專案檔案要寫入的路徑。請將佔位符替換為您機器上的絕對或相對路徑。

```java
String dataDir = "Your Data Directory";
```

### 步驟 3：建立新的 Project 實例
實例化 `Project` 物件——這代表一個空的 Microsoft Project 檔案，您可以自行填入內容。

```java
Project prj = new Project();
```

### 步驟 4：定義要新增的行事曆
使用 `Calendars.add(String name)` 方法建立新的行事曆項目。以下範例新增三個行事曆，您可依需求新增更多，並在之後設定其工作時間。

```java
Calendar cal1 = prj.getCalendars().add("no info");
Calendar cal2 = prj.getCalendars().add("no name");
Calendar cal3 = prj.getCalendars().add("cal3");
```

> **小技巧：** 新增行事曆後，可使用 `cal1.getWeekDays().add(...)` 自訂工作日，並透過 `cal1.getBaseCalendar().setWorkingTime(...)` 設定每日工作時數。

### 步驟 5：儲存專案（將專案儲存為 XML）
將專案（含新加入的行事曆）持久化為 XML 檔案。此格式易於檢視，且相容多種工具。

```java
prj.save(dataDir + "project.xml", SaveFileFormat.Xml);
```

### 步驟 6：顯示完成訊息
通知使用者操作已成功完成。

```java
System.out.println("Process completed Successfully");
```

透過上述六個簡潔步驟，您已成功 **為專案新增行事曆**，並將結果儲存為 XML 檔案。

## 常見問題與解決方案
| 問題 | 原因 | 解決方式 |
|------|------|----------|
| **`NullPointerException` 發生於 `prj.getCalendars()`** | 專案物件未正確初始化。 | 確保在存取行事曆前已呼叫 `new Project()`。 |
| **儲存時找不到檔案** | `dataDir` 指向不存在的資料夾。 | 先建立該目錄，或改用絕對路徑。 |
| **行事曆名稱顯示為「no info」** | 範例使用了佔位名稱。 | 替換為能反映排程內容的實際名稱（例如「美國假日行事曆」）。 |
| **儲存的 XML 無法在 MS Project 開啟** | 使用了過舊的 Aspose.Tasks 版本。 | 更新至最新的 Aspose.Tasks for Java 版本。 |

## 常見問答

**Q: Aspose.Tasks 能處理包含多個例外的複雜行事曆嗎？**  
A: 能——新增行事曆後，您可以使用 `WeekDay` 與 `Exception` 類別定義例外、工作時段與非工作日。

**Q: 可以將新行事曆指派給特定工作嗎？**  
A: 當然可以。透過 `prj.getRootTask().getChildren().add("Task Name")` 取得工作，然後設定 `task.set(Tsk.CALENDAR, cal3);`。

**Q: 函式庫是否支援儲存為其他格式，例如 MPP？**  
A: 支援。只需將 `SaveFileFormat.Xml` 替換為 `SaveFileFormat.Mpp` 或 `SaveFileFormat.P6` 即可。

**Q: 開發版需要授權嗎？**  
A: 測試時使用臨時評估授權即可；正式部署則需購買正式授權。

**Q: 若遇到問題該向哪裡尋求協助？**  
A: Aspose.Tasks 社群論壇是極佳的資源：[Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15)。

## 結論
使用 Aspose.Tasks for Java，您可以程式化 **為專案新增行事曆**、自訂排程規則，並 **將專案儲存為 XML**，僅需幾行程式碼。此自動化可減少手動工作、降低人為錯誤，並支援大規模專案組合的批次處理。

---

**最後更新：** 2025-12-02  
**測試環境：** Aspose.Tasks for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}