---
title: Aspose.Tasks .NET での段階的な WBS コード構成
linktitle: Aspose.Tasks での WBS コード マスクの構成
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks を使用して、.NET プロジェクトで WBS コード マスクの構成を段階的に確認します。プロジェクト管理機能を簡単に強化します。
type: docs
weight: 14
url: /ja/net/view-wbs-code-configuration/wbs-code-masks/
---
## 導入
Aspose.Tasks for .NET は、開発者が .NET アプリケーションでプロジェクト管理データを効率的に操作できるようにする強力なライブラリです。このチュートリアルでは、Aspose.Tasks を使用してワーク ブレークダウン ストラクチャ (WBS) コード マスクを構成するプロセスについて説明します。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
-  Aspose.Tasks for .NET ライブラリ: からライブラリをダウンロードしてインストールします。[Aspose.Tasks for .NET ドキュメント](https://reference.aspose.com/tasks/net/).
- 開発環境: 動作する .NET 開発環境がセットアップされていることを確認してください。
- ドキュメント ディレクトリ: プロジェクト ファイルを保存するシステム上のディレクトリを選択します。
## 名前空間のインポート
.NET プロジェクトに、Aspose.Tasks を操作するために必要な名前空間を含めます。
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Saving;
```
## ステップ 1: プロジェクト インスタンスを作成する
新しいプロジェクト インスタンスを作成することから始めます。
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## ステップ 2: WBS コード定義を定義する
プロジェクトの WBS コード定義をセットアップします。
```csharp
project.WBSCodeDefinition = new WBSCodeDefinition();
project.WBSCodeDefinition.GenerateWBSCode = true;
project.WBSCodeDefinition.VerifyUniqueness = true;
project.WBSCodeDefinition.CodePrefix = "CRS-";
```
## ステップ 3: WBS コードマスクを追加する
WBS コード マスクを定義し、プロジェクトに追加します。
```csharp
var mask = new WBSCodeMask();
mask.Length = 2;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedNumbers;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
mask = new WBSCodeMask();
mask.Length = 1;
mask.Separator = "-";
mask.Sequence = WBSSequence.OrderedUppercaseLetters;
project.WBSCodeDefinition.CodeMaskCollection.Add(mask);
```
## ステップ 4: タスクの作成
プロジェクトにタスクを追加します。
```csharp
var task = project.RootTask.Children.Add("Task 1");
task.Children.Add("Task 2");
```
## ステップ 5: 再計算
プロジェクトを再計算して、WBS コードが正しく適用されていることを確認します。
```csharp
project.Recalculate();
```
## ステップ 6: WBS マスク情報の表示
WBS マスクに関する情報をコンソールに出力します。
```csharp
Console.WriteLine("Number of WBS masks: " + project.WBSCodeDefinition.CodeMaskCollection.Count);
var i = 0;
foreach (var cm in project.WBSCodeDefinition.CodeMaskCollection)
{
    Console.WriteLine("WBS Mask #{0}: Level->{1}", ++i, cm.Level);
}
```
## ステップ 7: プロジェクトを保存する
追加した WBS コードを含むプロジェクトを保存します。
```csharp
project.Save(DataDir + @"AddWBSCodes_out.xml", SaveFileFormat.Xml);
```
おめでとう！ Aspose.Tasks プロジェクトで WBS コード マスクが正常に構成されました。
## 結論
このチュートリアルでは、Aspose.Tasks for .NET を使用して WBS コード マスクを構成する手順を段階的に説明しました。この強力なライブラリは、開発者に .NET アプリケーション内のプロジェクト管理機能を強化するシームレスな方法を提供します。

## よくある質問
### Aspose.Tasks を無料で使用できますか?
 Aspose.Tasks には無料トライアルがあり、ダウンロードできます。[ここ](https://releases.aspose.com/).
### 追加のサポートはどこで見つけられますか?
訪問[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)コミュニティサポートのために。
### 仮免許はどうやって取得できますか?
仮免許が取得できる[ここ](https://purchase.aspose.com/temporary-license/).
### 詳細なドキュメントはありますか?
はい、包括的なドキュメントが利用可能です[ここ](https://reference.aspose.com/tasks/net/).
### Aspose.Tasks はどこで購入できますか?
 Aspose.Task を購入する[ここ](https://purchase.aspose.com/buy).