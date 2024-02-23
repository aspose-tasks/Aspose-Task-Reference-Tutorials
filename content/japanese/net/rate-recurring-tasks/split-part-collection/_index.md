---
title: Aspose.Tasks で分割パーツの MS プロジェクトを収集する
linktitle: Aspose.Tasks の分割パーツのコレクション
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して MS Project の分割パーツを収集する方法を学びます。この包括的なチュートリアルでは、プロセスを段階的にガイドします。
type: docs
weight: 19
url: /ja/net/rate-recurring-tasks/split-part-collection/
---
## 導入
このチュートリアルでは、Aspose.Tasks for .NET を使用して MS Project の分割パーツを収集する方法を詳しく説明します。タスクを部分に分割することは、プロジェクト管理の重要な側面となる可能性があり、Aspose.Tasks はこれを効率的に処理する便利な方法を提供します。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
1. Aspose.Tasks for .NET のインストール: Aspose.Tasks for .NET がインストールされていることを確認してください。からダウンロードできます[ここ](https://releases.aspose.com/tasks/net/).
2. C# の基本知識: C# でコード スニペットを記述するため、C# プログラミング言語に精通していると役立ちます。

## 名前空間のインポート
C# プロジェクトに、必要な名前空間を含めます。
```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

```

## ステップ 1: プロジェクトをセットアップする
まず、好みの IDE で新しいプロジェクトを作成し、Aspose.Tasks for .NET が正しく参照されていることを確認します。
## ステップ 2: プロジェクト オブジェクトを初期化する
```csharp
//ドキュメントディレクトリへのパス。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Splits.mpp");
```
MS Project ファイルへのパスを使用して、新しい Project オブジェクトを初期化します。
## ステップ 3: タスクを取得し、分割された部分を反復処理する
```csharp
var task = project.RootTask.Children.GetById(1);
//分割された部分を反復処理する
Console.WriteLine("Iterate over split parts");
Console.WriteLine("Split parts count:" + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("Start: " + splitPart.Start);
    Console.WriteLine("Finish: " + splitPart.Finish);
}
```
プロジェクトからタスクを取得し、その分割部分を反復処理して、開始日と終了日を出力します。
## ステップ 4: インデックスによる分割パーツの取得
```csharp
//インデックスでパーツを取得する
var split = task.SplitParts[0];
Console.WriteLine("Split start: " + split.Start);
```
インデックスによって特定の分割部分を取得し、その開始日を出力します。

## 結論
MS Project ファイル内の分割パーツを管理すると、プロジェクト管理の効率が大幅に向上します。 Aspose.Tasks for .NET は、分割タスクをシームレスに処理する直感的な API を提供することで、このプロセスを簡素化します。
## よくある質問
### Q: 実行時にタスクを動的に分割できますか?
A: はい、Aspose.Tasks for .NET を使用してプログラムでタスクを分割できます。
### Q: Aspose.Tasks は MS Project ファイルのすべてのバージョンをサポートしていますか?
A: Aspose.Tasks は、さまざまなバージョンの MS Project ファイルをサポートし、さまざまなプラットフォーム間での互換性を確保します。
### Q: テスト目的で利用できる試用版はありますか?
 A: はい、以下から無料試用版を入手できます。[ここ](https://releases.aspose.com/)評価用に。
### Q: プロジェクトの一時ライセンスを取得するにはどうすればよいですか?
 A: 一時ライセンスは以下から取得できます。[ここ](https://purchase.aspose.com/temporary-license/)短期間の使用に。
### Q: Aspose.Tasks に関するヘルプやサポートはどこに問い合わせればよいですか?
 A: Aspose.Tasks フォーラムにアクセスしてください。[ここ](https://forum.aspose.com/c/tasks/15)コミュニティまたは Aspose サポート チームに支援を求めます。