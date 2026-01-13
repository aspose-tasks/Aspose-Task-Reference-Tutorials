---
date: 2026-01-13
description: 學習如何使用 Aspose.Tasks 在 Java 中計算資源百分比，包括如何取得 MS Project 資源的工作完成百分比。一步一步的指南，附有程式碼範例。
linktitle: Perform Percentage Calculations for Resources in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 使用 Aspose.Tasks 計算 Java 資源百分比
url: /zh-hant/java/resource-management/percentage-calculations/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Tasks 計算 Java 資源百分比

## 簡介
歡迎！在本教學中，您將學習 **如何計算資源百分比 java** 使用 Aspose.Tasks 函式庫 for Java。我們將示範如何從 Microsoft Project 檔案中提取每個資源的 *已完成工作百分比*，說明此指標的重要性，並提供您所需的完整程式碼。完成後，您即可將資源百分比計算整合到任何基於 Java 的專案管理解決方案中。

## 快速解答
- **「資源百分比」是什麼意思？** 它是資源已完成的工作量相對於其總指派工作量的百分比。  
- **哪個 API 呼叫會回傳此值？** 透過 `Resource` 類別的 `Rsc.PERCENT_WORK_COMPLETE`。  
- **我需要授權嗎？** 生產環境使用時需要臨時或完整的 Aspose.Tasks 授權。  
- **我可以將它與其他 Java 框架一起使用嗎？** 可以——此 API 可與 Spring、Hibernate 以及純 Java 專案一起使用。  
- **需要哪個版本的 Aspose.Tasks？** 任何支援 `Rsc` 列舉的近期版本（例如 24.x）。

## 什麼是計算資源百分比（Java）？
在 Java 中計算資源百分比是指以程式方式讀取 Microsoft Project 檔案，並判斷每個資源已完成多少工作。此資訊可協助專案經理預測時間表、平衡工作負載，並找出瓶頸。

## 為什麼要取得已完成工作百分比？
- **進度追蹤：** 一眼即可看出哪些團隊成員符合排程。  
- **容量規劃：** 根據實際表現調整未來的指派工作。  
- **報告：** 為利害關係人產生精確的狀態報告，免除手動計算。

## 先決條件
### Java 開發環境
確保已安裝 Java Development Kit（JDK）。您可以從 [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) 下載 JDK。

### Aspose.Tasks 函式庫
從 [here](https://releases.aspose.com/tasks/java/) 下載並將 Aspose.Tasks 函式庫加入您的專案，並依照文件中於 [here](https://reference.aspose.com/tasks/java/) 提供的安裝說明進行設定。

## 匯入套件
在開始編寫程式碼之前，先匯入本教學所需的套件：
```java
import com.aspose.tasks.Project;
import com.aspose.tasks.Resource;
import com.aspose.tasks.Rsc;
```

## 步驟 1：設定專案檔案路徑
將 `"Your Data Directory"` 替換為包含 Microsoft Project 檔案的資料夾路徑。
```java
String dataDir = "Your Data Directory";
```

## 步驟 2：載入專案
此程式會從您指定的目錄載入 **Software Development.mpp** 檔案。
```java
Project prj = new Project(dataDir + "Software Development.mpp");
```

## 步驟 3：遍歷資源
我們會遍歷專案中定義的每個資源。
```java
for (Resource res : prj.getResources()) {
```

## 步驟 4：檢查資源名稱並取得已完成工作百分比
程式碼首先確認資源是否有名稱，然後列印該資源的 **已完成工作百分比** 值。
```java
if (res.get(Rsc.NAME) != null) {
    System.out.println(res.get(Rsc.PERCENT_WORK_COMPLETE));
}
```

## 常見問題與解決方案
- **NullPointerException** – 確認專案檔案路徑正確，且檔案能順利載入。  
- **Incorrect percentages** – 確認資源確實有指派工作；否則百分比會是 `0`。  
- **License errors** – 使用有效的 Aspose.Tasks 授權或臨時評估授權，以避免執行時限制。  

## Frequently Asked Questions (Original)

### 我可以將 Aspose.Tasks for Java 與其他 Java 框架一起使用嗎？
是的，Aspose.Tasks for Java 相容於各種 Java 框架，如 Spring、Hibernate 等。

### Aspose.Tasks 是否支援所有版本的 Microsoft Project 檔案？
Aspose.Tasks 提供對所有版本的 Microsoft Project 檔案的支援，包括 MPP、MPT、XML 等。

### 我可以使用 Aspose.Tasks 操作專案排程嗎？
當然，Aspose.Tasks 提供完整功能以操作專案排程，包括工作、資源、行事曆等。

### 是否有 Aspose.Tasks 社群論壇可供支援？
是的，您可在 Aspose.Tasks 社群論壇 [here](https://forum.aspose.com/c/tasks/15) 獲得協助並與其他使用者交流。

### Aspose.Tasks 是否提供臨時授權供評估使用？
是的，您可從 [here](https://purchase.aspose.com/temporary-license/) 取得臨評估授權。

## Additional FAQ

**Q: 如何將輸出格式化為顯示帶 % 符號的百分比？**  
A: 使用 `res.get(Rsc.PERCENT_WORK_COMPLETE)` 取得數值，並以 `String.format("%.2f%%", value)` 進行格式化。

**Q: 我可以篩選資源，只顯示完成度低於 50 % 的嗎？**  
A: 可以，在列印前加入檢查 `res.get(Rsc.PERCENT_WORK_COMPLETE) < 50` 的 `if` 條件。

**Q: 能否將百分比寫回 Project 檔案？**  
A: `Rsc.PERCENT_WORK_COMPLETE` 欄位為唯讀；您需要改變工作指派才能間接調整。

**Q: 這能用於 Project Online（雲端）檔案嗎？**  
A: 必須先將 .mpp 檔案下載至本機；Aspose.Tasks 直接處理檔案格式，並不支援雲端服務。

## 結論
本指南示範了使用 Aspose.Tasks **如何計算資源百分比 java**，重點在於取得每個資源的 *已完成工作百分比*。依照上述步驟，您即可將精確的資源百分比分析嵌入 Java 應用程式，提升對專案健康與資源使用情況的可見性。

---

**最後更新：** 2026-01-13  
**測試環境：** Aspose.Tasks for Java 24.10  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}