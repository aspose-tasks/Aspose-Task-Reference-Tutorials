---
title: Aspose.Tasks でのカレンダー例外の処理
linktitle: Aspose.Tasks でのカレンダー例外の処理
second_title: Aspose.Tasks .NET API
description: ステップバイステップのチュートリアルと例を使用して、Aspose.Tasks for .NET でカレンダーの例外を管理する方法を学びます。
type: docs
weight: 12
url: /ja/net/calendar-scheduling/calendar-exceptions/
---
## 導入

このチュートリアルでは、.NET Framework を使用して Aspose.Tasks でカレンダーの例外を管理する方法を検討します。カレンダーの例外を使用すると、休日や臨時休業など、通常の作業スケジュールが変更される特別な日付や期間をプロジェクト カレンダーに定義できます。 Aspose.Tasks for .NET を使用して、カレンダーの例外を処理するさまざまな方法を段階的に説明します。

## 前提条件

始める前に、次の前提条件を満たしていることを確認してください。
- C# プログラミング言語の基本的な知識。
- Visual Studio がシステムにインストールされている。
- Aspose.Tasks for .NET ライブラリがプロジェクトに追加されました。

## 名前空間のインポート

まず、プロジェクトに必要な名前空間をインポートしましょう。

```csharp
using Aspose.Tasks;
using System;


```

## ステップ 1: カレンダーの例外を削除する

カレンダーの例外を削除するには、次の手順に従います。

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    //カレンダー情報を表示する
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    //最初の例外を削除する
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

## ステップ 2: カレンダー例外の稼働時間を取得する

カレンダー例外の稼働時間を取得するには、次の手順に従います。

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    //カレンダーと例外情報を表示する
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    //作業時間を取得して詳細を表示する
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## ステップ 3: カレンダーの例外を定義する

カレンダーの例外を追加または削除するには、次の手順に従います。

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    //新しいカレンダーの例外を作成する
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    //例外の詳細を設定する
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    //日付が例外かどうかを確認する
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    //カレンダーに例外を追加する
    calendar.Exceptions.Add(exception);

    //例外が存在する場合は削除します
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    //新しい例外を追加する
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    //印刷例外
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## 結論

この記事では、Aspose.Tasks for .NET でのカレンダー例外の処理に関するさまざまな側面について説明しました。提供された手順に従うことで、プロジェクト スケジュールの例外を効果的に管理し、作業時間や特別なイベントを正確に表現できるようになります。

## よくある質問

### Q1: 1 つのカレンダーに複数の例外を追加できますか?

A1: はい、カレンダーに複数の例外を追加して、さまざまな特別な日付や期間に対応できます。

### Q2: 特定の日付が例外かどうかを確認するにはどうすればよいですか?

 A2: を使用できます。`CheckException()`特定の日付が例外に該当するかどうかを確認するメソッド。

### Q3: カレンダーから既存の例外を削除することはできますか?

 A3: はい、にアクセスして例外を削除できます。`Exceptions`カレンダーの収集と使用`Remove()`方法。

### Q4: どのようなタイプのカレンダー例外がサポートされていますか?

A4: Aspose.Tasks は、日次、週次、月次、年次の例外を含むさまざまなタイプの例外をサポートしており、例外ルールを柔軟に定義できます。

### Q5: 特定の例外日の勤務時間をカスタマイズできますか?

A5: はい、Aspose.Tasks が提供する適切なメソッドを使用して、個々の例外日のカスタム作業時間を定義できます。