---
title: Aspose.Tasks での CSS の引数の保存
linktitle: Aspose.Tasks での CSS の引数の保存
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET に CSS 引数を保存して HTML 出力をカスタマイズする方法を学びます。カスタマイズされた CSS 設定でプレゼンテーションを強化します。
weight: 20
url: /ja/net/calendar-scheduling/css-saving-arguments/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks での CSS の引数の保存

## 導入

このチュートリアルでは、Aspose.Tasks for .NET を使用して CSS 引数を保存するプロセスを詳しく説明します。カスケード スタイル シート (CSS) は、HTML 要素のプレゼンテーションを定義するために重要です。 Aspose.Tasks を使用すると、これらの CSS 属性を効率的に操作して保存できます。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

1. インストール: Aspose.Tasks for .NET がインストールされていることを確認してください。からダウンロードできます。[Webサイト](https://releases.aspose.com/tasks/net/).

2. 基本知識: C# および .NET 開発環境に精通していることが推奨されます。

## 名前空間のインポート

まず、必要な名前空間をインポートします。

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```
## ステップ 1: CSS 保存コールバックを定義する

まず、CSS ファイルの保存を処理する CSS 保存コールバック メソッドを定義します。

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        //ここに CSS 保存ロジックを実装します
    }
}
```

## ステップ 2: フォントと画像の保存コールバックを実装する

次に、フォントと画像を保存するコールバック メソッドを同様に実装します。

```csharp
public void FontSaving(FontSavingArgs args)
{
    //ここにフォント保存ロジックを実装します。
}

public void ImageSaving(ImageSavingArgs args)
{
    //ここに画像保存ロジックを実装します
}
```

## ステップ 3: 保存オプションを構成する

次に、実装されたコールバックを利用するように HTML 保存オプションを構成します。

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        //HTML 保存オプションを構成する
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## ステップ 4: カスタマイズした CSS を使用してプロジェクトを保存する

最後に、カスタマイズした CSS 設定を使用してプロジェクトを保存します。

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## 結論

このチュートリアルでは、Aspose.Tasks for .NET を使用して CSS 引数を保存する方法を検討しました。 CSS 保存コールバックを定義し、HTML 保存オプションを構成することで、要件に応じて CSS 属性を効率的に操作できます。

## よくある質問

### Q1: Aspose.Tasks for .NET とは何ですか?

A1: Aspose.Tasks for .NET は、開発者がプログラムで Microsoft Project ファイルを操作できるようにする強力な .NET API です。

### Q2: Aspose.Tasks で HTML ファイルを保存するときに CSS 属性をカスタマイズできますか?

A2: はい、CSS 保存コールバックを定義して、ニーズに応じて CSS 属性をカスタマイズできます。

### Q3: Aspose.Tasks for .NET は、Microsoft Project ファイルのすべてのバージョンと互換性がありますか?

A3: Aspose.Tasks for .NET は、さまざまなバージョンの Microsoft Project ファイルをサポートし、さまざまな環境間での互換性を確保します。

### Q4: Aspose.Tasks for .NET の包括的なドキュメントはどこで見つけられますか?

A4: を参照してください。[ドキュメンテーション](https://reference.aspose.com/tasks/net/)詳細な情報と例については、

### Q5: Aspose.Tasks for .NET は開発者にサポートを提供しますか?

 A5: はい、Aspose.Tasks コミュニティからサポートを受けることができます。[フォーラム](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
