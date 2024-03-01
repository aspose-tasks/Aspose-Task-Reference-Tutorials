---
title: Aspose.Tasks の計算タイプ
linktitle: Aspose.Tasks の計算タイプ
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks ライブラリの計算タイプを使用して .NET プロジェクトの値の計算をカスタマイズする方法を学びます。
type: docs
weight: 30
url: /ja/net/advanced-features/calculation-type/
---
## 導入

このチュートリアルでは、Aspose.Tasks for .NET の計算タイプ機能を調べます。 Aspose.Tasks は、.NET 開発者がシステムに Microsoft Project をインストールしなくても Microsoft Project ファイルを操作できるようにする強力なライブラリです。計算タイプを使用すると、プロジェクト内のタスクとサマリー タスクの値を計算する方法を定義できます。

## 前提条件

始める前に、次の前提条件を満たしていることを確認してください。

1. C# と .NET Framework の基本的な知識。
2. Visual Studio がシステムにインストールされている。
3.  Aspose.Tasks for .NET ライブラリがインストールされています。からダウンロードできます[ここ](https://releases.aspose.com/tasks/net/).
4. 参照用の Aspose.Tasks for .NET ドキュメントへのアクセスが可能[ここ](https://reference.aspose.com/tasks/net/).

## 名前空間のインポート

例に入る前に、必要な名前空間を必ずインポートしてください。

```csharp
using Aspose.Tasks;
using System;


```

## ステップ 1: 新しいプロジェクトを作成する

まず、新しいプロジェクト オブジェクトを作成しましょう。

```csharp
var project = new Project();
```

## ステップ 2: タスクを追加する

次に、プロジェクトにタスクを追加しましょう。

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## ステップ 3: 拡張属性の計算タイプを定義する

[計算タイプ] を [式] に設定して拡張属性定義を作成します。

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## ステップ 4: 集計行の計算タイプを定義する

次に、サマリー タスクの値が平均ロールアップ タイプを使用して計算される別の拡張属性定義を作成します。

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## 結論

このチュートリアルでは、Aspose.Tasks for .NET で計算タイプを操作する方法を検討しました。拡張属性の計算タイプを定義することで、プロジェクト内のタスクおよびサマリー タスクの値の計算方法をカスタマイズでき、柔軟性と制御が向上します。

## よくある質問

### Q1: Aspose.Tasks の計算タイプとは何ですか?

A1: Aspose.Tasks の計算タイプは、プロジェクト内のタスクおよびサマリー タスクの値の計算方法を決定し、数式やロールアップなどのオプションを提供します。

### Q2: 拡張属性の計算タイプを設定するにはどうすればよいですか?

A2: 拡張属性の CalculationType プロパティを適切に定義することで、拡張属性の計算タイプを設定できます。

### Q3: プロジェクトの集計行の計算タイプをカスタマイズできますか?

A3: はい、Aspose.Tasks を使用すると、集計行の計算タイプを指定できるため、要件に基づいて値の計算を調整できます。

### Q4: サマリー タスクの計算に使用できるさまざまなロールアップ タイプはありますか?

A4: はい、Aspose.Tasks は、サマリー タスクの値を計算するために、Average、Sum、Count などのさまざまなロールアップ タイプを提供します。

### Q5: Aspose.Tasks for .NET に関するその他のリソースはどこで見つけられますか?

 A5: ドキュメントとコミュニティ サポート フォーラムを参照できます。[.NET 用の Aspose.Tasks](https://reference.aspose.com/tasks/net/)包括的な指導と支援を求めて。