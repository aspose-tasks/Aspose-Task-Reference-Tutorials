---
date: 2026-02-23
description: 學習如何使用 Aspose.Tasks for Java 管理專案任務中的加班，包括如何計算加班成本以及簡化資源追蹤。
linktitle: Overtimes in Tasks with Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何使用 Aspose.Tasks 管理任務加班
url: /zh-hant/java/task-properties/overtimes-in-tasks/
weight: 23
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中管理任務的加班

## Introduction
如果您正在尋找 **如何管理加班** 在 Microsoft Project 檔案中，您來對地方了。在本教學中，我們將展示 Aspose.Tasks for Java 如何讓您讀取、修改和報告每個任務的加班相關屬性，從而保持您的排程和預算的準確性。  

## Quick Answers
- **在專案中「加班」是什麼意思？** 超出資源正常容量的額外工作時數。  
- **哪個 API 類別提供加班資料？** `Task` 搭配 `Tsk` 欄位集合（例如 `Tsk.OVERTIME_COST`）。  
- **執行範例是否需要授權？** 是的，生產環境需要臨時或完整的 Aspose.Tasks 授權。  
- **我可以自動計算加班成本嗎？** 當然可以——取得 `Tsk.OVERTIME_COST` 並套用您的成本率邏輯。  
- **此功能是否相容於 Java 17？** 是，Aspose.Tasks for Java 支援 Java 8 及更新版本。

## What is Overtime Management in Project Tasks?
加班管理是指在資源超出正常工作時間時，追蹤額外的工作與成本。準確捕捉這些資料有助於預測預算、調整排程，並報告真實的專案健康狀況。

## Why Use Aspose.Tasks for Overtime?
* **不需 Microsoft Project** – 直接操作 .MPP 檔案。  
* **完整存取加班欄位** – 成本、工作量與完成百分比等值皆透過 `Tsk` 列舉公開。  
* **程式化控制** – 您可以在不使用手動 UI 步驟的情況下讀取、修改或計算加班成本。

## Prerequisites
在開始本教學之前，請確保您已具備以下前置條件：
- Java 開發環境：確保您的機器已設置 Java 開發環境。  
- Aspose.Tasks for Java：下載並安裝 Aspose.Tasks 程式庫。您可於 [此處](https://reference.aspose.com/tasks/java/) 找到程式庫與文件。  
- 專案檔案：準備一個專案檔（例如 TaskOvertimes.mpp）以供本教學使用。

## Import Packages
在您的 Java 專案中，匯入必要的 Aspose.Tasks 套件以利用其功能。加入以下匯入語句：

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## Step 1: Create a New Project
### 步驟 1：建立新專案
建立新專案（或載入既有專案）是任何分析的第一步。此步驟亦符合次要關鍵字 **create new project**。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create a new project
Project project = new Project(dataDir + "TaskOvertimes.mpp");
```

## Step 2: Iterate Through Tasks and Print Overtime Details
### 步驟 2：遍歷任務並列印加班詳細資訊
現在我們將逐一檢視每個最高層級任務，顯示其加班資訊，並示範如何透過讀取 `OVERTIME_COST` 欄位來 **計算加班成本**。

```java
for (Task tsk : project.getRootTask().getChildren()) {
    System.out.println("Overtime Cost: " + tsk.get(Tsk.OVERTIME_COST));
    System.out.println("Overtime Work: " + tsk.get(Tsk.OVERTIME_WORK).toString());
    System.out.println("Percent Complete: " + tsk.get(Tsk.PERCENT_COMPLETE));
    System.out.println("Percent Work Complete: " + tsk.get(Tsk.PERCENT_WORK_COMPLETE).toString());
    System.out.println("Physical Percent Complete: " + tsk.get(Tsk.PHYSICAL_PERCENT_COMPLETE).toString());
    // Set percent complete
    tsk.set(Tsk.PERCENT_COMPLETE, 100);
}
```

> **提示：** `OVERTIME_COST` 的值已由 Aspose.Tasks 依據資源的加班費率自動計算。如需自訂計算，可將 `OVERTIME_WORK` 乘以您自己的費率，並使用 `tsk.set(Tsk.OVERTIME_COST, yourValue);` 更新欄位。

## Common Issues and Solutions
| Issue | Solution |
|-------|----------|
| **加班欄位為 null 值** | 確保來源 .MPP 檔案實際包含加班資料；否則欄位會回傳 `null`。 |
| **修改後成本不正確** | 變更加班工作或成本後，呼叫 `project.save()` 以持久化變更。 |
| **找不到授權** | 將 `Aspose.Tasks.lic` 檔案放置於專案根目錄，或在載入專案前以程式方式設定授權。 |

## Frequently Asked Questions

**問：Aspose.Tasks 適用於大型專案管理嗎？**  
答：是的，Aspose.Tasks 設計能處理各種規模的專案，從小型計畫到大型且複雜的方案皆適用。

**問：我可以將 Aspose.Tasks 與其他 Java 框架整合嗎？**  
答：當然可以！Aspose.Tasks 可無縫整合 Spring、Jakarta EE 以及其他 Java 生態系，提升其彈性。

**問：使用 Aspose.Tasks 有授權上的考量嗎？**  
答：有，您可於 [此處](https://purchase.aspose.com/temporary-license/) 找到授權細節並取得臨時授權。

**問：我可以在哪裡尋求協助或討論 Aspose.Tasks 相關問題？**  
答：請前往 [Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15) 與社群互動並取得支援。

**問：Aspose.Tasks 有提供免費試用版嗎？**  
答：有，您可於 [此處](https://releases.aspose.com/) 取得免費試用版。

**問：如何計算特定資源的加班成本？**  
答：取得該資源的加班費率，將其乘以 `OVERTIME_WORK`（以小時為單位），若需自訂計算，將結果寫回 `OVERTIME_COST`。

## Conclusion
Aspose.Tasks for Java 簡化了 **如何管理加班** 在專案任務中的操作，讓開發者可直接以程式方式存取加班成本、工作量與進度指標。依照本指南，您可以載入專案、讀取加班細節、調整百分比，甚至自行計算自訂的加班成本——全部不需開啟 Microsoft Project。

---

**最後更新：** 2026-02-23  
**測試環境：** Aspose.Tasks for Java（最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}