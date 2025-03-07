---
title: Aspose.Tasks のリスク項目の統計
linktitle: Aspose.Tasks のリスク項目の統計
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して、MS Project ファイルのリスク分析機能を活用します。洞察を得て不確実性を軽減し、プロジェクトの成功を難なく推進します。
weight: 21
url: /ja/net/resource-risk-analysis/risk-item-statistics/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks のリスク項目の統計

## 導入
Aspose.Tasks for .NET を使用してプロジェクト管理能力を強化したいと考えていますか? MS Project ファイル内のリスク項目の統計を取得するためのステップバイステップのチュートリアルで、リスク分析の領域を掘り下げてください。 Aspose.Tasks の強力な機能を活用することで、プロジェクトの不確実性に関する貴重な洞察を取得し、情報に基づいた意思決定を行ってリスクを効果的に軽減できます。
## 前提条件
この作業を開始する前に、次の前提条件が満たされていることを確認してください。
1.  Aspose.Tasks for .NET ライブラリ: からライブラリをダウンロードしてインストールします。[Aspose.Tasks for .NET ドキュメント](https://reference.aspose.com/tasks/net/)。このライブラリには、MS Project ファイルをプログラムで操作するための強力なツールが備わっています。
2. .NET 開発環境: Visual Studio またはその他の任意の IDE を含む .NET 開発環境をセットアップして、Aspose.Tasks のプロジェクトへのシームレスな統合を促進します。

## 名前空間のインポート
Aspose.Tasks の機能を利用するには、必要な名前空間をプロジェクトに組み込みます。
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.RiskAnalysis;
```

## ステップ 1: データ ディレクトリを定義する
```csharp
String DataDir = "Your Document Directory";
```
必ず交換してください`"Your Document Directory"` MS Project ファイルが配置されているドキュメント ディレクトリへのパスを置き換えます。
## ステップ 2: リスク分析設定を構成する
```csharp
var settings = new RiskAnalysisSettings
{
    IterationsCount = 200
};
```
を調整します。`IterationsCount`プロジェクト要件に基づいてパラメータを調整し、リスク分析の精度を制御します。
## ステップ 3: MS プロジェクト ファイルをロードする
```csharp
var project = new Project(DataDir + "Software Development Plan-1.mpp");
```
目的の MS プロジェクト ファイルを`project`さらなる分析のためのオブジェクト。
## ステップ 4: タスクを定義し、リスク パターンを初期化する
```csharp
var task = project.RootTask.Children.GetById(17);
var pattern = new RiskPattern(task)
{
    Distribution = ProbabilityDistributionType.Normal,
    Optimistic = 70,
    Pessimistic = 130,
    ConfidenceLevel = ConfidenceLevel.CL75
};
settings.Patterns.Add(pattern);
```
リスク分析のタスクを指定し、分布タイプ、楽観的および悲観的な期間、信頼レベルなどの適切なパラメーターを使用してリスク パターンを構成します。
## ステップ 5: プロジェクトのリスクを分析する
```csharp
var analyzer = new RiskAnalyzer(settings);
var analysisResult = analyzer.Analyze(project);
```
定義された設定とプロジェクト データを使用してリスク分析プロセスを開始します。
## ステップ 6: 統計の取得と表示
```csharp
var statistics = analysisResult.GetRiskItems(RiskItemType.EarlyFinish).Get(project.RootTask);
Console.WriteLine("Short statistic: " + statistics);
Console.WriteLine();
Console.WriteLine("Statistic details: ");
Console.WriteLine("Item Type: {0}", statistics.ItemType);
Console.WriteLine("Expected value: {0}", statistics.ExpectedValue);
Console.WriteLine("StandardDeviation: {0}", statistics.StandardDeviation);
Console.WriteLine("10% Percentile: {0}", statistics.GetPercentile(10));
Console.WriteLine("50% Percentile: {0}", statistics.GetPercentile(50));
Console.WriteLine("90% Percentile: {0}", statistics.GetPercentile(90));
Console.WriteLine("Minimum: {0}", statistics.Minimum);
Console.WriteLine("Maximum: {0}", statistics.Maximum);
```
MS Project ファイル内のリスク項目に関連するさまざまな統計指標 (期待値、標準偏差、パーセンタイル、最小値、最大値など) を取得して表示します。

## 結論
結論として、Aspose.Tasks for .NET を使用して MS Project ファイルのリスク分析を習得すると、プロジェクト マネージャーと関係者に可能性の領域が開かれます。包括的なチュートリアルに従うことで、不確実性を自信を持って乗り越えることができ、プロジェクトの成果を確実に成功させることができます。
## よくある質問
### 拡張機能のために Aspose.Tasks を他の .NET ライブラリと統合できますか?
絶対に！ Aspose.Tasks はさまざまな .NET ライブラリとシームレスに統合されているため、プロジェクトの要件に応じてその機能を拡張できます。
### Aspose.Tasks for .NET の試用版はありますか?
はい、Aspose.Tasks の機能を調べるには、[無料トライアル](https://releases.aspose.com/)当社のウェブサイトで入手可能です。
### Aspose.Tasks の更新と機能強化はどのくらいの頻度でリリースされますか?
私たちは、アップデートと機能強化を定期的にリリースすることで Aspose.Tasks を継続的に改善し、常に最新の機能と最適化にアクセスできるように努めています。
### Aspose.Tasks のテクニカル サポートを受けることはできますか?
確かに！当社の専任サポート チームは、[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)導入の過程で遭遇する可能性のある質問や課題へのサポートを提供します。
### 短期プロジェクト向けに一時ライセンスを提供していますか?
はい、短期プロジェクトで Aspose.Tasks が必要な場合は、便利なツールをご利用いただけます。[仮免許](https://purchase.aspose.com/temporary-license/)長期契約なしでライセンスのニーズを満たすオプションです。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
