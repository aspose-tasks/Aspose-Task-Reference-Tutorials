---
date: 2026-03-08
description: このステップバイステップチュートリアルで、Aspose.Tasks for .NET を使用した月次繰り返しタスクの作成方法を学びましょう。
linktitle: How to Create Monthly Recurring Task in Aspose.Tasks
second_title: Aspose.Tasks .NET API
title: Aspose.Tasksで毎月繰り返しタスクを作成する方法
url: /ja/net/advanced-concepts/monthly-recurrence-patterns/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks を使用した月次繰り返しタスクの作成

## はじめに

Aspose.Tasks for .NET を使用すると、Microsoft Project ファイルをプログラムで操作でき、最も一般的な実務ニーズのひとつは **月次繰り返しタスク** のスケジュールを作成することです。プロジェクト追跡ツールの構築、リソース割り当ての自動化、定期的な保守作業項目の生成など、この記事ではタスクに月次繰り返しパターンを追加する具体的な手順を解説します。

次のセクションでは、プロジェクトの設定方法、繰り返しパラメータの定義方法、そして最終的に更新されたファイルを保存する手順を、分かりやすい説明と実用的なヒントとともに紹介します。

## クイック回答
- **“monthly recurring task” とは何ですか？** 毎月、特定の日または週のパターンで繰り返されるタスクです。  
- **どの API クラスが繰り返しを扱いますか？** `RecurringTaskParameters` と `MonthlyRecurrencePattern` を組み合わせて使用します。  
- **サンプルを実行するのにライセンスは必要ですか？** 評価目的なら無料トライアルで動作しますが、本番環境ではライセンスが必要です。  
- **間隔を変更できますか？** はい、`RepetitionInterval` に繰り返し間隔（月数）を設定します。  
- **サポートされているファイル形式は何ですか？** `.mpp` と `.xml` の両方の Project ファイルを読み込み・保存できます。

## 月次繰り返しパターンとは？

月次繰り返しパターンは、Microsoft Project（および Aspose.Tasks）に対して、タスクが各月どの頻度で繰り返すべきかを指示します。月の固定日（例: 1日）や相対的な位置（例: 最終金曜日）を指定できます。API はこれらのルールを Project ファイルの内部構造に変換します。

## なぜ Aspose.Tasks を使用するのか？

- **フルコントロール** – UI の制限がなく、パターンのすべての要素をコードで定義できます。  
- **クロスプラットフォーム** – .NET Framework、.NET Core、.NET 5/6+ で動作します。  
- **Microsoft Project は不要** – サーバーや CI パイプライン上でファイルの生成・変更が可能です。  

## 前提条件

開始する前に、以下が揃っていることを確認してください。

- .NET 6（または .NET 5 / Framework 4.7+）がインストールされていること。  
- プロジェクトに Aspose.Tasks for .NET の NuGet パッケージが追加されていること。  
- サンプル Project ファイル（`Project1.mpp`）が既知のフォルダー（`DataDir`）に配置されていること。  

## 名前空間のインポート

まず、タスク操作とプロジェクト保存に必要な名前空間をインポートします。

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

## ステップ 1: プロジェクトの初期化

既存の `.mpp` ファイルを指す `Project` インスタンスを作成します。これによりファイルがメモリにロードされ、変更が可能になります。

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

> **プロのコツ:** ファイルが存在しない場合、Aspose.Tasks は自動的に新しい空白プロジェクトを作成します。

## ステップ 2: 繰り返しタスクパラメータの設定

