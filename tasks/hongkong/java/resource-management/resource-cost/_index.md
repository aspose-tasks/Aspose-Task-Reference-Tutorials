---
date: 2026-01-15
description: 學習如何使用 Aspose.Tasks for Java 處理 Microsoft Project 檔案中已排程的預算成本工作。請跟隨我們的逐步指南。
linktitle: Handle Resource Cost in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks for Java 排程的預算成本工作
url: /zh-hant/java/resource-management/resource-cost/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks for Java 的預算成本已排程工作

## 介紹

管理 **預算成本已排程工作 (BCWS)** 對於確保專案按計畫執行、讓財務預測與規劃工作相符至關重要。在 Microsoft Project 中，BCWS 代表截至特定日期應已支出的金額。Aspose.Tasks for Java 為您提供完整的程式化控制，讓您能讀取、修改並報告資源成本，而無需手動開啟 .mpp 檔案。本教學將示範完整範例，說明如何載入專案、遍歷其資源，並顯示預算成本已排程工作以及其他關鍵成本指標。

## 快速解答
- **BCWS 是什麼意思？** Budgeted Cost Work Scheduled – 已排程工作的預算成本。  
- **哪個 API 屬性可取得 BCWS？** `Rsc.BCWS`（在 `Resource` 物件上）。  
- **執行範例是否需要授權？** 免費評估授權可用於測試；正式環境需購買正式授權。  
- **可以修改 BCWS 值嗎？** 可以，您可以像設定其他數值欄位一樣設定 `Rsc.BCWS`。  
- **支援哪些 Project 版本？** 從 2000 版到最新 .mpp 格式的所有 Microsoft Project 版本。

## 什麼是預算成本已排程工作？

**Budgeted Cost Work Scheduled (BCWS)** 是一項績效衡量指標，反映截至某一時間點應已發生的工作成本。它是盈餘價值管理 (EVM) 的基石，協助專案經理比較計畫成本與實際支出。

## 前置條件

在開始撰寫程式碼之前，請確保您已具備：

1. 扎實的 Java 基礎。  
2. 已將 Aspose.Tasks for Java 加入專案（Maven/Gradle 或 JAR）。  
3. 一個包含成本資料的 Microsoft Project 檔案（`.mpp`），例如 *ResourceCosts.mpp*。

## 匯入套件

首先，匯入處理專案與資源所需的 Aspose.Tasks 類別：

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## 步驟 1：定義資料目錄

```java
String dataDir = "Your Data Directory";
```

將 `"Your Data Directory"` 替換為 *ResourceCosts.mpp* 所在的絕對或相對路徑。

## 步驟 2：載入 MS Project 檔案

```java
Project prj = new Project(dataDir + "ResourceCosts.mpp");
```

`Project` 建構子會讀取 .mpp 檔案，並在記憶體中建立可供查詢的模型。

## 步驟 3：遍歷資源

```java
for (Resource res : prj.getResources()) {
```

此迴圈會走訪專案中定義的每一個資源，讓您取得其成本欄位。

## 步驟 4：檢查資源名稱與成本

```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.COST));
    System.out.println(res.get(Rsc.ACWP));
    System.out.println(res.get(Rsc.BCWS));
    System.out.println(res.get(Rsc.BCWP));
}
```

在 `if` 區塊內，我們會：

* 列印 **總成本** (`Rsc.COST`)。  
* 列印 **實際已執行工作成本** (`Rsc.ACWP`)。  
* 列印 **預算成本已排程工作** (`Rsc.BCWS`) —— 本教學的主要指標。  
* 列印 **預算成本已執行工作** (`Rsc.BCWP`)。

這四個值可快速了解專案的財務狀況。

## 為何要監控預算成本已排程工作

* **早期警訊：** 若 BCWS 明顯高於實際成本，可能表示資源配置過度。  
* **盈餘價值分析：** BCWS 是計算成本差異 (CV) 與進度差異 (SV) 的關鍵輸入。  
* **預測：** 正確的 BCWS 數據有助於預測未來現金流需求，並支援利害關係人報告。

## 常見問題與除錯

| 症狀 | 可能原因 | 解決方式 |
|------|----------|----------|
| `null` 顯示於 BCWS | 資源未定義成本費率表 | 在 Microsoft Project 中為資源設定成本費率表，或透過 `Rsc.COST_RATE_TABLE` 程式化設定 |
| 迭代資源時拋出 `ArrayIndexOutOfBoundsException` | 專案檔案受損或包含空白資源項目 | 在 Microsoft Project 中驗證 .mpp 檔案，並移除空白資源 |
| 出現異常值（例如負的 BCWS） | 自訂欄位覆寫了標準成本欄位 | 確認取得的是標準的 `Rsc.BCWS`，而非同名的自訂欄位 |

## 常見問答

**Q: 可以程式化更新 BCWS 嗎？**  
A: 可以。使用 `res.set(Rsc.BCWS, newValue)`，然後以 `prj.save("Updated.mpp")` 儲存專案。

**Q: Aspose.Tasks 支援多幣別專案嗎？**  
A: 完全支援。成本欄位會遵循專案檔案中設定的貨幣屬性。

**Q: 有辦法將這些成本指標匯出為 CSV 嗎？**  
A: 您可以遍歷資源，將值寫入 `StringBuilder`，或使用 CSV 函式庫產生檔案。

**Q: BCWS 與 BCWP 有何不同？**  
A: BCWS 是已排程工作的計畫成本；BCWP（Budgeted Cost Work Performed）則是已完成工作的計畫成本。

**Q: 讀取成本資料需要特殊授權嗎？**  
A: 評估授權提供完整的讀寫權限；正式授權則是生產環境的必要條件。

## 結論

透過 Aspose.Tasks for Java，您可以精確且程式化地存取 **預算成本已排程工作** 以及其他關鍵成本指標。這讓您能打造自訂儀表板、自動化盈餘價值報告，並在不需手動操作 Microsoft Project 的情況下，確保專案財務保持在正軌。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-01-15  
**測試環境：** Aspose.Tasks for Java 24.12（最新）  
**作者：** Aspose