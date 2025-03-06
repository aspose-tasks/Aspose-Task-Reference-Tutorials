---
title: Aspose.Tasks での割り当てベースラインの管理
linktitle: Aspose.Tasks での割り当てベースラインの管理
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して割り当てのベースラインを効率的に管理し、プロジェクトの進行状況とパフォーマンスを正確に追跡する方法を学びます。
weight: 14
url: /ja/net/advanced-features/assignment-baseline/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks での割り当てベースラインの管理

## 導入

プロジェクト管理タスクに取り組む場合、進捗状況を正確に追跡するには、割り当てのベースラインを管理することが重要です。 Aspose.Tasks for .NET は、割り当てベースラインを効率的に処理するための包括的なツール セットを提供します。このチュートリアルでは、割り当てベースラインを管理するプロセスを段階的に詳しく説明します。

## 前提条件

始める前に、次の前提条件を満たしていることを確認してください。

- C# プログラミング言語の基本的な知識。
- Visual Studio がシステムにインストールされている。
- Aspose.Tasks for .NET ライブラリがプロジェクトに追加されました。からダウンロードできます[ここ](https://releases.aspose.com/tasks/net/).
- MPP形式のプロジェクトファイルにアクセスします。

## 名前空間のインポート

Aspose.Tasks の使用を開始するには、必要な名前空間を C# プロジェクトにインポートする必要があります。 C# ファイルの先頭に次の名前空間を追加します。

```csharp
using Aspose.Tasks;
using System;


```

## ステップ 1: プロジェクトをロードしてベースラインを設定する

まず、プロジェクトファイルをロードします。`Project` Aspose.Tasks のクラス。次に、プロジェクトのベースライン タイプを設定します。`SetBaseline`方法。

```csharp
//ドキュメント ディレクトリへのパス。
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## ステップ 2: 割り当てのベースライン情報を読み取る

プロジェクト内の各リソース割り当てを繰り返し、各割り当てのベースライン情報を取得します。

```csharp
foreach (var assignment in project.ResourceAssignments)
{
    foreach (var baseline in assignment.Baselines)
    {
        Console.WriteLine("Baseline Start: " + baseline.Start);
        Console.WriteLine("Baseline Finish: " + baseline.Finish);
        Console.WriteLine("Baseline Number: " + baseline.BaselineNumber);
        Console.WriteLine("Bcwp: " + baseline.Bcwp);
        Console.WriteLine("Bcws: " + baseline.Bcws);
        Console.WriteLine("Cost: " + baseline.Cost);
        Console.WriteLine("Work: " + baseline.Work);
        if (baseline.TimephasedData != null)
        {
            foreach (var td in baseline.TimephasedData)
            {
                Console.WriteLine("TD Start: " + td.Start);
                Console.WriteLine("TD Finish: " + td.Finish);
                Console.WriteLine("TD Timephased Data Type: " + td.TimephasedDataType);
                Console.WriteLine();
            }
        }

        Console.WriteLine();
    }

    Console.WriteLine();
}
```

## ステップ 3: ベースラインの同等性を確認する

Aspose.Tasks が提供するさまざまな比較メソッドを使用して、さまざまな割り当てのベースライン情報を比較します。

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

//ベースラインの同等性をチェックする
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

//ベースラインの比較を確認する
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

//ベースラインハッシュコードを表示する
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## 結論

割り当てベースラインの管理はプロジェクト管理に不可欠であり、進捗状況とパフォーマンスを正確に追跡できます。 Aspose.Tasks for .NET を使用すると、割り当てベースラインの処理が合理化および効率化され、開発者にプロジェクト管理ワークフローを強化する強力なツールが提供されます。

## よくある質問

### Q1: Aspose.Tasks は 1 つの割り当てに対して複数のベースラインを処理できますか?

A1: はい、Aspose.Tasks は割り当てごとに複数のベースラインをサポートしているため、長期にわたるプロジェクトの進捗状況を包括的に追跡できます。

### Q2: Aspose.Tasks は MPP 以外のさまざまなプロジェクト ファイル形式と互換性がありますか?

A2: はい。Aspose.Tasks は、XML、MPX、MPP などの幅広いプロジェクト ファイル形式をサポートしており、さまざまなプロジェクト管理ツールとの互換性を確保しています。

### Q3: Aspose.Tasks を使用してベースライン情報をプログラムで変更できますか?

A3: もちろん、Aspose.Tasks はプロジェクト要件に応じてベースライン情報を動的に変更する広範な API を提供し、プロジェクト管理プロセスに対する柔軟性と制御を提供します。

### Q4: Aspose.Tasks は開発者向けのドキュメントとサポート リソースを提供しますか?

A4: はい、開発者は、Aspose.Tasks Web サイト上の包括的なドキュメント、チュートリアル、フォーラムにアクセスでき、スムーズな統合とトラブルシューティングが容易になります。

### Q5: Aspose.Tasks for .NET の試用版はありますか?

 A5: はい、開発者は、Aspose.Tasks for .NET の無料試用版を次のサイトから入手できます。[ここ](https://releases.aspose.com/)、購入を決定する前にその機能と機能を評価できるようになります。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
