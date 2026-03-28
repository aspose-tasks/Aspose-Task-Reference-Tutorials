---
date: 2026-03-24
description: Aspose.Tasks for .NETで計算設定を行う方法を学び、サマリ値の計算、計算式の定義、ロールアップサマリの設定例をご紹介します。
linktitle: Calculation Type in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Aspose.Tasksで計算タイプを設定する方法
url: /ja/net/advanced-features/calculation-type/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks で計算タイプを設定する方法

## はじめに

Microsoft Project ファイル内のタスクやサマリ行の **計算ルールの設定方法** が必要な場合、本チュートリアルでは Aspose.Tasks for .NET を使用した具体的な手順を示します。**計算タイプの例** を通して、**サマリ値の計算** 方法をデモし、**計算式の定義** と **拡張属性のロールアップサマリ設定** について解説します。最後まで読むと、タスクをプロジェクトに追加し、カスタム計算ロジックを設定し、ロールアップ動作を自信を持って制御できるようになります。

## クイック回答
- **主な目的は何ですか？** プロジェクトファイル内でタスクとサマリの値がどのように計算されるかを制御することです。  
- **使用する API クラスは？** `ExtendedAttributeDefinition` と `CalculationType`、`SummaryRowsCalculationType` を組み合わせて使用します。  
- **数式は使えますか？** はい – `CalculationType = CalculationType.Formula` として数式文字列を設定します。  
- **サマリ値をロールアップするには？** `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` を使用し、`RollupType`（例: `Average`）を指定します。  
- **ライセンスは必要ですか？** 本番環境で使用する場合は有効な Aspose.Tasks ライセンスが必要です。

## Calculation Type とは何か、そして計算を設定する方法

`CalculationType` は、拡張属性の値を Aspose.Tasks がどのように算出するかを指示します。静的値、数式、または子タスクからのロールアップのいずれかを選択できます。正しく計算タイプを設定することで、手動で更新することなくプロジェクトがカスタムビジネスルールを反映できるようになります。

## なぜ計算タイプを使ってサマリ値を計算するのか？

プロジェクトにサマリタスクが含まれる場合、サマリ行に集計データ（例: 総コスト、平均期間）を表示したくなることが多いです。`SummaryRowsCalculationType` と `RollupType` を通して **サマリ値の計算** を設定すれば、個々のタスクを変更するたびに集計が自動的に同期されます。

## 前提条件

開始する前に以下を確認してください：

1. C# と .NET フレームワークの基本的な知識。  
2. Visual Studio（最新バージョンいずれか）がインストールされていること。  
3. Aspose.Tasks for .NET ライブラリがインストール済み – ダウンロードは [here](https://releases.aspose.com/tasks/net/) から。  
4. 公式の Aspose.Tasks for .NET ドキュメントへのアクセスが可能 – こちらから参照できます: [here](https://reference.aspose.com/tasks/net/)。

## 名前空間のインポート

サンプルコードを実装する前に、必要な名前空間をインポートしてください。

```csharp
using Aspose.Tasks;
using System;
```

## 手順 1: 新しい Project を作成する

まず、タスクとカスタム属性を保持する空の `Project` オブジェクトを作成します。

```csharp
var project = new Project();
```

## 手順 2: プロジェクトにタスクを追加する

次に、開始日と 1 日の期間を設定したシンプルなタスクを作成し、**タスク データをプロジェクトに追加**します。

```csharp
var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2020, 4, 16, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(1, TimeUnitType.Day));
```

## 手順 3: 拡張属性の Calculation Type を定義する（数式例）

ここでは、数式から値が計算される拡張属性定義を作成します。**計算タイプの例** を示し、**計算式の定義** 方法を解説します。

```csharp
var calculation = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Date5, null);
calculation.CalculationType = CalculationType.Formula;
calculation.SummaryRowsCalculationType = SummaryRowsCalculationType.UseFormula;
calculation.Formula = "[stARt]";
project.ExtendedAttributes.Add(calculation);
```

## 手順 4: サマリ行の Calculation Type を定義する（ロールアップサマリの設定）

次に、Aspose.Tasks に **ロールアップサマリを設定** させる別の拡張属性定義を作成します。*Average* ロールアップタイプを使用し、コスト、作業量、またはカスタムフィールドの **サマリ値の計算** を行う典型的な方法です。

```csharp
var lookup = ExtendedAttributeDefinition.CreateTaskDefinition(ExtendedAttributeTask.Cost1, null);
lookup.SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup;
lookup.RollupType = RollupType.Average;
project.ExtendedAttributes.Add(lookup);
```

## よくある問題とトラブルシューティング

| 症状 | 考えられる原因 | 対策 |
|------|----------------|------|
| 数式が `null` を返す | 数式内のフィールド参照が間違っている | 角括弧内のフィールド名（例: `[Start]` ではなく `[stARt]`）を確認する。 |
| サマリ行が 0 を表示する | `SummaryRowsCalculationType` が設定されていない、または `RollupType` が誤っている | `SummaryRowsCalculationType = SummaryRowsCalculationType.Rollup` を設定し、適切な `RollupType` を選択する。 |
| 属性を追加した後にプロジェクトが読み込めない | 属性定義とタスク使用の不一致 | 属性定義はタスクに割り当てる **前に** 追加する。 |

## 結論

本チュートリアルでは、Aspose.Tasks for .NET における **計算ルールの設定方法** を、シンプルなタスク作成から数式ベース・ロールアップベースの計算タイプ定義まで網羅しました。これらの設定をマスターすれば、**サマリ値の計算** を細かく制御でき、手作業のスプレッドシート作業なしで高度なプロジェクト分析が可能になります。

## FAQ

### Q1: Aspose.Tasks の Calculation Type とは何ですか？

A1: Aspose.Tasks の Calculation Type は、プロジェクト内のタスクやサマリタスクの値がどのように計算されるかを決定するもので、Formula や Rollup などのオプションがあります。

### Q2: 拡張属性の Calculation Type はどうやって設定しますか？

A2: 拡張属性の `CalculationType` プロパティに適切な値を設定することで、Calculation Type を指定できます。

### Q3: プロジェクトのサマリ行に対して Calculation Type をカスタマイズできますか？

A3: はい、Aspose.Tasks ではサマリ行用の Calculation Type を指定でき、要件に合わせた値計算が可能です。

### Q4: サマリタスクの計算に利用できる Rollup Type はありますか？

A4: はい、Aspose.Tasks は Average、Sum、Count など、サマリタスクの値を計算するためのさまざまな Rollup Type を提供しています。

### Q5: Aspose.Tasks for .NET の追加リソースはどこで見つけられますか？

A5: 詳細なガイドやサポートは、[Aspose.Tasks for .NET](https://reference.aspose.com/tasks/net/) のドキュメントおよびコミュニティフォーラムでご確認いただけます。

---

**最終更新日:** 2026-03-24  
**テスト環境:** Aspose.Tasks for .NET（最新リリース）  
**作成者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}