---
date: 2026-01-05
description: 了解如何使用 Aspose.Tasks for Java 高效處理計劃工作與實際工作以及其他專案變異，輕鬆管理工作、成本、開始與完成的變異。
linktitle: Deal with Variances in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 計劃工作與實際工作：使用 Aspose.Tasks 高效處理項目差異
url: /zh-hant/java/resource-assignments/deal-with-variances/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 計劃工作與實際工作：使用 Aspose.Tasks 高效處理專案差異

## 介紹
在本教學中，您將學習 **如何取得差異** 資料，並比較 *計劃工作與實際工作*，使用 Aspose.Tasks Java API。差異（無論是工作、成本、開始日期或完成日期）都是排程健康狀況的關鍵指標。閱讀完本指南後，您將能計算成本差異、擷取每個資源指派的差異值，並有效管理專案差異，確保專案保持在正軌上。

## 快速回答
- **什麼是「計劃工作與實際工作」？** 指原先排定的工作量與實際執行的工作量之間的差異。  
- **哪個 API 類別提供差異資料？** `Asn` 類別（例如 `Asn.WORK_VARIANCE`、`Asn.COST_VARIANCE`）。  
- **執行範例是否需要授權？** 評估期間可使用免費試用版；正式環境需購買商業授權。  
- **可以在一次迴圈中取得所有差異類型嗎？** 可以——遍歷 `ResourceAssignment` 物件，呼叫 `ra.get(Asn.*_VARIANCE)` 即可。  
- **需要哪個 Java 版本？** 建議使用 Java 8 或更高版本。

## 前置條件
在開始之前，請確保您已具備以下前置條件：
1. 系統已安裝 Java Development Kit (JDK)。  
2. 已下載 Aspose.Tasks for Java 並加入專案中。可從 [此處](https://releases.aspose.com/tasks/java/) 下載。  
3. 具備基本的 Java 程式語言知識。

## 匯入套件
首先，匯入使用 Aspose.Tasks 所需的套件：

```java
import com.aspose.tasks.Asn;
import com.aspose.tasks.Project;
import com.aspose.tasks.ResourceAssignment;
```

## 步驟 1：遍歷資源指派
要 **管理專案差異**，必須在已載入的專案檔中逐一迴圈資源指派：

```java
// The path to the documents directory.
String dataDir = "Your Data Directory";
Project project = new Project(dataDir + "ResourceAssignmentVariance.mpp");
for (ResourceAssignment ra : project.getResourceAssignments()) {
    // Perform operations on each resource assignment
}
```

## 步驟 2：取得工作差異（計劃工作與實際工作）
工作差異顯示 **計劃工作與實際工作** 之間的差距。使用以下程式碼取得：

```java
System.out.println(ra.get(Asn.WORK_VARIANCE));
```

## 步驟 3：取得成本差異
若需 **計算成本差異**，請使用下列呼叫：

```java
System.out.println(ra.get(Asn.COST_VARIANCE));
```

## 步驟 4：取得開始差異
開始差異表示排定的開始日期與實際開始日期之間的差異：

```java
System.out.println(ra.get(Asn.START_VARIANCE));
```

## 步驟 5：取得完成差異
完成差異反映計劃完成日期與實際完成日期之間的偏差：

```java
System.out.println(ra.get(Asn.FINISH_VARIANCE));
```

## 為什麼要取得差異資料？
了解差異有助於您：
- 及早發現排程延遲。  
- 在成本失控前調整資源配置。  
- 為利害關係人產出精確的狀態報告。  
- 對延遲任務執行根本原因分析。

## 常見陷阱與技巧
- **陷阱：** 忘記載入正確的 `.mpp` 檔案路徑。  
  **技巧：** 確認 `dataDir` 指向包含 `ResourceAssignmentVariance.mpp` 的資料夾。  
- **陷阱：** 以為差異值一定是數值。  
  **技巧：** 若資料不存在，某些指派會回傳 `null`，請加入 null 檢查。  
- **進階技巧：** 同時使用 `ra.get(Asn.WORK)` 與 `ra.get(Asn.WORK_VARIANCE)` 來計算實際完成的工作量。

## 結論
處理 **計劃工作與實際工作** 以及其他差異是有效專案控制的關鍵。透過 Aspose.Tasks for Java，您可以程式化取得與分析這些指標，從而做出資料驅動的決策，確保專案按時、按預算完成。

## 常見問答
### Q: 可以將 Aspose.Tasks 與其他 Java 函式庫整合嗎？
A: 可以，Aspose.Tasks 能與其他 Java 函式庫無縫整合，提升專案管理功能。  
### Q: Aspose.Tasks 適用於大型專案嗎？
A: 當然，Aspose.Tasks 設計能處理任何規模的專案，具備穩定的效能與可靠性。  
### Q: 能否根據差異分析自訂報表？
A: 完全可以，Aspose.Tasks 提供豐富功能，讓您依差異分析需求自訂報表。  
### Q: Aspose.Tasks 使用者是否有技術支援？
A: 有，使用者可透過 [Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15) 取得技術支援與協助。  
### Q: 購買前可以先試用 Aspose.Tasks 嗎？
A: 可以，您可從 [此處](https://releases.aspose.com/) 下載免費試用版，評估功能後再決定購買。

## 常見問題

**Q: 如何計算特定任務的成本差異？**  
A: 在遍歷指派時使用 `ra.get(Asn.COST_VARIANCE)`，並結合 `ra.get(Asn.COST)` 進行完整成本分析。

**Q: 若差異值回傳 null 該怎麼辦？**  
A: null 代表來源檔案中未設定該資料，請在列印或使用前先做 null 檢查。

**Q: 能否將差異資料匯出至 Excel？**  
A: 可以——將值收集至集合後，使用 Apache POI 等函式庫寫入 Excel 工作表。

**Q: Aspose.Tasks 支援敏捷專案的差異指標嗎？**  
A: 雖然 API 主要針對傳統 MS‑Project 資料，但您可將敏捷衝刺資訊映射為任務，仍能取得差異值。

**Q: 有沒有辦法批次更新差異值？**  
A: 您可以修改底層欄位（例如 `Asn.WORK`），然後儲存專案；下次讀取時差異欄位會自動重新計算。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-01-05  
**測試環境：** Aspose.Tasks for Java 24.12  
**作者：** Aspose