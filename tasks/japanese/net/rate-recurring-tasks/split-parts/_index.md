---
title: Aspose.Tasks での MS プロジェクト分割パーツの処理
linktitle: Aspose.Tasks での分割パーツの処理
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して MS Project の分割部分を効率的に処理する方法を学びます。プロジェクト管理ワークフローを強化します。
weight: 18
url: /ja/net/rate-recurring-tasks/split-parts/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks での MS プロジェクト分割パーツの処理


## 導入
MS Project の分割部分の管理は、Aspose.Tasks for .NET を使用する場合のプロジェクト管理の重要な側面となります。このチュートリアルでは、ステップバイステップのガイダンスを使用して分割パーツを効果的に処理する方法を検討します。
## 前提条件
チュートリアルに進む前に、次の前提条件を満たしていることを確認してください。
1.  Aspose.Tasks for .NET のインストール: Aspose.Tasks for .NET を次の場所からダウンロードしてインストールします。[Webサイト](https://releases.aspose.com/tasks/net/).
   
2. C# の基本的な理解: C# プログラミング言語に精通していると役立ちます。

## 名前空間のインポート
C# コードで、必要な名前空間を必ずインポートしてください。
```csharp
    using Aspose.Tasks;
    using System;
    
```

## ステップ 1: プロジェクト インスタンスの作成
```csharp
var project = new Project();
```
の新しいインスタンスを作成します。`Project`クラス。
## ステップ 2: プロジェクトの開始日と終了日の設定
```csharp
project.Set(Prj.StartDate, new DateTime(2000, 3, 15, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 3, 21, 17, 0, 0));
```
プロジェクトの開始日と終了日を設定します。
## ステップ 3: タスクの追加
```csharp
var task = project.RootTask.Children.Add("Task1");
```
新しいタスクをプロジェクトに追加します。
## ステップ 4: タスクのプロパティを設定する
```csharp
task.Set(Tsk.IsManual, false);
task.Set(Tsk.Start, new DateTime(2000, 3, 15, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(3));
```
タスクの手動ステータス、開始日、期間などのプロパティを設定します。
## ステップ 5: リソース割り当ての追加
```csharp
var assignment = project.ResourceAssignments.Add(task, project.Resources.Add("r1"));
```
リソースの割り当てをタスクに追加します。
## ステップ 6: 割り当てプロパティの設定
```csharp
assignment.Set(Asn.Start, new DateTime(2000, 3, 15, 8, 0, 0));
assignment.Set(Asn.Work, task.Get(Tsk.Work));
assignment.Set(Asn.Finish, new DateTime(2000, 3, 19, 17, 0, 0));
```
割り当ての開始日、作業時間、終了日などのプロパティを設定します。
## ステップ 7: タイムスケール データの生成
```csharp
assignment.TimephasedDataFromTaskDuration(project.Get(Prj.Calendar));
```
プロジェクト カレンダーに基づいて、割り当てのタイムスケール データを生成します。
## ステップ 8: タスクを分割する
```csharp
assignment.SplitTask(new DateTime(2000, 3, 16, 8, 0, 0), new DateTime(2000, 3, 17, 17, 0, 0), project.Get(Prj.Calendar));
```
指定された時間枠内でタスクを複数の部分に分割します。
## ステップ 9: 分割パーツの反復処理
```csharp
Console.WriteLine("Number of split parts: " + task.SplitParts.Count);
foreach (var splitPart in task.SplitParts)
{
    Console.WriteLine("  Split Part Start: " + splitPart.Start);
    Console.WriteLine("  Split Part Finish: " + splitPart.Finish);
    Console.WriteLine();
}
```
タスクの分割部分を反復処理し、開始日と終了日を出力します。

## 結論
Aspose.Tasks for .NET で MS Project の分割部分を効果的に処理することは、プロジェクト管理の効率化にとって非常に重要です。このチュートリアルで概説されている手順に従うことで、分割タスクをシームレスに管理し、プロジェクト管理ワークフローを強化できます。
## よくある質問
### Q: Aspose.Tasks for .NET を他の .NET フレームワークと一緒に使用できますか?
A: はい、Aspose.Tasks for .NET は、.NET Core や .NET Standard を含むさまざまな .NET フレームワークと互換性があります。
### Q: Aspose.Tasks for .NET に利用できる無料トライアルはありますか?
 A: はい、以下から無料トライアルを入手できます。[ここ](https://releases.aspose.com/).
### Q: Aspose.Tasks for .NET はリソース管理をサポートしていますか?
A: はい、Aspose.Tasks for .NET を使用すると、プロジェクト リソースを効率的に管理できます。
### Q: Aspose.Tasks for .NET を使用してプロジェクト カレンダーをカスタマイズできますか?
A: もちろん、プロジェクトの要件に応じてプロジェクト カレンダーをカスタマイズできます。
### Q: Aspose.Tasks for .NET のサポートはどこで見つけられますか?
 A: 次のサイトでサポートと支援を見つけることができます。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
