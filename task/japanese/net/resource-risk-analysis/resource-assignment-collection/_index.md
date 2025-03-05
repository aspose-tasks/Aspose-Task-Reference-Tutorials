---
title: Aspose.Tasks のリソース割り当てのコレクション
linktitle: Aspose.Tasks のリソース割り当てのコレクション
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して Microsoft Project でリソースの割り当てを管理する方法を学びます。コード例を含むステップバイステップのチュートリアル。
type: docs
weight: 12
url: /ja/net/resource-risk-analysis/resource-assignment-collection/
---
## 導入
Aspose.Tasks for .NET を使用して Microsoft Project でリソース割り当てを管理するためのこの包括的なチュートリアルへようこそ。このチュートリアルでは、リソースの割り当てを効率的に操作する方法を確実に理解できるように、プロセスを段階的に詳しく説明します。経験豊富な開発者であっても、初心者であっても、このガイドでは、知っておくべきことをすべて説明します。
## 前提条件
コードに入る前に、次の設定がされていることを確認してください。
1.  Aspose.Tasks for .NET がインストールされている: Aspose.Tasks for .NET が開発環境にインストールされていることを確認します。そうでない場合は、からダウンロードできます[ここ](https://releases.aspose.com/tasks/net/).
2. C# の基本知識: このチュートリアルは、C# プログラミング言語の基本を理解していることを前提としています。
3. Microsoft Project ファイル: テスト目的で Microsoft Project ファイルを用意します。お持ちでない場合は、サンプル ファイルを作成できます。

## 名前空間のインポート
まず、必要な名前空間をインポートしましょう。
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## ステップ 1: プロジェクト ファイルをロードする
まず、Microsoft Project ファイルをロードします。
```csharp
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "TemplateResource2010.mpp");
```
## ステップ 2: タスクとリソースを追加する
次に、タスクとリソースをプロジェクトに追加しましょう。
```csharp
var task = project.RootTask.Children.Add("Task 1");
var resource = project.Resources.Add("Resource 1");
```
## ステップ 3: リソースをタスクに割り当てる
次に、リソースをタスクに割り当てます。
```csharp
var assignment = project.ResourceAssignments.Add(task, resource);
assignment.Set(Asn.Start, new DateTime(2019, 9, 23, 9, 0, 0));
assignment.Set(Asn.Work, project.GetWork(40));
assignment.Set(Asn.Finish, new DateTime(2019, 9, 27, 18, 0, 0));
```
## ステップ 4: さまざまな割り当てタイプを使用する
単位またはコストを含む割り当てを操作することもできます。
```csharp
var assignmentWithUnits = project.ResourceAssignments.Add(task, resource, 1d);
var assignmentWithCost = project.ResourceAssignments.Add(task, resource);
//手順 3 と同様に、単位とコストを使用して割り当てのプロパティを設定します。
```
## ステップ 5: 課題を印刷する
プロジェクトの割り当てを印刷します。
```csharp
Console.WriteLine("Print assignments for the project: " + project.ResourceAssignments.ParentProject.Get(Prj.Name));
Console.WriteLine("Resource assignment count: " + project.ResourceAssignments.Count);
foreach (var resourceAssignment in project.ResourceAssignments)
{
    //課題の詳細を印刷する
}
```
## ステップ 6: UID による割り当ての取得
UID によって割り当てを取得できます。
```csharp
var assignmentByUid = project.ResourceAssignments.GetByUid(2);
Console.WriteLine("Assignment By Uid Start: " + assignmentByUid.Get(Asn.Start));
```
## ステップ 7: 読み取り専用ステータスを確認する
リソース割り当てコレクションが読み取り専用かどうかを確認します。
```csharp
Console.WriteLine("Is resource assignment collection read-only?: " + project.ResourceAssignments.IsReadOnly);
```
## ステップ 8: コレクションをリストに変換して反復する
コレクションをリストに変換し、それを反復処理します。
```csharp
List<ResourceAssignment> resourceAssignments = project.ResourceAssignments.ToList();
foreach (var ra in resourceAssignments)
{
    Console.WriteLine(ra.ToString());
}
```

## 結論
おめでとう！ Aspose.Tasks for .NET を使用して Microsoft Project でリソースの割り当てを管理する方法を学習しました。これらの手順に従うことで、タスクとリソースを効率的に操作でき、プロジェクト管理が容易になります。
## よくある質問
### Q: Aspose.Tasks for .NET をさまざまなバージョンの Microsoft Project ファイルで使用できますか?
A: はい、Aspose.Tasks for .NET は、MPP、MPT、XML 形式など、さまざまなバージョンの Microsoft Project ファイルをサポートしています。
### Q: Aspose.Tasks for .NET を購入する前に利用できる試用版はありますか?
 A: はい、Aspose.Tasks for .NET の無料トライアルを次のサイトから入手できます。[ここ](https://releases.aspose.com/).
### Q: Aspose.Tasks for .NET の使用中に問題が発生した場合、どうすればサポートを受けることができますか?
 A: Aspose.Tasks フォーラムからサポートを求めることができます。[ここ](https://forum.aspose.com/c/tasks/15).
### Q: Aspose.Tasks for .NET の一時ライセンスを使用できますか?
 A: はい、一時ライセンスは評価目的で利用できます。から1つを入手できます[ここ](https://purchase.aspose.com/temporary-license/).
### Q: Aspose.Tasks for .NET のフル ライセンスはどこで購入できますか?
 A: Aspose オンライン ストアから完全なライセンスを購入できます。[ここ](https://purchase.aspose.com/buy).