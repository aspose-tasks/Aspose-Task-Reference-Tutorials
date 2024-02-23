---
title: Aspose.Tasks でのページ保存コールバックの実装
linktitle: Aspose.Tasks でのページ保存コールバックの実装
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET でページ保存コールバックを実装し、複数ページのドキュメント出力ストリームのカスタマイズされた処理を可能にする方法を学びます。
type: docs
weight: 12
url: /ja/net/advanced-concepts/page-saving-callback/
---
## 導入

このチュートリアルでは、Aspose.Tasks for .NET でページ保存コールバックを実装する方法を検討します。この機能により、複数ページのドキュメントをユーザーが提供するストリームに保存できるため、出力処理の柔軟性とカスタマイズが可能になります。

## 前提条件:

始める前に、以下のものがあることを確認してください。

1. C# プログラミング言語の知識: C# の構文と概念の基本を理解している必要があります。
   
2. Aspose.Tasks for .NET のインストール: 開発環境に Aspose.Tasks ライブラリがインストールされていることを確認してください。からダウンロードできます[ここ](https://releases.aspose.com/tasks/net/).

3. 開発環境のセットアップ: Visual Studio などの .NET 開発用の優先 IDE をセットアップします。

## 名前空間をインポートします。

まず、必要な名前空間を C# コードにインポートする必要があります。

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;

```

## ステップ 1: プロジェクト オブジェクトを作成する

インスタンス化する`Project`既存のプロジェクト ファイルをロードしてオブジェクトを作成します。

```csharp
var project = new Project(DataDir + "Homemoveplan.mpp");
```

## ステップ 2: 画像保存オプションを構成する

定義する`ImageSaveOptions`を設定してページ保存動作をカスタマイズします。`PageSavingCallback`財産：

```csharp
var imageSaveOptions = new ImageSaveOptions(SaveFileFormat.Png);
var callback = new CustomPageSavingCallback();
imageSaveOptions.PageSavingCallback = callback;
imageSaveOptions.RenderToSinglePage = false;
```

## ステップ 3: コールバックを使用してプロジェクトを保存する

構成された画像保存オプションを使用してプロジェクトを保存します。

```csharp
project.Save(Stream.Null, imageSaveOptions);
```

## ステップ 4: 保存されたページ ストリームを処理する

コールバックによって提供されるページ ストリームを反復処理して、各ページを個別に処理します。

```csharp
foreach (var stream in callback.PageStreams)
{
    //各ページストリームを処理する
}
```

## ステップ 5: カスタム ページ保存コールバックを実装する

を実装するクラスを作成します。`IPageSavingCallback`ページ保存を処理するインターフェース:

```csharp
private sealed class CustomPageSavingCallback : IPageSavingCallback
{
    public List<MemoryStream> PageStreams { get; } = new List<MemoryStream>();

    public void PageSaving(PageSavingArgs args)
    {
        var memoryStream = new MemoryStream();
        args.Stream = memoryStream;
        args.KeepStreamOpen = false;
        PageStreams.Add(memoryStream);
    }

    public void OnFinish()
    {
        //クリーンアップまたはファイナライズを実行する
    }
}
```

## 結論：

このチュートリアルでは、Aspose.Tasks for .NET でページ保存コールバックを実装し、複数ページのドキュメントを別のストリームに保存できるようにする方法を学習しました。これらの手順に従うことで、アプリケーションの機能を強化し、カスタマイズされた出力処理を実現できます。

## よくある質問

### Q1: Aspose.Tasks のページ保存コールバックとは何ですか?

A1: ページ保存コールバックは、Aspose.Tasks の機能で、ユーザーが各ページに個別にストリームを提供することで、複数ページのドキュメントの保存プロセスをカスタマイズできるようにします。

### Q2: このコールバックを使用してページを保存するために別の形式を使用できますか?

A2: はい、Aspose.Tasks でサポートされているさまざまなファイル形式 (PNG、JPEG、PDF など) をコールバックでページを保存するために利用できます。

### Q3: Aspose.Tasks は .NET Core と互換性がありますか?

A3: はい、Aspose.Tasks は .NET Core をサポートしているため、開発者はその機能をクロスプラットフォーム アプリケーションで使用できます。

### Q4: ページ保存プロセス中のエラーはどのように処理すればよいですか?

A4: コールバック メソッド内にエラー処理メカニズムを実装して、例外を管理し、アプリケーションの堅牢性を確保できます。

### Q5: Aspose.Tasks のその他のリソースとサポートはどこで入手できますか?

 A5: をご覧いただけます。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)サポートが必要な場合は、ドキュメントにアクセスしてください[ここ](https://reference.aspose.com/tasks/net/)、または、追加の機能とライセンス オプションを確認してください。[Aspose.Task の Web サイト](https://purchase.aspose.com/buy).