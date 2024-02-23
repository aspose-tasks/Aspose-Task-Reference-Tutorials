---
title: Aspose.Tasks を使用して MS プロジェクト ファイルをテンプレートとして保存する
linktitle: Aspose.Tasks のテンプレートの保存オプション
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して Microsoft Project ファイルをテンプレートとして保存する方法を学びます。テンプレート設定をカスタマイズして、プロジェクト管理を効率化します。
type: docs
weight: 18
url: /ja/net/saving-options/save-template-options/
---
## 導入
このチュートリアルでは、Aspose.Tasks for .NET を使用してテンプレートを保存するプロセスについて説明します。テンプレートは、将来の使用に備えてプロジェクトの構造と設定を標準化するのに役立ちます。プロジェクトをテンプレートとして保存し、途中でプロパティを調整する方法を示します。
## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
1.  Aspose.Tasks for .NET ライブラリ: Aspose.Tasks for .NET ライブラリがインストールされていることを確認してください。からダウンロードできます[ここ](https://releases.aspose.com/tasks/net/).
2. C# プログラミングの知識: 提供されたコード スニペットを理解して実装するには、C# プログラミングの基本的な知識が必要です。
3. Microsoft Project ファイル: テンプレートとして保存する Microsoft Project ファイル (MPP 形式) を用意します。

## 名前空間のインポート
```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```
## ステップ 1: プロジェクトをロードする
まず、テンプレートとして保存する Microsoft Project ファイル (.mpp) をロードする必要があります。
```csharp
//ドキュメントディレクトリへのパス。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "EstimatedMilestoneTasks.mpp");
```
## ステップ 2: プロジェクト ファイル情報を取得する
ロードされたプロジェクト ファイルに関する情報 (形式など) を取得します。
```csharp
var projectFileInfo = Project.GetProjectFileInfo(DataDir + "EstimatedMilestoneTasks.mpp");
Console.WriteLine("Project File Format: " + projectFileInfo.ProjectFileFormat);
```
## ステップ 3: テンプレートの保存オプションを構成する
テンプレートの保存オプションを作成し、要件に従ってそのプロパティを構成します。これらのオプションを使用すると、テンプレートから削除するデータをカスタマイズできます。
```csharp
var options = new SaveTemplateOptions
{
	//プロジェクト テンプレートからすべての固定費を削除します
	RemoveFixedCosts = true,
	//プロジェクト テンプレートからすべての実際の値を削除します
	RemoveActualValues = true,
	//プロジェクト テンプレートからリソース料金を削除する
	RemoveResourceRates = true,
	//プロジェクト テンプレートからすべてのベースライン値を削除します
	RemoveBaselineValues = true
};
```
## ステップ 4: プロジェクトをテンプレートとして保存する
指定したオプションを使用して、プロジェクトをテンプレートとして保存します。
```csharp
project.SaveAsTemplate(DataDir + "SaveProjectDataAsTemplate_out.mpt", options);
```
## ステップ 5: テンプレート ファイル情報を取得する
保存されたテンプレート ファイルの形式などの情報を取得します。
```csharp
var templateFileInfo = Project.GetProjectFileInfo(DataDir + "SaveProjectDataAsTemplate_out.mpt");
Console.WriteLine("Project File Format: " + templateFileInfo.ProjectFileFormat);
```
おめでとう！ Aspose.Tasks for .NET を使用してテンプレートを保存し、必要に応じてプロパティをカスタマイズしました。

## 結論
このチュートリアルでは、Aspose.Tasks for .NET を使用して Microsoft Project ファイルをテンプレートとして保存する方法を検討しました。テンプレートは、プロジェクトの構造と設定を標準化し、将来のプロジェクト作成を効率化するのに役立ちます。
## よくある質問
### Q: テンプレートから削除するデータをカスタマイズできますか?
A: はい、テンプレートの保存オプションを設定して、固定費、実際の値、リソース料金、ベースライン値などの特定のデータを削除できます。
### Q: Aspose.Tasks for .NET は Microsoft Project のすべてのバージョンと互換性がありますか?
A: Aspose.Tasks for .NET は、さまざまなバージョンの Microsoft Project との広範な互換性を提供し、シームレスな統合と機能を保証します。
### Q: テンプレートを既存のプロジェクトに適用できますか?
A: はい、テンプレート ファイルをロードし、必要に応じて現在のプロジェクトとマージすることで、テンプレートを既存のプロジェクトに適用できます。
### Q: Aspose.Tasks for .NET はクロスプラットフォーム開発をサポートしていますか?
A: Aspose.Tasks for .NET は主に、Windows プラットフォーム上で実行される .NET Framework アプリケーション用に設計されています。
### Q: Aspose.Tasks for .NET のテクニカル サポートは利用できますか?
 A: はい、Aspose.Tasks コミュニティから技術的な支援や指導を求めることができます。[フォーラム](https://forum.aspose.com/c/tasks/15)または、サポート チームに直接お問い合わせください。