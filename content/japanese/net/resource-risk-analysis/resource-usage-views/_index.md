---
title: Aspose.Tasks で MS Project のリソース使用状況ビューを構成する
linktitle: Aspose.Tasks でリソース使用状況ビューを構成する
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して MS Project のリソース使用状況ビューを構成する方法を学びます。コード例を含むステップバイステップのガイド。
type: docs
weight: 15
url: /ja/net/resource-risk-analysis/resource-usage-views/
---
## 導入
Microsoft Project (MS Project) は、ユーザーがプロジェクトを効率的に計画、実行、追跡できるようにする強力なプロジェクト管理ツールです。 Aspose.Tasks for .NET は MS Project ファイルとのシームレスな統合を提供し、開発者がプロジェクト データをプログラムで操作できるようにします。このチュートリアルでは、Aspose.Tasks for .NET を使用して MS Project のリソース使用状況ビューを構成する方法を説明します。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
1.  Aspose.Tasks for .NET: Aspose.Tasks for .NET ライブラリを次の場所からダウンロードしてインストールします。[ダウンロードリンク](https://releases.aspose.com/tasks/net/).
2. Microsoft Project ファイル: Microsoft Project ファイル (`.mpp`) 作業するプロジェクト データが含まれています。

## 名前空間のインポート
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```
## ステップ 1: プロジェクト ファイルをロードする
まず、Aspose.Tasks を使用して MS Project ファイルをロードします。
```csharp
//ドキュメントディレクトリへのパス。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ResourceUsageView.mpp");
```
## ステップ 2: 保存オプションを定義する
必要なタイムスケール設定とプレゼンテーション形式を指定して保存オプションを定義します。
```csharp
SaveOptions options = new PdfSaveOptions
{
    Timescale = Timescale.Days,
    PresentationFormat = PresentationFormat.ResourceUsage
};
```
## ステップ 3: リソース使用状況ビューを含むプロジェクトを保存する
構成されたリソース使用状況ビューを含むプロジェクトを PDF ファイルに保存します。
```csharp
project.Save(DataDir + "ResourceUsage_days_out.pdf", options);
```

## 結論
このチュートリアルでは、Aspose.Tasks for .NET を使用して MS Project のリソース使用状況ビューを構成する方法を学習しました。提供されている手順に従うことで、開発者は Aspose.Tasks を .NET アプリケーションにシームレスに統合して、プロジェクト データを効率的に操作できます。

## よくある質問
### Q: Aspose.Tasks は、Microsoft Project ファイルのさまざまなバージョンと互換性がありますか?
A: はい、Aspose.Tasks は、.mpp、.mpt、.xml、.mpx などのさまざまなバージョンの Microsoft Project ファイルをサポートしています。
### Q: タイムスケール設定とプレゼンテーション形式をさらにカスタマイズできますか?
A: もちろん、Aspose.Tasks は要件に応じてタイムスケール設定とプレゼンテーション形式をカスタマイズできる柔軟性を提供します。
### Q: Aspose.Tasks は PDF 以外の出力形式をサポートしていますか?
A: はい、Aspose.Tasks は、XLSX、MPP、XML、HTML などを含むさまざまな出力形式をサポートしています。
### Q: Aspose.Tasks サポートのためのコミュニティまたはフォーラムはありますか?
 A: はい、次のサイトにアクセスできます。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)ご質問、ディスカッション、サポートのニーズにお応えします。
### Q: 購入する前に Aspose.Tasks を試すことはできますか?
 A: もちろん、無料トライアルを利用して Aspose.Tasks を試すことができます。[ここ](https://releases.aspose.com/).