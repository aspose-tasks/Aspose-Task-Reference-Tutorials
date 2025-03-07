---
title: Aspose.Tasks での割り当ての操作
linktitle: Aspose.Tasks での割り当ての操作
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks を使用して .NET でプロジェクトの割り当てを管理する方法を学びます。リソースのスケジュール設定についてさまざまな輪郭を検討します。
weight: 13
url: /ja/net/advanced-features/working-with-assignment/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks での割り当ての操作

## 導入

このチュートリアルでは、Aspose.Tasks for .NET で割り当てを操作する方法を説明します。割り当ては、リソースをタスクに割り当て、スケジュール設定や進捗状況の追跡に役立つため、プロジェクト管理において非常に重要です。 Aspose.Tasks を使用して、さまざまな輪郭を持つリソース割り当てのタイムスケール データを生成することに焦点を当てます。

## 前提条件

始める前に、次の前提条件を満たしていることを確認してください。

1.  Aspose.Tasks for .NET のインストール: Aspose.Tasks for .NET ライブラリを次の場所からダウンロードしてインストールします。[ダウンロードリンク](https://releases.aspose.com/tasks/net/).
2. C# と .NET Framework の基本的な理解: C# プログラミング言語と .NET Framework の概念を理解しておく必要があります。

## 名前空間のインポート

必要な名前空間を C# プロジェクトにインポートしてください。

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
using Aspose.Tasks.Util;

```

## ステップ 1: プロジェクトとタスクを作成する

まず、新しいプロジェクトを作成し、それにタスクを追加しましょう。タスクの開始日、期間、終了日を設定します。

```csharp
var project = new Project();
project.Set(Prj.StartDate, new DateTime(2000, 1, 3, 8, 0, 0));
project.Set(Prj.FinishDate, new DateTime(2000, 1, 7, 17, 0, 0));

var task = project.RootTask.Children.Add("Task");
task.Set(Tsk.Start, new DateTime(2000, 1, 3, 8, 0, 0));
task.Set(Tsk.Duration, project.GetDuration(8, TimeUnitType.Hour));
task.Set(Tsk.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## ステップ 2: リソースを追加してタスクに割り当てる

次に、リソースをプロジェクトに追加し、以前に作成したタスクに割り当てます。

```csharp
var resource = project.Resources.Add("Resource");

var resourceAssignment = project.ResourceAssignments.Add(task, resource);
resourceAssignment.Set(Asn.Start, new DateTime(2000, 1, 3, 8, 0, 0));
resourceAssignment.Set(Asn.Work, project.GetWork(8));
resourceAssignment.Set(Asn.Finish, new DateTime(2000, 1, 3, 17, 0, 0));
```

## ステップ 3: 異なる等高線を含むタイムフェーズ データを生成する

ここで、リソース割り当てのさまざまな等高線を含むタイムスケール データを生成してみましょう。

```csharp
Console.WriteLine("Flat contour");

var collection = task.GetTimephasedData(project.Get(Prj.StartDate), project.Get(Prj.FinishDate));
foreach (var td in collection)
{
	Console.WriteLine(td.Start.ToShortDateString() + " " + td.Value);
}
```

## ステップ 4: 輪郭を変更してデータを生成する

等高線タイプを変更し、それに応じてタイムフェーズ データを生成できます。ここではいくつかの例を示します。

```csharp
//輪郭を変更する
resourceAssignment.Set(Asn.WorkContour, WorkContourType.Turtle);
//タイムスケールデータを生成して印刷する
//他の輪郭タイプに対してこの手順を繰り返します
```

## 結論

このチュートリアルでは、Aspose.Tasks for .NET で割り当てを操作する方法を学習しました。私たちは、さまざまな等高線を使用してリソース割り当てのタイムスケール データを生成することを検討しました。この知識は、プロジェクト管理シナリオで非常に役立ちます。

## よくある質問

### Q1: .NET アプリケーションでタスクをスケジュールするために Aspose.Tasks を使用できますか?

A1: はい、Aspose.Tasks は、.NET アプリケーションでのタスクのスケジュール設定と管理のための包括的な API を提供します。

### Q2: Aspose.Tasks に利用できる無料トライアルはありますか?

 A2: はい、以下から無料トライアルを利用できます。[ここ](https://releases.aspose.com/).

### Q3: Aspose.Tasks のタスクまたはリソースの数に制限はありますか?

A3: Aspose.Tasks では、プロジェクト内で管理できるタスクやリソースの数に制限はありません。

### Q4: Aspose.Tasks でリソース割り当ての輪郭をカスタマイズできますか?

A4: はい、このチュートリアルで説明したように、プロジェクトの要件に応じて、タートル、ベル、ピークなどのさまざまな輪郭を設定できます。

### Q5: Aspose.Tasks 関連のクエリのサポートはどこで見つけられますか?

A5: サポートは次のサイトで見つけることができます。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)専門家やコミュニティのメンバーが積極的に議論を交わす場です。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
