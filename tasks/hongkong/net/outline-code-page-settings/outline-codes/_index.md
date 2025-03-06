---
title: 在 Aspose.Tasks for .NET 中管理專案大綱程式碼
linktitle: 在 Aspose.Tasks 中管理大綱程式碼
second_title: Aspose.Tasks .NET API
description: 學習使用 Aspose.Tasks for .NET 管理 MS Project 大綱程式碼。毫不費力地簡化專案組織。
type: docs
weight: 10
url: /zh-hant/net/outline-code-page-settings/outline-codes/
---
## 介紹
在本教學中，我們將探討如何使用 Aspose.Tasks for .NET 管理 Microsoft Project 大綱程式碼。大綱程式碼是 Microsoft Project 中的自訂字段，可讓使用者根據特定條件對任務進行分類和組織。 Aspose.Tasks 簡化了以程式設計方式讀取和操作這些大綱程式碼的過程。
## 先決條件
在我們開始之前，請確保您具備以下條件：
1.  Aspose.Tasks for .NET 函式庫：從下列位置下載並安裝 Aspose.Tasks for .NET 函式庫：[網站](https://releases.aspose.com/tasks/net/).
2. 開發環境：為.NET程式設計建置適當的開發環境，例如Visual Studio。
3. C#基礎知識：熟悉C#程式語言有利於理解程式碼範例。

## 導入命名空間
首先，您需要將必要的命名空間匯入到您的 C# 專案中。這允許您存取 Aspose.Tasks 庫提供的類別和方法。
1. 開啟 Visual Studio：啟動 Visual Studio IDE。
2. 建立新專案：啟動一個新的 C# 專案或開啟一個要使用 Aspose.Tasks 的現有專案。
3. 新增 Aspose.Tasks 參考：在解決方案資源管理器中右鍵單擊您的項目，選擇“管理 NuGet 套件”，搜尋“Aspose.Tasks”，然後安裝最新版本。
4. 匯入 Aspose.Tasks 命名空間：在 C# 檔案的頂部，新增下列 using 指令：
```csharp
using Aspose.Tasks;
using System;

```
## 第 1 步：定義文檔目錄
首先，設定包含 MS Project 檔案的目錄的路徑。
```csharp
String DataDir = "Your Document Directory";
```
代替`"Your Document Directory"`與專案文件的實際路徑。
## 第 2 步：載入專案文件
實例化一個新的`Project`透過載入 MS Project 檔案來實現物件。
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
這將使用指定的檔案初始化項目物件。
## 第三步：閱讀大綱程式碼
迭代專案中的所有任務並檢索其大綱程式碼。
```csharp
foreach (var task in project.RootTask.SelectAllChildTasks())
{
    if (task.OutlineCodes.Count <= 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes of the task: " + task.Get(Tsk.Name));
    foreach (var value in task.OutlineCodes)
    {
        Console.WriteLine("  Field Id: " + value.FieldId);
        Console.WriteLine("  Value Guid: " + value.ValueGuid);
        Console.WriteLine("  Value Id: " + value.ValueId);
    }
}
```
此程式碼片段循環遍歷每個任務，檢查其是否有大綱程式碼，並列印與該任務關聯的每個大綱程式碼的欄位 Id、值 Guid 和值 Id 等詳細資訊。

## 結論
總之，Aspose.Tasks for .NET 提供了以程式設計方式管理 Microsoft Project 大綱程式碼的強大功能。透過遵循本教程中概述的步驟，您可以使用 C# 有效地讀取和操作 MS Project 檔案中的大綱程式碼。
## 常見問題解答
### Q：我可以使用Aspose.Tasks修改大綱程式碼嗎？
答：是的，您可以使用 Aspose.Tasks for .NET 以程式設計方式修改大綱程式碼。只需存取任務的大綱程式碼並根據需要更新其值即可。
### Q：Aspose.Tasks 是否與所有版本的 Microsoft Project 相容？
答：Aspose.Tasks 支援多種 Microsoft Project 版本，包括 2003、2007、2010、2013、2016 和 2019。
### Q：Aspose.Tasks 是否需要商業使用授權？
答：是的，Aspose.Tasks 的商業用途需要有效的授權。您可以從 Aspose 網站取得許可證。
### Q：我可以在購買前試用 Aspose.Tasks 嗎？
答：是的，您可以從網站下載 Aspose.Tasks 的免費試用版來評估其功能和功能。
### Q：我可以在哪裡獲得 Aspose.Tasks 的支援？
答：您可以透過造訪論壇獲得 Aspose.Tasks 的支援：[Aspose.Tasks 論壇](https://forum.aspose.com/c/tasks/15).## 完整原始碼