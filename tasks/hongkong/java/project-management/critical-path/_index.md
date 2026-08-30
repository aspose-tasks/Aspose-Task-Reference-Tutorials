---
date: 2026-04-01
description: 學習如何使用 Aspose.Tasks for Java 在 MS Project 中計算關鍵路徑，並將計算模式設為自動，以獲得準確的結果。
keywords:
- critical path ms project
- ms project critical path
- project management critical path
- set calculation mode automatic
linktitle: 計算 Aspose.Tasks 專案的關鍵路徑
second_title: Aspose.Tasks Java API
title: 關鍵路徑 MS Project – Aspose.Tasks Java 教程
url: /zh-hant/java/project-management/critical-path/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 關鍵路徑 MS Project – Aspose.Tasks Java 教程

## 介紹
在本教程中，我們將帶領您使用 Aspose.Tasks Java 函式庫 **計算關鍵路徑 MS Project**。了解關鍵路徑對於有效的專案管理至關重要，因為它突顯了直接影響專案完成日期的工作順序。完成本指南後，您將能夠載入 MS Project 檔案、設定自動計算，並僅透過幾行程式碼提取關鍵路徑。

## 快速解答
- **關鍵路徑代表什麼？** 決定專案期間的最長依賴工作序列。  
- **哪個函式庫可在 Java 中計算它？** Aspose.Tasks for Java。  
- **是否需要設定計算模式？** 是——將計算模式設為自動，以讓引擎計算關鍵路徑。  
- **前置條件是什麼？** 已安裝 JDK 並將 Aspose.Tasks for Java 加入您的專案。  
- **我可以在主控台查看關鍵工作嗎？** 當然可以——使用 `project.getCriticalPath()` 並遍歷這些工作。

## 什麼是關鍵路徑 MS Project？
**關鍵路徑 MS Project** 是零浮動時間的工作鏈；任何這些工作的延遲都會導致整個專案延遲。識別此路徑可讓您將資源集中於真正重要的工作上。

## 為什麼使用 Aspose.Tasks 計算關鍵路徑？
Aspose.Tasks 提供穩健、以 API 為先的方式來讀取、修改與分析 Microsoft Project 檔案，無需桌面應用程式。將計算模式設為自動可確保所有衍生欄位（如關鍵路徑）在任何變更後皆為最新。

## 前置條件
在開始之前，請確保您具備以下前置條件：
1. 已在系統上安裝 Java Development Kit（JDK）。  
2. 已下載 Aspose.Tasks for Java 函式庫並加入您的專案。您可從 [here](https://releases.aspose.com/tasks/java/) 下載。

## 匯入套件
首先，在您的 Java 類別中匯入必要的套件：
```java
import com.aspose.tasks.*;
```

## 步驟 1：設定資料目錄
定義資料目錄的路徑，該目錄存放您的 MS Project 檔案。
```java
String dataDir = "Your Data Directory";
```

## 步驟 2：載入 MS Project 檔案
使用 Aspose.Tasks 函式庫載入 MS Project 檔案。
```java
Project project = new Project(dataDir + "New project 2013.mpp");
```

## 步驟 3：設定計算模式
將計算模式設為自動，以啟用關鍵路徑的計算。
```java
project.setCalculationMode(CalculationMode.Automatic);
```

## 步驟 4：新增工作
向專案新增工作。在此範例中，我們新增三個子工作。
```java
Task subtask1 = project.getRootTask().getChildren().add("1");
Task subtask2 = project.getRootTask().getChildren().add("2");
Task subtask3 = project.getRootTask().getChildren().add("3");
```

## 步驟 5：建立工作連結
建立工作連結以定義工作之間的相依性。
```java
project.getTaskLinks().add(subtask1, subtask2, TaskLinkType.FinishToStart);
```

## 步驟 6：顯示關鍵路徑
取得並顯示專案的關鍵路徑。
```java
for (Task task : project.getCriticalPath()) {
    System.out.println(task.get(Tsk.NAME));
}
```

## 步驟 7：顯示結果
顯示訊息以表示流程已成功完成。
```java
System.out.println("Process completed Successfully");
```

## 常見問題與解決方案
- **關鍵路徑顯示為空：** 確保在新增工作或連結之前呼叫 `project.setCalculationMode(CalculationMode.Automatic)`。  
- **工作未正確連結：** 請確認使用正確的 `TaskLinkType`（例如 `FinishToStart`）。  
- **找不到檔案：** 請再次檢查 `dataDir` 路徑以及 `.mpp` 檔案的完整檔名。

## 結論
使用 Aspose.Tasks for Java 計算 **關鍵路徑 MS Project** 是快速了解排程風險並確保專案順利進行的簡便方法。依照上述步驟，您即可以程式方式識別驅動專案時間表的工作序列。

## 常見問答
### Q: 我可以在任何版本的 MS Project 檔案上使用 Aspose.Tasks for Java 嗎？
A: 可以，Aspose.Tasks for Java 支援多種版本的 MS Project 檔案，包括從 MS Project 2003 到 MS Project 2019 的 .mpp 檔案。

### Q: 是否提供 Aspose.Tasks for Java 的免費試用？
A: 有，您可從 [here](https://releases.aspose.com/) 下載免費試用版。

### Q: 我可以在哪裡取得 Aspose.Tasks for Java 的支援？
A: 您可在 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 上取得支援。

### Q: 我可以購買 Aspose.Tasks for Java 的臨時授權嗎？
A: 可以，您可從 [here](https://purchase.aspose.com/temporary-license/) 購買臨時授權。

### Q: 我要如何購買 Aspose.Tasks for Java？
A: 您可從網站 [here](https://purchase.aspose.com/buy) 購買 Aspose.Tasks for Java。

## 常見問題
**Q: 設定計算模式為自動會影響效能嗎？**  
A: 它會在每次變更後觸發重新計算，適合小至中型專案。對於非常大型的排程，您可以改為手動模式，批次更新後再一次重新計算。

**Q: 我可以將關鍵路徑匯出為 CSV 檔案嗎？**  
A: 可以——遍歷 `project.getCriticalPath()`，使用標準 Java I/O 將每個工作的屬性寫入 CSV。

**Q: 能否在原始 .mpp 檔案中標示關鍵工作？**  
A: 完全可以。設定 `Tsk.IS_CRITICAL` 標誌或透過 API 修改工作格式，然後儲存專案。

**最後更新：** 2026-04-01  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}