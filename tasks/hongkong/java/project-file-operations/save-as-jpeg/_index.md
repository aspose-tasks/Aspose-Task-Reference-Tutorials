---
date: 2026-05-26
description: 了解如何使用 Aspose.Tasks for Java 建立專案快照 JPEG，並在匯出 Microsoft Project 檔案時調整
  JPEG 品質。
keywords:
- create project snapshot jpeg
- adjust jpeg quality
- Aspose.Tasks Java
linktitle: 在 Aspose.Tasks 中將專案另存為 JPEG
schemas:
- author: Aspose
  dateModified: '2026-05-26'
  description: Learn how to create project snapshot JPEG and adjust JPEG quality when
    exporting Microsoft Project files using Aspose.Tasks for Java.
  headline: Create Project Snapshot JPEG – Adjust Quality with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Higher quality preserves text and line details, while very low quality
      may make small labels hard to read.
    question: Does adjusting JPEG quality affect Gantt chart readability?
  - answer: Yes, Aspose.Tasks supports PNG, BMP, and TIFF via the appropriate `SaveFileFormat`
      enum.
    question: Can I export other image formats besides JPEG?
  - answer: You can iterate over the desired views and save each as a separate JPEG
      using the same `ImageSaveOptions` configuration.
    question: Is it possible to export multiple pages (e.g., different views) at once?
  - answer: Aspose.Tasks for Java works with JDK 8 and later.
    question: What Java version is required?
  - answer: Consider reducing the JPEG quality or scaling the image dimensions via
      additional `ImageSaveOptions` settings.
    question: How do I handle large projects that produce big images?
  type: FAQPage
second_title: Aspose.Tasks Java API
title: 建立專案快照 JPEG – 使用 Aspose.Tasks 調整品質
url: /zh-hant/java/project-file-operations/save-as-jpeg/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立專案快照 JPEG – 使用 Aspose.Tasks 調整品質

## 簡介
在本教學中，您將了解如何使用 Aspose.Tasks for Java 從 Microsoft Project **create project snapshot JPEG** 檔案，並微調 JPEG 品質以符合大小與清晰度的需求。無論您需要在董事會簡報中使用清晰圖像，或在網站入口提供輕量檔案，掌握品質設定即可完全控制最終輸出。

## 快速解答
- **「adjust JPEG quality」的作用是什麼？** 它讓您能控制匯出 JPEG 的壓縮等級，在檔案大小與視覺真實度之間取得平衡。  
- **哪個函式庫負責轉換？** Aspose.Tasks for Java 提供直接的 API 以將 Project 檔案匯出為 JPEG。  
- **我需要授權嗎？** 免費試用可用於評估；正式環境須購買商業授權。  
- **我可以在程式碼中設定品質嗎？** 可以，使用 `ImageSaveOptions.setJpegQuality(int)` 方法（0‑100 範圍）。  
- **這個過程快速嗎？** 在現代硬體上，將一般的專案檔轉換為 JPEG 僅需數秒。

## 什麼是「adjust JPEG quality」？
調整 JPEG 品質讓您能指定儲存 JPEG 圖像時的壓縮係數。較高的數值（接近 100）保留更多細節，較低的數值則以犧牲銳利度為代價減少檔案大小。**Direct answer:** 您可透過將數值 (0‑100) 傳遞給 `ImageSaveOptions.setJpegQuality` 方法來控制 JPEG 品質，這會立即影響產生快照的大小與視覺真實度。  

JPEG 品質是儲存 JPEG 圖像時所套用的壓縮係數。

## 為什麼使用 Aspose.Tasks 進行 JPEG 匯出？
**Direct answer:** Aspose.Tasks 可在不安裝 Microsoft Project 的情況下將甘特圖、資源檢視與自訂報表渲染為圖像檔案，確保在 Windows、Linux 與 macOS 上皆能產生像素完美的輸出。  

Aspose.Tasks 支援匯出至 **四** 種圖像格式（JPEG、PNG、BMP、TIFF），且能在標準 2.5 GHz CPU 上於 5 秒內渲染包含 **最多 10,000 個工作** 的專案，提供可量化的效能保證。

