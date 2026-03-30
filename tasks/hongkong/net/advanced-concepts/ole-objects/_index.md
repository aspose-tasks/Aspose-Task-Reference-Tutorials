---
date: 2026-03-16
description: 學習如何使用 Aspose.Tasks for .NET 移除 OLE 物件，並探索在專案中如何有效管理與清除 OLE。
linktitle: How to Remove OLE Objects in Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: 如何在 Aspose.Tasks for .NET 中移除 OLE 物件
url: /zh-hant/net/advanced-concepts/ole-objects/
weight: 22
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.Tasks for .NET 中移除 OLE 物件

## Introduction

Aspose.Tasks for .NET 為您提供對 Microsoft Project 檔案中 OLE（Object Linking and Embedding）物件的完整控制。在本教學中，您將學習**如何移除 OLE 物件**、如何**管理 OLE**內容，以及在不再需要時**清除 OLE**資料的具體步驟。完成後，您將能夠載入專案檔案、檢查其內嵌的 OLE 物件、安全地刪除它們，並以乾淨、可讀的 C# 程式碼儲存已清理的專案。

## Quick Answers
- **移除 OLE 物件的主要方法是什麼？** 使用 `project.OleObjects.Clear()`，然後儲存專案。  
- **我需要特別的授權嗎？** 生產環境使用需具備有效的 Aspose.Tasks 授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6+。  
- **我可以在移除前檢查 OLE 內容嗎？** 可以，遍歷 `project.OleObjects` 以讀取屬性或內容位元組。  
- **在大型專案中清除 OLE 物件安全嗎？** 絕對安全——此操作快速且不會影響其他專案資料。

## What is “remove OLE objects” in the context of Aspose.Tasks?

在 Aspose.Tasks 的情境中，「移除 OLE 物件」是指刪除儲存在 Microsoft Project（.mpp）檔案內的嵌入檔案（圖像、Excel 工作表、Word 文件等）。當您想減少檔案大小、消除過時的參考，或遵守資料保留政策時，這非常有用。

## Why manage OLE objects with Aspose.Tasks?

- **細緻的控制** – 取得每個 OLE 物件的 ID、名稱與原始位元組。  
- **自動化** – 以程式方式清理多個專案，無需在 Microsoft Project 中開啟。  
- **跨版本支援** – 可處理 Project 2007‑2023 檔案。  

## Prerequisites

在開始之前，請確保您已具備以下條件：

