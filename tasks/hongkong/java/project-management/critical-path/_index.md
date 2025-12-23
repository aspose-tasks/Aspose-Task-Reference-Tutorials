---
date: 2025-12-23
description: 學習如何在 MS Project 中使用 Aspose.Tasks for Java 建立任務相依關係並計算關鍵路徑。一步一步的專案管理指南。
linktitle: Calculate Critical Path in Aspose.Tasks Projects
second_title: Aspose.Tasks Java API
title: 在 Aspose.Tasks 中建立任務相依性並計算關鍵路徑
url: /zh-hant/java/project-management/critical-path/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中建立工作項目相依性並計算關鍵路徑

## 簡介
在本教學中，**您將學會如何建立工作項目相依性**，並使用 Aspose.Tasks for Java 計算 MS Project 檔案的關鍵路徑。了解並視覺化關鍵路徑有助於讓您的專案維持在排程上，而正確連結工作項目則能讓任何延遲立即顯現。讓我們從環境設定一路走到最終顯示關鍵路徑的完整流程。

## 快速答覆
- **第一步是什麼？** 設定您的 Java 專案並加入 Aspose.Tasks 程式庫。  
- **必須啟用哪種模式？** `CalculationMode.Automatic`（設定自動計算）。  
- **如何連結工作項目？** 使用 `project.getTaskLinks().add(...)` 來建立工作項目相依性。  
- **如何檢視關鍵路徑？** 迭代 `project.getCriticalPath()` 並印出每個工作項目的名稱。  
- **是否需要授權？** 是，正式使用時必須擁有有效的 Aspose.Tasks 授權。

## 什麼是「建立工作項目相依性」？
建立工作項目相依性是指為工作項目定義關係（例如 Finish‑to‑Start），使排程能反映真實世界的限制。在 Aspose.Tasks 中，這透過 `TaskLink` 物件來完成。

## 為什麼要在 MS Project 中計算關鍵路徑？
**MS Project 的關鍵路徑** 顯示決定專案最短工期的最長相依工作項目序列。計算它可以快速辨識出若延遲將直接影響整體時程的工作項目——對於有效的 **project management Java** 應用程式至關重要。

## 先決條件
在開始之前，請確保您已具備：

1. 已在系統上安裝 Java Development Kit (JDK)。  
2. 下載並將 Aspose.Tasks for Java 程式庫加入您的專案。您可以從 [here](https://releases.aspose.com/tasks/java/) 下載。

## 匯入套件
要開始，請在您的 Java 類別中匯入必要的套件：
```java
import com.aspose.tasks.*;
```

## 如何設定自動計算？
將計算模式設定為自動，可確保任何工作項目或連結的變更即時更新排程，包括關鍵路徑。
```java
project.setCalculationMode(CalculationMode.Automatic);
```

## 逐步指南

### 步驟 1：設定資料目錄
定義包含您 MS Project 檔案的資料夾路徑。
```java
String dataDir = "Your Data Directory";
```

### 步驟 2：載入 MS Project 檔案
使用 Aspose.Tasks 載入既有的專案檔（例如 *New project 2013.mpp*）。
```java
Project project = new Project(dataDir + "New project 2013.mpp");
```

### 步驟 3：新增工作項目
建立三個簡單的子工作項目，稍後我們會將它們連結起來。
```java
Task subtask1 = project.getRootTask().getChildren().add("1");
Task subtask2 = project.getRootTask().getChildren().add("2");
Task subtask3 = project.getRootTask().getChildren().add("3");
```

### 步驟 4：建立工作項目連結（建立工作項目相依性）
定義工作項目之間的相依性。此處使用最常見的 Finish‑to‑Start 連結。
```java
project.getTaskLinks().add(subtask1, subtask2, TaskLinkType.FinishToStart);
project.getTaskLinks().add(subtask2, subtask3, TaskLinkType.FinishToStart);
```

### 步驟 5：顯示關鍵路徑（display critical path）
取得並印出關鍵路徑。`getCriticalPath()` 方法會回傳形成關鍵鏈的工作項目清單。
```java
for (Task task : project.getCriticalPath()) {
    System.out.println(task.get(Tsk.NAME));
}
```

### 步驟 6：確認完成
流程結束後顯示友善訊息。
```java
System.out.println("Process completed Successfully");
```

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| **關鍵路徑為空** | 確保在加入連結前已設定 `CalculationMode.Automatic`。 |
| **工作項目未連結** | 檢查是否已為每個相依性加入 `TaskLink` 物件。 |
| **授權例外** | 在建立 `Project` 實例之前先載入有效的 Aspose.Tasks 授權。 |

## 常見問答

### Q: 我可以在任何版本的 MS Project 檔案上使用 Aspose.Tasks for Java 嗎？
A: 可以，Aspose.Tasks for Java 支援多種版本的 MS Project 檔案，包含從 MS Project 2003 到 MS Project 2019 的 .mpp 檔案。

### Q: 是否提供 Aspose.Tasks for Java 的免費試用？
A: 有，您可以從 [here](https://releases.aspose.com/) 下載免費試用版。

### Q: 我可以在哪裡取得 Aspose.Tasks for Java 的支援？
A: 您可以在 [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) 上取得支援。

### Q: 我可以購買 Aspose.Tasks for Java 的臨時授權嗎？
A: 可以，您可從 [here](https://purchase.aspose.com/temporary-license/) 購買臨時授權。

### Q: 我要如何購買 Aspose.Tasks for Java？
A: 您可於網站 [here](https://purchase.aspose.com/buy) 購買 Aspose.Tasks for Java。

## 結論
透過上述步驟，您已 **建立工作項目相依性**、設定 **自動計算**，並成功 **顯示 MS Project 檔案的關鍵路徑**。此工作流程讓您完整掌控排程邏輯，並以 Java 為基礎的 **project management** 程式碼協助專案保持在正軌上。

---

**最後更新：** 2025-12-23  
**測試環境：** Aspose.Tasks for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}