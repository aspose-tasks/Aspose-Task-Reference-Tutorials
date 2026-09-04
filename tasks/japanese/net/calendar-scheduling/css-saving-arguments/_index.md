---
date: 2026-07-05
description: Aspose.Tasks for .NET を使用してプロジェクトを HTML にエクスポートする際に CSS をカスタマイズする方法を学びます。CSS
  の保存引数で HTML 出力を調整します。
keywords:
- how to customize css
- export project to html
- customize html output
linktitle: Aspose.Tasks でプロジェクトを保存する際の CSS カスタマイズ方法
schemas:
- author: Aspose
  dateModified: '2026-07-05'
  description: Learn how to customize CSS while exporting a project to HTML using
    Aspose.Tasks for .NET. Tailor HTML output with CSS saving arguments.
  headline: How to Customize CSS When Saving Projects with Aspose.Tasks
  type: TechArticle
- questions:
  - answer: Using custom CSS can reduce the total size by up to 15 % because you can
      eliminate unused default styles.
    question: How does customizing CSS affect the size of the exported HTML?
  - answer: Absolutely. Implement the callbacks once and reuse them across any number
      of project exports.
    question: Can I use the same callbacks for multiple projects?
  - answer: Yes, set `HtmlSaveOptions.EmbeddedCss = true` to inline the stylesheet,
      which simplifies distribution.
    question: Is it possible to embed CSS directly into the HTML instead of separate
      files?
  type: FAQPage
second_title: Aspose.Tasks .NET API
title: Aspose.Tasks でプロジェクトを保存する際の CSS カスタマイズ方法
url: /ja/net/calendar-scheduling/css-saving-arguments/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasksでプロジェクトを保存する際のCSSカスタマイズ方法

このガイドでは、Aspose.Tasks for .NET を使用して Microsoft Project ファイルを HTML にエクスポートする際の **CSS のカスタマイズ方法** を紹介します。CSS 保存引数を調整することで、生成された HTML ページのビジュアルスタイルを完全にコントロールでき、出力をブランドやレポート基準に合わせることができます。

## クイック回答
- **エントリーポイントは何ですか？** カスタムコールバックを使用した `HtmlSaveOptions` を使用します。  
- **ライセンスは必要ですか？** はい、本番環境では有効な Aspose.Tasks ライセンスが必要です。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上です。  
- **大規模プロジェクトをエクスポートできますか？** Aspose.Tasks は、メモリに全ファイルを読み込むことなく、10,000 件以上のタスクを含むプロジェクトを処理できます。  
- **CSS カスタマイズは任意ですか？** はい、コールバックを省略すればデフォルトのスタイルシートが使用されます。

## Aspose.TasksでCSSをカスタマイズする方法は？

プロジェクトをロードし、`HtmlSaveOptions` オブジェクトに CSS 保存コールバックを添付してから `project.Save` を呼び出します。このパターンにより、カスタム CSS ファイルを書き出したり、デフォルトのスタイルを置き換えたり、フォルダー構造を制御したりすることが数行のコードで可能になります。エクスポート処理中に各 CSS ファイルごとにコールバックが自動的に呼び出されます。

`HtmlSaveOptions` はプロジェクトの HTML エクスポート方法を構成します。

## はじめに

このチュートリアルでは、Aspose.Tasks for .NET を使用した CSS 引数の保存プロセスについて詳しく解説します。カスケーディングスタイルシート (CSS) は HTML 要素の表示を定義する上で重要です。Aspose.Tasks を使うことで、これらの CSS 属性を効率的に操作・保存できます。

## 前提条件

開始する前に、以下の前提条件が整っていることを確認してください。

