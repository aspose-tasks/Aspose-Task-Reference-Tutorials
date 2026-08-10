---
date: 2026-04-06
description: Aspose.Tasks for .NET を使用して、プロジェクトにリソースを追加し、リソースの利用可能期間を設定する方法を学びましょう。リソース
  カレンダーの管理に関するステップバイステップ ガイドです。
keywords:
- add resource to project
- set resource availability
- configure work schedule
linktitle: Aspose.Tasksで利用可能期間を扱う
second_title: Aspose.Tasks .NET API
title: Aspose.Tasksでプロジェクトにリソースを追加し、可用性を設定する
url: /ja/net/advanced-features/working-with-availability-periods/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# プロジェクトにリソースを追加し、Aspose.Tasksで可用性を設定する

## はじめに

このチュートリアルでは、**プロジェクトにリソースを追加する方法**を学び、Aspose.Tasks .NET ライブラリを使用してその可用性期間を定義します。リソース カレンダーの管理は、現実的なプロジェクト スケジュールを作成するために不可欠であり、以下の手順では、プロジェクト インスタンスの作成から各期間の詳細を出力するまでの全プロセスを案内します。

## クイック回答
- **目的は何ですか？** プロジェクトにリソースを追加し、可用性期間を設定することです。  
- **必要なライブラリはどれですか？** Aspose.Tasks for .NET。  
- **本番環境でライセンスが必要ですか？** はい、商用ライセンスが必要です。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+。  
- **実装時間は？** 基本的なシナリオでは通常 15 分未満です。

## 「プロジェクトにリソースを追加する」とは何ですか？

プロジェクトにリソースを追加すると、タスクに割り当て可能な人物、機器、または資材のプレースホルダーが作成されます。リソースが作成されたら、**リソースの可用性を設定**し、作業カレンダーを定義し、スケジューラがこれらの制約を考慮するようにできます。

## なぜ作業スケジュールと可用性期間を設定するのか？

- **正確な計画:** タスクはリソースが実際に空いているときにのみスケジュールされます。  
- **コスト管理:** 可用性単位はパートタイムの作業量を表し、労働コストを正確に計算するのに役立ちます。  
- **リソース平準化:** エンジンは各リソースのカレンダーを把握している場合、過剰割り当てを自動的に平準化できます。

## 前提条件

1. Visual Studio (または任意の .NET 対応 IDE)。  
2. Aspose.Tasks for .NET – ダウンロードは[here](https://releases.aspose.com/tasks/net/)。  
3. 基本的な C# の知識。

## 名前空間のインポート

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;
```

## リソースをプロジェクトに追加する方法は？

### ステップ 1: 新しい `Project` インスタンスを作成する

```csharp
var project = new Project();
```

このオブジェクトは、メモリ内のプロジェクト ファイル全体を表します。

### ステップ 2: プロジェクトにリソースを追加する

```csharp
var resource = project.Resources.Add("Work Resource");
```

この呼び出しにより、後でタスクに割り当て可能な *Work Resource* という **リソース** が作成されます。

### ステップ 3: 可用性期間を定義する

```csharp
IEnumerable<AvailabilityPeriod> periods = this.GetPeriods();
```

`GetPeriods()` はヘルパーメソッド（実装は省略）で、`AvailabilityPeriod` オブジェクトのコレクションを返します。各期間は開始日、終了日、およびリソースが利用可能な単位（フルタイム作業のパーセンテージ）を指定します。

### ステップ 4: 期間をリソースに追加する

```csharp
foreach (var period in periods)
{
    resource.AvailabilityPeriods.Add(period);
}
```

ここでは、コレクションをループし、各期間をリソースのカレンダーに追加することで **リソースの可用性を設定** しています。

### ステップ 5: 可用性の詳細を表示する

```csharp
foreach (var period in resource.AvailabilityPeriods)
{
    Console.WriteLine("Available From: " + period.AvailableFrom);
    Console.WriteLine("Available To: " + period.AvailableTo);
    Console.WriteLine("Available Units: " + period.AvailableUnits);
    Console.WriteLine();
}
```

コンソール出力により、期間が正しく保存されたことを確認できます。

## 一般的な落とし穴とヒント

- **Date precision:** `AvailableFrom` と `AvailableTo` は `DateTime` 値です。全日単位の期間が必要な場合は、午前0時に設定されていることを確認してください。  
- **Units range:** 有効な値は 0‑100 % です。この範囲外の値は例外をスローします。  
- **Over‑lapping periods:** 重複する期間は自動的にマージされますが、明確にするために別々に保つ方が良いです。

## よくある質問

### Q1: 商用プロジェクトで Aspose.Tasks for .NET を使用できますか？
A1: はい、Aspose.Tasks for .NET は商用プロジェクトで使用できます。ライセンスは[here](https://purchase.aspose.com/buy)で購入できます。

### Q2: Aspose.Tasks for .NET の無料トライアルは利用できますか？
A2: はい、Aspose.Tasks for .NET の無料トライアルは[here](https://releases.aspose.com/)で入手できます。

### Q3: Aspose.Tasks for .NET のドキュメントはどこで見つけられますか？
A3: ドキュメントは[here](https://reference.aspose.com/tasks/net/)で見つけられます。

### Q4: Aspose.Tasks for .NET のサポートはどのように受けられますか？
A4: コミュニティフォーラム[here](https://forum.aspose.com/c/tasks/15)からサポートを受けられます。

### Q5: Aspose.Tasks for .NET の一時ライセンスは提供していますか？
A5: はい、一時ライセンスは[here](https://purchase.aspose.com/temporary-license/)で利用可能です。

---

**最終更新日:** 2026-04-06  
**テスト環境:** Aspose.Tasks for .NET (latest stable release)  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}