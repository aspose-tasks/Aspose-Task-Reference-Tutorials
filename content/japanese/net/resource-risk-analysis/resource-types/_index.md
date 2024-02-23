---
title: Aspose.Tasks のリソースの種類
linktitle: Aspose.Tasks のリソースの種類
second_title: Aspose.Tasks .NET API
description: ステップバイステップのチュートリアルを通じて、Aspose.Tasks for .NET で作業リソース、材料リソース、コスト リソースなどのさまざまな種類のリソースを操作する方法を学びます。
type: docs
weight: 14
url: /ja/net/resource-risk-analysis/resource-types/
---
## 導入
Aspose.Tasks for .NET は、開発者がプログラムで Microsoft Project ファイルを操作できるようにする強力なライブラリです。タスク、リソース、スケジュールのいずれを管理している場合でも、Aspose.Tasks は包括的な API セットを提供することでプロセスを簡素化します。このチュートリアルでは、Aspose.Tasks for .NET を使用してプロジェクト内で利用できるさまざまな種類のリソースについて詳しく説明します。
## 前提条件
始める前に、以下のものがあることを確認してください。
1. Visual Studio: .NET 開発用の強力な統合開発環境 (IDE) である Visual Studio をインストールします。
2.  Aspose.Tasks for .NET:Aspose.Tasks for .NET ライブラリをダウンロードしてインストールします。[ここ](https://releases.aspose.com/tasks/net/).
3. C# の基本知識: .NET 開発に使用されるプログラミング言語である C# について理解します。

## 名前空間のインポート
まず、Aspose.Tasks for .NET の機能にアクセスするために必要な名前空間をインポートしましょう。
```csharp
    
```

## ステップ 1: 新しいプロジェクト インスタンスを作成する
```csharp
var project = new Project();
```
この行は、すべてのプロジェクト関連のデータと操作のコンテナーとして機能する新しい Project オブジェクトを初期化します。
## ステップ 2: 作業リソースを追加する
```csharp
var work = project.Resources.Add("Work resource");
work.Set(Rsc.Type, ResourceType.Work);
```
ここでは、「Work resource」という名前の新しい作業リソースを作成し、そのタイプを ResourceType.Work として指定します。
## ステップ 3: マテリアル リソースを追加する
```csharp
var material = project.Resources.Add("Material resource");
material.Set(Rsc.Type, ResourceType.Material);
material.Set(Rsc.MaterialLabel, "kg");
```
このステップでは、「マテリアル リソース」という名前のマテリアル リソースを追加し、そのタイプを ResourceType.material に設定します。また、材質表示には測定単位を「kg」と表記しております。
## ステップ 4: コストリソースを追加する
```csharp
var cost = project.Resources.Add("Cost resource");
cost.Set(Rsc.Type, ResourceType.Cost);
cost.Set(Rsc.Cost, 59.99m);
```
最後に、「Cost resource」という名前のコスト リソースを追加し、そのタイプを ResourceType.Cost として設定します。さらに、このリソースに関連付けられた金銭的価値を表すコスト値を 59.99 に設定します。

## 結論
このチュートリアルでは、Aspose.Tasks for .NET で作業リソース、材料リソース、コスト リソースなど、さまざまな種類のリソースを操作する方法を検討しました。ステップバイステップのガイドに従うことで、プロジェクト内のリソースをプログラムで効果的に管理できます。
## よくある質問
### Q: Aspose.Tasks for .NET を他のプロジェクト管理ソフトウェア形式で使用できますか?
A: はい、Aspose.Tasks は Microsoft Project (MPP)、Primavera P6 などを含むさまざまな形式をサポートしています。
### Q: Aspose.Tasks for .NET に利用できる無料トライアルはありますか?
 A: はい、無料トライアルにアクセスできます。[ここ](https://releases.aspose.com/).
### Q: Aspose.Tasks for .NET のテクニカル サポートを受けるにはどうすればよいですか?
 A: Aspose.Tasks フォーラムにアクセスしてください。[ここ](https://forum.aspose.com/c/tasks/15)技術的なサポートのため。
### Q: Aspose.Tasks for .NET の一時ライセンスを購入できますか?
 A: はい、一時ライセンスを購入できます。[ここ](https://purchase.aspose.com/temporary-license/).
### Q: Aspose.Tasks for .NET には参照用のドキュメントが提供されていますか?
 A: はい、ドキュメントは見つかります。[ここ](https://reference.aspose.com/tasks/net/).