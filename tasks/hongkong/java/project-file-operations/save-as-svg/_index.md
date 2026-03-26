---
date: 2025-12-21
description: 學習如何在 Java 中從 MPP 檔案建立 SVG，並使用 Aspose.Tasks 函式庫將專案儲存為 SVG。一步一步的指南，附有程式碼範例。
linktitle: Save As SVG in Aspose.Tasks
second_title: Aspose.Tasks Java API
title: 如何在 Java 中使用 Aspose.Tasks 從 MPP 產生 SVG
url: /zh-hant/java/project-file-operations/save-as-svg/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中從 MPP 建立 SVG

## 介紹
在本教學中，您將學會如何使用 **Aspose.Tasks for Java** **從 MPP 檔案建立 SVG**。將 Microsoft Project（MPP）檔案轉換為可縮放向量圖形（SVG），即可將高品質、與解析度無關的圖表直接嵌入網頁、報告或儀表板。我們將說明所需的設定步驟、提供完整程式碼，並逐一解釋每個環節，讓您能在自己的應用程式中自信地 **將專案儲存為 SVG**。

## 快速答覆
- **「從 MPP 建立 SVG」是什麼意思？**  
  它會將 Microsoft Project 檔案（.mpp）轉換為 SVG 圖像，該圖像可在任何瀏覽器上顯示且不會失真。  
- **哪個函式庫負責轉換？**  
  Aspose.Tasks for Java 提供單行 `save` 方法即可完成轉換。  
- **需要授權嗎？**  
  商業使用需使用臨時授權；亦提供免費試用版。  
- **前置條件是什麼？**  
  Java JDK 8 以上以及 Aspose.Tasks for Java JAR。  
- **轉換需要多長時間？**  
  一般的標準專案檔案通常在一秒以內完成。

## 「從 MPP 建立 SVG」是什麼？
從 MPP 檔案建立 SVG，意指將專案排程的視覺呈現（工作、時間軸、資源等）匯出為可縮放向量圖形格式。SVG 基於 XML、檔案輕量，且在高解析度螢幕上可完美縮放。

## 為什麼使用 Aspose.Tasks 來 **將專案儲存為 SVG**？
- **不需安裝 Microsoft Project** – 函式庫可獨立運作。  
- **完整保真度** – 圖表、甘特條與里程碑皆保留原有樣式。  
- **跨平台** – 可在 Windows、Linux 或 macOS 上執行。  
- **易於整合** – 單行 API 呼叫可自然嵌入現有 Java 工作流程。

## 前置條件
- **Java Development Kit (JDK)** – 版本 8 或更新版本。請自 Oracle 官方網站下載。  
- **Aspose.Tasks for Java** – 從官方下載頁面 **[此處](https://releases.aspose.com/tasks/java/)** 取得函式庫。  

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
指定來源 MPP 檔案所在位置以及 SVG 輸出路徑。

```java
String dataDir = "Your Data Directory";
```

> **小技巧：** 使用絕對路徑或相對於專案資源資料夾的路徑，可避免 `FileNotFoundException`。

## 步驟 2：載入 MPP 檔案
透過載入現有的 Microsoft Project 檔案，建立 `Project` 實例。

```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

此行程式會從先前定義的資料夾讀取 *HomeMovePlan.mpp*。

## 步驟 3：將專案儲存為 SVG
現在只需一行指令，即可 **將專案儲存為 SVG**。

```java
project.save(dataDir + "project5.svg", SaveFileFormat.Svg);
```

此方法會將 `project5.svg` 寫入相同目錄。產生的 SVG 可在任何現代瀏覽器開啟，或直接嵌入 HTML 中。

## 常見問題與解決方案
| 問題 | 原因 | 解決方式 |
|------|------|----------|
| **找不到檔案** | `dataDir` 路徑不正確 | 確認目錄字串以分隔符（`/` 或 `\\`）結尾。 |
| **SVG 輸出為空白** | 專案未載入任何檢視 | 確認 MPP 檔案中包含甘特圖檢視後再儲存。 |
| **授權例外** | 未套用有效授權 | 在呼叫 `save` 前使用 `License.setLicense("path/to/license.xml")` 套用臨時授權。 |

## 常見問答

**Q: Aspose.Tasks for Java 是否相容所有版本的 Microsoft Project 檔案？**  
A: 是的，支援從舊版到最新版的 MPP、MPT 與 XML 格式。

**Q: 我可以自訂 SVG 輸出的外觀嗎？**  
A: 當然可以。使用 `SvgOptions` 在呼叫 `save` 前設定字型、顏色與版面配置等選項。

**Q: Aspose.Tasks for Java 商業使用是否需要授權？**  
A: 需要。您可於 **[此處](https://purchase.aspose.com/temporary-license/)** 取得臨時授權。

**Q: 我可以先試用 Aspose.Tasks for Java 再決定購買嗎？**  
A: 可以，免費試用版可於 **[此處](https://purchase.aspose.com/buy)** 取得。

**Q: 我該向哪裡尋求 Aspose.Tasks for Java 的支援？**  
A: 請前往社群論壇 **[此處](https://forum.aspose.com/c/tasks/15)** 提問或分享使用心得。

## 結論
現在您已掌握如何在 Java 中 **從 MPP 建立 SVG**，並使用 Aspose.Tasks **將專案儲存為 SVG**。此功能讓您能將豐富的專案視覺化圖表整合至網站入口、報表儀表板或任何需要可縮放圖形的地方。可自行嘗試 `SvgOptions` 進一步微調輸出，讓這項強大的工具成為開發套件中的利器。

---

**最後更新：** 2025-12-21  
**測試環境：** Aspose.Tasks for Java 24.10  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}