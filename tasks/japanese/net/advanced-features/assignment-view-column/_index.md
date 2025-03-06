---
title: Aspose.Tasks のカスタム割り当てビュー列
linktitle: Aspose.Tasks のカスタム割り当てビュー列
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET にカスタム割り当てビュー列を追加して、プロジェクト管理機能を強化する方法を学びます。
weight: 16
url: /ja/net/advanced-features/assignment-view-column/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks のカスタム割り当てビュー列

## 導入

このチュートリアルでは、Aspose.Tasks for .NET を使用して割り当てビューのカスタム列を追加する方法を検討します。カスタム列を使用すると柔軟性が高まり、プロジェクト管理のニーズに関連する追加情報を表示できます。

## 前提条件

始める前に、以下のものがあることを確認してください。

1. C# プログラミング言語の基本的な知識。
2.  Aspose.Tasks for .NET ライブラリがインストールされています。そうでない場合は、ダウンロードできます[ここ](https://releases.aspose.com/tasks/net/).
3. Visual Studio などの統合開発環境 (IDE)。

## 名前空間のインポート

まず、カスタム割り当てビュー列の作成に必要なクラスとメソッドにアクセスするために必要な名前空間をインポートしましょう。

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## ステップ 1: プロジェクトをロードする

まず、次のコマンドを使用してプロジェクト ファイルをロードします。`Project`クラス：

```csharp
//ドキュメント ディレクトリへのパス。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject2.mpp");
```

## ステップ 2: スプレッドシートの保存オプションを作成する

次に、インスタンスを作成します`Spreadsheet2003SaveOptions`これにより、割り当てビューの列をカスタマイズできるようになります。

```csharp
var options = new Spreadsheet2003SaveOptions();
```

## ステップ 3: カスタム列を定義する

次に、のインスタンスを作成してカスタム列を定義します。`AssignmentViewColumn`。このクラスには、列名、幅、および代入データを列テキストに変換するためのデリゲート関数が必要です。

```csharp
var column = new AssignmentViewColumn("Notes", 200, delegate(ResourceAssignment assignment) { return assignment.Get(Asn.NotesText); });
```

## ステップ 4: カスタム列をオプションに追加する

カスタム列を保存オプションの割り当てビュー列コレクションに追加します。

```csharp
options.AssignmentView.Columns.Add(column);
```

## ステップ 5: 割り当てを反復処理する

プロジェクト内の各リソース割り当てを反復処理し、カスタム列テキストを表示します。

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

## ステップ 6: カスタム列を含むプロジェクトを保存する

最後に、カスタム割り当てビュー列を含むプロジェクトを保存します。

```csharp
project.Save(OutDir + "UsingSpreadsheet2003SaveOptions_out.xml", options);
```

## 結論

このチュートリアルでは、Aspose.Tasks for .NET を使用してカスタム割り当てビュー列を追加する方法を学びました。カスタム列により、プロジェクト要件に合わせた追加情報を柔軟に表示でき、プロジェクト管理機能が強化されます。

## よくある質問

### Q1: 複数のカスタム列を割り当てビューに追加できますか?

 A1: はい、追加のインスタンスを作成することで、複数のカスタム列を追加できます。`AssignmentViewColumn`そしてそれらを`Columns`コレクション。

### Q2: 共通の割り当てフィールドに使用できる事前定義されたコンバータはありますか?

A2: はい、Aspose.Tasks には一般的な割り当てフィールド用の定義済みコンバータが用意されており、カスタム列のデータを簡単に抽出できるようになります。

### Q3: テキストの書式設定やスタイルの適用など、カスタム列の外観をカスタマイズできますか?

A3: はい、幅、フォント、配置などのプロパティを変更することでカスタム列の外観をカスタマイズできます。

### Q4: 割り当てビューからデフォルトの列を削除することはできますか?

 A4: はい、デフォルトの列を削除できます。`Columns`コレクションを実行するか、幅をゼロに設定します。

### Q5: Aspose.Tasks は、カスタム列を含むスプレッドシート以外の他の形式へのプロジェクトのエクスポートをサポートしていますか?

A5: はい。Aspose.Tasks は、PDF、HTML、XML などのさまざまな形式へのプロジェクトのエクスポートをサポートしており、汎用性の高いプロジェクト レポート オプションが可能です。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
