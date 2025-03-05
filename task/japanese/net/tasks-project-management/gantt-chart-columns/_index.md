---
title: Aspose.Tasks を使用してガント チャートの列をカスタマイズする
linktitle: Aspose.Tasks のガント チャートの列
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET でガント チャートの列を調整して、特定のタスク情報を効率的に表示する方法を学びます。
type: docs
weight: 21
url: /ja/net/tasks-project-management/gantt-chart-columns/
---
## 導入
ガント チャートはプロジェクト管理の基本ツールであり、タスク、タイムライン、リソースを視覚的に表現します。 Aspose.Tasks for .NET は、特定のタスク情報を表示する列のカスタマイズなど、ガント チャートを操作するための強力な機能を提供します。このチュートリアルでは、Aspose.Tasks for .NET を使用してガント チャートの列を操作する方法を説明します。
## 前提条件
始める前に、以下のものがあることを確認してください。
1. インストール: Aspose.Tasks for .NET がシステムにインストールされています。そうでない場合は、からダウンロードしてインストールします[ここ](https://releases.aspose.com/tasks/net/).
2. .NET 開発環境: C# と .NET Framework の実践的な知識。
3. サンプル プロジェクト ファイル: サンプルの Microsoft Project ファイル (`.mpp`) 実験するのに便利です。お持ちでない場合は、MS Project で簡単なプロジェクトを作成して保存できます。

## 名前空間のインポート
まず、Aspose.Tasks for .NET を操作するために必要な名前空間をインポートする必要があります。
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Globalization;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## ステップ 1: プロジェクト ファイルをロードする
を使用してプロジェクト ファイルをロードします。`Project` Aspose.Tasks によって提供されるクラス:
```csharp
//ドキュメントディレクトリへのパス。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var task = project.RootTask.Children.GetById(1);
```
## ステップ 2: ガント チャートの列を定義する
ガント チャートに表示する列を定義します。組み込みフィールドを指定することも、カスタムフィールドを作成することもできます。
```csharp
var columns = new List<ViewColumn>
{
    new GanttChartColumn(20, Field.TaskUniqueID),
    new GanttChartColumn("Name", 150, Field.TaskName),
    new GanttChartColumn("Start", 100, Field.TaskStart),
    new GanttChartColumn("End", 100, Field.TaskFinish),
    new GanttChartColumn("R-Initials", 100, Field.TaskResourceInitials),
    new GanttChartColumn("R-Names", 100, Field.TaskResourceNames),
    new GanttChartColumn("Work", 50, Field.TaskWork),
    new GanttChartColumn(
        "Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new GanttChartColumn(
        "Actual Cost", 
        80,
        delegate(Task t)
        {
            return t.Get(Tsk.ActualCost).ToString(CultureInfo.InvariantCulture);
        },
        Field.TaskActualCost)
};
```
## ステップ 3: 列を反復処理する
定義された列を反復処理して、そのプロパティにアクセスし、情報を表示します。
```csharp
foreach (var column in columns)
{
    var col = (GanttChartColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(task));
    Console.WriteLine();
}
```
## ステップ 4: ガント チャートを CSV に保存する
定義された列を含むガント チャートを CSV ファイルに保存します。
```csharp
var options = new CsvOptions
{
    View = new ProjectView(columns)
};
project.Save(DataDir + "WorkWithGanttChartColumn_out.csv", options);
```
これらの手順に従うことで、Aspose.Tasks for .NET でガント チャートの列を効果的に操作できるようになり、必要に応じてタスク情報をカスタマイズして表示できるようになります。

## 結論
Aspose.Tasks for .NET でガント チャートの列の操作をマスターすると、プロジェクト管理ビジュアルを特定のニーズに合わせて調整する無限の可能性が広がります。このチュートリアルで概説されている手順に従うことで、タスク情報を効率的に処理し、プロジェクトの明確さと組織性を高めることができます。
## よくある質問
### Q: Aspose.Tasks for .NET でカスタム列を作成できますか?
A: はい、カスタム列を定義して、プロジェクトの要件に応じて特定のタスク属性を表示できます。
### Q: Aspose.Tasks for .NET は、Microsoft Project ファイルのすべてのバージョンと互換性がありますか?
A: Aspose.Tasks for .NET は、さまざまなバージョンの Microsoft Project ファイルをサポートし、さまざまなプロジェクト環境間での互換性を確保します。
### Q: Aspose.Tasks for .NET を使用して複雑なプロジェクト構造を処理するにはどうすればよいですか?
A: Aspose.Tasks for .NET は、複雑なプロジェクト構造を管理するための包括的な API と機能を提供し、柔軟性と拡張性を提供します。
### Q: ガント チャートに追加できる列の数に制限はありますか?
A: Aspose.Tasks for .NET は広範なカスタマイズ オプションを提供しており、制限なくガント チャートに多数の列を追加できます。
### Q: Aspose.Tasks for .NET の追加のサポートとリソースはどこで見つけられますか?
A: Aspose.Tasks for .NET が提供するドキュメント、コミュニティ フォーラム、サポート チャネルを調べて、包括的なリソースや支援にアクセスできます。