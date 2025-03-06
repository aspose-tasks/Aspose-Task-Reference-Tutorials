---
title: 在 Aspose.Tasks 中設定 MS Project 資源使用視圖
linktitle: 在 Aspose.Tasks 中配置資源使用視圖
second_title: Aspose.Tasks .NET API
description: 了解如何使用 Aspose.Tasks for .NET 設定 MS Project 資源使用視圖。包含程式碼範例的分步指南。
weight: 15
url: /zh-hant/net/resource-risk-analysis/resource-usage-views/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Aspose.Tasks 中設定 MS Project 資源使用視圖

## 介紹
Microsoft Project (MS Project) 是一個強大的專案管理工具，可讓使用者有效率地規劃、執行和追蹤他們的專案。 Aspose.Tasks for .NET 提供與 MS Project 檔案的無縫集成，使開發人員能夠以程式設計方式操作專案資料。在本教學中，我們將探討如何使用 Aspose.Tasks for .NET 設定 MS Project 資源使用視圖。
## 先決條件
在我們開始之前，請確保您符合以下先決條件：
1.  Aspose.Tasks for .NET：從下列位置下載並安裝 Aspose.Tasks for .NET 函式庫：[下載連結](https://releases.aspose.com/tasks/net/).
2. Microsoft Project 檔案：有一個 Microsoft Project 檔案 (`.mpp`）包含您要使用的項目資料。

## 導入命名空間
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
## 第 1 步：載入專案文件
首先，使用 Aspose.Tasks 載入 MS Project 檔案：
```csharp
//文檔目錄的路徑。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ResourceUsageView.mpp");
```
## 第 2 步：定義儲存選項
定義指定所需時間刻度設定和示範格式的儲存選項：
```csharp
SaveOptions options = new PdfSaveOptions
{
    Timescale = Timescale.Days,
    PresentationFormat = PresentationFormat.ResourceUsage
};
```
## 步驟 3：使用資源使用視圖儲存項目
將具有配置的資源使用視圖的項目儲存到 PDF 檔案：
```csharp
project.Save(DataDir + "ResourceUsage_days_out.pdf", options);
```

## 結論
在本教學中，我們學習如何使用 Aspose.Tasks for .NET 設定 MS Project 資源使用視圖。透過遵循提供的步驟，開發人員可以將 Aspose.Tasks 無縫整合到他們的 .NET 應用程式中，以有效地操作專案資料。

## 常見問題解答
### Q：Aspose.Tasks 是否與不同版本的 Microsoft Project 檔案相容？
答：是的，Aspose.Tasks 支援各種版本的 Microsoft Project 文件，包括 .mpp、.mpt、.xml 和 .mpx。
### Q：我可以進一步自訂時間刻度設定和示範格式嗎？
答：當然，Aspose.Tasks 提供了根據您的要求自訂時間刻度設定和簡報格式的靈活性。
### Q：Aspose.Tasks 是否支援 PDF 以外的其他輸出格式？
答：是的，Aspose.Tasks 支援多種輸出格式，包括 XLSX、MPP、XML、HTML 等。
### Q：是否有 Aspose.Tasks 支援的社群或論壇？
答： 是的，您可以訪問[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15)如有任何疑問、討論或支援需求。
### Q：我可以在購買前試用 Aspose.Tasks 嗎？
答：當然，您可以透過免費試用版探索 Aspose.Tasks[這裡](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
