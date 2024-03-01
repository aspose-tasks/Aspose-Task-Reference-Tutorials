---
title: MS プロジェクト オプション Primavera を Aspose.Tasks で保存する
linktitle: Primavera の Aspose.Tasks の保存オプション
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して、Primavera の MS Project オプションをシームレスに保存する方法を説明します。ステップバイステップのチュートリアルに従ってください。
type: docs
weight: 14
url: /ja/net/saving-options/primavera-save-options/
---
## 導入
Aspose.Tasks for .NET は、開発者が .NET アプリケーションで Microsoft Project ファイルをシームレスに操作できるようにする強力なライブラリです。これが提供する重要な機能の 1 つは、人気のあるプロジェクト管理ソフトウェアである Primavera の MS Project オプションを保存する機能です。このチュートリアルでは、Aspose.Tasks を使用してこれを実現する方法を詳しく説明します。
## 前提条件
始める前に、以下のものがあることを確認してください。
- C# と .NET Framework の基本的な理解。
-  Aspose.Tasks for .NET が開発環境にインストールされています。そうでない場合は、ダウンロードできます[ここ](https://releases.aspose.com/tasks/net/).
- 実験用のサンプル MS Project ファイル。

## 名前空間のインポート
まず、必要な名前空間を C# コードにインポートしましょう。
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## ステップ 1: MS プロジェクト ファイルをロードする
まず、作業する MS Project ファイルを C# アプリケーションにロードします。これを行うには、`Project` Aspose.Tasks によって提供されるクラス。
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## ステップ 2: Primavera の保存オプションを定義する
次に、Primavera 保存オプションを作成し、要件に応じてカスタマイズします。この手順には、アクティビティ ID のプレフィックス、サフィックス、増分、アクティビティ ID の番号を付け直すかどうかなどのパラメーターの指定が含まれます。
```csharp
var options = new PrimaveraSaveOptions
{
    ActivityIdPrefix = "TEST",
    ActivityIdSuffix = 10000,
    ActivityIdIncrement = 5,
    RenumberActivityIds = true
};
```
## ステップ 3: Primavera の MS プロジェクト オプションを保存する
プロジェクト ファイルをロードし、Primavera 保存オプションを定義したので、次は Primavera のオプションを保存します。使用`Save`によって提供されるメソッド`Project`クラスに、必要な出力ファイルのパスと Primavera 保存オプションを渡します。
```csharp
project.Save(DataDir + "WorkWithPrimaveraSaveOptions_out.xer", options);
```

## 結論
結論として、Aspose.Tasks for .NET を活用すると、開発者は Primavera の保存オプションを含め、MS Project ファイルをシームレスに操作できるようになります。このチュートリアルで概説されている手順に従うことで、この機能を .NET アプリケーションに効率的に統合できます。
## よくある質問
### Q: Primavera の MS Project オプションを保存するときに、アクティビティ ID 以外の他のパラメーターをカスタマイズできますか?
A: はい、Aspose.Tasks には、リソース割り当てやタスク スケジュールなど、カスタマイズのための幅広いオプションが用意されています。
### Q: Aspose.Tasks は、Primavera 以外の他のプロジェクト管理ソフトウェアをサポートしていますか?
A: はい、Aspose.Tasks は、Oracle Primavera、Microsoft Project Server などの一般的なプロジェクト管理ツールと互換性のあるさまざまな形式をサポートしています。
### Q: Aspose.Tasks は小規模プロジェクトとエンタープライズ レベルのプロジェクトの両方に適していますか?
A: もちろん、Aspose.Tasks はあらゆる規模のプロジェクトに取り組む開発者のニーズを満たすように設計されており、スケーラビリティと堅牢なパフォーマンスを提供します。
### Q: 購入する前に、Aspose.Tasks を無料で試すことはできますか?
 A: はい、Aspose.Tasks の無料トライアルを次のサイトからダウンロードできます。[ここ](https://releases.aspose.com/)その機能と機能を探索します。
### Q: Aspose.Tasks の使用中に問題が発生したり質問がある場合、どこでサポートを受けられますか?
 A: Aspose.Tasks コミュニティおよびサポート チームに支援を求めることができます。[フォーラム](https://forum.aspose.com/c/tasks/15).