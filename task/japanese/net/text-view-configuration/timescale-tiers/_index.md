---
title: Aspose.Tasks でのガント チャートのタイムスケール層の構成
linktitle: Aspose.Tasks でのタイムスケール層の構成
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を探索して、ガント チャート ビューでタイムスケール層を構成し、プロジェクトのタイムラインを正確に視覚化します。 #Aspose.Task #MS プロジェクト
type: docs
weight: 16
url: /ja/net/text-view-configuration/timescale-tiers/
---
## 導入
プロジェクト管理の動的な状況では、タイムラインと期限を理解するために効果的な視覚化が非常に重要です。 Aspose.Tasks for .NET は強力なツールセットを提供します。このチュートリアルでは、ガント チャート ビューで最適に表示されるようにタイムスケール層を構成する方法を検討します。以下の段階的な手順に従って、プロジェクトの視覚化を強化します。
## 前提条件
チュートリアルに入る前に、次のものが揃っていることを確認してください。
- C# と .NET の基本的な知識。
-  Aspose.Tasks for .NET ライブラリがインストールされています。ダウンロードできます[ここ](https://releases.aspose.com/tasks/net/).
- .NET アプリケーション開発のためにセットアップされた開発環境。
## 名前空間のインポート
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
ここで、提供された例の各ステップを詳しく見てみましょう。
## ステップ 1: プロジェクトを初期化し、タスク リンクを追加する
```csharp
//ドキュメント ディレクトリへのパス。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "CreateProject1.mpp");
project.TaskLinks.Add(project.RootTask.Children.Add("Task 1"), project.RootTask.Children.Add("Task 2"));
```
ここでは、プロジェクトを作成し、「タスク 1」と「タスク 2」の間にタスクのリンクを確立します。
## ステップ 2: ガント チャート ビューを構成する
```csharp
var view = (GanttChartView)project.DefaultView;
```
カスタマイズするにはガント チャート ビューにアクセスします。
## ステップ 3: 中間タイムスケール層を調整する
```csharp
view.MiddleTimescaleTier = new TimescaleTier();
view.MiddleTimescaleTier.Unit = TimescaleUnit.Weeks;
view.MiddleTimescaleTier.Count = 1;
view.MiddleTimescaleTier.Label = DateLabel.WeekDddDd;
view.MiddleTimescaleTier.Alignment = HorizontalStringAlignment.Center;
view.MiddleTimescaleTier.ShowTicks = true;
view.MiddleTimescaleTier.UsesFiscalYear = true;
```
中間のタイムスケール層をカスタマイズして、特定のラベルと配置で週を表示します。
## ステップ 4: 最上位のタイムスケール層を追加する
```csharp
view.TopTimescaleTier = new TimescaleTier(TimescaleUnit.Months, 1);
```
月を表す最上位のタイムスケール層を追加します。
## ステップ 5: 中間層の日付をカスタマイズする
```csharp
view.TopTimescaleTier.DateTimeConverter = date =>
    new[] { "Янв.", "Фев.", "Мар.", "Апр.", "Май", "Июнь", "Июль", "Авг.", "Сен.", "Окт.", "Ноя.", "Дек." }[date.Month - 1];
```
月のラベルをパーソナライズして、視覚的にわかりやすくします。
## ステップ 6: プロジェクトのタイムスケールを設定する
```csharp
project.Set(Prj.TimescaleStart, new DateTime(2012, 7, 30));
project.Set(Prj.TimescaleFinish, new DateTime(2012, 10, 6));
```
プロジェクトのタイムスケールを定義して、全体のタイムラインを制御します。
## ステップ 7: カスタマイズしたタイムスケールでプロジェクトを保存する
```csharp
var pdfSaveOptions = new PdfSaveOptions
{
    Timescale = Timescale.DefinedInView
};
project.Save(DataDir+ "CustomizeTimescaleTierLabels_out.pdf", pdfSaveOptions);
```
定義したタイムスケール設定でプロジェクトを保存します。
## 結論
結論として、Aspose.Tasks for .NET でタイムスケール層を構成すると、プロジェクトのタイムラインをよりカスタマイズされ、視覚的に魅力的に表現できるようになります。これらの手順により、プロジェクト管理のニーズを正確に満たすガント チャート ビューを作成できるようになります。
## よくある質問
### Aspose.Tasks を他の .NET ライブラリで使用できますか?
はい、Aspose.Tasks は他の .NET ライブラリとシームレスに統合し、開発スタックに柔軟性を提供します。
### 一時ライセンスはテスト目的で利用できますか?
はい、一時ライセンスを取得できます[ここ](https://purchase.aspose.com/temporary-license/)評価用に。
### ガント チャート ビューに追加のカスタマイズ オプションはありますか?
もちろん、Aspose.Tasks は、さまざまなプロジェクト要件に合わせてガント チャート ビューに広範なカスタマイズ オプションを提供します。
### タイムスケールをさまざまな形式でレンダリングできますか?
確かに、プロジェクトのコンテキストに最適なタイムスケール表現のさまざまな形式とスタイルを検討できます。
### Aspose.Tasks サポートのためのコミュニティ フォーラムはありますか?
はい、訪問してください[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)コミュニティのサポートとディスカッションのために。