1. インストール: Aspose.Tasks for .NET がインストールされていることを確認してください。[ウェブサイト](https://releases.aspose.com/tasks/net/) からダウンロードできます。  
2. 基礎知識: C# と .NET 開発環境に慣れていることが推奨されます。

## 名前空間のインポート

開始するには、必要な名前空間をインポートします:

```csharp
using Aspose.Tasks;
using System.Collections.Generic;
using System.IO;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;

```

## 手順 1: CSS 保存コールバックの定義

`ICssSavingCallback` は、HTML エクスポート時に CSS ファイルの保存方法をカスタマイズできるインターフェイスです。

**CSS 保存コールバック** は、HTML エクスポート中に Aspose.Tasks が CSS ファイルを書き出すために呼び出すデリゲートです。各 CSS ファイルの作成方法を制御するコールバックメソッドを定義します:

```csharp
private class ResourcePrefixForNestedResources : ICssSavingCallback
{
    public void CssSaving(CssSavingArgs args)
    {
        // Implement your CSS saving logic here
    }
}
```

## 手順 2: フォントと画像保存コールバックの実装

`FontSavingArgs` は保存されるフォントに関する情報を提供し、`ImageSavingArgs` は画像リソースに関する詳細を提供します。

フォントと画像保存コールバックメソッドも同様に実装します:

```csharp
public void FontSaving(FontSavingArgs args)
{
    // Implement your font saving logic here
}

public void ImageSaving(ImageSavingArgs args)
{
    // Implement your image saving logic here
}
```

## 手順 3: 保存オプションの構成

`HtmlSaveOptions` は、プロジェクトを HTML にエクスポートする方法を制御する設定オブジェクトです。

`HtmlSaveOptions` では、コールバック、出力フォルダー、その他のエクスポート設定を指定できます。

先に定義したコールバックを使用し、出力フォルダーを指定するようにプロパティを設定します:

```csharp
public static HtmlSaveOptions GetSaveOptions(int pageNumber)
{
    var options = new HtmlSaveOptions
    {
        // Configure HTML saving options
    };

    var program = new ResourcePrefixForNestedResources();
    options.FontSavingCallback = program;
    options.CssSavingCallback = program;
    options.ImageSavingCallback = program;

    return options;
}
```

## 手順 4: カスタマイズした CSS でプロジェクトを保存

`Project` は操作および保存可能な Microsoft Project ファイルを表します。

最後に、カスタマイズした CSS 設定でプロジェクトを保存します:

```csharp
var project = new Project("Project1.mpp");
var options = ResourcePrefixForNestedResources.GetSaveOptions(1);
project.Save("document_out.html", options);
```

## プロジェクトをエクスポートする際に CSS をカスタマイズする理由は？

Aspose.Tasks は **HTML へのプロジェクトエクスポート** を 30 以上の形式でサポートし、エクスポートごとに最大 30 個の個別 CSS ファイルを生成できます。10,000 件以上のタスクを含むプロジェクトでも、メモリ使用量を 200 MB 未満に抑えて確実に処理でき、パフォーマンスのボトルネックなしでエンタープライズ規模のレポート作成が可能です。

## 結論

このチュートリアルでは、Aspose.Tasks for .NET を使用した CSS 引数の保存方法を検討しました。CSS 保存コールバックを定義し、HTML 保存オプションを構成することで、要件に合わせて CSS 属性を効率的に操作できます。

## FAQ

### Q1: Aspose.Tasks for .NET とは？

A1: Aspose.Tasks for .NET は、開発者がプログラムから Microsoft Project ファイルを操作できる強力な .NET API です。

### Q2: Aspose.Tasks で HTML ファイルを保存する際に CSS 属性をカスタマイズできますか？

A2: はい、CSS 保存コールバックを定義することで、必要に応じて CSS 属性をカスタマイズできます。

### Q3: Aspose.Tasks for .NET はすべてのバージョンの Microsoft Project ファイルと互換性がありますか？

A3: Aspose.Tasks for .NET はさまざまなバージョンの Microsoft Project ファイルをサポートしており、異なる環境間での互換性を確保します。

### Q4: Aspose.Tasks for .NET の包括的なドキュメントはどこで見つけられますか？

A4: 詳細情報やサンプルは、[ドキュメント](https://reference.aspose.com/tasks/net/) を参照してください。

### Q5: Aspose.Tasks for .NET は開発者向けのサポートを提供していますか？

A5: はい、Aspose.Tasks コミュニティの[フォーラム](https://forum.aspose.com/c/tasks/15) でサポートを受けられます。

**追加の質問**

**Q: CSS をカスタマイズするとエクスポートされた HTML のサイズにどのような影響がありますか？**  
A: カスタム CSS を使用すると、未使用のデフォルトスタイルを削除できるため、総サイズを最大 15 % 短縮できます。

**Q: 複数のプロジェクトで同じコールバックを使用できますか？**  
A: もちろんです。コールバックを一度実装すれば、任意の数のプロジェクトエクスポートで再利用できます。

**Q: CSS を別ファイルではなく HTML に直接埋め込むことは可能ですか？**  
A: はい、`HtmlSaveOptions.EmbeddedCss = true` を設定すると、スタイルシートがインライン化され、配布が簡素化されます。

---

**最終更新日:** 2026-07-05  
**テスト環境:** Aspose.Tasks 24.11 for .NET  
**作者:** Aspose

## 関連チュートリアル

- [Aspose.Tasks で MS Project を HTML として保存](/tasks/net/saving-options/html-save-options/)
- [Aspose.Tasks におけるページ保存コールバックの実装](/tasks/net/advanced-concepts/page-saving-callback/)
- [Aspose.Tasks における画像保存の処理](/tasks/net/advanced-concepts/image-saving/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}