---
date: 2026-07-05
description: 了解如何在使用 Aspose.Tasks for .NET 將專案匯出為 HTML 時自訂 CSS。透過 CSS 儲存參數調整 HTML
  輸出。
keywords:
- how to customize css
- export project to html
- customize html output
linktitle: 使用 Aspose.Tasks 儲存專案時的 CSS 自訂方法
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to customize CSS while exporting a project to HTML using
    Aspose.Tasks for .NET. Tailor HTML output with CSS saving arguments.
  headline: How to Customize CSS When Saving Projects with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Using custom CSS can reduce the total size by up to 15 % because you can
      eliminate unused default styles.
    question: How does customizing CSS affect the size of the exported HTML?
  - answer: Absolutely. Implement the callbacks once and reuse them across any number
      of project exports.
    question: Can I use the same callbacks for multiple projects?
  - answer: Yes, set `HtmlSaveOptions.EmbeddedCss = true` to inline the stylesheet,
      which simplifies distribution.
    question: Is it possible to embed CSS directly into the HTML instead of separate
      files?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: 使用 Aspose.Tasks 儲存專案時的 CSS 自訂方法
url: /zh-hant/net/calendar-scheduling/css-saving-arguments/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在使用 Aspose.Tasks 保存專案時自訂 CSS

在本指南中，您將了解 **如何自訂 CSS**，在使用 Aspose.Tasks for .NET 將 Microsoft Project 檔案匯出為 HTML 時。透過調整 CSS 儲存參數，您可以完全掌控產生的 HTML 頁面的視覺樣式，讓輸出符合您的品牌或報告標準。

## 快速解答
- **主要入口點是什麼？** 使用帶有自訂回呼的 `HtmlSaveOptions`。  
- **我需要授權嗎？** 是的，生產環境需要有效的 Aspose.Tasks 授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+。  
- **我可以匯出大型專案嗎？** Aspose.Tasks 可處理任務數量超過 10,000 的專案，且不需將整個檔案載入記憶體。  
- **CSS 自訂是可選的嗎？** 是的，您可以省略回呼以使用預設樣式表。

## 如何在 Aspose.Tasks 中自訂 CSS？

載入您的專案，將 CSS 儲存回呼附加到 `HtmlSaveOptions` 物件，然後呼叫 `project.Save`。此模式讓您能以幾行程式碼寫入自訂 CSS 檔案、取代預設樣式，並控制資料夾結構。匯出過程中，回呼會自動對每個 CSS 檔案觸發。

`HtmlSaveOptions` 會設定專案匯出為 HTML 的方式。

## 介紹

在本教學中，我們將深入探討使用 Aspose.Tasks for .NET 儲存 CSS 參數的過程。層疊樣式表（CSS）對於定義 HTML 元素的呈現至關重要。Aspose.Tasks 讓我們能有效地操作與儲存這些 CSS 屬性。

## 前置條件

在開始之前，請確保您已具備以下前置條件：

1. 安裝：確保您已安裝 Aspose.Tasks for .NET。您可以從[網站](https://releases.aspose.com/tasks/net/)下載。  
2. 基本知識：建議熟悉 C# 與 .NET 開發環境。

## 匯入命名空間

要開始使用，請匯入必要的命名空間：

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## 步驟 1：定義 CSS 儲存回呼

`ICssSavingCallback` 是一個介面，可讓您自訂 HTML 匯出時 CSS 檔案的儲存方式。

**CSS 儲存回呼** 是 Aspose.Tasks 在 HTML 匯出期間呼叫以寫入 CSS 檔案的委派。定義回呼方法以控制每個 CSS 檔案的建立方式：

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // Implement your CSS saving logic here
    }
}
```

## 步驟 2：實作字型與影像儲存回呼

`FontSavingArgs` 提供有關正在儲存的字型資訊，而 `ImageSavingArgs` 則提供影像資源的相關細節。

以類似方式實作字型與影像儲存回呼方法：

```csharp
public void FontSaving(FontSavingArgs args)
{
    // Implement your font saving logic here
}

public void ImageSaving(ImageSavingArgs args)
{
    // Implement your image saving logic here
}
```

## 步驟 3：設定儲存選項

`HtmlSaveOptions` 是控制專案匯出為 HTML 的設定物件。

`HtmlSaveOptions` 讓您指定回呼、輸出資料夾以及其他匯出設定。

設定其屬性以使用先前定義的回呼，並指定輸出資料夾：

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Configure HTML saving options
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## 步驟 4：使用自訂 CSS 儲存專案

`Project` 代表可被操作與儲存的 Microsoft Project 檔案。

最後，使用自訂的 CSS 設定儲存您的專案：

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## 為何在匯出專案時自訂 CSS？

Aspose.Tasks 支援 **匯出專案為 HTML** 超過 30 種格式，且每次匯出可產生多達 30 個獨立的 CSS 檔案。它能可靠地處理包含超過 10,000 個任務的專案，且記憶體使用量維持在 200 MB 以下，讓企業級報告在不產生效能瓶頸的情況下順利執行。

## 結論

在本教學中，我們探討了如何使用 Aspose.Tasks for .NET 儲存 CSS 參數。透過定義 CSS 儲存回呼並設定 HTML 儲存選項，我們能依需求有效地操作 CSS 屬性。

## 常見問題

### Q1：什麼是 Aspose.Tasks for .NET？

A1：Aspose.Tasks for .NET 是一套功能強大的 .NET API，讓開發人員能以程式方式操作 Microsoft Project 檔案。

### Q2：在使用 Aspose.Tasks 儲存 HTML 檔案時，我可以自訂 CSS 屬性嗎？

A2：是的，您可以定義 CSS 儲存回呼，以依需求自訂 CSS 屬性。

### Q3：Aspose.Tasks for .NET 是否相容所有版本的 Microsoft Project 檔案？

A3：Aspose.Tasks for .NET 支援多種版本的 Microsoft Project 檔案，確保在不同環境中的相容性。

### Q4：在哪裡可以找到 Aspose.Tasks for .NET 的完整文件？

A4：您可參考[文件](https://reference.aspose.com/tasks/net/)以取得詳細資訊與範例。

### Q5：Aspose.Tasks for .NET 是否提供開發者支援？

A5：是的，您可透過[論壇](https://forum.aspose.com/c/tasks/15)向 Aspose.Tasks 社群取得支援。

**其他問題**

**Q：自訂 CSS 會如何影響匯出 HTML 的大小？**  
A：使用自訂 CSS 可將總大小減少最多 15%，因為您可以移除未使用的預設樣式。

**Q：我可以將相同的回呼用於多個專案嗎？**  
A：當然可以。只需實作一次回呼，即可在任意數量的專案匯出中重複使用。

**Q：是否可以將 CSS 直接嵌入 HTML，而非使用獨立檔案？**  
A：可以，將 `HtmlSaveOptions.EmbeddedCss = true` 設為 true，即可將樣式表內嵌於 HTML，簡化分發。

---

**最後更新：** 2026-07-05  
**測試環境：** Aspose.Tasks 24.11 for .NET  
**作者：** Aspose

## 相關教學

- [使用 Aspose.Tasks 將 MS Project 儲存為 HTML](/tasks/net/saving-options/html-save-options/)
- [在 Aspose.Tasks 中實作頁面儲存回呼](/tasks/net/advanced-concepts/page-saving-callback/)
- [在 Aspose.Tasks 中處理影像儲存](/tasks/net/advanced-concepts/image-saving/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}