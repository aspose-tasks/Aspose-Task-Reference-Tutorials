---
date: 2026-02-28
description: 學習如何在 Java 專案中使用 Aspose.Tasks 管理任務的預算、工作量與成本。本指南亦示範如何有效計算任務成本。
linktitle: Budget, Work, and Cost Management for Tasks in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何在 Aspose.Tasks Java 中管理預算、工作量與成本
url: /zh-hant/java/task-properties/task-budget-work-cost/
weight: 31
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks Java 中管理預算、工作與成本

管理專案的財務是任何專案經理的核心職責。在本教學中，您將學習如何使用 Aspose.Tasks Java API **管理預算**（包括工作、任務與資源），以及在需要精確財務報告時 **計算任務成本**。完成本指南後，您將能直接從 Microsoft Project 檔案中讀取、顯示和操作與預算相關的欄位。

## 快速回答
- **「預算工作」代表什麼？** 指分配給任務或資源的工作量（以小時計）。  
- **我可以以程式方式取得預算成本嗎？** 可以，使用任務、資源或指派的 `BUDGET_COST` 欄位。  
- **使用 Aspose.Tasks 是否需要授權？** 正式環境需要授權；亦提供免費試用版。  
- **支援哪個 Java 版本？** Aspose.Tasks 支援 Java 8 及以上版本。  
- **可以從指派計算任務成本嗎？** 當然可以——將指派的 `BUDGET_COST` 值加總即可。  

## Aspose.Tasks 中的預算管理是什麼？
Aspose.Tasks 於任務、資源與指派中使用專屬欄位（`BUDGET_WORK`、`BUDGET_COST`）儲存預算資訊。這些欄位讓您能在執行任何工作之前，規劃預期的工時與金額支出，從而實現精確的預測與差異分析。

## 為什麼要計算任務成本？
計算任務成本可協助您：
- 追蹤財務表現與原始估算的差異。  
- 為利害關係人產生基於成本的報告。  
- 及早發現超出預算的任務。  

## 前置條件
在開始編寫程式碼之前，請確保您已具備：

- Java 開發環境（JDK 8 以上）。  
- Aspose.Tasks for Java 程式庫 – 點擊 **[此處](https://releases.aspose.com/tasks/java/)** 下載。  
- 一個範例 Microsoft Project 檔案（例如 `BudgetWorkAndCost.mpp`），放置於已知目錄中。  

## 匯入套件
在您的 Java 專案中，首先匯入必要的套件，以確保能使用 Aspose.Tasks 功能。請在 Java 檔案的開頭加入以下程式碼：
```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.ResourceAssignment;
import com.aspose.tasks.ResourceType;
import com.aspose.tasks.Rsc;
import com.aspose.tasks.Task;
import com.aspose.tasks.Tsk;
```

## 步驟 1：設定文件目錄
首先設定文件目錄的路徑，該目錄用於存放您的專案檔案。
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

## 步驟 2：載入專案
使用 Aspose.Tasks 程式庫載入專案檔案。將 `"BudgetWorkAndCost.mpp"` 替換為您的專案檔案名稱。
```java
Project project = new Project(dataDir + "BudgetWorkAndCost.mpp");
Task projSummary = project.getRootTask();
```

## 步驟 3：取得專案與資源預算
取得並顯示專案層級與資源層級的預算。本步驟示範如何透過讀取已儲存的值 **計算任務成本**。
```java
System.out.println("projSummary.BudgetWork = " + projSummary.get(Tsk.BUDGET_WORK));
System.out.println("projSummary.BudgetCost = " + projSummary.get(Tsk.BUDGET_COST));
Resource rsc = project.getResources().getByUid(2);
System.out.println("Resource BudgetWork = " + rsc.get(Rsc.BUDGET_WORK));
System.out.println("Resource BudgetCost = " + rsc.get(Rsc.BUDGET_COST));
```

## 步驟 4：顯示指派預算
遍歷彙總任務（或任何任務）的指派，並顯示每筆指派的預算資訊。讓您能看到分配給各資源的成本。
```java
for (ResourceAssignment assn : projSummary.getAssignments()) {
    if (assn.get(Asn.RESOURCE).get(Rsc.TYPE) == ResourceType.Work) {
        System.out.println("Assignment BudgetWork = " + assn.get(Asn.BUDGET_WORK));
    } else {
        System.out.println("Assignment BudgetCost = " + assn.get(Asn.BUDGET_COST));
    }
}
```

## 常見問題與專業提示
- **Null 值：** 若預算欄位回傳 `null`，表示專案檔可能未包含該資料。列印前請使用 `project.getRootTask().get(Tsk.BUDGET_WORK) != null` 進行檢查。  
- **UID 錯誤：** 確認您查詢的資源 UID（`getByUid(2)`）是否存在；否則會拋出 `NullPointerException`。  
- **貨幣格式化：** `BUDGET_COST` 會回傳原始 double 值。可使用 `NumberFormat.getCurrencyInstance()` 進行格式化，以提供使用者友好的輸出。  

## 常見問題

**Q: 我可以將 Aspose.Tasks for Java 與其他 Java 框架一起使用嗎？**  
**A:** 是的，Aspose.Tasks for Java 相容於各種 Java 框架，確保整合的彈性。

**Q: 是否提供 Aspose.Tasks for Java 的試用版？**  
**A:** 是的，您可在 **[此處](https://releases.aspose.com/)** 取得 Aspose.Tasks for Java 的免費試用版。

**Q: 我可以在哪裡取得 Aspose.Tasks for Java 的額外支援？**  
**A:** 可前往 Aspose.Tasks 社群論壇 **[此處](https://forum.aspose.com/c/tasks/15)** 獲取支援與討論。

**Q: 我如何取得 Aspose.Tasks for Java 的臨時授權？**  
**A:** 可在 **[此處](https://purchase.aspose.com/temporary-license/)** 取得臨時授權，以供測試與評估使用。

**Q: 有其他 Aspose.Tasks for Java 的資源嗎？**  
**A:** 請參考文件 **[此處](https://reference.aspose.com/tasks/java/)**，獲取深入資訊與範例。

---

**最後更新：** 2026-02-28  
**測試環境：** Aspose.Tasks for Java 24.10  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}