---
title: Aspose.Tasks でのベースライン コレクションの操作
linktitle: Aspose.Tasks でのベースライン コレクションの操作
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET でベースラインを効率的に管理する方法を学びます。段階的なガイダンスについては、包括的なチュートリアルに従ってください。
weight: 20
url: /ja/net/advanced-features/working-with-baseline-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks でのベースライン コレクションの操作

## 導入

Aspose.Tasks for .NET は、開発者が .NET アプリケーションで Microsoft Project ファイルをシームレスに操作できるようにする強力なライブラリです。多くの機能の中でも、プロジェクト内のベースラインの管理を強力にサポートします。ベースラインは、元のプロジェクト計画と現在のステータスを比較して、プロジェクトの進捗状況をより適切に追跡および分析できるため、プロジェクト管理には不可欠です。

## 前提条件

Aspose.Tasks でのベースライン コレクションの操作に入る前に、次の前提条件が満たされていることを確認してください。

1. Visual Studio: システムに Visual Studio IDE をインストールします。
2.  Aspose.Tasks for .NET: Aspose.Tasks for .NET ライブラリを次の場所からダウンロードしてインストールします。[ダウンロードリンク](https://releases.aspose.com/tasks/net/).
3. C# の基本的な理解: C# プログラミング言語に慣れておきます。
4. Microsoft Project ファイル: テスト用に Microsoft Project ファイル (.mpp) を用意します。

## 名前空間のインポート

Aspose.Tasks でベースライン コレクションの操作を開始するには、次の名前空間をインポートする必要があります。

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

ここで、各例を複数のステップに分けてみましょう。

## ステップ 1: プロジェクト ファイルをロードする

まず、Aspose.Tasks を使用して Microsoft Project ファイルを読み込みます。

```csharp
//ドキュメント ディレクトリへのパス。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "WorkWithBaselineCollection.mpp");
```

## ステップ 2: リソースを取得する

次に、プロジェクトから目的のリソースを取得します。

```csharp
var resource = project.Resources.GetByUid(1);
```

## ステップ 3: ベースライン情報の表示

ここで、リソースに関連付けられたベースラインに関する情報を表示します。

```csharp
Console.WriteLine("Count of assignment baselines: " + resource.Baselines.Count);
Console.WriteLine("Parent Resource Name: " + resource.Baselines.ParentResource.Get(Rsc.Name));
```

## ステップ 4: ベースラインを反復処理する

リソースに関連付けられた各ベースラインを反復処理し、関連情報を出力します。

```csharp
foreach (var baseline in resource.Baselines)
{
    Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
    Console.WriteLine("Cost: " + baseline.Cost);
    Console.WriteLine("Work: " + baseline.Work);
    Console.WriteLine("BCWP: " + baseline.Bcwp);
    Console.WriteLine("BCWS: " + baseline.Bcws);
    Console.WriteLine();
}
```

## ステップ 5: ベースラインを削除する

リソースに関連付けられたすべてのベースラインを削除します。

```csharp
Console.WriteLine("Delete all baselines: ");
List<Baseline> baselines = resource.Baselines.ToList();
foreach (var baseline in baselines)
{
    Console.WriteLine("Delete baseline with name: " + baseline.BaselineNumber);
    resource.Baselines.Remove(baseline);
}
```

## 結論

このチュートリアルでは、Aspose.Tasks for .NET でベースライン コレクションを操作する方法を検討しました。ステップバイステップのガイドに従うことで、.NET アプリケーション内のベースラインを簡単に管理でき、効果的なプロジェクトの追跡と分析が可能になります。

## よくある質問

### Q1: Aspose.Tasks は大きなプロジェクト ファイルを処理できますか?

A1: はい、Aspose.Tasks は大きなプロジェクト ファイルを効率的に処理できるように最適化されており、スムーズなパフォーマンスを保証します。

### Q2: Aspose.Tasks は Microsoft Project のすべてのバージョンと互換性がありますか?

A2: Aspose.Tasks はさまざまなバージョンの Microsoft Project をサポートし、さまざまな環境間での互換性を確保します。

### Q3: Aspose.Tasks でベースラインをカスタマイズできますか?

A3: はい、Aspose.Tasks for .NET を使用して、プロジェクトの要件に応じてベースラインをカスタマイズできます。

### Q4: Aspose.Tasks はクラウド プラットフォームのサポートを提供しますか?

A4: はい、Aspose.Tasks は一般的なクラウド プラットフォームとの統合をサポートし、導入の柔軟性を提供します。

### Q5: Aspose.Tasks ユーザーが助けを求めたり、知識を共有したりできるコミュニティ フォーラムはありますか?

 A5: はい、ご覧いただけます。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)コミュニティに参加し、専門家の支援を受けることができます。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
