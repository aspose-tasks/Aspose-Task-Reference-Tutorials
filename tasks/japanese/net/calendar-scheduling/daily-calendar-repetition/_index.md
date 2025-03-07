---
title: Aspose.Tasks での日次カレンダーの繰り返し
linktitle: Aspose.Tasks での日次カレンダーの繰り返し
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET で毎日のカレンダーを繰り返す繰り返しタスクを作成する方法を学びます。プロジェクト管理の効率を簡単に向上させます。
weight: 25
url: /ja/net/calendar-scheduling/daily-calendar-repetition/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks での日次カレンダーの繰り返し

## 導入

 Aspose.Tasks for .NET は、タスクとプロジェクトをプログラムで管理するための強力なツール セットを提供します。その注目すべき機能の 1 つは、毎日のカレンダーの繰り返しを効率的に処理できることです。このチュートリアルでは、`DailyCalendarRepetition`クラスを他の関連クラスとともに使用して、指定されたカレンダーに基づいて毎日繰り返される繰り返しタスクを作成します。

## 前提条件

始める前に、次の設定がされていることを確認してください。

1. インストール: Aspose.Tasks for .NET がインストールされていることを確認してください。そうでない場合は、からダウンロードできます[ここ](https://releases.aspose.com/tasks/net/).

2. 名前空間のインポート: 必要な名前空間をプロジェクトにインポートします。

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;

using Aspose.Tasks.Saving;

```

## ステップ 1: プロジェクトを初期化する

まず、既存のプロジェクトをロードするか、作業する新しいプロジェクトを作成する必要があります。

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## ステップ 2: カレンダーを定義する

次に、24 時間のカレンダーを作成し、プロジェクトに関連付けます。

```csharp
var calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(calendar);
```

## ステップ 3: 定期的なタスクのパラメータを設定する

次に、定期的なタスクのパラメーターを設定しましょう。その名前、期間、繰り返しパターン、および範囲を定義します。

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "t1",
    Duration = project.GetDuration(1, TimeUnitType.Day),
    RecurrencePattern = new DailyRecurrencePattern
    {
        Repetition = new DailyCalendarRepetition { RepetitionInterval = 1 },
        RecurrenceRange = new EndByRecurrenceRange
        {
            Start = new DateTime(2018, 7, 2, 0, 0, 0),
            Finish = new DateTime(2018, 7, 8, 16, 0, 0)
        }
    }
};
```

## ステップ 4: タスクのカレンダーを設定する

定義したカレンダーをタスクに関連付けます。

```csharp
parameters.SetCalendar(project, "24 Hours");
```

## ステップ 5: タスクをプロジェクトに追加する

パラメータが定義されたタスクをプロジェクトに追加します。

```csharp
project.RootTask.Children.Add(parameters);
```

## ステップ 6: プロジェクトを保存する

最後に、定期的なタスクを追加してプロジェクトを保存します。

```csharp
project.Save(OutDir + "CanAddRecurringTask_Days_CalendarDays_24h_Test_out.mpp", SaveFileFormat.Mpp);
```

これで、Aspose.Tasks for .NET を使用して、24 時間カレンダーに基づいて毎日繰り返すように設定された定期タスクを持つプロジェクトが正常に作成されました。

## 結論

このチュートリアルでは、Aspose.Tasks for .NET を利用して毎日のカレンダーの繰り返しを効率的に処理する方法を説明しました。これらの手順に従うことで、定期的なタスクをプロジェクトにシームレスに統合し、生産性と組織性を向上させることができます。

## よくある質問

### Q1: 各繰り返しの長さをカスタマイズできますか?

A1: はい、コード内のパラメーターを変更することで、要件に応じて各繰り返しの長さを調整できます。

### Q2: 同じプロジェクト内のタスクごとに異なるカレンダーを設定することはできますか?

A2: もちろん、Aspose.Tasks を使用すると、特定のカレンダーを個々のタスクに割り当てることができ、柔軟なスケジュール設定が可能になります。

### Q3: Aspose.Tasks は毎日以外の他の繰り返しパターンをサポートしていますか?

A3: はい、Aspose.Tasks は、週次、月次、年次などの幅広い繰り返しパターンを提供し、プロジェクトの多様なニーズに対応します。

### Q4: Aspose.Tasks を使用して作成された定期的なタスクを視覚化できますか?

A4: 確かに、Aspose.Tasks には、定期的なタスクを効果的に分析および追跡するのに役立つ視覚化オプションが用意されています。

### Q5: Aspose.Tasks の試用版はありますか?

 A5: はい、Aspose.Tasks の無料トライアルを利用できます。[ここ](https://releases.aspose.com/)購入する前にその機能を調べてください。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
