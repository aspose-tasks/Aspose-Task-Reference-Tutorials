---
title: Aspose.Tasks for .NET を使用した MS プロジェクトの使用量の計測
linktitle: Aspose.Tasks での使用量の計測
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して MS Project の使用状況を効果的に監視し、最適化する方法を学びます。効率的なプロジェクト管理のためのステップバイステップのガイド。
weight: 17
url: /ja/net/license-management/metering-usage/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks for .NET を使用した MS プロジェクトの使用量の計測

## 導入
Aspose.Tasks を使用して MS Project の使用状況を効果的に管理および監視したいと考えていますか?メーター機能を利用すると、使用状況を追跡し、プロジェクト管理の取り組みを最適化できます。このチュートリアルでは、Aspose.Tasks for .NET を使用して MS Project の使用量を測定するプロセスを段階的に説明します。
## 前提条件
MS Project の使用量の計測に入る前に、次の前提条件を満たしていることを確認してください。
1.  Aspose.Tasks for .NET ライブラリ: Aspose.Tasks for .NET ライブラリを次の場所からダウンロードしてインストールします。[ダウンロードページ](https://releases.aspose.com/tasks/net/)。インストール手順に従って、開発環境にライブラリをセットアップします。
2. 公開キーと秘密キー: Aspose から公開キーと秘密キーを取得します。これらのキーは使用量の計測に不可欠です。まだキーを持っていない場合は、Aspose からキーをリクエストできます。[仮免許](https://purchase.aspose.com/temporary-license/)ページ。

## 名前空間のインポート
続行する前に、必要な名前空間をプロジェクトにインポートします。
```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;
using System.Net;

```
## ステップ 1: メータリングを設定する
MS Project の使用量の計測を開始するには、公開キーと秘密キーを指定して計測環境をセットアップします。
```csharp
String DataDir = "Your Document Directory";
var metered = new Metered();
metered.SetMeteredKey("<public key>", "<private key>");
```
交換する`"Your Document Directory"`をドキュメント ディレクトリへのパスに置き換え、`<public key>`そして`<private key>` Aspose から取得した実際のキーを使用します。
## ステップ 2: MS プロジェクト ファイルをロードする
次に、Aspose.Tasks を使用して MS Project ファイルを読み込みます。
```csharp
var project = new Project(DataDir + "Project2.mpp");
Console.WriteLine("Project Name: " + project.Get(Prj.Name));
```
このステップでは、指定されたディレクトリから「Project2.mpp」という名前の MS Project ファイルを読み込みます。ファイル名を独自の MS Project ファイルに置き換えることができます。
## ステップ 3: プロジェクトの操作
プロジェクトがロードされたので、プロジェクト管理タスクの必要に応じて、プロジェクトに対してさまざまな操作を実行できます。
```csharp
//ここでプロジェクト管理タスクを実行します
```
## ステップ 4: クレジットとバイト消費量を確認する
使用期間中に消費されたクレジットと消費されたバイト数を確認できます。
```csharp
try
{
    Console.WriteLine("Credits spent: {0}", Metered.GetConsumptionCredit());
    Console.WriteLine("Bytes consumed: {0}", Metered.GetConsumptionQuantity());
}
catch (WebException)
{
    //ここで例外を処理します
}
```
このステップでは、操作によって消費されたクレジットと消費されたバイト数を取得して表示します。このプロセス中に発生する可能性のある例外を処理します。
## ステップ 5: 従量制キーをリセットする
オプションで、従量制キーをリセットしてバイトのカウントを停止できます。
```csharp
metered.ResetMeteredKey();
```
このステップにより、計測プロセスが停止され、計測対象キーがリセットされます。

## 結論
このチュートリアルでは、Aspose.Tasks for .NET を使用して MS Project の使用状況を測定する方法を学習しました。これらの手順に従うことで、リソースの効率的な利用を確保しながら、プロジェクト管理の取り組みを効果的に監視および最適化できます。
### よくある質問
### Q: 複数の MS Project ファイルの使用量を測定できますか?
A: はい、各ファイルを個別にロードし、それに応じて使用状況を監視することで、複数の MS Project ファイルにわたる使用量を測定できます。
### Q: MS Project の使用状況の計測は、Aspose.Tasks for .NET のすべてのバージョンと互換性がありますか?
A: はい、MS Project の使用状況の計測は、Aspose.Tasks for .NET のすべてのバージョンでサポートされています。
### Q: 使用量を測定するにはインターネット接続が必要ですか?
A: はい、使用量を測定するために Aspose のサーバーと通信するには、インターネット接続が必要です。
### Q: 使用状況をリアルタイムで追跡できますか?
A: はい、消費されたクレジットと消費されたバイト数を定期的にチェックすることで、使用状況をリアルタイムで追跡できます。
### Q: MS Project の使用量の計測は試用版でも利用できますか?
A: はい、MS Project の使用状況の計測は、Aspose.Tasks for .NET の試用版とライセンス版の両方で利用できます。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