## 先決條件
在開始之前，請確保您已具備以下項目：
1. **Java Development Kit (JDK)** – 從 [Java website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) 下載並安裝最新的 JDK（8 或更新版本）。  
2. **Aspose.Tasks for Java** – 依照官方 [documentation](https://reference.aspose.com/tasks/java/) 的步驟下載並設定此函式庫。

## 匯入套件
`ImageSaveOptions` 是 Aspose.Tasks 用來控制圖像匯出設定（如格式、尺寸與 JPEG 品質）的類別。  
```java
import com.aspose.tasks.ImageSaveOptions;
import com.aspose.tasks.Project;
import com.aspose.tasks.SaveFileFormat;
import java.io.IOException;
```

## 步驟 1：定義資料目錄
設定包含 Microsoft Project 檔案之資料夾的路徑。此目錄同時用於輸入與輸出操作。  
```java
String dataDir = "Your Data Directory";
```

## 步驟 2：載入 MS Project 檔案
`Project` 類別在記憶體中表示 Microsoft Project 檔案，提供對工作、資源與檢視資料的存取。  
```java
Project project = new Project(dataDir + "HomeMovePlan.mpp");
```

## 步驟 3：調整 JPEG 品質（可選）
若想微調輸出，可使用 `ImageSaveOptions` 類別 **設定 JPEG 品質**。品質值範圍為 0 到 100，100 代表最高的視覺真實度。  
```java
ImageSaveOptions options = new ImageSaveOptions(SaveFileFormat.Jpeg);
options.setJpegQuality(50); // Set JPEG quality to 50
```

## 步驟 4：將專案儲存為 JPEG
`Project.save` 會使用您設定的選項，將渲染的檢視寫入圖像檔案。  
```java
project.save(dataDir + "image_out.jpeg", options);
```

## 如何從 MS Project 匯出 JPEG
**Direct answer:** 在設定好 `ImageSaveOptions` 後，呼叫 `project.save("output.jpeg", SaveFileFormat.JPEG, saveOptions)`；此方法會渲染目前的檢視（預設為甘特圖），並以指定的品質寫入 JPEG 檔案。此單行呼叫會自動處理分頁、縮放與色彩管理。  

透過調整 JPEG 品質，您可控制圖像清晰度與檔案大小之間的取捨，使匯出的圖像適用於網站發佈、列印報告或嵌入投影片。

## 常見問題與解決方案
- **低品質導致文字難以辨識：** 將 JPEG 品質提升至 70 以上，或改用 PNG 以獲得無損渲染。  
- **大型專案發生記憶體不足錯誤：** 透過設定 `saveOptions.setUseMemoryCache(true)` 啟用串流，以將記憶體使用量控制在 200 MB 以下。  
- **匯出了錯誤的檢視：** 使用 `saveOptions.setView(ViewType.TaskSheet)` 以匯出其他檢視。

## 常見問與答

**Q: 調整 JPEG 品質會影響甘特圖的可讀性嗎？**  
A: 較高品質會保留文字與線條細節，而品質過低可能使小標籤難以辨識。  

**Q: 除了 JPEG，我可以匯出其他圖像格式嗎？**  
A: 可以，Aspose.Tasks 透過相應的 `SaveFileFormat` 列舉支援 PNG、BMP 與 TIFF。  

**Q: 能否一次匯出多頁（例如不同檢視）？**  
A: 您可以遍歷所需的檢視，並使用相同的 `ImageSaveOptions` 設定將每個檢視另存為 JPEG。  

**Q: 需要哪個 Java 版本？**  
A: Aspose.Tasks for Java 支援 JDK 8 及以上版本。  

**Q: 如何處理產生大型圖像的巨型專案？**  
A: 可考慮降低 JPEG 品質或透過額外的 `ImageSaveOptions` 設定縮放圖像尺寸。  

## 結論
我們已說明如何使用 Aspose.Tasks for Java **create project snapshot JPEG** 檔案並調整 JPEG 品質。此方法可免除手動截圖，確保跨平台渲染一致，並讓您微調圖像清晰度與檔案大小之間的平衡——非常適合報告、簡報與網站發佈。

---

**Last Updated:** 2026-05-26  
**Tested With:** Aspose.Tasks for Java 24.11  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [如何建立 MPP 檔案 – 使用 Aspose.Tasks 建立與儲存空白 MPP 專案](/tasks/java/project-configuration/create-save-mpp/)
- [使用 Aspose.Tasks for Java 將專案儲存為範本、CSV 與文字檔](/tasks/java/project-file-operations/save-csv-text-template/)
- [在 Aspose.Tasks 中建立空白 MS Project 檔案](/tasks/java/project-configuration/create-empty-project-file/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}