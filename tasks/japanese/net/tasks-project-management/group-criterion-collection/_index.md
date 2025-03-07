---
title: Aspose.Tasks を使用して MS プロジェクト グループ基準を管理する
linktitle: Aspose.Tasks でのグループ基準コレクションの管理
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用してグループ基準 MS プロジェクトのコレクションを管理する方法を学びます。開発者向けのステップバイステップのガイド。
weight: 28
url: /ja/net/tasks-project-management/group-criterion-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks を使用して MS プロジェクト グループ基準を管理する

## 導入
Aspose.Tasks for .NET は、開発者がプログラムで Microsoft Project ファイルを操作できるようにする強力な API です。このチュートリアルでは、Aspose.Tasks を使用して MS Project 内でグループ基準コレクションを管理する方法を説明します。

## 前提条件

始める前に、以下のものがあることを確認してください。

1.  Aspose.Tasks for .NET: Aspose.Tasks ライブラリが .NET プロジェクトにインストールされていることを確認してください。からダウンロードできます[ここ](https://releases.aspose.com/tasks/net/).

2. Microsoft Project ファイル: Microsoft Project ファイル (MPP) を使用できるように準備します。

## 名前空間のインポート

まず、必要な名前空間を C# コードにインポートする必要があります。この手順は、Aspose.Tasks が提供する機能にアクセスするために重要です。

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

## ステップ 1: プロジェクト ファイルをロードする

を初期化します`Project` MPP ファイルをロードしてオブジェクトを読み込みます。 

```csharp
string DataDir = "Your Document Directory";
var project = new Project(DataDir + "ReadGroupDefinitionData.mpp");
```

## ステップ 2: グループ基準にアクセスする

プロジェクトからグループを取得し、その基準にアクセスします。

```csharp
var group = project.TaskGroups.ToList()[0];
```

## ステップ 3: グループ基準を反復処理する

グループ内の各基準をループし、そのプロパティを表示します。

```csharp
foreach (var criterion in group.GroupCriteria)
{
    Console.WriteLine("Index: " + criterion.Index);
    Console.WriteLine("Field: " + criterion.Field);
    Console.WriteLine("Group On: " + criterion.GroupOn);
    Console.WriteLine();
}
```

## ステップ 4: グループ基準をクリアする

既存のグループ基準が読み取り専用でない場合はクリアします。

```csharp
group.GroupCriteria.Clear();
```

## ステップ 5: 新しい基準を追加する

新しいグループ基準を作成し、グループに追加します。

```csharp
var criterionToAdd = new GroupCriterion
{
    Ascending = true,
    Field = Field.TaskActive
};

if (!group.GroupCriteria.Contains(criterionToAdd))
{
    group.GroupCriteria.Add(criterionToAdd);
}
```

## ステップ 6: 条件を別のグループにコピーする

基準をあるグループから別のグループにコピーします。

```csharp
var otherGroup = project.TaskGroups.ToList()[0];

var criteria = new GroupCriterion[group.GroupCriteria.Count];
group.GroupCriteria.CopyTo(criteria, 0);
foreach (var criterion in criteria)
{
    otherGroup.GroupCriteria.Add(criterion);
}
```

### 結論

このチュートリアルでは、Aspose.Tasks for .NET を使用してグループ基準 MS プロジェクト コレクションを管理する方法を学習しました。これらの手順に従うことで、Microsoft Project ファイル内のグループ基準をプログラムで効果的に操作できます。

## よくある質問

### Q1: Aspose.Tasks は Microsoft Project のすべてのバージョンと互換性がありますか?

A: はい、Aspose.Tasks は、2003、2007、2010、2013、2016 などのさまざまなバージョンの Microsoft Project ファイルをサポートしています。

### Q2: 1 つのグループに複数の基準を適用できますか?

A: もちろん、複数の条件をグループに追加するには、それぞれを反復処理し、それに応じて追加します。

### Q3: Aspose.Tasks の試用版はありますか?

 A: はい、Aspose.Tasks の無料トライアルを次のサイトから入手できます。[ここ](https://releases.aspose.com/).

### Q4: Aspose.Tasks のドキュメントはどこで見つけられますか?

 A: ドキュメントを参照してください。[ここ](https://reference.aspose.com/tasks/net/).

### Q5: 問題が発生した場合、どうすればサポートを受けられますか?

 A: 質問がある場合、または問題に直面している場合は、Aspose.Tasks フォーラムからサポートを求めることができます。[ここ](https://forum.aspose.com/c/tasks/15).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
