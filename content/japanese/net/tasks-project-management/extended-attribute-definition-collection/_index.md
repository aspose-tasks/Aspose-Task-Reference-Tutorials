---
title: Aspose.Tasks のマスター拡張属性定義 MS プロジェクト
linktitle: Aspose.Tasks の拡張属性定義のコレクション
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して Microsoft Project で拡張属性定義を管理する方法を学習します。プロジェクト データを簡単にカスタマイズおよび強化します。
type: docs
weight: 14
url: /ja/net/tasks-project-management/extended-attribute-definition-collection/
---
## 導入
このチュートリアルでは、Aspose.Tasks for .NET を使用して Microsoft Project で拡張属性定義を操作する方法を説明します。拡張属性を使用すると、プロジェクト データをカスタマイズおよび拡張する柔軟な方法が提供され、ユーザーはデフォルトで提供される標準フィールド以外のフィールドを追加できます。 Aspose.Tasks を使用すると、これらの拡張属性を簡単に管理して、プロジェクト管理のニーズに合わせて調整できます。
## 前提条件
続行する前に、次の前提条件がインストールされていることを確認してください。
- [。ネットフレームワーク](https://dotnet.microsoft.com/download)
- .NET ライブラリの Aspose.Tasks。からダウンロードできます[ここ](https://releases.aspose.com/tasks/net/).

## 名前空間のインポート
まず、.NET プロジェクトの Aspose.Tasks クラスとメソッドにアクセスするために必要な名前空間をインポートする必要があります。次の手順を実行します：
## ステップ 1: .NET プロジェクトを開く
Visual Studio などの好みの IDE で .NET プロジェクトを開きます。
## ステップ 2: Aspose.Tasks 名前空間を追加する
コード ファイルの先頭に次の行を追加して、Aspose.Tasks 名前空間をインポートします。
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```

ここで、包括的な理解のために、提供されたコード例を複数のステップに分けてみましょう。
## ステップ 1: プロジェクト ファイルをロードする
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadTaskExtendedAttributes.mpp");
```
## ステップ 2: 既存の拡張属性定義をクリアする (オプション)
```csharp
if (!project.ExtendedAttributes.IsReadOnly)
{
    if (project.ExtendedAttributes.Count > 0)
    {
        project.ExtendedAttributes.Clear();
    }
}
```
## ステップ 3: タスクの拡張属性定義を作成および追加する
```csharp
var taskDefinition = ExtendedAttributeDefinition.CreateTaskDefinition(CustomFieldType.Start, ExtendedAttributeTask.Start7, "Start 7");
project.ExtendedAttributes.Add(taskDefinition);
```
## ステップ 4: タスク拡張属性を反復処理する
```csharp
Console.WriteLine("Iterate over extended attributes of " + project.ExtendedAttributes.ParentProject.Get(Prj.Name) + " project: ");
foreach (var attribute in project.ExtendedAttributes)
{
    Console.WriteLine("Attribute Alias: " + attribute.Alias);
    Console.WriteLine("Attribute CfType: " + attribute.CfType);
    Console.WriteLine();
}
```
## ステップ 5: リソースの拡張属性定義を作成および追加する
```csharp
var resourceDefinition = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Cost, ExtendedAttributeResource.Cost5, "My cost");
if (!project.ExtendedAttributes.Contains(resourceDefinition))
{
    project.ExtendedAttributes.Add(resourceDefinition);
}
```
## ステップ 6: リソース拡張属性定義を挿入する
```csharp
var resourceDefinition2 = ExtendedAttributeDefinition.CreateResourceDefinition(CustomFieldType.Number, ExtendedAttributeResource.Cost1, "My Cost 2");
if (project.ExtendedAttributes.IndexOf(resourceDefinition2) < 0)
{
    project.ExtendedAttributes.Insert(0, resourceDefinition2);
}
```
## ステップ 7: インデックスによる拡張属性の削除
```csharp
project.ExtendedAttributes.RemoveAt(0);
```

## 結論
このチュートリアルでは、Aspose.Tasks for .NET を使用して Microsoft Project で拡張属性定義を操作する基本について説明しました。これらの手順に従うことで、プロジェクト管理要件に合わせて拡張属性を効率的に管理およびカスタマイズできます。
## よくある質問
### Q: 既存の拡張属性定義を変更できますか?
A: はい、必要に応じて既存の拡張属性定義を変更したり、新しい拡張属性定義を作成したりできます。
### Q: 拡張属性は Microsoft Project のすべてのバージョンでサポートされていますか?
A: はい、拡張属性は、最新バージョンを含む Microsoft Project のほとんどのバージョンでサポートされています。
### Q: 拡張属性を使用してカスタム フィールドを計算できますか?
A: もちろん、拡張属性を使用して、定義した特定の基準に基づいてカスタム フィールドを計算できます。
### Q: Aspose.Tasks は他の .NET フレームワークと互換性がありますか?
A: Aspose.Tasks はさまざまな .NET フレームワークと互換性があり、柔軟性と統合の容易さを保証します。
### Q: Aspose.Tasks のその他のリソースとサポートはどこで入手できますか?
 A: にアクセスできます。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)サポートが必要な場合やドキュメントを参照する場合[ここ](https://reference.aspose.com/tasks/net/).