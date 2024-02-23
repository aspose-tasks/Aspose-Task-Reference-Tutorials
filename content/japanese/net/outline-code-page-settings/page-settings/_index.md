---
title: Aspose.Tasks を使用して MS プロジェクト ページ設定を構成する
linktitle: Aspose.Tasks でページ設定を構成する
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して MS Project ページ設定を構成する方法を学習します。簡単な手順で方向やサイズなどをカスタマイズします。
type: docs
weight: 20
url: /ja/net/outline-code-page-settings/page-settings/
---
## 導入
このチュートリアルでは、Aspose.Tasks for .NET を使用して Microsoft Project ページ設定を構成するプロセスについて説明します。 Aspose.Tasks は、開発者が Microsoft Project ファイルをプログラムで操作できるようにする強力な API です。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
1.  Aspose.Tasks for .NET: Aspose.Tasks for .NET がインストールされていることを確認してください。からダウンロードできます[ここ](https://releases.aspose.com/tasks/net/).
2. 開発環境: Visual Studio またはその他の .NET 開発用の推奨 IDE を使用して開発環境をセットアップします。

## 名前空間のインポート
開始するには、必要な名前空間をプロジェクトにインポートする必要があります。これらの名前空間は、MS Project ファイルの操作に必要な Aspose.Tasks クラスとメソッドへのアクセスを提供します。
```csharp
using Aspose.Tasks;
using System.Linq;
    using System;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Visualization;
```
## ステップ 1: プロジェクト ファイルをロードする
まず、ページ設定を構成する MS Project ファイルをロードする必要があります。
```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "Your Document Directory";
var project = new Project(dataDir + "Project2.mpp");
```
## ステップ 2: ページ設定にアクセスする
次に、プロジェクト ファイルのページ設定にアクセスします。
```csharp
//設定を取得する
var settings = project.DefaultView.PageInfo.PageSettings;
```
## ステップ 3: ページ設定を構成する
次に、要件に応じてページ設定のさまざまなプロパティを構成しましょう。
```csharp
//ページの向きを縦向きに設定する
settings.IsPortrait = true;
//印刷する幅のページ数を設定します
settings.PagesInWidth = 5;
//印刷する縦のページ数を設定します
settings.PagesInHeight = 7;
//印刷を調整する通常サイズのパーセンテージを設定します
settings.PercentOfNormalSize = 200;
//用紙サイズを設定する
settings.PaperSize = PrinterPaperSize.PaperB4;
//印刷する最初のページ番号を設定する
settings.FirstPageNumber = 3;
```
## ステップ 4: プロジェクト ファイルを保存する
最後に、更新されたページ設定を含むプロジェクト ファイルを保存します。
```csharp
SimpleSaveOptions options = new MPPSaveOptions
{
    WriteViewData = true
};
project.Save(dataDir + "TestCanWritePageSettings.mpp", options);
```

## 結論
このチュートリアルでは、Aspose.Tasks for .NET を使用して Microsoft Project ページ設定を構成する方法を学習しました。これらの手順に従うことで、要件に応じてページの向き、サイズ、その他の印刷オプションを簡単にカスタマイズできます。

## よくある質問
### Q: 複数の MS Project ファイルのページ設定を同時に構成できますか?
A: はい、複数のプロジェクト ファイルをループして、それぞれに同じページ設定を適用できます。
### Q: ページ設定をデフォルトに戻すことはできますか?
A: もちろん、構成手順を省略したり、設定をデフォルト値にリセットしたりすることもできます。
### Q: サポートされる用紙サイズに制限はありますか?
A: Aspose.Tasks は、標準サイズやカスタム サイズを含む幅広い用紙サイズをサポートしています。
### Q: ページ設定の構成プロセスを自動化できますか?
A: 確かに、この機能をアプリケーションのワークフローに統合して、ページ設定の構成を自動化することができます。
### Q: Aspose.Tasks は .mpp 以外のさまざまなファイル形式をサポートしていますか?
A: はい、Aspose.Tasks は、XML、MPT、HTML などのさまざまなファイル形式をサポートしています。