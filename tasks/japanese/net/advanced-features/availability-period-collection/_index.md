---
date: 2026-03-21
description: Aspose.Tasks for .NET を使用して、リソースの利用可能期間の管理方法を学び、プロジェクトのリソース利用可能性を効果的に実現しましょう。このステップバイステップガイドでは、利用可能期間の追加、更新、削除方法を示します。
linktitle: Collection of Availability Periods in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: プロジェクトリソースの可用性 – Aspose.Tasksでの可用期間の管理
url: /ja/net/advanced-features/availability-period-collection/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# プロジェクトリソースの可用性: Aspose.Tasks における可用期間のコレクション

プロジェクトリソースの **可用性** を管理することは、成功するプロジェクト計画の核心です。このチュートリアルでは、Aspose.Tasks for .NET API を使用して、プロジェクトの読み込みからリソース間で期間をコピーするまで、可用性を段階的に管理する方法を学びます。

## クイック回答
- **可用期間のメインクラスは何ですか？** `Aspose.Tasks` 名前空間の `AvailabilityPeriod`。  
- **既存の期間をクリアできますか？** はい、`resource.AvailabilityPeriods.Clear()` を呼び出します。  
- **新しい期間はどうやって追加しますか？** `AvailabilityPeriod` オブジェクトを作成し、`Add` または `Insert` を使用します。  
- **別のリソースに期間をコピーできますか？** もちろんです – `CopyTo` を使用し、各項目を対象リソースに追加します。  
- **本番環境でライセンスは必要ですか？** はい、トライアル以外のデプロイには商用の Aspose.Tasks ライセンスが必要です。

## プロジェクトリソースの可用性とは？
プロジェクトリソースの可用性は、リソースがタスクに割り当て可能な日付と単位（容量のパーセンテージ）を定義します。これらの期間を管理することで、過剰割り当てを防ぎ、スケジュールの精度を向上させます。

## なぜ Aspose.Tasks で可用期間を管理するのか？
- **完全な .NET 統合** – COM 相互運用が不要で、純粋なマネージドコード。  
- **細かな制御** – 正確な開始/終了日と小数単位を設定可能。  
- **簡単なコピー** – 手動で解析することなく、リソース間で可用データを移動。  
- **パフォーマンス最適化** – 大規模な MPP ファイルでも効率的に動作。

## 前提条件
1. **Visual Studio** – 最近のバージョン（2019、2022、またはそれ以降）。  
2. **Aspose.Tasks for .NET** – [here](https://releases.aspose.com/tasks/net/) からダウンロード。  
3. **基本的な C# 知識** – クラス、コレクション、LINQ に慣れていること。

## 名前空間のインポート

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

コアの Aspose.Tasks 名前空間と、後で使用する標準 .NET コレクションをインポートします。

## 手順 1: プロジェクトとリソースの初期化

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "UpdateResourceData.mpp");
var resource = project.Resources.GetById(1);
```

既存の MPP ファイルを読み込み、可用性を編集したいリソース（ID = 1）を取得します。

## 手順 2: 既存の可用期間をクリア

```csharp
resource.AvailabilityPeriods.Clear();
```

クリアすると、以前に定義された期間がすべて削除され、クリーンな状態になります。

## 手順 3: 可用期間を追加

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
foreach (var period in periods)
{
    if (!resource.AvailabilityPeriods.IsReadOnly)
    {
        resource.AvailabilityPeriods.Add(period);
    }
}
```

`AvailabilityPeriod` オブジェクトのコレクションを取得し（`GetPeriods` ヘルパーは別途定義されていると想定）、書き込み可能であることを確認しながら各期間を追加します。

## 手順 4: 新しい可用期間を挿入

```csharp
var period2013 = new AvailabilityPeriod { AvailableFrom = new DateTime(2013, 1, 1), AvailableTo = new DateTime(2013, 12, 12), AvailableUnits = 0.81 };

if (!resource.AvailabilityPeriods.Contains(period2013))
{
    resource.AvailabilityPeriods.Insert(1, period2013);
}
```

2013 年用のカスタム期間を作成し、既に存在しなければ位置 1（2 番目のスロット）に挿入します。

## 手順 5: 可用期間を表示

```csharp
Console.WriteLine("Count of availability periods: " + resource.AvailabilityPeriods.Count);
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

コンソールへの簡易ダンプで、総数と各期間の詳細を出力します。デバッグや検証に便利です。

## 手順 6: 別リソースへ可用期間をコピー

```csharp
var periodsToCopy = new AvailabilityPeriod[resource.AvailabilityPeriods.Count];
resource.AvailabilityPeriods.CopyTo(periodsToCopy, 0);

var otherResource = project.Resources.GetById(2);
otherResource.AvailabilityPeriods.Clear();
foreach (var period in periodsToCopy)
{
    otherResource.AvailabilityPeriods.Add(period);
}
```

コレクション全体を配列にコピーし、対象リソースの期間をクリアしてから再度設定します。これにより、リソース間で可用データを複製する方法が示されます。

## 手順 7: 可用期間の更新と削除

```csharp
// Update available units for a specific period
otherResource.AvailabilityPeriods[otherResource.AvailabilityPeriods.Count - 2].AvailableUnits = 0.90;

// Remove a specific period
otherResource.AvailabilityPeriods.Remove(period2013);
```

ここでは、最後から2番目の期間の `AvailableUnits` を調整し、以前追加した 2013 年の期間を削除します。

## よくある問題と解決策
- **読み取り専用コレクションエラー** – プロジェクトが読み取り専用モードで開かれていないか、`resource.AvailabilityPeriods.Clear()` を新しい項目を追加する前に呼び出したか確認してください。  
- **期間の重複** – Aspose.Tasks は自動でマージしません。重複を検出・解消するカスタムロジックが必要です。  
- **日付形式が正しくない** – 常に `DateTime` オブジェクトを使用してください。文字列解析はロケール依存のバグを招く可能性があります。

## FAQ

**Q: 可用期間にカスタムフィールドを追加できますか？**  
A: いいえ、Aspose.Tasks for .NET の可用期間はカスタムフィールドをサポートしていません。

**Q: 可用期間は特定のタスクにリンクされていますか？**  
A: いいえ、リソースに紐付いており、リソースがタスクに対して一般的に利用可能な時期を定義します。

**Q: 外部ソースから可用期間をインポートできますか？**  
A: はい、CSV、XML、データベースなどから期間を読み取り、`AvailabilityPeriod` オブジェクトを作成してコレクションに追加することでインポート可能です。

**Q: 重複する可用期間はどう処理すればよいですか？**  
A: 重複は自動で解決されません。カスタムバリデーションを実装し、期間をマージまたは拒否するロジックを作成してください。

**Q: リソースが持てる可用期間の数に上限はありますか？**  
A: ハードコードされた上限はありませんが、非常に大きなコレクションはパフォーマンスに影響する可能性があります。可能な限り期間を統合することを検討してください。

## 結論

本ガイドでは、Aspose.Tasks for .NET を使用して **プロジェクトリソースの可用性** を管理するために必要なすべての手順を網羅しました。プロジェクトの初期化、古いデータのクリア、期間の追加・挿入・コピー・更新・削除までを学び、リソースカレンダーを正確に保ち、プロジェクトスケジュールを現実的に保つ方法を習得できます。

---

**最終更新日:** 2026-03-21  
**テスト環境:** Aspose.Tasks for .NET（最新リリース）  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}