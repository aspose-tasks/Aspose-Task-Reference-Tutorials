---
title: Aspose.Tasks を使用した MS Project 拡張属性の操作
linktitle: Aspose.Tasks での拡張属性の操作
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して MS Project の拡張属性を操作する方法を学びます。タスク データをプログラムで簡単に操作します。
type: docs
weight: 11
url: /ja/net/tasks-project-management/working-with-extended-attributes/
---
## 導入
Aspose.Tasks for .NET は、開発者が Microsoft Project ファイルをプログラムで操作できるようにする強力なライブラリです。このライブラリの重要な機能の 1 つは、MS Project の拡張属性を操作できることです。拡張属性は、プロジェクト内のタスクに追加のカスタマイズとメタデータを提供し、ユーザーが標準のタスク プロパティを超えて特定の情報を保存および管理できるようにします。
このチュートリアルでは、Aspose.Tasks for .NET を使用して MS Project の拡張属性を操作する方法を検討します。前提条件を説明し、名前空間をインポートし、各例をステップバイステップのガイド形式で複数のステップに分けて説明します。このチュートリアルを終えると、.NET アプリケーションで拡張属性を活用する方法をしっかりと理解できるようになります。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
### 1. Visual Studioのインストール
システムに Visual Studio がインストールされていることを確認してください。まだダウンロードしていない場合は、Web サイトからダウンロードできます。
### 2. .NET ライブラリの Aspose.Tasks
 Aspose.Tasks for .NET ライブラリを次の場所からダウンロードしてインストールします。[Webサイト](https://releases.aspose.com/tasks/net/).

## 名前空間のインポート
Aspose.Tasks for .NET の使用を開始するには、必要な名前空間をプロジェクトにインポートする必要があります。次の手順を実行します：
### ステップ 1: Visual Studio を開く
システム上で Visual Studio を起動します。
### ステップ 2: 新しいプロジェクトを作成する
Aspose.Tasks を使用する新しいプロジェクトを作成するか、既存のプロジェクトを開きます。
### ステップ 3: 名前空間をインポートする
C# ファイルの先頭に次の名前空間を追加します。
```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

```

環境をセットアップしたので、Aspose.Tasks for .NET を使用した MS Project 拡張属性の操作に移りましょう。
## ステップ 1: データ ディレクトリを定義する
MS Project ファイルが配置されているディレクトリへのパスを定義します。
```csharp
String DataDir = "Your Document Directory";
```
交換する`"Your Document Directory"`ドキュメントディレクトリへの実際のパスを置き換えます。
## ステップ 2: プロジェクト ファイルをロードする
次のコマンドを使用して MS Project ファイルをロードします。`Project`クラス：
```csharp
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
このコードは、`Project`クラスを呼び出して、指定された MS Project ファイルをロードします。
## ステップ 3: タスクの拡張属性を読み取る
タスクとその拡張属性を反復処理して情報を読み取ります。
```csharp
foreach (var task in project.RootTask.Children)
{
    foreach (var attribute in task.ExtendedAttributes)
    {
        //拡張属性に関する共通情報を読む
        Console.WriteLine("Extended Attribute: " + attribute.ToString());
    }
}
```
このコード スニペットは、各タスクとその拡張属性をループし、その情報をコンソールに出力します。

## 結論
このチュートリアルでは、Aspose.Tasks for .NET を使用して MS Project の拡張属性を操作する方法を学習しました。上記の手順に従うことで、.NET アプリケーションの拡張属性データを効率的に管理および操作できます。
## よくある質問
### Aspose.Tasks for .NET は Microsoft Project のすべてのバージョンと互換性がありますか?
はい、Aspose.Tasks for .NET は、2003、2007、2010、2013、2016、2019 などのさまざまなバージョンの Microsoft Project をサポートしています。
### Aspose.Tasks for .NET を使用して新しい MS Project ファイルを作成できますか?
絶対に！ Aspose.Tasks for .NET を使用すると、MS Project ファイルをプログラムで作成、変更、操作できます。
### Aspose.Tasks for .NET を商用利用するにはライセンスが必要ですか?
はい、Aspose.Tasks for .NET の商用利用にはライセンスを購入する必要があります。ただし、無料トライアルを利用してその機能を評価することもできます。
### プロジェクトの要件に応じて拡張属性をカスタマイズできますか?
はい、Aspose.Tasks for .NET は、プロジェクト固有のニーズに合わせて拡張属性をカスタマイズするための広範な機能を提供します。
### Aspose.Tasks for .NET の使用中に問題が発生した場合、どこでサポートを受けられますか?
 Aspose.Tasks コミュニティ フォーラムからサポートを受けることができます。[ここ](https://forum.aspose.com/c/tasks/15).