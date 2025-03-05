---
title: Aspose.Tasks でのプロジェクト コレクションの管理
linktitle: Aspose.Tasks でのグループ コレクションの管理
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して MS Project コレクションを効率的に管理する方法を学びます。ステップバイステップのガイドに従ってください。
type: docs
weight: 26
url: /ja/net/tasks-project-management/group-collection/
---
## 導入
このチュートリアルでは、Aspose.Tasks for .NET を使用してグループ MS Project コレクションを管理する方法を説明します。グループ コレクションの管理は、プロジェクト内でタスクとリソースを効率的に整理および操作するために重要です。
## 前提条件
このチュートリアルに進む前に、次の前提条件を満たしていることを確認してください。
1.  Aspose.Tasks for .NET ライブラリ: Aspose.Tasks for .NET ライブラリを次の場所からダウンロードしてインストールします。[ダウンロードリンク](https://releases.aspose.com/tasks/net/).
2. C# の基本知識: このチュートリアルには C# でのコーディングが含まれるため、C# プログラミング言語の基本を理解してください。
3. 開発環境: Visual Studio や .NET 開発をサポートするその他の IDE などの開発環境をセットアップします。

## 名前空間のインポート
まず、C# コードで Aspose.Tasks 機能を操作するために必要な名前空間をインポートしましょう。

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;

```
## ステップ 1: プロジェクトをロードする
```csharp
//ドキュメントディレクトリへのパス。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```
この手順では、MS プロジェクト ファイルを Aspose.Tasks プロジェクト オブジェクトにロードし、そのファイルに対して操作を実行できるようにします。
## ステップ 2: タスク グループを反復処理する
```csharp
Console.WriteLine("Print task groups of {0} project: ", project.Get(Prj.Name));
Console.WriteLine("Task Group Count: " + project.TaskGroups.Count);
foreach (var group in project.TaskGroups)
{
    Console.WriteLine("Index: " + group.Index);
    Console.WriteLine("Name: " + group.Name);
    Console.WriteLine("Show In Menu: " + group.ShowInMenu);
    Console.WriteLine();
}
```
ここでは、プロジェクト内のタスク グループを反復処理し、各グループのメニューのインデックス、名前、表示/非表示などの詳細を出力します。
## ステップ 3: リソース グループを反復処理する
```csharp
Console.WriteLine("Project resource group count: " + project.ResourceGroups.Count);
foreach (var group in project.ResourceGroups)
{
    Console.WriteLine("Resource group Index: " + group.Index);
    Console.WriteLine("Resource group Name: " + group.Name);
    Console.WriteLine("Resource group ShowInMenu" + group.ShowInMenu);
}
```
同様に、このステップはリソース グループを反復処理し、そのインデックス、名前、およびメニュー内の表示設定を表示します。
## ステップ 4: グループをクリアして別のプロジェクトにコピーする
```csharp
var otherProject = new Project(DataDir + "Blank2010.mpp");
//他のプロジェクトのグループをクリアする
otherProject.TaskGroups.Clear();
//グループを他のプロジェクトにコピーする
var groups = new Group[project.TaskGroups.Count];
project.TaskGroups.CopyTo(groups, 0);
foreach (var group in groups)
{
    otherProject.TaskGroups.Add(group);
}
```
ここでは、別のプロジェクトのグループをクリアし、元のプロジェクトからグループをコピーします。
## ステップ 5: カスタム タスク グループを追加する
```csharp
var customGroup = new Group
{
    Name = "Custom Group",
    ShowInMenu = true
};
if (!otherProject.TaskGroups.Contains(customGroup))
{
    if (!otherProject.TaskGroups.IsReadOnly)
    {
        otherProject.TaskGroups.Add(customGroup);
    }
}
```
このステップでは、カスタム タスク グループを作成し、それがまだ存在しない場合は他のプロジェクトに追加します。
## ステップ 6: すべてのグループを削除する
```csharp
List<Group> groupsToDelete = otherProject.TaskGroups.ToList();
foreach (var group in groupsToDelete)
{
    otherProject.TaskGroups.Remove(group);
}
```
最後に、他のプロジェクトからすべてのグループを削除します。

## 結論
Aspose.Tasks for .NET でグループ MS Project コレクションを管理することは、プロジェクト データを効率的に整理および操作するために不可欠です。このチュートリアルで概説されている手順に従うことで、プロジェクト内のタスクおよびリソース グループを効果的に処理でき、全体的なプロジェクト管理が向上します。
## よくある質問
### Aspose.Tasks for .NET は MS Project のすべてのバージョンと互換性がありますか?
Aspose.Tasks for .NET は、2003、2007、2010、2013、2016、2019 などのさまざまなバージョンの Microsoft Project をサポートします。
### Aspose.Tasks for .NET を使用してグループ プロパティをカスタマイズできますか?
はい、Aspose.Tasks for .NET を使用して、名前や表示設定などのグループ プロパティをカスタマイズできます。
### Aspose.Tasks for .NET はクロスプラットフォーム互換性を提供しますか?
Aspose.Tasks for .NET は主に .NET Framework をターゲットとしていますが、.NET Core および .NET Standard を使用したクロスプラットフォーム シナリオでも使用できます。
### Aspose.Tasks for .NET のサポートを受けるにはどうすればよいですか?
 Aspose.Tasks for .NET のサポートは、[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15).
### Aspose.Tasks for .NET の試用版はありますか?
はい、Aspose.Tasks for .NET の無料試用版を次のサイトからダウンロードできます。[Webサイト](https://releases.aspose.com/).