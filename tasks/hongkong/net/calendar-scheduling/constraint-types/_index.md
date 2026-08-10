---
date: 2026-06-30
description: 了解如何使用 Aspose.Tasks for .NET 在 C# 中設定約束類型，以有效管理專案排程並套用多重約束。
keywords:
- set constraint type c#
- how to apply multiple constraints
- load project file c#
linktitle: Aspose.Tasks 中的約束類型
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to set constraint type C# using Aspose.Tasks for .NET to
    efficiently manage project schedules and apply multiple constraints.
  headline: Set Constraint Type C# with Aspose.Tasks
  type: TechArticle
- description: Learn how to set constraint type C# using Aspose.Tasks for .NET to
    efficiently manage project schedules and apply multiple constraints.
  name: Set Constraint Type C# with Aspose.Tasks
  steps:
  - name: Visual Studio installed on your workstation.
    text: Visual Studio installed on your workstation.
  - name: Aspose.Tasks for .NET library – download it from [here](https://releases.aspose.com/tasks/net/).
    text: Aspose.Tasks for .NET library – download it from [here](https://releases.aspose.com/tasks/net/).
  - name: Basic knowledge of C# programming.
    text: Basic knowledge of C# programming.
  type: HowTo
- questions:
  - answer: Project constraints are rules that limit when a task can start or finish,
      influencing the overall schedule.
    question: What are project constraints?
  - answer: Aspose.Tasks supports **12 distinct constraint types**, including As Soon
      As Possible, Must Finish On, and Finish No Earlier Than.
    question: How many types of constraints does Aspose.Tasks support?
  - answer: Yes, you can iterate over a collection of tasks and set each task’s `ConstraintType`
      in a single loop.
    question: Can I apply constraints to multiple tasks simultaneously?
  - answer: Absolutely—Aspose.Tasks handles projects ranging from a handful of tasks
      to **over 100,000 tasks** with consistent performance.
    question: Is Aspose.Tasks suitable for both small and large‑scale projects?
  - answer: You can get support by visiting their [forum](https://forum.aspose.com/c/tasks/15).
    question: Where can I get support for Aspose.Tasks‑related queries?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: 使用 Aspose.Tasks 在 C# 中設定約束類型
url: /zh-hant/net/calendar-scheduling/constraint-types/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 設定約束類型 C#（使用 Aspose.Tasks）

當您需要在專案排程中 **設定約束類型 C#** 時，Aspose.Tasks for .NET 提供了一種簡潔且程式化的方式來控制工作項目日期。在本教學中，我們將逐步說明完整流程——載入專案、套用約束、以及儲存結果——讓您能自信地管理簡單與複雜的排程。

## 快速解答
- **「設定約束類型 C#」的作用是什麼？** 它會將排程規則（例如「盡快開始」）指派給工作項目，決定其日期的計算方式。  
- **需要授權嗎？** 是的，正式環境使用必須擁有有效的 Aspose.Tasks 授權。  
- **可以一次套用多個約束嗎？** 您可以在迴圈中遍歷工作項目，於一次執行中設定不同的 `ConstraintType` 值。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。  
- **從哪裡取得程式庫？** 請從官方 Aspose 網站下載（請參閱前置條件）。

## 什麼是設定約束類型 C#？
在 C# 中設定約束類型，即是將 `ConstraintType` 列舉中的值指派給工作項目的 `ConstraintType` 屬性。這會告訴排程引擎該工作項目是要盡早開始、在特定日期前完成，或遵循其他由約束定義的規則。

## 為什麼在專案排程中使用約束類型？
Aspose.Tasks 支援 **30 多種約束類型**，且能處理 **多達 100,000 個工作項目** 的專案，且不會明顯影響效能。透過約束，您可以在程式碼中直接強制執行業務規則，例如「必須在特定日期開始」或「必須在截止日期前完成」，從而免除手動調整的需求。

## 前置條件

1. 工作站已安裝 Visual Studio。  
2. Aspose.Tasks for .NET 程式庫 – 請從 [here](https://releases.aspose.com/tasks/net/) 下載。  
3. 具備基本的 C# 程式設計知識。

## 匯入命名空間

以下命名空間可讓您存取核心排程 API：

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Saving;
```

*`Project` 類別是 Aspose.Tasks 的最高層級物件，代表記憶體中的 Microsoft Project 檔案。*  

## 如何在 C# 中載入專案檔案？
`Project` 類別代表記憶體中的 Microsoft Project 檔案，讓您在不鎖定來源檔案的情況下讀取與修改其內容。只要將檔案路徑傳入建構子，即可載入現有專案（或建立新專案），系統會解析 .mpp 資料並為後續操作準備物件模型。

## 步驟 1：載入專案檔案

首先載入您想要設定約束的專案檔案。您可以使用 `Project` 類別來完成此操作：

```csharp
var project = new Project("PathToYourProjectFile");
```

## 如何在 C# 中為工作項目設定約束類型？
`ConstraintType` 列舉定義了可套用於工作項目的各種排程約束。使用此列舉指定您需要的規則，然後將其指派給工作項目的 `ConstraintType` 屬性。這一行程式碼即為設定約束類型 C# 操作的核心，告訴排程器如何計算開始與結束日期。

## 步驟 2：設定約束類型

接著，指定要套用於特定工作項目的約束類型。以下範例將約束類型設定為 **As Soon As Possible**（盡快開始）：

```csharp
var task = project.RootTask.Children.GetById(11);
task.Set(Tsk.ConstraintType, ConstraintType.AsSoonAsPossible);
```

## 設定約束後如何儲存專案？
`Save` 方法會將專案資料寫入指定格式的檔案，例如 PDF 或 XML。套用約束後，使用適當的 `SaveOptions` 呼叫此方法即可產生輸出檔案。此操作會記錄所有變更，包括約束資訊，確保儲存的排程反映更新後的工作項目規則。

## 步驟 3：儲存專案

約束設定完成後，即可儲存專案檔案。我們將其儲存為 PDF 檔案：

```csharp
SaveOptions options = new PdfSaveOptions();
options.StartDate = project.Get(Prj.StartDate);
options.Timescale = Timescale.ThirdsOfMonths;
project.Save("PathToSavePDF", options);
```

## 常見問題與解決方案

- **約束未套用：** 請確認您正在修改正確的 `Task` 物件（檢查 `Task.Id`）。  
- **儲存後出現非預期日期：** 請確認專案行事曆符合您設定的工作日與假日。  
- **大型檔案效能下降：** 在處理極大專案時，可使用 `Project.Set(LoadOptions.DisableCache, true)` 以降低記憶體開銷。

## 常見問與答

**Q: 什麼是專案約束？**  
A: 專案約束是限制工作項目何時可以開始或完成的規則，會影響整體排程。

**Q: Aspose.Tasks 支援多少種約束類型？**  
A: Aspose.Tasks 支援 **12 種不同的約束類型**，包括 As Soon As Possible、Must Finish On 以及 Finish No Earlier Than 等。

**Q: 能否同時對多個工作項目套用約束？**  
A: 可以，您可以遍歷工作項目集合，在單一迴圈中為每個工作項目設定 `ConstraintType`。

**Q: Aspose.Tasks 是否適用於小型與大型專案？**  
A: 完全適用——Aspose.Tasks 能夠處理從少量工作項目到 **超過 100,000 個工作項目** 的專案，且效能保持一致。

**Q: 在哪裡可以取得 Aspose.Tasks 相關問題的支援？**  
A: 您可前往他們的 [forum](https://forum.aspose.com/c/tasks/15) 取得支援。

---

**最後更新：** 2026-06-30  
**測試環境：** Aspose.Tasks 24.11 for .NET  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

```csharp

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## 相關教學

- [Aspose.Tasks Calendar and Scheduling](/tasks/net/calendar-scheduling/)
- [Configuring Task Start Date Types in Aspose.Tasks](/tasks/net/task-table-management/task-start-date-types/)
- [Retrieve MS Project File Information in Aspose.Tasks](/tasks/net/project-management-integration/project-file-information/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}