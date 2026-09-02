---
date: 2026-04-06
description: 學習如何在 Aspose.Tasks for .NET 中變更條形樣式並自訂條形顏色，以提升專案視覺化。
keywords:
- how to change bar
- customize bar colors
- Aspose.Tasks bar styling
linktitle: Aspose.Tasks 中的樣式列
second_title: Aspose.Tasks .NET API
title: 如何在 Aspose.Tasks 中更改條形樣式
url: /zh-hant/net/advanced-features/styling-bar/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何變更 Aspose.Tasks 中的條形樣式

## 介紹

如果您需要在 Microsoft Project 檔案中 **如何變更條形** 外觀，Aspose.Tasks for .NET 為您提供對條形顏色、形狀和文字樣式的完整控制。透過自訂條形顏色和其他視覺屬性，您可以讓專案計畫更易於閱讀，且更符合組織的品牌形象。在本教學中，我們將逐步示範完整範例，說明如何變更條形樣式，從載入專案到匯出套用新視覺規則的檔案。

## 快速解答
- **我可以樣式化什麼？** 條形、里程碑以及甘特圖中的任務文字。  
- **哪種格式支援樣式化的條形？** PDF、XLSX、HTML 以及使用 `PdfSaveOptions` 儲存時的原生 MPP。  
- **我需要授權嗎？** 正式環境需要商業授權；免費試用可用於測試。  
- **我可以套用多個樣式嗎？** 可以 – 依需求新增任意數量的 `BarStyle` 物件。  
- **它相容 .NET Core 嗎？** 絕對相容 – 可在 .NET Framework 及 .NET Core/5/6+ 上執行。

## Aspose.Tasks 中的條形樣式是什麼？

條形樣式允許您定義視覺規則，由 Aspose.Tasks 引擎在繪製甘特圖時套用。每個規則（**BarStyle**）針對特定項目類型——任務、里程碑或彙總任務——並可設定顏色、形狀，甚至自訂文字。

## 為何要自訂條形顏色？

自訂條形顏色可協助利害關係人即時辨識關鍵路徑、延遲任務或里程碑。亦可配合企業色彩方案，使報告更具專業感且符合品牌形象。

## 前置條件

1. **Aspose.Tasks for .NET** – 從 [download page](https://releases.aspose.com/tasks/net/) 下載。  
2. 支援 .NET 的開發環境（Framework 4.6+、.NET Core 3.1+ 或更新版本）。  
3. 具備 C# 基礎知識 – 範例使用簡單、獨立的程式碼。

## 匯入命名空間

首先，匯入包含我們將使用類別的命名空間：

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## 步驟 1：載入專案

載入現有的 MPP 檔案（或建立新檔），以取得可操作的專案物件：

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
```

## 步驟 2：設定儲存選項

建立 `PdfSaveOptions` 實例，並初始化 `BarStyles` 集合，以儲存自訂樣式：

```csharp
SaveOptions options = new PdfSaveOptions
{
    BarStyles = new List<BarStyle>()
};
```

## 步驟 3：定義條形樣式

現在建立 `BarStyle` 物件，並設定控制條形外觀的屬性。這裡就是 **customize bar colors**（自訂條形顏色）與形狀的地方：

```csharp
var style = new BarStyle();
style.ItemType = BarItemType.Milestone; // Set bar item type
style.BarColor = Color.Green; // Set bar color
style.BarShape = BarShape.HalfHeight; // Set bar shape
style.StartShape = Shape.LeftBracket; // Set shape at the beginning of the bar
style.StartShapeColor = Color.Aqua; // Set color of the start shape
style.EndShape = Shape.RightBracket; // Set shape at the end of the bar
style.EndShapeColor = Color.Aquamarine; // Set color of the end shape
style.TextStyle = new TextStyle(); // Set text style
style.TextStyle.BackgroundColor = Color.Black; // Set background color for text
```

## 步驟 4：自訂文字轉換器（可選）

如果您想微調條形上顯示的文字，可指派自訂轉換器。範例會在未以 “T” 開頭的任務名稱前加上前綴：

```csharp
style.LeftBarTextConverter = task =>
{
    if (!task.Get(Tsk.Name).StartsWith("T"))
    {
        task.Set(Tsk.Name, "T" + task.Get(Tsk.Name));
    }
    return task.Get(Tsk.Name);
};
```

## 步驟 5：將條形樣式加入選項

將完整設定的樣式加入儲存選項的 `BarStyles` 集合：

```csharp
options.BarStyles.Add(style);
```

## 步驟 6：儲存專案

最後，匯出專案。PDF（或其他格式）將使用我們定義的條形樣式繪製甘特圖：

```csharp
project.Save(DataDir + "WorkWithBarStyle_out.mpp", options);
```

## 常見問題與解決方案

| 問題 | 原因 | 解決方式 |
|-------|--------|-----|
| **條形樣式未套用** | `BarStyles` 集合為空或未附加至儲存選項。 | 確保在呼叫 `Save` 前將 `BarStyle` 加入 `options.BarStyles`。 |
| **PDF 中的顏色看起來不同** | PDF 渲染可能使用不同的色彩配置檔。 | 使用標準的 `System.Drawing.Color` 值或自訂 ARGB 顏色。 |
| **文字轉換器拋出空參考例外** | 某些任務的 `Tsk.Name` 屬性為 null。 | 在存取 `task.Get(Tsk.Name)` 前加入 null 檢查。 |

## 常見問答

### Q1：我可以在單一專案套用多個條形樣式嗎？

A1：可以，您可以在同一專案中為不同類型的任務定義並套用多個條形樣式。

### Q2：是否可以在執行期間動態變更條形樣式？

A2：可以，您可以根據特定條件或使用者偏好在應用程式中動態修改條形樣式。

### Q3：Aspose.Tasks 是否支援將帶樣式條形的專案匯出為不同檔案格式？

A3：是的，Aspose.Tasks 支援將帶樣式條形的專案匯出為多種格式，例如 PDF、XLSX 與 HTML。

### Q4：Aspose.Tasks 是否提供預定義的條形樣式？

A4：雖然 Aspose.Tasks 提供預設的條形樣式，開發人員仍可依專案需求自行建立客製化條形樣式。

### Q5：我可以使用 API 取得並修改專案中現有的條形樣式嗎？

A5：可以，您可透過 Aspose.Tasks for .NET API 程式化取得並修改現有的條形樣式。

## 常見問題

**Q: 如何將一般任務的條形顏色變更為非里程碑？**  
A: 設定 `style.ItemType = BarItemType.Task;` 並將 `style.BarColor` 指派為所需的 `Color`。

**Q: 我可以在匯出為 HTML 時使用此方法樣式化條形嗎？**  
A: 可以。使用 `HtmlSaveOptions`，並以相同方式填充其 `BarStyles` 集合。

**Q: 我可以定義的條形樣式數量有上限嗎？**  
A: 實際上沒有；您可以依需求新增任意數量，但對於非常大的集合需考慮效能。

**Q: 在變更樣式後需要呼叫 `project.Calculate()` 嗎？**  
A: 不需要，樣式會在儲存操作時套用；僅在排程變更時才需要重新計算。

---

**最後更新：** 2026-04-06  
**測試環境：** Aspose.Tasks 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}