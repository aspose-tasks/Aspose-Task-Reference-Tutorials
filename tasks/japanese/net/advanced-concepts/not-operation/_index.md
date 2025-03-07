---
title: Aspose.Tasks での NOT 操作の使用
linktitle: Aspose.Tasks での NOT 操作の使用
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET で NOT 操作を使用してタスクを効果的にフィルタリングする方法を学びます。今すぐプロジェクト管理機能を強化してください。
weight: 20
url: /ja/net/advanced-concepts/not-operation/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks での NOT 操作の使用

## 導入

このチュートリアルでは、Aspose.Tasks for .NET で NOT 操作を利用する方法を検討します。 NOT 演算を使用すると、フィルター条件を逆にでき、指定された基準を満たさない要素を選択できるようになります。

## 前提条件

始める前に、以下のものがあることを確認してください。

1. Visual Studio: コード例に従うには、Visual Studio が動作するインストールが必要です。
2.  Aspose.Tasks for .NET: Aspose.Tasks for .NET ライブラリを次の場所からダウンロードしてインストールします。[Webサイト](https://releases.aspose.com/tasks/net/).
3. C# の基本的な理解: C# プログラミング言語に精通していると、コード例を理解するのに役立ちます。

## 名前空間のインポート

まず、コードに必要な名前空間をインポートしましょう。

```csharp
using Aspose.Tasks;
using Aspose.Tasks.Util;
using Aspose.Tasks.Saving;
using Aspose.Tasks.Visualization;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
```

## ステップ 1: プロジェクトとタスクを設定する

```csharp
var project = new Project(DataDir + "Project2.mpp");
```

まず、「Project2.mpp」という名前のプロジェクト ファイルをロードします。`Project` Aspose.Tasks によって提供されるクラス。指定したディレクトリにプロジェクト ファイルが存在することを確認してください。

## ステップ 2: プロジェクト タスクを収集する

```csharp
var coll = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, coll, 0);
```

ここでは、`ChildTasksCollector`プロジェクト内のすべてのタスクを収集するオブジェクト。次に使用します`TaskUtils.Apply`メソッドを使用して、プロジェクトのタスク階層を横断し、すべての子タスクを収集します。

## ステップ 3: フィルター条件を定義する

```csharp
var filter = new NullCondition();
```

という名前のカスタム クラスを使用してフィルター条件を定義します。`NullCondition`。この条件では、NULL 値を持つタスクが選択されます。

## ステップ 4: NOT 操作を適用する

```csharp
var condition = new Not<Task>(filter);
```

次を使用してフィルター条件に NOT 演算を適用します。`Not<T>`Aspose.Tasks によって提供されるクラス。これにより、フィルター条件が逆になり、null 値を持たないタスクが選択されます。

## ステップ 5: タスクをフィルタリングする

```csharp
List<Task> collection = Filter(coll.Tasks, condition);
```

カスタム フィルターを使用して、適用された条件に基づいて収集されたタスクをフィルターします。`Filter`方法。このメソッドは、入力パラメーターとしてタスクの列挙可能なコレクションとフィルター条件を受け取り、条件を満たすタスクのリストを返します。

## ステップ 6: フィルタリングされたタスクを処理する

```csharp
foreach (var task in collection)
{
    Console.WriteLine("Name: " + task.Get(Tsk.Name));

    //他のプロパティを操作する...
}
```

最後に、フィルタリングされたタスクを繰り返し処理し、必要な操作を実行します。この例では、タスクの名前をコンソールに出力するだけです。

## 結論

このチュートリアルでは、Aspose.Tasks for .NET で NOT 操作を操作する方法を学びました。フィルター条件を逆にすることで、指定された基準を満たさない要素を選択して、プロジェクト内でのタスク操作の柔軟性を高めることができます。

## よくある質問

### Q1: Aspose.Tasks を他の .NET フレームワークで使用できますか?

A: はい、Aspose.Tasks は、.NET Core、.NET Standard、.NET Framework などのさまざまな .NET フレームワークをサポートしています。

### Q2: Aspose.Tasks に利用できる無料トライアルはありますか?

 A: はい、次のサイトから無料トライアルをダウンロードできます。[Webサイト](https://releases.aspose.com/).

### Q3: Aspose.Tasks のサポートを受けるにはどうすればよいですか?

 A: にアクセスできます。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)サポートに関する問い合わせや技術サポートについては、こちらをご覧ください。

### Q4: Aspose.Tasks の一時ライセンスを購入できますか?

 A: はい、次のサイトから一時ライセンスを購入できます。[購入ページ](https://purchase.aspose.com/temporary-license/).

### Q5: Aspose.Tasks の包括的なドキュメントはどこで見つけられますか?

 A: 完全なドキュメントには、[Aspose.Tasks ドキュメント ページ](https://reference.aspose.com/tasks/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
