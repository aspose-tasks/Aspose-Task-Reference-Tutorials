---
title: Aspose.Tasks のカレンダー例外のコレクション
linktitle: Aspose.Tasks のカレンダー例外のコレクション
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks を使用して .NET プロジェクトでカレンダー例外を効率的に処理し、正確なスケジュールとリソース管理を確保する方法を学びます。
type: docs
weight: 13
url: /ja/net/calendar-scheduling/calendar-exception-collection/
---
## 導入

プロジェクト管理では、正確なスケジュール設定が成功に不可欠です。ただし、実際のシナリオでは、休日、特別なイベント、またはその他の要因により、標準スケジュールからの逸脱が必要になることがよくあります。 Aspose.Tasks for .NET は、カレンダー例外コレクション機能を通じてこのような例外を管理するための堅牢なソリューションを提供します。このチュートリアルでは、この機能を利用するプロセスを段階的に説明します。

## 前提条件

チュートリアルに進む前に、次の前提条件を満たしていることを確認してください。

1.  Aspose.Tasks for .NET: ライブラリがインストールされていることを確認してください。ダウンロードできます[ここ](https://releases.aspose.com/tasks/net/).
2. C# の基本知識: C# プログラミング言語に精通していると、例を理解するのに役立ちます。
3. 開発環境: Visual Studio や JetBrains Rider など、好みの開発環境をセットアップします。

## 名前空間のインポート

Aspose.Tasks for .NET の使用を開始する前に、必要な名前空間をプロジェクトにインポートする必要があります。この手順により、カレンダーの例外を管理するために必要なクラスとメソッドにアクセスできるようになります。

```csharp
using Aspose.Tasks;
using System;
using System.Collections.Generic;


```

ここで、提供された例を複数のステップに分けてみましょう。

## ステップ 1: プロジェクトをロードしてカレンダーを取得する

```csharp
var project = new Project(DataDir + "project_update_test.mpp");
var calendar = project.Calendars.GetByUid(3);
```

このステップでは、プロジェクト ファイルをロードし、UID によって目的のカレンダーを取得します。

## ステップ 2: 既存の例外をクリアし、標準カレンダーを設定する

```csharp
calendar.Exceptions.Clear();
Calendar.MakeStandardCalendar(calendar);
```

この手順では、カレンダーから既存の例外をすべてクリアし、標準構成に設定します。

## ステップ 3: 労働時間の例外を定義して追加する

```csharp
var exception = new CalendarException();
exception.FromDate = new DateTime(2020, 3, 30, 8, 0, 0);
exception.ToDate = new DateTime(2020, 4, 3, 17, 0, 0);
exception.DayWorking = true;
exception.Name = "Exception 1";

var wt1 = new WorkingTime(9, 13);
var wt2 = new WorkingTime(14, 19);

exception.WorkingTimes.Add(wt1);
exception.WorkingTimes.Add(wt2);
calendar.Exceptions.Add(exception);
```

この手順では、特定の開始日と終了日、およびそれらの日付内の稼働時間を持つ稼働時間例外を定義し、カレンダーに追加します。

## ステップ 4: 非稼働時間の例外を定義および追加する

```csharp
var nonWorkingExceptions = new CalendarException[2];
nonWorkingExceptions[0] = new CalendarException();
nonWorkingExceptions[0].FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
nonWorkingExceptions[0].ToDate = new DateTime(2020, 4, 18, 17, 0, 0);
nonWorkingExceptions[0].DayWorking = false;
nonWorkingExceptions[0].Name = "Exception 2";

//必要に応じて例外を追加します

calendar.Exceptions.AddRange(nonWorkingExceptions);
```

このステップでは、休日などの非稼働時間の例外を定義し、カレンダーに追加します。

## ステップ 5: カレンダーの例外を表示する

```csharp
Console.WriteLine("Exceptions of calendar {0}: ", calendar.Exceptions.ParentCalendar.Name);
Console.WriteLine("Exceptions count: {0}", calendar.Exceptions.Count);
Console.WriteLine();
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Name: " + calendarException.Name);
    Console.WriteLine("From Date: " + calendarException.FromDate);
    Console.WriteLine("To Date: " + calendarException.ToDate);
    Console.WriteLine("Is day working: " + calendarException.DayWorking);
    Console.WriteLine();
}
```

このステップでは、追加されたカレンダーの例外とその詳細が表示されます。

## ステップ 6: すべての例外を削除する

```csharp
Console.WriteLine("Remove calendar exceptions...");
List<CalendarException> exceptions = calendar.Exceptions.ToList();
foreach (var calendarException in exceptions)
{
    calendar.Exceptions.Remove(calendarException);
}
```

最後に、このステップではカレンダーからすべての例外を削除します。

## 結論

カレンダーの例外を管理することは、プロジェクトのスケジュールを正確に行うために非常に重要です。 Aspose.Tasks for .NET は、カレンダー例外コレクションを含む包括的な機能セットを提供することで、このタスクを簡素化します。このチュートリアルで概説されている手順に従うことで、プロジェクト内のさまざまなスケジュール シナリオを効率的に処理できます。

## よくある質問

### Q1: 1 つのカレンダーに複数の例外を追加できますか?

 A1: はい、カレンダーに複数の例外を追加できます。`AddRange`方法。

### Q2: 毎週の休日など、繰り返し発生する例外はどのように処理すればよいですか?

A2: カスタム ロジックを使用して、定期的な例外をプログラムで計算し、カレンダーに追加できます。

### Q3: カレンダーの例外を外部ソースからインポートすることは可能ですか?

A3: はい、データベースや CSV ファイルなどの外部ソースからカレンダーの例外を読み取り、プロジェクトに統合できます。

### Q4: カレンダーに重複する例外がある場合はどうなりますか?

A4: Aspose.Tasks for .NET を使用すると、プロジェクトの要件に基づいて優先順位を定義したり競合を解決したりすることで、重複する例外を処理できます。

### Q5: 例外的に毎日の勤務時間をカスタマイズできますか?

A5: はい、特定のスケジュールのニーズに対応するために、例外内の個々の日にカスタムの稼働時間を指定できます。