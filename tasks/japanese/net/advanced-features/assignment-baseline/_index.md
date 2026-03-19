---
date: 2026-03-19
description: Aspose.Tasks for .NET を使用してプロジェクトのベースラインを設定し、割り当てベースラインを効率的に管理する方法を学び、プロジェクトの進捗を正確に追跡できるようにします。
linktitle: Managing Assignment Baseline in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: プロジェクトベースラインの設定 – Aspose.Tasks における割り当てベースラインの管理
url: /ja/net/advanced-features/assignment-baseline/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# プロジェクトベースラインの設定 – Aspose.Tasks における割り当てベースラインの管理

## はじめに

プロジェクト管理タスクを行う際、**プロジェクトベースラインの設定**は、実際の進捗を元の計画と比較するために不可欠です。Aspose.Tasks for .NET は **プロジェクトベースラインの設定**だけでなく、割り当てベースラインを完全に制御できる機能を提供し、正確なパフォーマンス追跡を可能にします。このチュートリアルでは、プロジェクトの読み込み、ベースラインの設定、割り当てベースラインデータの取得、ベースラインの比較という一連の手順を詳しく解説し、プロジェクトを自信を持って監視できるようにします。

## クイック回答
- **「プロジェクトベースラインを設定する」とは何ですか？** 元のスケジュールとコストデータを記録し、後で実績と比較できるようにします。  
- **ベースラインを設定する API メソッドはどれですか？** `Project.SetBaseline(BaselineType.Baseline)`。  
- **割り当てベースラインは別途呼び出しが必要ですか？** いいえ、プロジェクトベースラインを設定すると自動的に保存されます。  
- **サポートされているフォーマットは何ですか？** MPP、XML、MPX など、Aspose.Tasks が扱えるすべての形式。  
- **本番環境でライセンスは必要ですか？** はい、トライアル以外の使用には商用ライセンスが必要です。

## 前提条件

開始する前に、以下を用意してください。

- C# プログラミングの基本知識。  
- Visual Studio（最新バージョンのいずれか）。  
- プロジェクトに追加した Aspose.Tasks for .NET ライブラリ。ダウンロードは [here](https://releases.aspose.com/tasks/net/) から。  
- MPP 形式のプロジェクトファイルへのアクセス（例: `AssignmentBaseline2007.mpp`）。

## 名前空間のインポート

C# ファイルの先頭に必要な名前空間を追加し、コンパイラが Aspose.Tasks クラスを認識できるようにします。

```csharp
using Aspose.Tasks;
using System;
```

## 手順 1: プロジェクトの読み込みとプロジェクトベースラインの設定

まず既存の MPP ファイルを読み込み、`SetBaseline` を呼び出して **プロジェクトベースラインを設定**します。

```csharp
// The path to the documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "AssignmentBaseline2007.mpp");
project.SetBaseline(BaselineType.Baseline);
```

## 手順 2: 割り当てベースライン情報の読み取り

ベースラインが設定されると、各リソース割り当ては独自のベースラインレコードを保持します。以下のループは、開始/終了日、コスト、作業量、時間フェーズデータなどの詳細を抽出して表示します。

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

## 手順 3: 割り当てベースラインの比較

組み込みの等価演算子と比較演算子を使用して、異なる割り当てのベースラインを比較できます。タスク間のスケジュールシフトやコスト超過を検出する際に便利です。

```csharp
var assn1 = project.ResourceAssignments.GetByUid(5);
var assn2 = project.ResourceAssignments.GetByUid(7);

var assignmentBaseline1 = assn1.Baselines.ToList()[0];
var assignmentBaseline2 = assn2.Baselines.ToList()[0];

// Check baseline equality
Console.WriteLine("Are baselines equal: " + assignmentBaseline1.Equals(assignmentBaseline2));

// Check baseline comparison
Console.WriteLine("Is baseline 1 less than baseline 2: " + (assignmentBaseline1 < assignmentBaseline2));

// Display baseline hashcodes
Console.WriteLine("Assignment baseline 1 hashcode: " + assignmentBaseline1.GetHashCode());
Console.WriteLine("Assignment baseline 2 hashcode: " + assignmentBaseline2.GetHashCode());
```

## よくある問題と解決策

| 問題 | 発生理由 | 対策 |
|-------|----------------|-----|
| **ベースラインデータが空です** | プロジェクトファイルが読み取り専用モードで開かれた、またはベースラインが設定されていない。 | 割り当てベースラインを読む前に `project.SetBaseline(BaselineType.Baseline)` を呼び出す。 |
| **`TimephasedData` で `NullReferenceException` が発生** | すべてのベースラインが時間フェーズエントリを持つわけではない。 | コード例のように `baseline.TimephasedData != null` を必ずチェックする。 |
| **UID の取得が正しくない** | ファイルバージョン間で UID が異なる場合がある。 | 正しい UID を使用して `ResourceAssignments.GetByUid` を呼び出すか、目的の割り当てが見つかるまで列挙する。 |

## よくある質問

**Q: Aspose.Tasks は単一の割り当てに対して複数のベースラインを扱えますか？**  
A: はい、Aspose.Tasks は各割り当てに対して複数のベースラインをサポートしており、プロジェクトの進捗を時間軸で包括的に追跡できます。

**Q: Aspose.Tasks は MPP 以外のさまざまなプロジェクトファイル形式に対応していますか？**  
A: はい、Aspose.Tasks は XML、MPX、MPP など幅広いプロジェクトファイル形式をサポートし、さまざまなプロジェクト管理ツールとの互換性を確保します。

**Q: Aspose.Tasks を使ってプログラムからベースライン情報を変更できますか？**  
A: もちろんです。Aspose.Tasks は豊富な API を提供しており、プロジェクト要件に応じてベースライン情報を動的に変更でき、柔軟かつ細かな管理が可能です。

**Q: Aspose.Tasks は開発者向けのドキュメントやサポートリソースを提供していますか？**  
A: はい、開発者は Aspose.Tasks のウェブサイトで包括的なドキュメント、チュートリアル、フォーラムにアクセスでき、スムーズな統合とトラブルシューティングを支援します。

**Q: Aspose.Tasks for .NET のトライアル版はありますか？**  
A: はい、開発者は [here](https://releases.aspose.com/) から Aspose.Tasks for .NET の無料トライアル版を入手でき、購入前に機能と性能を評価できます。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-19  
**Tested With:** Aspose.Tasks 24.12 for .NET  
**Author:** Aspose