---
title: Aspose.Tasks でのツリー アルゴリズムの使用
linktitle: Aspose.Tasks でのツリー アルゴリズムの使用
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks のツリー アルゴリズムを使用して、.NET プロジェクトのタスク階層を効果的に操作する方法を学びます。
type: docs
weight: 13
url: /ja/net/advanced-concepts/tree-algorithm/
---
## 導入

Aspose.Tasks for .NET は、プロジェクト管理タスク、リソース、スケジュールを操作するための強力な機能を提供します。そのような機能の 1 つがツリー アルゴリズムで、ユーザーはタスク階層を効率的に操作できます。このチュートリアルでは、Aspose.Tasks for .NET のツリー アルゴリズムを利用して、プロジェクト内の共通作業を収集し、作業値を更新する方法を検討します。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

1. Visual Studio: Visual Studio がシステムにインストールされていることを確認してください。
2.  Aspose.Tasks for .NET:Aspose.Tasks for .NET をダウンロードしてインストールします。[ここ](https://releases.aspose.com/tasks/net/).
3. C# の基本的な理解: 例に従うには、C# プログラミング言語に精通している必要があります。

## 名前空間のインポート

C# プロジェクトで、Aspose.Tasks 機能を操作するために必要な名前空間をインポートします。

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Util;

```

ここで、各例を複数のステップに分けてみましょう。

## ステップ 1: プロジェクト ファイルをロードする

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

を使用してプロジェクト ファイルをメモリにロードします。`Project`クラス。

## ステップ 2: タスク階層を定義する

```csharp
var root = project.RootTask.Children.Add("Project Management");
var summary = root.Children.Add("Manage iteration");
var task = summary.Children.Add("Acquire staff");
```

親タスクと子タスクを追加してタスク階層を定義します。

## ステップ 3: タスクのプロパティを設定する

```csharp
task.Set(Tsk.Start, new DateTime(1999, 5, 3, 9, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8 * 14, TimeUnitType.Hour));
task.Set(Tsk.Finish, project.Get(Prj.Calendar).GetFinishDateByStartAndWork(task.Get(Tsk.Start), task.Get(Tsk.Duration)));
```

タスクの開始日、期間、終了日などのプロパティを設定します。

## ステップ 4: リソースを追加する

```csharp
var resource = project.Resources.Add("Project Manager");
resource.Set(Rsc.Type, ResourceType.Work);
project.ResourceAssignments.Add(task, resource);
```

必要に応じてリソースをプロジェクトに追加し、タスクに割り当てます。

## ステップ 5: ツリー アルゴリズムを適用する

```csharp
var acc = new WorkAccumulator();
TaskUtils.Apply(summary, acc, 0);
```

を初期化します`WorkAccumulator`クラスを作成し、ツリー アルゴリズムを適用して共通の作業を収集します。

## ステップ 6: タスク作業を更新する

```csharp
var summaryWork = acc.Work.ToDouble();
summary.Set(Tsk.Work, project.GetWork(summaryWork));
summary.Set(Tsk.RemainingWork, project.GetWork(summaryWork));
```

収集した情報に基づいてタスクの作業値を更新します。

## 結論

このチュートリアルでは、Aspose.Tasks for .NET のツリー アルゴリズムを利用してタスク階層を効果的に操作する方法を学びました。ステップバイステップのガイドに従うことで、プロジェクト内のタスクとリソースを効率的に管理できます。

## よくある質問

### Q1: Aspose.Tasks for .NET とは何ですか?

A1: Aspose.Tasks for .NET は、開発者が C# を使用して Microsoft Project ファイルをプログラム的に操作できるようにする強力な API です。

### Q2: Aspose.Tasks for .NET の無料トライアルをダウンロードできますか?

 A2: はい、Aspose.Tasks for .NET の無料トライアルを次のサイトからダウンロードできます。[ここ](https://releases.aspose.com/).

### Q3: Aspose.Tasks for .NET のドキュメントはどこで見つけられますか?

 A3: Aspose.Tasks for .NET のドキュメントを見つけることができます。[ここ](https://reference.aspose.com/tasks/net/).

### Q4: Aspose.Tasks for .NET のサポートを受けるにはどうすればよいですか?

 A4: Aspose.Tasks for .NET に関連するサポートについては、次のサイトにアクセスしてください。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15).

### Q5: テスト目的で利用できる一時ライセンスはありますか?

 A5: はい、テスト目的の一時ライセンスを次のサイトから取得できます。[ここ](https://purchase.aspose.com/temporary-license/).