1. **Aspose.Tasks for .NET** 已安裝。您可從 [here](https://releases.aspose.com/tasks/net/) 下載。  
2. 具備 **C#** 與 **.NET** 生態系的基本知識。  
3. 如 **Visual Studio**（Community 或更高版）等開發環境。  

## Import Namespaces

首先，匯入提供 Aspose.Tasks API 的命名空間：

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## How to manage OLE objects – Step‑by‑step guide

以下示範三種常見情境：

1. **檢查 OLE 物件** – 讀取其屬性與二進位內容的片段。  
2. **清除所有 OLE 物件** – 核心的「移除 OLE 物件」操作。  
3. **讀取視覺放置資訊** – 當您需要調整 OLE 物件在甘特圖或其他檢視中的顯示方式時很有用。

### Scenario 1: Inspect OLE objects

情境 1：檢查 OLE 物件

#### Step 1: Load project file  
步驟 1：載入專案檔案  
```csharp
var project = new Project("TaskImage2010.mpp");
```

#### Step 2: Access OLE objects  
步驟 2：存取 OLE 物件  
```csharp
List<OleObject> oleObjects = project.OleObjects.ToList();
```

#### Step 3: Iterate through OLE objects  
步驟 3：遍歷 OLE 物件  
```csharp
foreach (var oleObject in oleObjects)
{
    // Access and print OLE object properties
    Console.WriteLine("Id: " + oleObject.Id);
    Console.WriteLine("Name: " + oleObject.Name);
    // Continue for other properties
}
```

#### Step 4: Retrieve a small chunk of the binary content (optional)  
步驟 4：取得二進位內容的一小段（可選）  
```csharp
private string Get10Bytes(OleObject oleObject)
{
    byte[] bytes = oleObject.Content;
    var chunk = new byte[10];
    Array.Copy(bytes, chunk, 10);
    var builder = new StringBuilder();
    foreach (var b in chunk)
    {
        builder.Append(b + ", ");
    }

    builder.Remove(builder.Length - 3, 1);
    return builder.ToString();
}
```

### Scenario 2: How to clear OLE – removing all embedded objects

情境 2：如何清除 OLE – 移除所有嵌入的物件

#### Step 1: Load project file  
步驟 1：載入專案檔案  
```csharp
var project = new Project("TaskImage2010.mpp");
```

#### Step 2: Clear OLE objects  
步驟 2：清除 OLE 物件  
```csharp
project.OleObjects.Clear();
```

#### Step 3: Save the cleaned project  
步驟 3：儲存已清理的專案  
```csharp
project.Save("ClearedProject.mpp");
```

> **專業提示：** 清除 OLE 物件後，您可以使用不同的檔名呼叫 `project.Save`，以保留原始檔案不受影響。

### Scenario 3: Getting visual object placement properties

情境 3：取得視覺物件放置屬性

#### Step 1: Load project file  
步驟 1：載入專案檔案  
```csharp
var project = new Project("TaskImage2010.mpp");
```

#### Step 2: Access the first OLE object and its placement in the Gantt view  
步驟 2：存取第一個 OLE 物件及其在甘特圖檢視中的放置位置  
```csharp
var oleObject = project.OleObjects.First();
var view = project.Views.First(v => v.Name == "&Gantt Chart");
var oleObjectPlacement = view.VisualObjectsPlacements.First(p => p.OleObjectId == oleObject.Id);
```

#### Step 3: Retrieve placement properties  
步驟 3：取得放置屬性  
```csharp
Console.WriteLine("BorderLineColor: {0}", oleObjectPlacement.BorderLineColor);
Console.WriteLine("BorderLineThickness: {0}", oleObjectPlacement.BorderLineThickness);
if (oleObjectPlacement.TaskId > 0)
{
    Console.WriteLine("Attached to task: {0}", oleObjectPlacement.TaskId);
}
else
{
    Console.WriteLine("Attached to timescale date: {0}", oleObjectPlacement.TimescaleDate);
}
```

## Common pitfalls and troubleshooting

常見陷阱與疑難排解

| 問題 | 原因 | 解決方法 |
|------|------|----------|
| `project.OleObjects` 為空 | 原始 .mpp 檔案未包含 OLE 物件。 | 確認專案檔案確實嵌入了 OLE 資料（例如，附加的 Excel 工作表）。 |
| `project.Save` 拋出例外 | 檔案被鎖定或您沒有寫入權限。 | 關閉所有開啟的檔案實例，並確保目標資料夾可寫入。 |
| 內容位元組看起來損壞 | 您將完整位元組陣列當作文字讀取。 | 使用 `Get10Bytes` 或將位元組寫入檔案，以在適當的檢視器中檢查。 |

## Frequently Asked Questions

**Q: Aspose.Tasks 能處理各種 OLE 物件格式嗎？**  
A: 可以，它支援圖像、Office 文件、PDF 以及許多其他 OLE 格式。

**Q: API 是否相容於較舊的 Microsoft Project 版本？**  
A: 絕對相容——Aspose.Tasks 可處理 2007 至最新 2023 版的 Project 檔案。

**Q: 如何只移除特定的 OLE 物件，而不是全部清除？**  
A: 依據 `Id` 或 `Name` 找到目標 `OleObject`，然後在儲存前呼叫 `project.OleObjects.Remove(oleObject)`。

**Q: 清除 OLE 物件會影響任務相依性或排程嗎？**  
A: 不會。OLE 物件是獨立的視覺元素，移除它們不會修改任務關係。

**Q: 我可以在哪裡找到更多 OLE 操作的範例？**  
A: 請參閱官方 Aspose.Tasks 文件與 `OleObject`、`VisualObjectsPlacements` 類別的 API 參考。

## Conclusion

結論

我們已說明在 Aspose.Tasks for .NET 中**移除 OLE 物件**與管理 OLE 內容的全部要點。透過逐步範例，您可以檢查、清除並調整 OLE 物件的視覺放置，讓專案檔案保持精簡且聚焦。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-16  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose