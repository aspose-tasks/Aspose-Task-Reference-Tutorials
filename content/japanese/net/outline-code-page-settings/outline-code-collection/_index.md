---
title: Aspose.Tasks のアウトライン コードのコレクション MS プロジェクト
linktitle: Aspose.Tasks のアウトライン コードのコレクション
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して Microsoft Project アウトライン コードを収集する方法を学びます。この包括的なチュートリアルでは、段階的な手順を説明します。
type: docs
weight: 11
url: /ja/net/outline-code-page-settings/outline-code-collection/
---
## 導入
このチュートリアルでは、Aspose.Tasks for .NET を使用して Microsoft Project のアウトライン コードを収集する方法を説明します。明確さと理解を確実にするために、プロセスを段階的な手順に分けて説明します。
## 前提条件
始める前に、以下のものがあることを確認してください。
1. Visual Studio: システムに Visual Studio をインストールします。
2.  Aspose.Tasks for .NET:Aspose.Tasks for .NET をダウンロードしてインストールします。[ここ](https://releases.aspose.com/tasks/net/).
3. C# プログラミングの基本的な理解: C# に精通していると役立ちます。

## 名前空間のインポート
まず、C# プロジェクトの Aspose.Tasks 機能にアクセスするために必要な名前空間をインポートします。
```csharp
    using Aspose.Tasks;
    using System;
    
    using Aspose.Tasks.Util;
```
## ステップ 1: プロジェクト ファイルをロードする
まず、次のコマンドを使用して Microsoft Project ファイルをロードします。`Project`クラス。
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "OutlineCodes2003.mpp");
```
## ステップ 2: アウトライン コードを収集する
プロジェクト タスクからアウトライン コードを収集するコレクターを作成します。
```csharp
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
```
## ステップ 3: タスクとアウトライン コードを反復処理する
収集したタスクとアウトライン コードを繰り返し処理し、詳細を出力します。
```csharp
for (var i = 0; i < collector.Tasks.Count; i++)
{
    var current = collector.Tasks[i];
    if (current.Get(Tsk.Id) == 0)
    {
        continue;
    }
    Console.WriteLine("Print outline codes for the " + current.Get(Tsk.Name) + " task.");
    Console.WriteLine("Count of outline codes: " + current.OutlineCodes.Count);
    foreach (var outlineCode in current.OutlineCodes)
    {
        Console.WriteLine("Field Id: " + outlineCode.FieldId);
        Console.WriteLine("Value Id: " + outlineCode.ValueId);
        Console.WriteLine("Value Guid: " + outlineCode.ValueGuid);
        Console.WriteLine();
    }
}
```
## ステップ 4: カスタム アウトライン コード定義を追加する
カスタム アウトライン コード定義をプロジェクトに追加します。
```csharp
var outlineCodeDefinition = new OutlineCodeDefinition { FieldId = ((int)ExtendedAttributeTask.OutlineCode3).ToString("D"), Alias = "My Outline Code" };
project.OutlineCodes.Add(outlineCodeDefinition);
```
## ステップ 5: アウトライン コードを作成して挿入する
アウトライン コードを作成し、タスクに挿入します。
```csharp
var value = new OutlineValue { Type = OutlineValueType.Text, Value = "Val1", Description = "Descr1", ValueId = 1 };
outlineCodeDefinition.Values.Add(value);
var codeOne = new OutlineCode { FieldId = outlineCodeDefinition.FieldId, ValueId = 1, ValueGuid = value.ValueGuid.ToString("D").ToUpperInvariant() };
var task = project.RootTask.Children.GetByUid(2);
task.OutlineCodes.Add(codeOne);
```
## ステップ 6: アウトライン コードを操作する
必要に応じて、アウトライン コードを挿入、削除、クリアなど操作します。
```csharp
//操作例
//、
// 2 を含むコードを正しい位置に挿入します
task.OutlineCodes.Insert(2, code2);
//コードが挿入されたかどうかを確認する
Console.WriteLine("Is outline codes contains the inserted value: " + task.OutlineCodes.Contains(code2));
```

## 結論
このチュートリアルでは、Aspose.Tasks for .NET を使用して Microsoft Project アウトライン コードを収集する方法を学びました。これらの手順に従うことで、プロジェクト内のアウトライン コードを効果的に管理し、組織性と明確性を高めることができます。
## よくある質問
### Q: Aspose.Tasks for .NET を他のプログラミング言語で使用できますか?
A: はい、Aspose.Tasks for .NET は主に .NET プラットフォームをターゲットとしていますが、Aspose.Tasks for Cloud を通じて他のプログラミング言語のサポートも提供します。
### Q: Aspose.Tasks for .NET が処理できるプロジェクト ファイルのサイズに制限はありますか?
A: Aspose.Tasks for .NET は大きなプロジェクト ファイルを効率的に処理できますが、パフォーマンスはファイルの複雑さとサイズによって異なる場合があります。
### Q: Aspose.Tasks for .NET は Microsoft Project の最新バージョンと互換性がありますか?
A: はい、Aspose.Tasks for .NET は、最新バージョンを含むさまざまなバージョンの Microsoft Project をサポートしています。
### Q: Aspose.Tasks for .NET を使用するときに出力形式をカスタマイズできますか?
A: もちろん、Aspose.Tasks for .NET には、要件に応じて出力形式をカスタマイズするための広範なオプションが用意されています。
### Q: Aspose.Tasks for .NET の追加のサポートやリソースはどこで見つけられますか?
 A: にアクセスできます。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15) Aspose.Tasks for .NET に関するサポートや質問については、こちらをご覧ください。