---
title: Aspose.Tasks でのタスクの管理
linktitle: Aspose.Tasks でのタスクの管理
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用したタスク管理に関する包括的なガイドをご覧ください。分割パーツの追加、表示、移動、プロパティの取得/設定などを学びます。
type: docs
weight: 15
url: /ja/net/task-table-management/managing-tasks/
---
## 導入
プロジェクト内のタスクを効率的に管理したいと考えている .NET 開発者には、Aspose.Tasks for .NET が堅牢なソリューションを提供します。このチュートリアルでは、Aspose.Tasks を使用したタスク管理のさまざまな側面について説明し、段階的な手順とコード例を示します。タスクの追加、分割パーツの表示、同じ親の下でのタスクの移動、タスク プロパティの取得/設定、タスク割り当ての反復、タスク ベースラインの読み取り、またはタスクの削除を行う場合でも、このガイドではすべてをカバーできます。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
1.  Aspose.Tasks for .NET ライブラリ: Aspose.Tasks for .NET ライブラリがインストールされていることを確認します。ダウンロードできます[ここ](https://releases.aspose.com/tasks/net/).
2. ドキュメント ディレクトリ: プロジェクト ドキュメントを保存するディレクトリを設定します。
## 名前空間のインポート
.NET プロジェクトに、Aspose.Tasks を操作するために必要な名前空間を含めます。
```csharp

    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    using System.Linq;
    
    using Aspose.Tasks.Saving;
    using Aspose.Tasks.Util;
```
## 1. プロジェクトへのタスクの追加
```csharp
//新しいプロジェクトを作成する
var project = new Project();
//タスクを追加する
var task = project.RootTask.Children.Add("Task1");
task.Set(Tsk.Start, new DateTime(2012, 8, 23, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(24, TimeUnitType.Hour));
task.Set(Tsk.ActualStart, new DateTime(2012, 8, 23, 8, 0, 0));
//プロジェクトを保存する
project.Save(DataDir + "CreateNewTask_out.xml", SaveFileFormat.Xml);
```
## 2. タスクの分割部分を表示する
```csharp
//分割タスクを含むプロジェクトをロードする
var project = new Project(DataDir + "ViewSplitTasks.mpp");
//タスクにアクセスする
var task = project.RootTask.Children.GetById(4);
//分割部分を表示する
var collection = task.SplitParts;
foreach (var splitPart in collection)
{
    Console.WriteLine("Start: " + splitPart.Start + "\nFinish: " + splitPart.Finish + "\n");
}
```
## 3. 同じ親の下でタスクを移動する
```csharp
try
{
    //プロジェクトをロードする
    var project = new Project(DataDir + "MoveTask.mpp");
    //ID 5 のタスクを ID 3 のタスクの前に移動します
    var task = project.RootTask.Children.GetById(5);
    task.MoveToSibling(3);
    //変更したプロジェクトを保存する
    project.Save(DataDir + "MoveTaskUnderSameParent_out.mpp", SaveFileFormat.Mpp);
}
catch (NotSupportedException ex)
{
    Console.WriteLine(ex.Message + "\nPlease apply a valid Aspose.Tasks License.");
}
```
## 4. タスクのプロパティの取得/設定
```csharp
//新しいプロジェクトを作成する
var project = new Project();
//タスクを追加してプロパティを設定する
var task = project.RootTask.Children.Add();
task.Set(Tsk.Name, "Task1");
task.Set(Tsk.Start, new DateTime(2020, 3, 31, 8, 0, 0));
task.Set(Tsk.Finish, new DateTime(2020, 3, 31, 17, 0, 0));
//タスクのプロパティを収集して表示する
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var tsk in collector.Tasks)
{
    Console.WriteLine("Task Id: {0}", tsk.Get(Tsk.Id));
    Console.WriteLine("Task Uid: {0}", tsk.Get(Tsk.Uid));
    Console.WriteLine("Task Name: {0}", tsk.Get(Tsk.Name));
    Console.WriteLine("Task Start: {0}", tsk.Get(Tsk.Start));
    Console.WriteLine("Task Finish: {0}", tsk.Get(Tsk.Finish));
}
```
## 5. タスクの割り当てを反復処理する
```csharp
//割り当てのあるプロジェクトをロードする
var project = new Project(DataDir + "BudgetWorkAndCost.mpp");
//タスクの割り当てを収集して表示する
var collector = new ChildTasksCollector();
TaskUtils.Apply(project.RootTask, collector, 0);
foreach (var task in collector.Tasks)
{
    foreach (var assignment in task.Assignments)
    {
        Console.WriteLine(assignment.ToString());
    }
}
```
## 6. タスクのベースラインの読み取り
```csharp
//新しいプロジェクトを作成する
var project = new Project();
//タスクを追加してベースラインを設定する
var task = project.RootTask.Children.Add("Task");
project.SetBaseline(BaselineType.Baseline);
//タスクのベースライン期間を表示する
foreach (var baseline in task.Baselines)
{
    Console.WriteLine("Baseline duration is 1 day: {0}", baseline.Duration.ToString().Equals("1 day"));
    Console.WriteLine("BaselineStart is same as Task Start: {0}", baseline.Start.Equals(task.Get(Tsk.Start)));
    Console.WriteLine("BaselineFinish is same as Task Finish: {0}", baseline.Finish.Equals(task.Get(Tsk.Finish)));
}
```
## 7. タスクの削除
```csharp
//新しいプロジェクトを作成する
var project = new Project();
//タスクを追加する
var task = project.RootTask.Children.Add("Task");
//削除前後のタスク数を表示
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
//タスクを削除する
task.Delete();
Console.WriteLine("Number of tasks: " + project.RootTask.Children.Count);
```
## 結論
Aspose.Tasks for .NET でのタスクの管理は、提供されている例を使用したシームレスなプロセスです。経験豊富な開発者であっても、初心者であっても、これらのテクニックを取り入れることでプロジェクト管理能力が強化されます。
## よくある質問
### Q: Aspose.Tasks はすべての .NET フレームワークと互換性がありますか?
A: はい、Aspose.Tasks はさまざまな .NET フレームワークをサポートしており、開発環境との互換性を確保しています。
### Q: Aspose.Tasks の一時ライセンスを取得するにはどうすればよいですか?
 A: 30 日間の一時ライセンスは、次のサイトから取得できます。[ここ](https://purchase.aspose.com/temporary-license/).
### Q: Aspose.Tasks で分割タスクを使用する場合、制限はありますか?
 A: タスクの分割は強力な機能であり、詳細なドキュメントが見つかります。[ここ](https://reference.aspose.com/tasks/net/).
### Q: 例に示されているもの以外にタスクのプロパティをカスタマイズできますか?
A: もちろんです！ Aspose.Tasks は、タスク プロパティの広範なカスタマイズ オプションを提供します。詳細については、ドキュメントを確認してください。
### Q: Aspose.Tasks のサポートを受けるにはどうすればよいですか?
A: にアクセスしてください。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)コミュニティのサポートとディスカッションのために。