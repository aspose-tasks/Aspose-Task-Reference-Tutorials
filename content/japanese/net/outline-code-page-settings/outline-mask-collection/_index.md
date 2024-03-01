---
title: Aspose.Tasks を使用して MS プロジェクトのアウトライン マスクをマスターする
linktitle: Aspose.Tasks のアウトライン マスクのコレクション
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して MS Project コレクションのアウトライン マスクを操作する方法を学びます。この包括的なチュートリアルで生産性を向上させます。
type: docs
weight: 15
url: /ja/net/outline-code-page-settings/outline-mask-collection/
---
## 導入
Aspose.Tasks for .NET を使用して Microsoft Project のアウトライン マスクの機能を活用したいと考えていますか?正しい場所に来ました！この包括的なチュートリアルでは、プロセスを段階的にガイドし、プロジェクトでアウトライン マスクを効果的に操作する方法を確実に理解できるようにします。経験豊富な開発者であっても、初心者であっても、このガイドではワークフローを最適化するために必要な知識とスキルを身につけることができます。
## 前提条件
このチュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
### 1. Aspose.Tasks for .NET のインストール
開発環境に Aspose.Tasks for .NET がインストールされていることを確認してください。 Aspose Web サイトからライブラリをダウンロードできます。[ここ](https://releases.aspose.com/tasks/net/).
### 2. C# と .NET Framework の基礎知識
このチュートリアルでは両方を利用するため、C# プログラミング言語と .NET Framework についてよく理解してください。
### 3. Microsoft プロジェクト ファイル
テスト目的で Microsoft Project ファイル (MPP) を用意します。既存のファイルを使用することも、実験用に新しいファイルを作成することもできます。
## 名前空間のインポート
まず、必要な名前空間を C# プロジェクトにインポートします。この手順により、Aspose.Tasks for .NET によって提供される必要なクラスと機能に確実にアクセスできるようになります。

コード ファイルの先頭に次の名前空間を追加します。
```csharp
    using Aspose.Tasks;
    using System;
    
```
ここで、提供された例を複数のステップに分割し、各ステップを詳しく説明しましょう。
## ステップ 1: プロジェクト オブジェクトを初期化する
```csharp
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
ここでは、`Project`クラスを作成し、「OutlineValues2010.mpp」という名前の既存の Microsoft Project ファイルを読み込みます。
## ステップ 2: アウトライン コードにアクセスする
```csharp
var outline = project.OutlineCodes[0];
```
プロジェクトからアウトライン コードにアクセスします。アウトライン コードは、タスクを分類および整理できる Microsoft Project のカスタム フィールドです。
## ステップ 3: アウトラインマスクをクリアする
```csharp
if (outline.Masks.Count > 0)
{
    if (!outline.Masks.IsReadOnly)
    {
        outline.Masks.Clear();
    }
}
```
この手順により、先に進む前に既存のアウトライン マスクがすべてクリアされます。
## ステップ 4: アウトライン マスクを作成する
```csharp
var mask = new OutlineMask();
mask.Type = MaskType.Characters;
var maskWrong = new OutlineMask();
maskWrong.Type = MaskType.Null;
outline.Masks.Add(mask);
```
新しいアウトライン マスクを作成し、そのタイプを指定します。この例では、有効なアウトライン マスクと間違ったアウトライン マスクを作成します。
## ステップ 5: マスクの挿入と編集
```csharp
outline.Masks.Insert(0, maskWrong);
var idx = outline.Masks.IndexOf(mask);
outline.Masks[idx].Length = 2;
```
ここでは、間違ったマスクをコレクションに挿入し、そのインデックスを使用してマスクの長さを編集します。
## ステップ 6: マスクを削除する
```csharp
var idxOfWrong = outline.Masks.IndexOf(maskWrong);
outline.Masks.RemoveAt(idxOfWrong);
```
インデックスに基づいて、間違ったマスクをコレクションから削除します。
## ステップ 7: マスクを反復処理する
```csharp
foreach (var outlineMask in outline.Masks)
{
    Console.WriteLine("Length: " + outlineMask.Length);
    Console.WriteLine("Level: " + outlineMask.Level);
    Console.WriteLine("Separator: " + outlineMask.Separator);
    Console.WriteLine("Type: " + outlineMask.Type);
}
```
このループは、コレクション内の各アウトライン マスクを反復処理し、長さ、レベル、区切り文字、タイプなどのプロパティを出力します。
## ステップ 8: マスクを別のプロジェクトにコピーする
```csharp
var otherProject = new Project(DataDir + "OutlineValues2010.mpp");
var otherOutline = otherProject.OutlineCodes[0];
var masks = new OutlineMask[outline.Masks.Count];
outline.Masks.CopyTo(masks, 0);
foreach (var maskToAdd in masks)
{
    if (!otherOutline.Masks.Contains(maskToAdd))
    {
        otherOutline.Masks.Add(maskToAdd);
    }
}
```
最後に、アウトライン マスクをあるプロジェクトから別のプロジェクトにコピーして、異なるプロジェクト間での一貫性を確保します。
## 結論
おめでとう！ Aspose.Tasks for .NET を使用して MS Project コレクションのアウトライン マスクを操作する方法を学習しました。このチュートリアルに従うことで、プロジェクト内のアウトライン マスクを効率的に管理するスキルを身につけ、最終的に生産性とワークフローを向上させることができます。
## よくある質問
### Q1: Aspose.Tasks for .NET をさまざまなバージョンの Microsoft Project ファイルで使用できますか?
A: はい、Aspose.Tasks for .NET は、MPP、MPT、XML 形式など、さまざまなバージョンの Microsoft Project ファイルをサポートしています。
### Q2: Aspose.Tasks for .NET は .NET Core と互換性がありますか?
A: はい、Aspose.Tasks for .NET は .NET Core と互換性があるため、クロスプラットフォーム アプリケーションで使用できます。
### Q3: プロジェクトの要件に応じてアウトライン マスクのプロパティをカスタマイズできますか?
A: もちろんです！特定のプロジェクトのニーズに合わせて、アウトライン マスクの長さ、レベル、セパレーター、タイプを調整して、アウトライン マスクをカスタマイズできます。
### Q4: Aspose.Tasks for .NET はドキュメントとサポートを提供しますか?
A: はい、Aspose.Tasks for .NET は、Web サイトを通じて包括的なドキュメントと専用のサポートを提供しています。[フォーラム](https://forum.aspose.com/c/tasks/15).
### Q5: Aspose.Tasks for .NET に利用できる無料トライアルはありますか?
 A: はい、Aspose.Tasks for .NET の無料トライアルにアクセスできます。[Webサイト](https://releases.aspose.com/tasks/net/)。購入する前にその特徴や機能を調べてください。