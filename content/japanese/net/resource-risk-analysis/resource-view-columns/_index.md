---
title: Aspose.Tasks の MS Project リソース ビュー列をカスタマイズする
linktitle: Aspose.Tasks のリソース ビュー列のカスタマイズ
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して MS Project リソース ビューの列を効率的にカスタマイズする方法を学びます。プロジェクト管理を改善するためにカスタマイズされたビューを作成します。
type: docs
weight: 17
url: /ja/net/resource-risk-analysis/resource-view-columns/
---
## 導入
Aspose.Tasks for .NET は、開発者がプログラムで Microsoft Project ファイルを操作できるようにする強力な API です。プロジェクト管理における一般的なタスクの 1 つは、ビューをカスタマイズして特定の情報を表示することです。このチュートリアルでは、Aspose.Tasks for .NET を使用して MS Project のリソース ビュー列をカスタマイズする方法を説明します。
## 前提条件
始める前に、以下のものがあることを確認してください。
1.  Aspose.Tasks for .NET ライブラリ: 次からダウンロードできます。[ここ](https://releases.aspose.com/tasks/net/).
2. Microsoft Project ファイル: テストに便利なサンプル MS Project ファイルを用意します。
3. 開発環境: .NET Framework で構築された開発環境。
## 名前空間のインポート
まず、必要な名前空間をプロジェクトにインポートしましょう。
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
using System.Globalization;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
## ステップ 1: プロジェクト ファイルをロードする
Aspose.Tasks API を使用して MS Project ファイルを読み込みます。
```csharp
var project = new Project("Your_Project_File_Path.mpp");
```
## ステップ 2: リソースを取得してオプションを定義する
次に、ビュー列をカスタマイズするリソースを取得し、PDF 保存オプションを定義します。
```csharp
var resource = project.Resources.GetById(1);
var options = new PdfSaveOptions();
```
## ステップ 3: カスタム列を定義する
次に、リソース ビューのカスタム列を定義します。さまざまなフィールドを指定したり、カスタム計算にデリゲートを使用したりすることもできます。
```csharp
var columns = new List<ViewColumn>
{
    new ResourceViewColumn(100, Field.ResourceName),
    new ResourceViewColumn(100, Field.ResourceActualWork),
    new ResourceViewColumn(100, Field.ResourceCost),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }),
    new ResourceViewColumn(
        "Resource Cost2", 
        80,
        delegate(Resource res)
        {
            return res.Get(Rsc.Cost).ToString(CultureInfo.InvariantCulture);
        }, 
        Field.ResourceCost2)
};
```
## ステップ 4: 列を反復処理する
定義された列を反復処理して、そのプロパティを表示します。
```csharp
foreach (var column in columns)
{
    var col = (ResourceViewColumn)column;
    Console.WriteLine("Column Name: " + col.Name);
    Console.WriteLine("Column Field: " + col.Field);
    Console.WriteLine("Column Text: " + col.GetColumnText(resource));
    Console.WriteLine();
}
```
## ステップ 5: カスタマイズしたビューを保存する
最後に、カスタム ビューを設定し、PDF ファイルとして保存します。
```csharp
options.View = new ProjectView(columns);
options.PresentationFormat = PresentationFormat.ResourceUsage;
project.Save("Output_PDF_File_Path.pdf", options);
```
これらの手順に従うことで、Aspose.Tasks for .NET を使用して MS Project のリソース ビュー列を効率的にカスタマイズできます。
## 結論
MS Project のリソース ビュー列のカスタマイズは、プロジェクトのニーズに合わせた関連情報を表示するために不可欠です。 Aspose.Tasks for .NET を使用すると、このタスクが簡単かつ効率的になり、カスタマイズされたビューを簡単に作成できるようになります。
## よくある質問
### リソース以外の他の要素のビューをカスタマイズできますか?
はい、Aspose.Tasks では、タスク、割り当て、その他のプロジェクト要素もカスタマイズできます。
### Aspose.Tasks は PDF 以外の形式でのビューの保存をサポートしていますか?
はい、XLSX、HTML、画像などのさまざまな形式でビューを保存できます。
### カスタムビューに書式設定を適用することはできますか?
もちろん、Aspose.Tasks には、カスタマイズされたビューの外観を向上させるための広範な書式設定オプションが用意されています。
### プロジェクト データの変更に基づいてカスタム ビューを動的に更新できますか?
はい、基礎となるプロジェクト データが変更されるたびに、カスタム ビューを更新して再生成できます。
### Aspose.Tasks はクロスプラットフォーム開発をサポートしていますか?
Aspose.Tasks for .NET は主に .NET プラットフォームをターゲットとしていますが、Java やその他のプラットフォームで利用できるバージョンもあります。