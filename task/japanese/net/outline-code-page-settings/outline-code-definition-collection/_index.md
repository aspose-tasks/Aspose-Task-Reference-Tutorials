---
title: Aspose.Tasks .NET のアウトライン コード定義のコレクション
linktitle: Aspose.Tasks のアウトライン コード定義のコレクション
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して Microsoft Project ドキュメント内のアウトライン コード定義を操作する方法を学習します。プロジェクト データを簡単に分類できます。
type: docs
weight: 13
url: /ja/net/outline-code-page-settings/outline-code-definition-collection/
---
## 導入
Aspose.Tasks は、Microsoft Project ドキュメントを簡単かつ効率的に操作できるように設計された強力な .NET ライブラリです。その重要な機能の 1 つは、アウトライン コード定義を操作できることで、ユーザーはプロジェクト データを効果的に整理および分類できるようになります。このチュートリアルでは、Aspose.Tasks for .NET を使用してアウトライン コード定義を操作する方法を検討します。
## 前提条件
チュートリアルに入る前に、次のものが揃っていることを確認してください。
1. C# の基本的な理解: C# プログラミング言語に精通していると役立ちます。
2. Visual Studio: Visual Studio またはその他の推奨される C# 開発環境をインストールします。
3.  Aspose.Tasks for .NET:Aspose.Tasks for .NET ライブラリをダウンロードしてインストールします。[ここ](https://releases.aspose.com/tasks/net/).

## 名前空間のインポート
まず、必要な名前空間をインポートしてください。
```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## ステップ 1: Microsoft Project ドキュメントをロードする
まず、Microsoft Project ドキュメントをロードして、アウトライン コード定義の操作を開始します。
```csharp
//ドキュメントディレクトリへのパス。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes.mpp");
```
## ステップ 2: アウトライン コード定義にアクセスする
次に、プロジェクト内のアウトライン コード定義にアクセスしてみましょう。
```csharp
Console.WriteLine("Count of outline code definitions: " + project.OutlineCodes.Count);
foreach (var outlineCode in project.OutlineCodes)
{
	Console.WriteLine("Field Name: " + outlineCode.FieldName);
	Console.WriteLine("Alias: " + outlineCode.Alias);
	Console.WriteLine();
}
```
## ステップ 3: カスタム アウトライン コード定義を追加する
次のようにカスタム アウトライン コード定義を追加できます。
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
if (!project.OutlineCodes.IsReadOnly)
{
    project.OutlineCodes.Add(outlineCodeDefinition);
}
```
## ステップ 4: アウトライン コード定義を変更する
既存のアウトライン コード定義を簡単に変更します。
```csharp
var index = project.OutlineCodes.IndexOf(outlineCodeDefinition);
project.OutlineCodes[index].Alias = "New Alias";
```
## ステップ 5: アウトライン コード定義を削除する
不要になったアウトライン コード定義を削除します。
```csharp
if (project.OutlineCodes.Contains(outlineCodeDefinition))
{
    project.OutlineCodes.Remove(outlineCodeDefinition);
}
```
## ステップ 6: 変更を保存する
最後に、変更をプロジェクト ドキュメントに保存します。
```csharp
project.Save(DataDir + "ModifiedOutlineCodes.mpp", SaveFileFormat.MPP);
```

## 結論
結論として、Aspose.Tasks for .NET は、Microsoft Project ドキュメントのアウトライン コード定義を管理するための包括的な機能を提供します。このチュートリアルで概説されている手順に従うことで、アウトライン コード定義を効率的に操作して、プロジェクト データを効果的に整理および分類できます。
## よくある質問
### Q: 複数のアウトライン コード定義を 1 つのプロジェクトに追加できますか?
 A: はい、要件に基づいて複数のアウトライン コード定義をプロジェクトに追加できます。単純に使用してください`Add`含める各定義のメソッド。
### Q: すべてのアウトライン コード定義をプロジェクトから一度に削除することはできますか?
 A: はい、次のコマンドを使用してプロジェクトからすべてのアウトライン コード定義をクリアできます。`Clear`方法。
### Q: 読み取り専用のアウトライン コード定義を変更しようとするとどうなりますか?
A: アウトライン コード定義が読み取り専用の場合、それを直接変更することはできません。変更を試みる前に、読み取り専用ステータスを確認する必要があります。
### Q: プロジェクトに追加できるアウトライン コード定義の数に制限はありますか?
A: Aspose.Tasks for .NET では、プロジェクトに追加できるアウトライン コード定義の数に特別な制限はありません。ただし、多数の定義を操作する場合は、パフォーマンスへの影響を考慮してください。
### Q: アウトライン コード定義を使用して、カスタム基準に基づいてタスクをグループ化できますか?
A: はい、アウトライン コード定義を使用すると、カスタム基準に基づいてタスクを分類できるため、プロジェクト データを柔軟に編成できます。## 完全なソース コード