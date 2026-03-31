---
date: 2026-03-19
description: Aspose.Tasks for .NET を使用してプロジェクトを XML にエクスポートする際に、複数のカスタム列を追加し、カスタム列の幅を設定する方法を学びましょう。
linktitle: Add Multiple Custom Columns to Assignment View in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks の割り当てビューに複数のカスタム列を追加する
url: /ja/net/advanced-features/assignment-view-column/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks の割り当てビューに複数のカスタム列を追加する

## Introduction

このチュートリアルでは、Aspose.Tasks for .NET を使用して割り当てビューに **複数のカスタム列** を追加する方法を紹介します。カスタム列を使用すると、メモ、コスト、カスタムフラグなどの追加データをエクスポートされたレポートに直接表示できます。ガイドの最後までに、カスタム列の幅を設定し、プロジェクトを XML にエクスポートし、ビューをプロジェクト管理のニーズに合わせて調整できるようになります。

## Quick Answers
- **What can I achieve?** カスタム列に任意の割り当てデータを表示し、その外観を制御できます。  
- **Which format supports it?** `Spreadsheet2003SaveOptions` を使用してプロジェクトを XML（または他の形式）にエクスポートします。  
- **Do I need a license?** はい、本番環境で使用するには有効な Aspose.Tasks ライセンスが必要です。  
- **Which .NET versions work?** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **How many columns can I add?** 無制限です – 追加の `AssignmentViewColumn` インスタンスを作成するだけです。

## What are multiple custom columns?
複数のカスタム列は、プロジェクトが保存またはエクスポートされる際にデフォルトの割り当て列と並んで表示されるユーザー定義フィールドです。`ResourceAssignment` オブジェクトの任意のプロパティ（カスタムメモ、コストコード、計算値など）を表示できる柔軟性を提供します。

## Why add multiple custom columns to the assignment view?
- **Enhanced reporting:** 組み込み列ではカバーされないプロジェクト固有の情報を含められます。  
- **Better decision‑making:** ステークホルダーは生データを掘り下げることなく、必要な正確なデータを確認できます。  
- **Consistent formatting:** 列幅とテキスト変換を制御し、見やすく整った出力を実現します。  

## Prerequisites

Before we dive in, make sure you have:

1. C# プログラミング言語の基本的な知識。  
2. Aspose.Tasks for .NET ライブラリがインストールされていること。未インストールの場合は **[here](https://releases.aspose.com/tasks/net/)** からダウンロードできます。  
3. Visual Studio などの統合開発環境（IDE）。

## Step-by-Step Guide

### Step 1: Import Namespaces
First, import the namespaces that provide the classes we’ll need for working with projects and visualizations.

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

### Step 2: Load the Project
Create a `Project` instance and load an existing MPP file.

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

### Step 3: Create Spreadsheet Save Options
Instantiate `Spreadsheet2003SaveOptions` – this object lets us customize the assignment view before exporting.

```csharp
var options = new Spreadsheet2003SaveOptions();
```

### Step 4: Define Custom Column
Create an `AssignmentViewColumn` for each piece of data you want to show. Below we add a **Notes** column with a width of 200 points.

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

**Tip:** To add *multiple* custom columns, repeat this step with different field names and delegate logic, then add each instance to `options.AssignmentView.Columns`.

### Step 5: Add Custom Column to Options
Add the column (or columns) to the `Columns` collection of the assignment view.

```csharp
options.AssignmentView.Columns.Add(column);
```

### Step 6: Iterate Through Assignments (Optional Debugging)
You can loop through the assignments to verify that the custom column text is generated correctly.

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var col in options.AssignmentView.Columns)
    {
        var assnCol = (AssignmentViewColumn)col;
        Console.WriteLine("Column Field: " + assnCol.Field);
        Console.WriteLine("Column Text (converted): " + assnCol.GetColumnText(assignment));
        Console.WriteLine();
    }
}
```

### Step 7: Save the Project with Custom Columns
Finally, save the project. The example saves to XML, but you can choose any supported format.

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## How to export project to XML with custom columns?
When you call `project.Save` with the configured `Spreadsheet2003SaveOptions`, Aspose.Tasks writes the project data—including all **multiple custom columns**—to the chosen XML file. This makes it easy to share enriched project information with other systems or stakeholders.

## Format custom column width for better readability
The second parameter of the `AssignmentViewColumn` constructor controls the column width (measured in points). Adjust this value to suit the amount of text you expect. For example, a width of **300** works well for longer notes, while **100** is sufficient for short flags.

## Common Issues and Solutions
- **Column text appears blank:** Ensure the delegate returns a string and that the underlying assignment property (e.g., `Asn.NotesText`) is populated.  
- **Columns are not visible in the exported file:** Verify that `options.AssignmentView.Columns` contains your custom columns before calling `Save`.  
- **Width seems ignored:** Some export formats have their own layout rules; XML respects the width, but PDF/HTML may need additional styling.

## Frequently Asked Questions

### Q1: Can I add multiple custom columns to the assignment view?
**A:** Yes, simply create additional `AssignmentViewColumn` objects and add each to `options.AssignmentView.Columns`.

### Q2: Are there predefined converters available for common assignment fields?
**A:** Yes, Aspose.Tasks provides built‑in converters for many standard fields, making it easy to pull data without writing custom delegates.

### Q3: Can I customize the appearance of custom columns, such as formatting text or applying styles?
**A:** Absolutely. Besides setting the width, you can modify font, alignment, and other visual properties through the column’s styling options.

### Q4: Is it possible to remove default columns from the assignment view?
**A:** You can exclude default columns by removing them from the `Columns` collection or by setting their width to zero.

### Q5: Does Aspose.Tasks support exporting projects to other formats besides spreadsheets with custom columns?
**A:** Yes, Aspose.Tasks can export to PDF, HTML, XML, and many other formats while preserving custom column definitions.

---

**Last Updated:** 2026-03-19  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}