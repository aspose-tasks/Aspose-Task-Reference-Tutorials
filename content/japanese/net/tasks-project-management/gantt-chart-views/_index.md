---
title: Aspose.Tasks のガント チャート ビューをマスターする
linktitle: Aspose.Tasks のガント チャート ビュー
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して Microsoft Project ファイルのガント チャート ビューをカスタマイズする方法を学びます。効率的なプロジェクト管理のためのステップバイステップのガイド。
type: docs
weight: 22
url: /ja/net/tasks-project-management/gantt-chart-views/
---
## 導入
ガント チャートは、プロジェクト管理でタスク、タイムライン、依存関係を視覚化するために使用される強力なツールです。 Aspose.Tasks for .NET は、Microsoft Project ファイルのガント チャート ビューを操作するための堅牢な機能を提供します。このチュートリアルでは、Aspose.Tasks を利用してガント チャート ビューを操作し、外観をカスタマイズし、PDF ファイルとして保存する方法を説明します。
## 前提条件
続行する前に、次の前提条件が満たされていることを確認してください。
### 1. Aspose.Tasks for .NET のインストール
 Aspose.Tasks for .NET がインストールされていることを確認してください。ライブラリはからダウンロードできます[ここ](https://releases.aspose.com/tasks/net/)ドキュメントに記載されているインストール手順に従ってください。[ここ](https://reference.aspose.com/tasks/net/).
### 2. Microsoft プロジェクト ファイル
Microsoft Project ファイルを準備します (`Project2.mpp`) ガント チャート ビューを操作するために使用します。
### 3. C# と .NET Framework の基礎知識
このチュートリアルは、C# プログラミング言語と .NET Framework の基本を理解していることを前提としています。
## 名前空間のインポート
Aspose.Tasks でガント チャート ビューの操作を開始する前に、必要な名前空間を C# コードにインポートする必要があります。その方法は次のとおりです。

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
using System.Drawing;
using System.Linq;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using Aspose.Tasks;
using System.Drawing;
```

提供されているサンプル コードを複数のステップに分割し、各ステップを詳しく説明してみましょう。
## ステップ 1: プロジェクト ファイルをロードする
```csharp
var project = new Project(DataDir + "Project2.mpp");
```
この手順には、Microsoft Project ファイル (`Project2.mpp` ) のインスタンスに`Project`クラス。
## ステップ 2: ステータス日付を設定する
```csharp
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
ここでは、プロジェクトの状況報告日を開始日に設定します。
## ステップ 3: ガント チャート ビューにアクセスする
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
プロジェクトからガント チャート ビューにアクセスします。 Aspose.Tasks を使用すると、ガント チャート、ネットワーク ダイアグラム、タスクの使用状況などのビューにアクセスできます。
## ステップ 4: ガント チャート ビューをカスタマイズする
次に、ガント チャート ビューのさまざまな側面をカスタマイズしましょう。
### バーの丸め設定
```csharp
view.BarRounding = false;
```
ガント チャートのバーを最も近い日に四捨五入するかどうかを設定します。
### バーのサイズを設定する
```csharp
view.BarSize = GanttBarSize.BarSize24;
```
これにより、チャート内のガント バーの高さが決まります。
### ロールアップバーを非表示にする
```csharp
view.HideRollupBarsWhenSummaryExpanded = true;
```
サマリー タスクを展開するときにロールアップ バーを非表示にするかどうかを指定します。
### 非稼働時間の色の設定
```csharp
view.NonWorkingTimeColor = Color.Azure;
```
ガント チャート上の非稼働時間の色を定義します。
### ガント バーをロールアップする
```csharp
view.RollUpGanttBars = true;
```
ガント チャートのバーをロールアップするかどうかを指定します。
### バーの分割を表示
```csharp
view.ShowBarSplits = true;
```
ガント チャート上のタスク分割を表示する必要があるかどうかを決定します。
### 図面を表示する
```csharp
view.ShowDrawings = true;
```
ガント チャート上の図面を表示するかどうかを指定します。
### タイムスケール サイズのパーセンテージ
```csharp
view.TimescaleSizePercentage = 10;
```
タイムスケール層上のユニット間の間隔を調整するパーセンテージを設定します。
## ステップ 5: ガント チャート ビューを PDF として保存する
```csharp
project.Save(DataDir + "WorkWithGanttChartViews_out.pdf", SaveFileFormat.Pdf);
```
最後に、カスタマイズしたガント チャート ビューを PDF ファイルとして保存します。
## 結論
このチュートリアルでは、Aspose.Tasks for .NET でガント チャート ビューを操作する方法を学習しました。提供されている手順に従うことで、プロジェクトの要件に応じてガント チャートを効率的に操作およびカスタマイズできます。
## よくある質問
### Q: ガント チャートのバーの外観をさらにカスタマイズできますか?
A: はい。Aspose.Tasks には、色、形状、サイズなど、ガント チャート バーの外観をカスタマイズするための広範なオプションが用意されています。
### Q: Aspose.Tasks は、Microsoft Project ファイルのさまざまなバージョンと互換性がありますか?
A: はい、Aspose.Tasks は、MPP、MPT、XML 形式など、さまざまなバージョンの Microsoft Project ファイルをサポートしています。
### Q: ガント チャート ビューを PDF 以外の形式にエクスポートできますか?
A: もちろん、Aspose.Tasks は、ガント チャート ビューの PNG、JPEG、XPS などの複数の形式へのエクスポートをサポートしています。
### Q: Aspose.Tasks は、複雑なプロジェクト スケジューリング アルゴリズムをサポートしていますか?
A: はい、Aspose.Tasks は、複雑なプロジェクト スケジュールを効率的に処理するための高度なスケジューリング アルゴリズムを提供します。
### Q: Aspose.Tasks について助けを求めたり、経験を共有したりできるコミュニティ フォーラムはありますか?
 A: はい、次のサイトにアクセスできます。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)他のユーザーと交流し、質問し、質問に対する解決策を見つけることができます。