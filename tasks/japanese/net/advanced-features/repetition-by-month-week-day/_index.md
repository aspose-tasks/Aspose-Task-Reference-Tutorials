---
date: 2026-04-01
description: Aspose.Tasks for .NETで繰り返し設定を行う方法、繰り返しタスクを追加する方法、そして月・週・日単位で繰り返しタスクを自動化する方法を学びましょう。
keywords:
- how to set recurrence
- add recurring task
- automate recurring tasks
linktitle: Aspose.Tasks における月・週・日単位の繰り返し
second_title: Aspose.Tasks .NET API
title: Aspose.Tasksで繰り返し設定を行う方法（月、週、日）
url: /ja/net/advanced-features/repetition-by-month-week-day/
weight: 26
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks での繰り返し設定方法（月、週、日）

## はじめに

プロジェクト内のタスクの **繰り返し設定方法** が必要な場合、Aspose.Tasks for .NET は月、週、日単位で実行される繰り返しタスク定義を追加するためのクリーンでプログラム的な方法を提供します。このチュートリアルでは、実際の例を通じて **繰り返しタスクの追加** エントリ、**繰り返しタスクの自動化**、および C# コードから直接管理する方法を示します。最後まで読めば、この機能を任意のスケジューリングやプロジェクト管理ソリューションに統合できるようになります。

## クイック回答
- **Aspose.Tasks の「recurrence（繰り返し）」は何を意味しますか？** 日次、週次、月次のパターンを定義し、日付範囲内でタスクインスタンスを自動的に作成します。  
- **繰り返しを作成する主なメソッドはどれですか？** `RecurringTaskParameters` と特定の `RecurrencePattern` を組み合わせます。  
- **このコードを実行するのにライセンスは必要ですか？** 評価にはトライアルで動作しますが、本番環境では商用ライセンスが必要です。  
- **月次ではなく週次タスクをスケジュールできますか？** はい – `MonthlyRecurrencePattern` を `WeeklyRecurrencePattern` に置き換えます。  
- **サポートされている .NET バージョンは何ですか？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以降です。

## Aspose.Tasks の繰り返しとは何ですか？

繰り返しは、Aspose.Tasks に対してタスクインスタンスを定期的（日次、週次、月次）に生成させるルールの集合で、手動でタスクを複製する必要がありません。この機能は、ステータス会議、検査、保守作業などの定例活動を含むプロジェクトに不可欠です。

## なぜ繰り返し機能を使用するのか？

- **時間の節約:** タスクを手動でコピー＆ペーストする必要がありません。  
- **エラー削減:** ライブラリは一貫した日付と期間を保証します。  
- **柔軟性:** パターンを組み合わせられます（例: 「2か月ごとの最初の日曜日」）。  
- **自動化:** CI パイプラインやレポートツールでスケジュールを生成するのに最適です。

## 前提条件

開始する前に、以下が揃っていることを確認してください：

1. **C# の基本的な理解** – 数行の C# コードを書きます。  
2. **Aspose.Tasks for .NET がインストール済み** – [download page](https://releases.aspose.com/tasks/net/) から取得してください。  
3. **.mpp プロジェクトファイル** – ソースファイルとして `Project1.mpp` を使用します。

## 名前空間のインポート

まず、必要な Aspose.Tasks の名前空間をインポートします：

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

### 手順 1: プロジェクトファイルの読み込み

```csharp
// The path to th documents directory.
String DataDir = "Your Document Directory";
var project = new Project(DataDir + "Project1.mpp");
```

既存の Microsoft Project ファイルを指す `Project` インスタンスを作成します。

### 手順 2: 繰り返しタスクパラメータの定義

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new MonthlyRecurrencePattern
    {
        Repetition = new ByMonthWeekDayRepetition
        {
            Position = OrdinalNumber.First,
            WeekDay = DayOfWeek.Sunday,
            RepetitionInterval = 2
        },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 1, 8, 0, 0),
            Finish = new DateTime(2018, 9, 2, 17, 0, 0)
        }
    }
};
```

ここで **繰り返しタスク** パラメータを作成します：

- **TaskName** – 生成されるタスクの名前です。  
- **Duration** – 各発生の期間です。  
- **RecurrencePattern** – 2か月ごとに最初の日曜日に繰り返す月次パターンです。  
- **RecurrenceRange** – スケジュールを限定する開始日と終了日です。

### 手順 3: プロジェクトに繰り返しタスクを追加

```csharp
project.RootTask.Children.Add(parameters);
```

この行は **繰り返しタスク** をプロジェクト階層のルートに追加します。

### 手順 4: 更新されたプロジェクトの保存

```csharp
project.Save(DataDir + "CanAddRecurringTask_Months_WeekDay_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

プロジェクトは自動スケジュールを含む新しい `.mpp` ファイルとして保存されます。

## よくある問題と解決策

| 問題 | 原因 | 対策 |
|-------|--------|-----|
| **タスクが表示されない** | 繰り返し範囲がプロジェクトの日付外です。 | `Start` と `Finish` の値がプロジェクトカレンダー内にあることを確認してください。 |
| **曜日が間違っている** | `WeekDay` 列挙型が一致しません。 | 必要に応じて `DayOfWeek.Monday` … `DayOfWeek.Sunday` を使用してください。 |
| **ライセンス例外** | 本番環境で有効なライセンスなしで実行しています。 | 保存する前に一時的または完全なライセンスを適用してください。 |

## よくある質問

### Q1: 提供された例以外に繰り返しパターンをカスタマイズできますか？

A1: はい、Aspose.Tasks for .NET は繰り返しパターンに対する豊富なカスタマイズオプションを提供しており、特定の要件に合わせて調整できます。

### Q2: Aspose.Tasks for .NET のトライアル版は利用可能ですか？

A2: はい、[releases page](https://releases.aspose.com/) から Aspose.Tasks for .NET の無料トライアルを取得できます。

### Q3: Aspose.Tasks for .NET のサポートはどのように受けられますか？

A3: [Aspose.Tasks forum](https://forum.aspose.com/c/tasks/15) で支援を求め、コミュニティと交流できます。

### Q4: Aspose.Tasks for .NET の一時ライセンスは利用可能ですか？

A4: はい、テストや評価目的で [purchase page](https://purchase.aspose.com/temporary-license/) から一時ライセンスを取得できます。

### Q5: Aspose.Tasks for .NET の包括的なドキュメントはどこで見つけられますか？

A5: ライブラリの詳細な活用方法については、Aspose のウェブサイトにある詳細な [documentation](https://reference.aspose.com/tasks/net/) を参照してください。

---

**最終更新日:** 2026-04-01  
**テスト環境:** Aspose.Tasks 24.11 for .NET  
**作成者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}