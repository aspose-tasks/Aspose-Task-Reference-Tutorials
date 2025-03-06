---
title: Aspose.Tasks での MS Project ページ ビュー設定のカスタマイズ
linktitle: Aspose.Tasks でのページ ビュー設定の構成
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET でページ ビュー設定を構成し、Microsoft Project ドキュメントの印刷形式を調整する方法を学びます。
weight: 21
url: /ja/net/outline-code-page-settings/page-view-settings/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks での MS Project ページ ビュー設定のカスタマイズ

## 導入
Microsoft Project はプロジェクト管理のための強力なツールですが、プロジェクトの表示方法と印刷方法をカスタマイズする必要がある場合があります。 Aspose.Tasks for .NET を使用すると、特定の要件を満たすようにページ ビュー設定を簡単に構成できます。このチュートリアルでは、プロセスを段階的に説明します。
## 前提条件
始める前に、以下のものがあることを確認してください。
1.  Aspose.Tasks for .NET: Aspose.Tasks for .NET ライブラリをダウンロードしてインストールしていることを確認してください。からダウンロードできます[ここ](https://releases.aspose.com/tasks/net/).
2. Microsoft Project ファイル: ページ ビュー設定を構成する Microsoft Project ファイルを用意します。

## 名前空間のインポート
まず、.NET プロジェクトで Aspose.Tasks を操作するために必要な名前空間をインポートする必要があります。
```csharp
    
    using Aspose.Tasks.Saving;
```
## ステップ 1: プロジェクト ファイルをロードする
まず、Microsoft Project ファイルを`Project`クラス。
```csharp
//ドキュメントディレクトリへのパス。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Input.mpp");
```
## ステップ 2: 最初の列数を設定する
すべてのページに印刷する最初の列の数を指定します。
```csharp
project.DefaultView.PageInfo.PageViewSettings.FirstColumnsCount = 2;
```
## ステップ 3: メモを印刷する
プロジェクトと一緒にメモを印刷するかどうかを選択します。
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintNotes = true;
```
## ステップ 4: タイムスケールをページの最後に合わせる
印刷時にタイムスケールをページの最後に合わせるかどうかを決定します。
```csharp
project.DefaultView.PageInfo.PageViewSettings.FitTimescaleToEndOfPage = true;
```
## ステップ 5: シートのすべての列を印刷する
ビューのすべてのシート列を印刷するかどうかを指定します。
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintAllSheetColumns = true;
```
## ステップ 6: 空白ページを印刷する
ビューの空白ページを印刷するかどうかを選択します。
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintBlankPages = false;
```
## ステップ 7: すべてのページの最初の列を印刷する
全ページに指定した数の最初の列を印刷するかどうかを設定します。
```csharp
project.DefaultView.PageInfo.PageViewSettings.PrintFirstColumnsCountOnAllPages = true;
```
## ステップ 8: 設定を構成してプロジェクトを保存する
最後に、PDF などの出力形式を指定して、ページ ビュー設定を構成したプロジェクトを保存します。
```csharp
project.Save(DataDir + "ProjectWithComments_out.pdf", SaveFileFormat.Pdf);
```

## 結論
Aspose.Tasks for .NET での Microsoft Project のページ ビュー設定の構成は簡単で、ニーズに合わせて印刷形式を調整できます。このチュートリアルで概説されている手順に従うことで、プロジェクト ドキュメントが要求どおりに正確に表示されることを確認できます。
## よくある質問
### Q: PDF 以外のファイル形式のページ表示設定を構成できますか?
A: はい、Aspose.Tasks は、XLSX、MPP、HTML など、プロジェクトを保存するためのさまざまなファイル形式をサポートしています。
### Q: 印刷できる列の数に制限はありますか?
A: Aspose.Tasks を使用すると、要件に基づいて印刷する列の数をカスタマイズできます。
### Q: プロジェクトごとに異なるページビュー設定を適用できますか?
A: はい、作業するプロジェクト ファイルごとにページ ビュー設定を個別に調整できます。
### Q: Aspose.Tasks は Microsoft Project のすべてのバージョンと互換性がありますか?
A: Aspose.Tasks は、Microsoft Project 2003 以降のバージョンとの互換性を提供します。
### Q: Aspose.Tasks に関するさらなるサポートやサポートはどこで入手できますか?
 A: にアクセスできます。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)ご利用中に発生したご質問や問題については、
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
