---
title: Aspose.Tasks での毎月の繰り返しパターンの処理
linktitle: Aspose.Tasks での毎月の繰り返しパターンの処理
second_title: Aspose.Tasks .NET API
description: このステップバイステップのチュートリアルで、Aspose.Tasks for .NET で毎月の繰り返しパターンを処理する方法を学習します。
type: docs
weight: 18
url: /ja/net/advanced-concepts/monthly-recurrence-patterns/
---
## 導入

Aspose.Tasks for .NET は、開発者が Microsoft Project ファイルをプログラムで操作できるようにする強力な API です。それが提供する重要な機能の 1 つは、繰り返し発生するタスクを効率的に処理する機能です。このチュートリアルでは、Aspose.Tasks を使用して毎月の繰り返しパターンを操作する方法を段階的に詳しく説明します。

## 前提条件

始める前に、次の前提条件がインストールされていることを確認してください。

## 名前空間のインポート

まず、必要な名前空間が .NET プロジェクトにインポートされていることを確認してください。

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;
```

ここで、毎月の繰り返しパターンを処理するプロセスを複数のステップに分けてみましょう。

## ステップ 1: プロジェクトを初期化する

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## ステップ 2: 定期的なタスクのパラメータを設定する

タスク名、期間、繰り返しパターンなど、繰り返しタスクのパラメータを定義します。

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

## ステップ 3: プロジェクトにパラメータを追加する

```csharp
project.RootTask.Children.Add(parameters);
```

## ステップ 4: プロジェクトを保存する

変更したプロジェクトを定期的なタスクとともに保存します。

```csharp
project.Save(OutDir + "CanAddRecurringTask_Months_EndByRecurrenceRange_Test_out.mpp", SaveFileFormat.Mpp);
```

## 結論

Aspose.Tasks for .NET での毎月の繰り返しパターンの処理は簡単かつ効率的です。このチュートリアルで概説されている手順に従うことで、特定の月次間隔と繰り返し範囲を持つ繰り返しタスクを簡単に作成できます。

## よくある質問

### Q1: Aspose.Tasks は、Microsoft Project ファイルのすべてのバージョンと互換性がありますか?

A1: Aspose.Tasks は、MPP、MPT、XML、MPX など、さまざまなバージョンの Microsoft Project ファイルをサポートしています。

### Q2: 繰り返しパターンをさらにカスタマイズできますか?

A2: はい、Aspose.Tasks には、日次、週次、月次、年次などの繰り返しパターンをカスタマイズするための広範なオプションが用意されています。

### Q3: Aspose.Tasks に利用できる無料トライアルはありますか?

 A3: はい、Web サイトから Aspose.Tasks の無料トライアルを入手できます。[ここ](https://releases.aspose.com/).

### Q4: Aspose.Tasks のサポートを受けるにはどうすればよいですか?

 A4: 支援を求めたり、議論に参加したりできます。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15).

### Q5: Aspose.Tasks のライセンスはどこで購入できますか?

 A5: Aspose.Tasks のライセンスは Web サイトから購入できます。[ここ](https://purchase.aspose.com/buy)