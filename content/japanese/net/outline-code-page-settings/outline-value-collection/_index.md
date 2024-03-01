---
title: Aspose.Tasks を使用して MS プロジェクトのアウトライン値を管理する
linktitle: Aspose.Tasks のアウトライン値のコレクション
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して Microsoft Project ファイルのアウトライン値を管理する方法を学習します。コード例を含むステップバイステップのチュートリアル。
type: docs
weight: 17
url: /ja/net/outline-code-page-settings/outline-value-collection/
---
## 導入
Aspose.Tasks for .NET は、Microsoft Project ファイルと対話するための包括的な機能セットを提供します。そのような機能の 1 つは、プロジェクト内のアウトライン値を管理する機能です。このチュートリアルでは、Aspose.Tasks for .NET を使用してアウトライン値を収集および操作する方法を検討します。
## 前提条件
始める前に、以下のものがあることを確認してください。
1.  Aspose.Tasks for .NET: ライブラリは次からダウンロードできます。[ここ](https://releases.aspose.com/tasks/net/).
2. 開発環境: Visual Studio などの適切な IDE がインストールされていることを確認してください。
3. C# の基礎知識: C# プログラミング言語に精通していると役立ちます。
## 名前空間のインポート
C# コード ファイルで、Aspose.Tasks クラスとメソッドにアクセスするために必要な名前空間をインポートします。
```csharp
using Aspose.Tasks;
using System;

```
提供された例を複数のステップに分けてみましょう。
## ステップ 1: プロジェクト ファイルをロードする
まず、初期化します`Project`既存の Microsoft Project ファイルをロードしてオブジェクトを作成します。
```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineValues2010.mpp");
```
## ステップ 2: 既存のアウトライン値をクリアする
次に、既存のアウトライン値をプロジェクトからクリアします。
```csharp
foreach (var outlineCode in project.OutlineCodes)
{
    if (outlineCode.Values.Count <= 0)
    {
        continue;
    }
    if (!outlineCode.Values.IsReadOnly)
    {
        outlineCode.Values.Clear();
    }
}
```
## ステップ 3: 新しいアウトライン コードを定義する
ここで、説明と値を含む新しいアウトライン コードを定義します。
```csharp
var codeDefinition = new OutlineCodeDefinition
{
    Alias = "New task outline code1",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode1).ToString(),
    FieldName = "Outline Code1"
};
var value = new OutlineValue { Description = "Value description", ValueId = 1, Value = "123456", Type = OutlineValueType.Number };
codeDefinition.Values.Add(value);
project.OutlineCodes.Add(codeDefinition);
```
## ステップ 4: アウトライン値を更新する
アウトライン コードの値を更新します。
```csharp
codeDefinition.Values[0].Value = "654321";
```
## ステップ 5: アウトライン値を反復処理する
アウトライン値を反復処理し、その詳細を出力します。
```csharp
foreach (var definitionValue in codeDefinition.Values)
{
    Console.WriteLine("Value: " + definitionValue.Value);
    Console.WriteLine("Value Id: " + definitionValue.ValueId);
    Console.WriteLine("Value Guid: " + definitionValue.ValueGuid);
    Console.WriteLine();
}
```
## ステップ 6: アウトライン値を操作する
必要に応じて、アウトライン値の削除、挿入、コピーなどの操作を実行します。
```csharp
if (codeDefinition.Values.Contains(value))
{
    codeDefinition.Values.Remove(value);
}
codeDefinition.Values.Insert(0, value);
Console.WriteLine("Index of inserted value: " + codeDefinition.Values.IndexOf(value));
codeDefinition.Values.RemoveAt(codeDefinition.Values.Count - 1);
var codeDefinition2 = new OutlineCodeDefinition
{
    Alias = "New outline code 2",
    FieldId = ((int)ExtendedAttributeTask.OutlineCode2).ToString(),
    FieldName = "Outline Code2"
};
var outlineValues = new OutlineValue[codeDefinition.Values.Count];
codeDefinition.Values.CopyTo(outlineValues, 0);
foreach (var outlineValue in outlineValues)
{
    codeDefinition2.Values.Add(outlineValue);
}
```
## 結論
このチュートリアルでは、Aspose.Tasks for .NET を使用して Microsoft Project ファイル内のアウトライン値を操作する方法を学びました。提供された手順に従うことで、プロジェクト内のアウトライン値を効率的に管理でき、より優れた制御と柔軟性が可能になります。
## よくある質問
### Q: 複数のアウトライン コードを同時に操作できますか?
A: はい、Aspose.Tasks を使用して、プロジェクト内で複数のアウトライン コードを定義および操作できます。
### Q: Aspose.Tasks は、Microsoft Project ファイルのさまざまなバージョンと互換性がありますか?
A: はい、Aspose.Tasks は、MPP 形式や XML 形式など、さまざまなバージョンの Microsoft Project ファイルをサポートしています。
### Q: アウトライン値の操作中にエラーを処理するにはどうすればよいですか?
A: try-catch ブロックなどのエラー処理メカニズムを実装して、例外を適切に管理できます。
### Q: プロジェクト内のアウトライン値の外観をカスタマイズできますか?
A: はい、Aspose.Tasks は、要件に応じてアウトライン値の外観と動作をカスタマイズするための広範な API を提供します。
### Q: Aspose.Tasks の追加リソースとサポートはどこで入手できますか?
 A: にアクセスできます。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)コミュニティのサポートを求めて、[ドキュメンテーション](https://reference.aspose.com/tasks/net/) API と機能の詳細については、こちらをご覧ください。