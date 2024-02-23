---
title: Aspose.Tasks の高度な AND 演算
linktitle: Aspose.Tasks の高度な AND 演算
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET で高度な AND 演算を実行し、複数の条件に基づいてプロジェクト タスクを効率的にフィルタリングする方法を学びます。
type: docs
weight: 10
url: /ja/net/advanced-features/advanced-and-operation/
---
## 導入

このチュートリアルでは、タスクとプロジェクトを管理するための強力なツールである Aspose.Tasks for .NET の高度な AND 演算について詳しく説明します。を使用して、複数の条件に基づいてプロジェクト タスクをフィルタリングする方法を検討します。`Util.And`クラス。

## 前提条件

始める前に、以下のものがあることを確認してください。

1. C# プログラミング言語の基本的な知識。
2.  Aspose.Tasks for .NET がインストールされました。そうでない場合は、からダウンロードできます[ここ](https://releases.aspose.com/tasks/net/).
3. Visual Studio などの統合開発環境 (IDE)。

## 名前空間のインポート

まず、必要な名前空間を C# プロジェクトにインポートしましょう。

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

using Aspose.Tasks.Util;

```

## ステップ 1: プロジェクトの初期化とタスクの収集

まず、新しい Aspose.Tasks プロジェクトを初期化し、そのプロジェクト内のすべてのタスクを収集します。

```csharp
//ドキュメント ディレクトリへのパス。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project2.mpp");
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

## ステップ 2: フィルター条件を定義する

次にフィルター条件を定義します。この例では、2 つの条件を作成します。1 つはサマリー タスクをフィルターするための条件、もう 1 つは null 以外のタスクをフィルターするための条件です。

```csharp
var condition1 = new SummaryCondition();
var condition2 = new NotNullCondition();
```

## ステップ 3: 条件を AND 演算で結合する

ここで、次を使用して条件を組み合わせます。`Util.And`複合条件を作成するクラス:

```csharp
var joinedCondition = new And<Task>(condition1, condition2);
```

## ステップ 4: 条件を適用してタスクをフィルターする

収集されたタスクに結合条件を適用し、それに応じてフィルタリングします。

```csharp
List<Task> collection = Filter(coll.Tasks, joinedCondition);
```

## ステップ 5: フィルタリングされたタスクを出力する

最後に、フィルタリングされたタスクを出力します。

```csharp
Console.WriteLine("Filtered tasks: ");
foreach (var task in collection)
{
    Console.WriteLine(" Name: " + task.Get(Tsk.Name));
    //追加の処理はここで行うことができます
}
```

## 結論

このチュートリアルでは、Aspose.Tasks for .NET で高度な AND 操作を実行する方法を学びました。を使用して条件を組み合わせることで、`Util.And`クラスを使用すると、複数の基準に基づいてタスクを効率的にフィルタリングできます。

## よくある質問

### Q1: Aspose.Tasks for .NET とは何ですか?

A: Aspose.Tasks for .NET は、開発者が .NET アプリケーションで Microsoft Project ファイルをプログラム的に操作できるようにする堅牢な API です。

### Q2: Util.And を使用して 3 つ以上の条件を適用できますか?

A: はい、Util.And を使用すると、任意の数の条件を組み合わせて複雑なフィルタリング条件を作成できます。

### Q3: Aspose.Tasks for .NET に利用できる無料トライアルはありますか?

 A: はい、以下から無料トライアルをダウンロードできます。[ここ](https://releases.aspose.com/).

### Q4: Aspose.Tasks for .NET のドキュメントはどこで見つけられますか?

 A: ドキュメントは見つかります。[ここ](https://reference.aspose.com/tasks/net/).

### Q5: Aspose.Tasks for .NET のサポートを受けるにはどうすればよいですか?

 A: Aspose.Tasks コミュニティ フォーラムからサポートを受けることができます。[ここ](https://forum.aspose.com/c/tasks/15).