---
title: Aspose.Tasks を使用した MS プロジェクトの進捗ラインの処理
linktitle: Aspose.Tasks での進行状況ラインの処理
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して MS Project ファイル内の進捗ラインを操作し、プロジェクトの視覚化と管理を強化する方法を学びます。
type: docs
weight: 15
url: /ja/net/project-management-integration/progress-lines/
---
## 導入
Microsoft Project (MS Project) はプロジェクト管理用の強力なツールであり、ユーザーはプロジェクトのさまざまな側面を追跡できます。 MS Project の重要な機能の 1 つは、進行状況を視覚化する機能であり、関係者がプロジェクトのステータスと軌道を理解するのに役立ちます。このチュートリアルでは、.NET 用の Aspose.Tasks ライブラリを使用して MS Project で進行状況ラインを処理する方法を検討します。
## 前提条件
始める前に、以下のものがあることを確認してください。
1. Visual Studio: Visual Studio またはその他の推奨 .NET 開発環境をインストールします。
2.  Aspose.Tasks for .NET:Aspose.Tasks for .NET をダウンロードしてインストールします。[ここ](https://releases.aspose.com/tasks/net/).
3. C# の基礎知識: C# プログラミング言語に精通していると役立ちます。

## 名前空間のインポート
まず、必要な名前空間をインポートしましょう。
```csharp
using Aspose.Tasks;
using System;
using System.Drawing;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
ここで、進捗ラインを処理する各ステップを詳しく見てみましょう。
## ステップ 1: プロジェクト ファイルをロードする
```csharp
//ドキュメント ディレクトリへのパス。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
project.Set(Prj.StatusDate, project.Get(Prj.StartDate));
```
ここでは、MS Project ファイルをロードします。`Project2.mpp`ステータス日付を設定します。
## ステップ 2: ガント チャート ビューを定義する
```csharp
var view = (GanttChartView)project.Views.ToList()[0];
```
さらに操作するために、プロジェクトのビューをガント チャート ビューにキャストします。
## ステップ 3: 進捗ラインを定義する
```csharp
view.ProgressLines = new ProgressLines();
var progressLines = view.ProgressLines;
```
ガント チャート ビューの進捗ラインを初期化します。
## ステップ 4: プログレスライン設定を構成する
```csharp
progressLines.BeginAtDate = project.Get(Prj.StatusDate);
progressLines.BeginAtProjectStart = true;
progressLines.DateFormat = DateLabel.DayDddd;
progressLines.DisplayAtCurrentDate = true;
progressLines.DisplayAtRecurringIntervals = true;
progressLines.DisplaySelected = true;
progressLines.IsBaselinePlan = false;
progressLines.Font = new FontDescriptor("Arial", 10);
progressLines.LineColor = Color.Aquamarine;
progressLines.LinePattern = LinePattern.Dashed;
progressLines.OtherLineColor = Color.Azure;
progressLines.OtherLinePattern = LinePattern.Dotted;
progressLines.OtherProgressPointColor = Color.Red;
progressLines.OtherProgressPointShape = GanttBarEndShape.Circle;
progressLines.ProgressPointColor = Color.Orange;
progressLines.ProgressPointShape = GanttBarEndShape.Diamond;
progressLines.RecurringInterval = new RecurringInterval();
progressLines.RecurringInterval.Interval = Interval.Daily;
progressLines.RecurringInterval.DailyDayNumber = 1;
progressLines.ShowDate = true;
```
ここでは、線の色、パターン、フォントなど、進捗線のさまざまなプロパティを設定します。
## ステップ 5: 進捗ラインの構成を確認する
```csharp
//出力進捗ラインの設定
Console.WriteLine("Begin At Date: " + progressLines.BeginAtDate);
Console.WriteLine("Begin At Project Start: " + progressLines.BeginAtProjectStart);
//その他の設定を出力...
```
構成された進捗ラインの設定を検証のために出力します。
## ステップ 6: プロジェクト ファイルを保存する
```csharp
project.Save(DataDir + "WorkWithProgressLines_out.mpp", SaveFileFormat.Mpp);
```
最後に、変更したプロジェクト ファイルを進捗ラインとともに保存します。

## 結論
このチュートリアルでは、Aspose.Tasks for .NET を使用して MS Project の進捗ラインを処理する方法を学習しました。これらの手順に従うことで、MS Project ファイル内の進行状況ラインをプログラム的に効果的にカスタマイズして視覚化できます。
## よくある質問
### Q: 進行状況ラインの外観をさらにカスタマイズできますか?
A: はい、要件に合わせて線の色、パターン、フォントなどのさまざまなプロパティを調整できます。
### Q: Aspose.Tasks は他のプロジェクト管理機能をサポートしていますか?
A: はい、Aspose.Tasks は、タスク、リソース、カレンダーなど、MS Project ファイルのさまざまな側面を操作するための広範なサポートを提供します。
### Q: Aspose.Tasks を他の .NET ライブラリと統合できますか?
A: もちろん、Aspose.Tasks は他の .NET ライブラリとシームレスに統合できるように設計されており、プロジェクト管理アプリケーションをさらに強化できます。
### Q: Aspose.Tasks サポートのためのコミュニティ フォーラムはありますか?
 A: はい、Aspose.Tasks フォーラムで役立つリソースを見つけて支援を求めることができます。[ここ](https://forum.aspose.com/c/tasks/15).
### Q: Aspose.Tasks は評価目的の一時ライセンスを提供していますか?
 A: はい、次から評価用の一時ライセンスを取得できます。[ここ](https://purchase.aspose.com/temporary-license/).