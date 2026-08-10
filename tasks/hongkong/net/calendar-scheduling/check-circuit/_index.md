---
date: 2026-04-09
description: 學習如何使用 Aspose.Tasks for .NET 檢查電路並驗證 Microsoft Project 檔案完整性。
keywords:
- how to check circuit
- check project structure
- validate microsoft project
- project file integrity check
linktitle: 在 Aspose.Tasks 中檢查電路
second_title: Aspose.Tasks .NET API
title: 如何在 Aspose.Tasks 中檢查電路
url: /zh-hant/net/calendar-scheduling/check-circuit/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks 中檢查電路

## 介紹

在 .NET 開發領域，有效管理任務與專案至關重要。**檢查電路**在專案檔中是一項常見需求，當您需要確保 Microsoft Project 時程的完整性時。Aspose.Tasks for .NET 提供簡易的 API，讓您僅透過幾行程式碼即可驗證專案結構並偵測斷裂的任務層級。

## 快速回答
- **「檢查電路」的功能是什麼？** 它會掃描任務層級，尋找循環參照或斷裂的父子關聯。  
- **為什麼它很重要？** 它有助於保持專案檔案的整潔，並防止 Microsoft Project 中的計算錯誤。  
- **使用哪個函式庫？** Aspose.Tasks for .NET。  
- **需要授權嗎？** 生產環境需要臨時授權；測試可使用免費試用版。  
- **支援的平台？** .NET Framework、.NET Core 以及 .NET 5/6+。

## 什麼是專案電路檢查？

電路檢查（有時稱為「結構驗證」）會從根任務開始遍歷每個任務，並驗證每個子任務是否指向有效的父任務。若發現循環或孤立任務，函式庫會拋出 `TasksException`，讓您以程式方式處理此問題。

## 為什麼要驗證 Microsoft Project 檔案？

- **防止計算錯誤：** 循環參照可能會破壞時程計算。  
- **維持資料完整性：** 確保每個任務屬於正確的層級結構。  
- **自動化品質檢查：** 在 CI 流程中，專案檔案會自動產生或修改，此功能相當有用。  
- **節省時間：** 及早偵測問題，免於在 Microsoft Project 中除錯破損的時程。

## 前置條件

在深入本教學之前，請確保已具備以下前置條件：

1. Visual Studio：確保您的系統已安裝 Visual Studio。  
2. Aspose.Tasks for .NET：從 [here](https://releases.aspose.com/tasks/net/) 下載並安裝 Aspose.Tasks for .NET 函式庫。  
3. 基本 C# 知識：熟悉 C# 程式語言才能跟隨範例。

## 匯入命名空間

在您的 C# 專案中，加入以下命名空間以存取所需的類別與方法：

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;
```

## 步驟 1：載入專案檔案

首先載入您想要檢查結構是否斷裂的 Microsoft Project 檔案（.mpp）。使用 `Project` 類別載入檔案。

```csharp
var project = new Project(DataDir + "ParentChildTasks.mpp");
```

## 步驟 2：檢查專案結構

為了偵測專案中任何斷裂的結構，我們將使用 `CheckCircuit` 類別搭配 `TaskUtils.Apply` 方法。此步驟 **檢查專案結構**，若發現電路問題將拋出例外。

```csharp
try
{
    TaskUtils.Apply(project.RootTask, new CheckCircuit(), 0);
}
catch (TasksException ex)
{
    Console.WriteLine(ex);
}
```

## 常見陷阱與提示

- **陷阱：** 忘記將呼叫包在 `try/catch` 中。`CheckCircuit` 操作在發現問題時會拋出 `TasksException`，因此必須妥善處理。  
- **提示：** 使用 `project.RootTask` 作為入口點；傳入其他任務可能會遺漏上游問題。  
- **提示：** 修正電路後，可重新執行檢查以確認專案檔案的完整性。

## 常見問題

**Q: 我可以在其他 .NET 框架中使用 Aspose.Tasks for .NET 嗎？**  
A: 可以，Aspose.Tasks for .NET 相容於多種 .NET 框架，包括 .NET Core 與 .NET Framework。

**Q: 購買前是否有試用版可供使用？**  
A: 有，您可從 [here](https://releases.aspose.com/) 取得 Aspose.Tasks for .NET 的免費試用版。

**Q: 如何取得 Aspose.Tasks for .NET 的支援？**  
A: 您可前往 Aspose.Tasks 社群論壇 [here](https://forum.aspose.com/c/tasks/15) 尋求協助。

**Q: 測試用途是否需要臨時授權？**  
A: 需要，您可從 [here](https://purchase.aspose.com/temporary-license/) 取得臨時授權以供測試。

**Q: 在哪裡可以購買 Aspose.Tasks for .NET？**  
A: 您可從 [here](https://purchase.aspose.com/buy) 購買 Aspose.Tasks for .NET 完整版。

## 結論

透過本指南，您已學會在 Aspose.Tasks 專案中 **檢查電路**，有效驗證專案檔案的完整性並確保任務層級的整潔。將此檢查納入建置或匯入流程，可節省大量手動除錯時間，讓您的時程保持可靠。

---

**最後更新：** 2026-04-09  
**測試環境：** Aspose.Tasks for .NET（最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}