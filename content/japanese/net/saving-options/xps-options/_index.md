---
title: Aspose.Tasks を使用した MSP から XPS への変換オプション
linktitle: Aspose.Tasks の XPS オプション
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して Microsoft Project ファイルを XPS 形式に変換する方法を学習します。簡単な統合、堅牢な機能。
type: docs
weight: 21
url: /ja/net/saving-options/xps-options/
---
## 導入
Microsoft Project (MSP) は、プロジェクト管理に広く使用されているツールで、プロジェクト活動の計画、追跡、レポート作成を容易にします。 Aspose.Tasks for .NET は、MSP ファイルをプログラムで操作するための堅牢な機能を提供し、開発者がプロジェクト管理に関連するさまざまなタスクを自動化できるようにします。このチュートリアルでは、Aspose.Tasks for .NET を活用して MSP ドキュメントから XPS ファイルを生成する方法について詳しく説明し、必要な手順と考慮事項を検討します。
## 前提条件
始める前に、次の前提条件が満たされていることを確認してください。
1.  Aspose.Tasks for .NET のインストール: Aspose.Tasks for .NET を次の場所からダウンロードしてインストールします。[Webサイト](https://releases.aspose.com/tasks/net/).
2. Microsoft Project ドキュメント: XPS 形式に変換する Microsoft Project ドキュメント (.mpp) を準備します。

## 名前空間のインポート
プロセスを開始するには、.NET プロジェクトに必要な名前空間をインポートします。
```csharp

using Aspose.Tasks.Saving;
```

## ステップ 1: ドキュメント ディレクトリのパスを設定する
```csharp
//ドキュメントディレクトリへのパス。
String DataDir = "Your Document Directory";
```
交換する`"Your Document Directory"`MSP ドキュメントが存在するパスに置き換えます。
## ステップ 2: MSP ドキュメントをロードする
```csharp
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
ここでは、新しいものを初期化します`Project`MSP ドキュメントのパスを渡すことでオブジェクトを取得します。
## ステップ 3: XPS 保存オプションを作成する
```csharp
//XPS 保存オプションを作成し、パラメーターを調整する
var options = new XpsOptions
{
    RenderMetafileAsBitmap = true
};
```
このステップでは、インスタンスを作成します`XpsOptions`パラメータを設定します。設定`RenderMetafileAsBitmap`に`true`メタファイルの適切なレンダリングを保証します。
## ステップ 4: ドキュメントを XPS として保存する
```csharp
project.Save(DataDir + "UseSvgOptions_out.xps", options);
```
最後に、私たちは`Save`のメソッド`Project`オブジェクト、出力ファイルのパスと以前に構成されたパスを指定します。`XpsOptions`.

## 結論
結論として、Aspose.Tasks for .NET は、Microsoft Project ドキュメントをプログラムによって XPS 形式に変換するプロセスを簡素化します。このチュートリアルで概説されている手順に従うことで、開発者はこの機能を .NET アプリケーションにシームレスに統合し、プロジェクト管理ワークフローを簡単に強化できます。
## よくある質問
### Q: Aspose.Tasks for .NET は複雑な MSP ファイルを処理できますか?
A: はい、Aspose.Tasks for .NET は複雑な Microsoft Project ファイルを効率的に処理でき、さまざまな形式への正確な変換を保証します。
### Q: Aspose.Tasks for .NET の試用版はありますか?
 A: はい、以下から無料試用版を入手できます。[ここ](https://releases.aspose.com/).
### Q: Aspose.Tasks for .NET は XPS 以外の出力形式をサポートしていますか?
A: はい、Aspose.Tasks for .NET は、PDF、HTML、PNG、JPEG などのさまざまな出力形式をサポートしています。
### Q: 出力ファイルのレンダリング オプションをカスタマイズできますか?
A: もちろん、Aspose.Tasks for .NET には、要件に応じてレンダリング パラメーターをカスタマイズするための広範なオプションが用意されています。
### Q: Aspose.Tasks for .NET の追加のサポートや支援はどこで入手できますか?
 A: にアクセスできます。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15) Aspose.Tasks for .NET に関する質問やサポートについては、こちらをご覧ください。