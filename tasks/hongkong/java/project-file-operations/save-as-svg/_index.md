---
date: 2026-03-27
description: 學習如何在 Java 中使用 Aspose.Tasks 將 MPP 匯出為 SVG。逐步指南、程式碼範例與技巧，快速將專案儲存為 SVG。
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何在 Java 中使用 Aspose.Tasks 將 MPP 匯出為 SVG
url: /zh-hant/java/project-file-operations/save-as-svg/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中將 MPP 匯出為 SVG

## 匯出 MPP 為 SVG – 介紹
在本教學中，您將學習如何使用 Aspose.Tasks for Java **匯出 MPP 為 SVG** 檔案。將 Microsoft Project (MPP) 檔案轉換為可縮放向量圖形 (SVG) 圖像，可讓您直接在網頁、報告或儀表板中嵌入高品質、解析度獨立的圖表。我們將逐步說明所需的設定、展示完整程式碼，並解釋每個步驟，讓您能自信地在自己的應用程式中 **將專案儲存為 SVG**。

## 快速解答
- **「匯出 MPP 為 SVG」是什麼意思？**  
  它會將 Microsoft Project 檔案 (.mpp) 轉換為 SVG 圖像，該圖像可在任何瀏覽器上顯示且不會失真。  
- **哪個函式庫負責轉換？**  
  Aspose.Tasks for Java 提供單行 `save` 方法來執行轉換。  
- **我需要授權嗎？**  
  商業使用需申請臨時授權；亦提供免費試用。  
- **先決條件是什麼？**  
  Java JDK 8 以上以及 Aspose.Tasks for Java JAR。  
- **轉換需要多長時間？**  
  標準專案檔案通常在一秒內完成。

## 什麼是「匯出 MPP 為 SVG」？
匯出 MPP 為 SVG 意指將專案排程的視覺呈現——任務、時間軸與資源——寫入 SVG 檔案。SVG 基於 XML、輕量且在高解析度顯示器上可完美縮放。

## 為什麼使用 Aspose.Tasks 匯出 MPP 為 SVG？
- **不需安裝 Microsoft Project** – 函式庫可獨立運作。  
- **完整保真** – 圖表、甘特條與里程碑皆保留樣式。  
- **跨平台** – 可在 Windows、Linux 或 macOS 上執行程式碼。  
- **單行 API** – 只需一次呼叫即可將專案儲存為 SVG，輕鬆整合至現有 Java 工作流程。

## 先決條件
- **Java Development Kit (JDK)** – 版本 8 或更新。可從 Oracle 官方網站下載。  
- **Aspose.Tasks for Java** – 從官方下載頁面取得函式庫 **[here](https://releases.aspose.com/tasks/java/)**。

## 匯入套件
首先，匯入您需要的類別。匯入區塊保持不變。

```java
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import com.aspose.tasks.SaveOptions;
import com.aspose.tasks.SvgOptions;
import com.aspose.tasks.Timescale;
import java.io.IOException;
```

## 步驟 1：定義資料目錄
指定來源 MPP 檔案所在位置以及 SVG 要寫入的路徑。

```java
String dataDir = "Your Data Directory";
```

> **專業提示：** 使用絕對路徑或相對於專案 resources 資料夾的路徑，以避免 `FileNotFoundException`。

## 步驟 2：載入 MPP 檔案
透過載入現有的 Microsoft Project 檔案，建立 `Project` 實例。

```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

此行程式會從先前定義的資料夾讀取 *HomeMovePlan.mpp*。

## 步驟 3：將專案儲存為 SVG
現在您可以使用單一指令 **匯出 MPP 為 SVG**。

```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```

此方法會將 `project5.svg` 寫入相同目錄。產生的 SVG 可在任何現代瀏覽器開啟，或直接嵌入 HTML 中。

## 常見使用情境
- **專案儀表板** – 在網路入口網站嵌入即時甘特圖，無需客戶安裝 Microsoft Project。  
- **自動化報告** – 即時產生 SVG 圖像，用於 PDF 或 HTML 報告。  
- **跨團隊協作** – 與只需要瀏覽器即可檢視的利害關係人分享視覺化排程。

## 常見問題與解決方案
| 問題 | 原因 | 解決方式 |
|-------|--------|-----|
| **找不到檔案** | `dataDir` 路徑不正確 | 確認目錄字串以分隔符 (`/` 或 `\\`) 結尾。 |
| **SVG 輸出為空白** | 專案未載入任何視圖 | 確保 MPP 檔案在儲存前包含甘特圖視圖。 |
| **授權例外** | 未套用有效授權 | 在呼叫 `save` 前使用 `License.setLicense("path/to/license.xml")` 套用臨時授權。 |

## 常見問與答

**Q: Aspose.Tasks for Java 是否相容所有版本的 Microsoft Project 檔案？**  
A: 是的，支援從舊版到最新版本的 MPP、MPT 與 XML 格式。

**Q: 我可以自訂 SVG 輸出的外觀嗎？**  
A: 當然可以。使用 `SvgOptions` 在呼叫 `save` 前設定字型、顏色與版面配置等選項。

**Q: Aspose.Tasks for Java 商業使用是否需要授權？**  
A: 需要。正式環境必須使用有效授權。您可在此取得臨時授權 **[here](https://purchase.aspose.com/temporary-license/)**。

**Q: 我可以在購買前先試用 Aspose.Tasks for Java 嗎？**  
A: 可以，免費試用版可在此取得 **[here](https://purchase.aspose.com/buy)**。

**Q: 我該向哪裡尋求 Aspose.Tasks for Java 的支援？**  
A: 前往社群論壇 **[here](https://forum.aspose.com/c/tasks/15)** 提問或分享回饋。

## 結論
您現在已掌握如何在 Java 中 **匯出 MPP 為 SVG**，並使用 Aspose.Tasks 高效 **將專案儲存為 SVG**。此功能讓您能將豐富的專案視覺化整合至網路入口、報告儀表板或任何需要可縮放圖形的地方。嘗試使用 `SvgOptions` 微調輸出，即可在開發工具箱中擁有一把強大的利器。

---

**最後更新：** 2026-03-27  
**測試環境：** Aspose.Tasks for Java 24.10  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}