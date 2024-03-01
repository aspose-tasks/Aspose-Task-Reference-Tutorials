---
title: Aspose.Tasks for .NET のタスク使用状況ビューをマスターする
linktitle: Aspose.Tasks でのタスク使用状況ビューの構成
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を調べて、タスクの使用状況ビューを構成する方法を学びます。タイムスケール設定をカスタマイズし、プロジェクト管理のビジュアルを強化します。
type: docs
weight: 24
url: /ja/net/task-table-management/task-usage-views/
---
## 導入
プロジェクト管理の領域では、タスクの使用状況を視覚化することは、効果的な計画と実行にとって極めて重要です。 Aspose.Tasks for .NET は、タスク使用状況ビューをレンダリングするための堅牢なソリューションを提供し、タイムスケール設定とプレゼンテーション形式をカスタマイズできるようにします。このチュートリアルでは、Aspose.Tasks を使用してタスク使用状況ビューを構成する手順を説明します。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
1.  Aspose.Tasks for .NET: Aspose.Tasks ライブラリが .NET プロジェクトに統合されていることを確認します。ダウンロードできます[ここ](https://releases.aspose.com/tasks/net/).
2. .NET 環境: マシン上に動作する .NET 環境をセットアップします。
## 名前空間のインポート
.NET プロジェクトで、Aspose.Tasks 機能にアクセスするために必要な名前空間をインポートします。コードに次の行を追加します。
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## ステップ 1: ドキュメント ディレクトリのパスを設定する
 Aspose.Tasks 機能を使用する前に、ドキュメント ディレクトリへのパスを設定します。交換する`"Your Document Directory"`実際のパスを使用します。
```csharp
String DataDir = "Your Document Directory";
```
## ステップ 2: プロジェクトをロードする
Aspose.Tasks を初期化する`Project`プロジェクト ファイル (TaskUsageView.mpp など) をロードしてオブジェクトを作成します。
```csharp
var project = new Project(DataDir + "TaskUsageView.mpp");
```
## ステップ 3: SaveOptions を定義する
を作成します`SaveOptions`オブジェクトを使用してレンダリング オプションを指定します。タイムスケールを「日」に設定し、プレゼンテーション形式を「TaskUsage」に設定します。
```csharp
SaveOptions options = new PdfSaveOptions
{
    Timescale = Timescale.Days,
    PresentationFormat = PresentationFormat.TaskUsage
};
```
## ステップ 4: 日数のタイムスケールで保存する
事前定義されたタイムスケール設定「日」を使用してプロジェクトを保存します。
```csharp
var outputProject = "TaskUsageView_result_days_out.pdf";
project.Save(DataDir + outputProject, options);
```
## ステップ 5: ThirdsOfMonths タイムスケールで保存する
タイムスケール設定を「ThirdsOfMonths」に変更し、プロジェクトを保存します。
```csharp
options.Timescale = Timescale.ThirdsOfMonths;
outputProject = "TaskUsageView_result_thirdsOfMonths_out.pdf";
project.Save(DataDir + outputProject, options);
```
## ステップ 6: 月単位のタイムスケールで保存する
タイムスケールを「月」に設定し、更新された設定でプロジェクトを保存します。
```csharp
options.Timescale = Timescale.Months;
outputProject = "TaskUsageView_result_months_out.pdf";
project.Save(DataDir + outputProject, options);
```
## 結論
Aspose.Tasks for .NET を使用してタスク使用状況ビューを構成するのは簡単なプロセスです。タイムスケール設定をカスタマイズすることで、特定のニーズに応じてプロジェクト タスクの視覚化を調整できます。
より多くの機能を自由に探索してください。[ドキュメンテーション](https://reference.aspose.com/tasks/net/).
## よくある質問
### 事前定義された設定を超えてタイムスケールをカスタマイズできますか?
はい、間隔と単位を指定してカスタム タイムスケールを設定できます。
### 他のプレゼンテーション形式はありますか?
Aspose.Tasks は、GanttChart、ResourceUsage などを含むさまざまなプレゼンテーション形式をサポートしています。
### Aspose.Tasks はさまざまなプロジェクト ファイル形式と互換性がありますか?
はい、Aspose.Tasks は MPP、XML、CSV などの一般的なプロジェクト ファイル形式をサポートしています。
### 特定のタスクに異なるタイムスケール設定を適用できますか?
もちろん、プロジェクト内の個々のタスクのタイムスケール設定をカスタマイズすることもできます。
### Aspose.Tasks のサポートを受けたり支援を求めたりするにはどうすればよいですか?
訪問[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)コミュニティのサポートと指導のために。