---
title: Aspose.Tasks での毎日の作業の繰り返し
linktitle: Aspose.Tasks での毎日の作業の繰り返し
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して、Microsoft Project ファイルに毎日繰り返されるタスクを作成する方法を学びます。生産性と組織力を簡単に向上させます。
type: docs
weight: 26
url: /ja/net/calendar-scheduling/daily-work-repetition/
---
## 導入

Aspose.Tasks for .NET は、開発者が Microsoft Project ファイルを簡単に操作できるようにする強力なライブラリです。その無数の機能の中には、繰り返し発生するタスクを効率的に処理する機能があります。このチュートリアルでは、プロジェクト内で毎日繰り返すタスクを作成できる日次作業繰り返し機能について詳しく説明します。

## 前提条件

このチュートリアルに入る前に、次のものが揃っていることを確認してください。

- C# と .NET Framework の基本的な知識。
- Visual Studio がシステムにインストールされている。
-  .NET ライブラリの Aspose.Tasks。ダウンロードできます[ここ](https://releases.aspose.com/tasks/net/).
- Microsoft Project ファイル (.mpp) に精通していること。

## 名前空間のインポート

始める前に、必要な名前空間をインポートしていることを確認してください。

```csharp
using Aspose.Tasks;
using System;
using System.Diagnostics.CodeAnalysis;


```

提供された例を複数のステップに分けてみましょう。

## ステップ 1: プロジェクト ファイルをロードする

まず、次のコマンドを使用してプロジェクト ファイルをロードします。`Project`クラス：

```csharp
var project = new Project(DataDir + "Project1.mpp");
```

## ステップ 2: 定期的なタスクのパラメータを定義する

定期的なタスクのパラメータを定義します。

```csharp
var parameters = new RecurringTaskParameters
{
    TaskName = "New recurrent task",
    RecurrencePattern = new DailyRecurrencePattern
    {
        RecurrenceRange = new EndAfterRecurrenceRange
        {
            Start = new DateTime(2018, 1, 1, 8, 0, 0),
            OccurrenceNumber = 9
        },
        Repetition = new DailyWorkRepetition { RepetitionInterval = 1 }
    },
    Duration = project.GetDuration(1, TimeUnitType.Hour)
};
```

## ステップ 3: カレンダーとタスクの開始日を設定する

タスクのカレンダーと開始日を設定します。

```csharp
parameters.SetCalendar(project, "Standard");
var task = project.RootTask.Children.Add(parameters);
task.Set(Tsk.Start, new DateTime(2020, 4, 27, 8, 0, 0));
```

## 結論

このチュートリアルでは、Aspose.Tasks for .NET を利用して毎日の作業を繰り返す繰り返しタスクを作成する方法を検討しました。これらの手順に従うことで、プロジェクト内のタスクを効率的に管理し、スムーズなワークフローと組織化を実現できます。

## よくある質問

### Q1: 繰り返しパターンをさらにカスタマイズできますか?

A1: はい、開始日、発生回数、繰り返し間隔などのパラメータを調整して、要件に応じて繰り返しパターンを調整できます。

### Q2: Aspose.Tasks は Microsoft Project のさまざまなバージョンと互換性がありますか?

A2: はい、Aspose.Tasks はさまざまなバージョンの Microsoft Project をサポートし、互換性とシームレスな統合を保証します。

### Q3: 定期的なタスクの例外や変更はどのように処理すればよいですか?

A3: Aspose.Tasks は、定期的なタスク内の例外と変更を管理するための堅牢な機能を提供し、柔軟性とカスタマイズを可能にします。

### Q4: プロジェクトを別の形式にエクスポートできますか?

A4: もちろん、Aspose.Tasks は、PDF、HTML、XML などのさまざまな形式へのプロジェクトのエクスポートのサポートを提供し、共有やコラボレーションを容易にします。

### Q5: Aspose.Tasks は技術サポートを提供していますか?

A5: はい、Aspose.Tasks はフォーラムを通じて包括的な技術サポートを提供しており、そこで支援を求めたり、経験を共有したり、他のユーザーと交流したりすることができます。