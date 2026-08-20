---
date: 2026-03-05
description: Aspose.Tasks for .NET を使用して画像の保存、画像付き HTML の生成、画像エクスポートのカスタマイズ方法を学びます。プロジェクトを
  HTML として保存するステップバイステップガイド。
linktitle: How to Save Images with Aspose.Tasks for .NET
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks for .NET を使用して画像を保存する方法
url: /ja/net/advanced-concepts/image-saving/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for .NET で画像を保存する方法

## はじめに

このチュートリアルでは、Aspose.Tasks API for .NET を使用して Microsoft Project ファイルから **画像の保存方法** を学びます。レポートにチャートを埋め込む必要がある場合や、プロジェクトのビジュアルを含む HTML ページを生成する場合、あるいは単に図表リソースをエクスポートしたい場合でも、以下の手順がプロジェクト オブジェクトの設定から画像エクスポート コールバックのカスタマイズまで、全プロセスを案内します。

## クイック回答
- **Aspose.Tasks における「画像の保存方法」とは何ですか？**  
  `IImageSavingCallback` インターフェイスを使用して、視覚リソースを書き込む場所と方法を制御することを指します。
- **画像を埋め込んだ状態でプロジェクトを HTML として保存できますか？**  
  はい、`HtmlSaveOptions` と画像保存コールバックを組み合わせることで、生成されたすべての画像を含む **HTML としてプロジェクトを保存** できます。
- **画像エクスポートにライセンスは必要ですか？**  
  テスト用には一時的な評価ライセンスで動作しますが、本番環境ではフルライセンスが必要です。
- **対応している .NET バージョンはどれですか？**  
  Aspose.Tasks for .NET は .NET Framework 4.5 以降、.NET Core 3.1 以降、そして .NET 5/6 以降をサポートしています。
- **画像エクスポート（形式、フォルダー、命名）をカスタマイズできますか？**  
  もちろんです。コールバックによりファイル名、形式、保存先を完全に制御できます。

## Aspose.Tasks のコンテキストで「画像の保存方法」とは何ですか？

画像を保存するとは、Project ファイルから視覚要素（チャート、ガントバー、リソース グラフィックなど）を抽出し、画像ファイル（PNG、JPEG など）として書き出すことを指します。Aspose.Tasks は柔軟なコールバック機構を提供し、保存場所、命名規則、さらには画像形式まで自由に決定できます。

## なぜ Aspose.Tasks を使って画像を保存するのか？

- **完全なプログラム制御** – 手動の UI 操作は不要です。  
- **クロスプラットフォーム** – .NET Core 経由で Windows、Linux、macOS で動作します。  
- **高忠実度レンダリング** – 画像は元の Project ビューと同等の品質を保持します。  
- **簡単な HTML 生成** – `HtmlSaveOptions` と画像コールバックを組み合わせることで、**画像付き HTML を自動的に生成**できます。

## 前提条件

開始する前に、以下が揃っていることを確認してください。

1. 開発マシンに Visual Studio がインストールされていること。  
2. Aspose.Tasks for .NET を [here](https://releases.aspose.com/tasks/net/) からダウンロードしていること。  
3. C# と .NET プロジェクト構造の基本的な知識があること。

## 名前空間のインポート

まず、必要な名前空間をソース ファイルにインポートします。

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
```

## 手順 1: Project オブジェクトの作成

操作したい Microsoft Project ファイルをロードします。

```csharp
var project = new Project("Project1.mpp");
```

## 手順 2: 保存オプションの定義

画像保存コールバックも保持する HTML 保存オプションを作成します。

```csharp
var options = GetSaveOptions(1);
```

## 手順 3: プロジェクトを HTML として保存 (save project as html)

プロジェクトを HTML ファイルにエクスポートします。HTML で参照される画像は、次に定義するコールバックによって生成されます。

```csharp
project.Save("document_out.html", options);
```

## 手順 4: 画像保存コールバックの実装 (画像エクスポートのカスタマイズ)

`IImageSavingCallback` インターフェイスを実装します。ここで **画像エクスポートの動作をカスタマイズ** します。

```csharp
private class ResourcePrefixForNestedResources : IImageSavingCallback
{
    public void ImageSaving(ImageSavingArgs args)
    {
        // Image saving logic goes here
    }
}
```

## 手順 5: 画像を指定ディレクトリに保存

`ImageSaving` メソッド内で、各画像の保存先を決定します。以下の例は PNG リソースと他の形式を区別しています。

```csharp
if (args.FileName.EndsWith("png"))
{
    // Save nested resources
}
else
{
    // Save regular resources
}
```

## 手順 6: 保存オプションの指定（コールバック含む）

フォント、CSS、画像のコールバックを接続します。これにより、すべての視覚要素が一貫して処理されます。

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Specify save options here
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## よくある問題と解決策

| 問題 | 原因 | 対策 |
|------|------|------|
| 生成された HTML に画像が表示されない | コールバックが有効なファイルパスを割り当てていない | `args.Path` が書き込み可能なフォルダーを指していることを確認し、`args.ImageStream` を正しく設定してください。 |
| PNG ファイルが誤った拡張子で保存される | 条件ロジックが “png” サフィックスのみをチェックしている | 堅牢な検出のために `Path.GetExtension(args.FileName).Equals(".png", StringComparison.OrdinalIgnoreCase)` を使用してください。 |
| ファイル移動後に HTML の参照が壊れる | 出力フォルダーを移動したことで相対パスが変わった | HTML と画像フォルダーを一緒に保管するか、`options.ImageFolder` を適宜更新してください。 |

## 結論

これらの手順に従うことで、Project ファイルから **画像を保存する方法**、**プロジェクトを HTML として保存する方法**、そしてアプリケーションのフォルダー構造に合わせて **画像エクスポートをカスタマイズ** できるようになりました。このアプローチにより、レポートやドキュメント ポータル、Web ダッシュボードにシームレスに埋め込める **画像付き HTML を生成** できます。

## よくある質問

**Q1: Aspose.Tasks を使用して HTML 以外の形式のプロジェクト ファイルを操作できますか？**  
A1: はい、Aspose.Tasks は PDF、XLSX、MPP などさまざまな形式をサポートしています。

**Q2: Aspose.Tasks はクラウドストレージ統合をサポートしていますか？**  
A2: はい、Aspose.Tasks は Amazon S3 や Google Drive などの一般的なクラウドストレージサービスと連携する API を提供しています。

**Q3: Aspose.Tasks は .NET Core と互換性がありますか？**  
A3: はい、Aspose.Tasks は .NET Core と互換性があり、クロスプラットフォーム アプリケーションの開発が可能です。

**Q4: 保存する画像の外観をカスタマイズできますか？**  
A4: はい、コールバック メソッド内の画像保存ロジックを変更することで、保存画像の外観をカスタマイズできます。

**Q5: Aspose.Tasks は評価用のトライアル版を提供していますか？**  
A5: はい、[here](https://releases.aspose.com/) から Aspose.Tasks の無料トライアルを入手できます。

**最終更新日:** 2026-03-05  
**テスト環境:** Aspose.Tasks 24.11 for .NET  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}