タスク名、期間、適用したい月次パターンなど、繰り返しタスクの詳細を定義します。

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthDayRepetition { DayPosition = 1, RepetitionInterval = 2 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 30, 17, 0, 0)
        }
    }
};
```

- `DayPosition = 1` はタスクが月の **最初の日** に発生することを意味します。  
- `RepetitionInterval = 2` はタスクが **2か月ごと** に繰り返されることを意味します。  
- `Start` と `Finish` は繰り返しが有効になる全体の期間を定義します。

## ステップ 3: パラメータをプロジェクトに追加

`RecurringTaskParameters` オブジェクトをルートタスクの子コレクションに添付します。これによりプロジェクト階層内に繰り返しタスクが作成されます。

```csharp
project.RootTask.Children.Add(parameters);
```

## ステップ 4: プロジェクトの保存

変更を永続化するために、プロジェクトを新しいファイルに保存します。サポートされている任意の形式を選択できますが、ここではネイティブの `.mpp` 形式を使用します。

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

コードを実行した後、Microsoft Project で生成されたファイルを開くと、作成した月次繰り返しタスクが確認できます。

## 一般的な問題と解決策

| 問題 | 原因 | 対策 |
|------|------|------|
| 保存後にタスクが表示されない | UI でプロジェクトが更新されていない | ファイルを再度開くか、保存前に `project.UpdateTaskLinks()` を呼び出す。 |
| 開始日が間違っている | `Start` が週末に設定されている | 作業日の `DateTime` を使用するか、カレンダーを調整する。 |
| 繰り返し間隔が無視される | `DayPosition` = 0 の `ByMonthDayRepetition` を使用している | `DayPosition` が 1‑31 の範囲であることを確認する。 |

## 結論

これらの手順に従うことで、Aspose.Tasks for .NET を使用した **月次繰り返しタスク** のスケジュール作成方法が習得できました。API は繰り返し間隔、開始/終了範囲、特定の日パターンに対して細かい制御を提供し、複雑なプロジェクト計画シナリオの自動化を可能にします。

## FAQ

### Q1: Aspose.Tasks はすべてのバージョンの Microsoft Project ファイルに対応していますか？

A1: Aspose.Tasks は MPP、MPT、XML、MPX など、さまざまなバージョンの Microsoft Project ファイルに対応しています。

### Q2: 繰り返しパターンをさらにカスタマイズできますか？

A2: はい、Aspose.Tasks は日次、週次、月次、年次など、繰り返しパターンを細かくカスタマイズできる豊富なオプションを提供します。

### Q3: Aspose.Tasks の無料トライアルはありますか？

A3: はい、[こちら](https://releases.aspose.com/) から Aspose.Tasks の無料トライアルを取得できます。

### Q4: Aspose.Tasks のサポートはどこで受けられますか？

A4: [Aspose.Tasks フォーラム](https://forum.aspose.com/c/tasks/15) で支援を求めたり、ディスカッションに参加したりできます。

### Q5: Aspose.Tasks のライセンスはどこで購入できますか？

A5: [こちら](https://purchase.aspose.com/buy) から Aspose.Tasks のライセンスを購入できます。

## よくある質問

**Q: このコードを .NET Core アプリケーションで使用できますか？**  
A: もちろんです。Aspose.Tasks for .NET は .NET Core 3.1 以降を完全にサポートしています。

**Q: 繰り返しを「月の最終平日」に変更するには？**  
A: `ByMonthDayRepetition` を使用し、`DayPosition = -1`（負の値は月末からカウント）に設定し、`WeekDay` を適切に指定します。

**Q: 繰り返し範囲がプロジェクトのカレンダーを超えた場合はどうなりますか？**  
A: API はプロジェクトカレンダーを尊重します。非稼働日になる発生は、カレンダー設定に従ってスキップまたは移動されます。

**Q: 繰り返しタスクの特定の発生を削除できますか？**  
A: はい。繰り返しタスクを追加した後、`Task.GetOccurrences()` で個々の発生を取得し、不要なものを削除できます。

**Q: Aspose.Tasks はタイムゾーンの違いを自動的に処理しますか？**  
A: ライブラリは日付を UTC で保存します。必要に応じて標準の .NET `DateTime` メソッドでローカル時間に変換できます。

---

**Last Updated:** 2026-03-08  
**Tested With:** Aspose.Tasks 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}