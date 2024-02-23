---
title: Aspose.Tasks でのカレンダーの操作
linktitle: Aspose.Tasks でのカレンダーの操作
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET を使用して、プロジェクト カレンダーの管理、期間の計算、例外の処理を簡単に実行できます。
type: docs
weight: 10
url: /ja/net/calendar-scheduling/working-with-calendar/
---
## 導入

Aspose.Tasks for .NET は、カレンダーを操作するための強力な機能を提供し、開発者がプロジェクトのスケジュールとリソースの割り当てを効率的に管理できるようにします。このチュートリアルでは、Aspose.Tasks を利用してカレンダーを操作する方法を検討し、カレンダー情報の取得、週労働時間の定義、労働時間の計算などの重要な操作を取り上げます。

## 前提条件

始める前に、次の前提条件が設定されていることを確認してください。

- C# プログラミング言語の基本的な理解。
-  Aspose.Tasks for .NET のインストール。インストールされていない場合は、からダウンロードしてください[ここ](https://releases.aspose.com/tasks/net/).
- Visual Studio またはその他の推奨される .NET 開発環境に精通していること。

## 名前空間のインポート

コーディングを開始する前に、必要な名前空間を必ずインポートしてください。

```csharp
using Aspose.Tasks;
using System;

using Aspose.Tasks.Saving;

```

ここで、各例をステップバイステップのガイド形式で複数のステップに分けてみましょう。

## ステップ 1: カレンダー情報を取得する

プロジェクトからカレンダー情報を取得するには、次の手順に従います。

```csharp
public static void RetrieveCalendarInfo()
{
    var project = new Project(DataDir + "RetrieveCalendarInfo.mpp");

    //カレンダー情報の取得
    foreach (var calendar in project.Calendars)
    {
        if (calendar.Name == null)
        {
            continue;
        }

        Console.WriteLine("Calendar UID: " + calendar.Uid);
        Console.WriteLine("Calendar Name: " + calendar.Name);
    }
}
```

説明：
- プロジェクトファイルをロードします。
- プロジェクト内の各カレンダーを繰り返し処理します。
- 各カレンダーの UID と名前を出力します。

## ステップ 2: 勤務週間情報を読む

カレンダーから稼働週情報を読み取るには、次の手順に従います。

```csharp
public static void ReadWorkWeeksInformation()
{
    var project = new Project(DataDir + "WorkWithWorkWeekCollection.mpp");
    var calendar = project.Calendars.GetByUid(1);

    foreach (var workWeek in calendar.WorkWeeks)
    {
        var name = workWeek.Name;
        var fromDate = workWeek.FromDate;
        var toDate = workWeek.ToDate;
        Console.WriteLine("Name: " + name);
        Console.WriteLine("From Date: " + fromDate);
        Console.WriteLine("To Date: " + toDate);

        foreach (var day in workWeek.WeekDays)
        {
            foreach (var workingTime in day.WorkingTimes)
            {
                Console.WriteLine(workingTime.From);
                Console.WriteLine(workingTime.To);
            }
        }
    }
}
```

説明：
- プロジェクトファイルをロードします。
- UID でカレンダーを取得します。
- カレンダー内の各稼働週を繰り返します。
- 各勤務週の名前、開始日、終了日を印刷します。
- 各週の勤務日と勤務時間を調べます。

## ステップ 3: カレンダーのプロパティを読み取る

プロジェクト カレンダーのプロパティを読み取るには、次の手順に従います。

```csharp
public void ReadCalendarProps()
{
    var project = new Project(DataDir + "Project_GeneralCalendarProperties.xml");

    foreach (var calendar in project.Calendars)
    {
        if (calendar.Name == null)
        {
            continue;
        }

        Console.WriteLine("UID : " + calendar.Uid + " Name: " + calendar.Name);

        Console.Write("Base Calendar : ");
        Console.WriteLine(calendar.IsBaseCalendar ? "Self" : calendar.BaseCalendar.Name);

        foreach (var wd in calendar.WeekDays)
        {
            var ts = wd.GetWorkingTime();
            Console.WriteLine("Day Type: " + wd.DayType + " Hours: " + ts);
        }
    }
}
```

説明：
- プロジェクトファイルをロードします。
- プロジェクト内の各カレンダーを繰り返し処理します。
- UID、名前、および基本カレンダーかどうかを出力します。
- 曜日ごとの勤務時間を印刷します。

## ステップ 4: 労働時間を計算する

タスクの作業時間を計算するには、次の手順に従います。

```csharp
public void CalculateWorkHours()
{
    var project = new Project(DataDir + "CalculateWorkHours.mpp");
    var task = project.RootTask.Children.GetById(1);
    var taskCalendar = task.Get(Tsk.Calendar);
    var startDate = task.Get(Tsk.Start);
    var endDate = task.Get(Tsk.Finish);
    var resource = project.Resources.GetByUid(1);
    var resourceCalendar = resource.Get(Rsc.Calendar);
    TimeSpan timeSpan;
    double durationInMins = 0;
    var tempDate = startDate;

    while (tempDate < endDate)
    {
        if (taskCalendar.IsDayWorking(tempDate) && resourceCalendar.IsDayWorking(tempDate))
        {
            timeSpan = taskCalendar.GetWorkingHours(tempDate);
            durationInMins += timeSpan.TotalMinutes;
        }

        tempDate = tempDate.AddDays(1);
    }

    Console.WriteLine("Duration in Minutes = " + durationInMins);
}
```

説明：
- プロジェクトファイルをロードします。
- カレンダー、開始日、終了日などのタスクの詳細を取得します。
- 毎日を繰り返して、その日が稼働日かどうかを確認して、労働時間を計算します。
- 合計時間を分単位で合計します。

## ステップ 5: カレンダーの曜日を定義する

カレンダーの曜日を定義するには、次の手順に従います。

```csharp
public void DefineWeekdaysForCalendar()
{
    var project = new Project();
    var calendar = project.Calendars.Add("Calendar1");

    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
    calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
    calendar.WeekDays.Add(new WeekDay(DayType.Saturday));
    calendar.WeekDays.Add(new WeekDay(DayType.Sunday));

    var weekDay = new WeekDay(DayType.Friday);
    var workingTime = new WorkingTime(9, 12);
    var workingTime2 = new WorkingTime(13, 16);
    weekDay.WorkingTimes.Add(workingTime);
    weekDay.WorkingTimes.Add(workingTime2);
    weekDay.DayWorking = true;
    calendar.WeekDays.Add(weekDay);
}
```

説明：
- 新しいプロジェクトとカレンダーを作成します。
- デフォルトの稼働日 (月曜日から木曜日) と金曜日のカスタム稼働時間を追加します。
- 土曜日と日曜日を非稼働日として設定します。

## ステップ 6: 更新されたカレンダー データを MPP に書き込む

更新されたカレンダー データを MPP ファイルに書き込むには、次の手順に従います。

```csharp
public void WriteUpdatedCalendarDataToMpp()
{
    try
    {
        var project = new Project(DataDir + "project_update_test.mpp");
        var calendar = project.Calendars.GetByName("Standard");

        Calendar.MakeStandardCalendar(calendar);
        calendar.Name = "Test calendar";
        var exception = new CalendarException();
        exception.Name = "Exception 1";
        exception.FromDate = DateTime.Now;
        exception.ToDate = DateTime.Now.AddDays(2);
        exception.DayWorking = true;

        exception.WorkingTimes.Add(new WorkingTime(9, 13));
        exception.WorkingTimes.Add(new WorkingTime(14, 19));
        exception.WorkingTimes.Add(new WorkingTime(20, 21));
        calendar.Exceptions.Add(exception);

        var exception2 = new CalendarException();
        exception.Name = "Exception 2";
        exception2.FromDate = DateTime.Now.AddDays(7);
        exception2.ToDate = exception2.FromDate;
        exception2.DayWorking = false;
        calendar.Exceptions.Add(exception2);

        project.Set(Prj.Calendar, calendar);

        project.Save(OutDir + "WriteUpdatedCalendarDataToMPP_out.mpp", SaveFileFormat.Mpp);
    }
    catch (NotSupportedException ex)
    {
        Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase a full license or get a 30-day temporary license from [here](https://Purchase.aspose.com/temporary-license/.");
    }
}
```

説明：
- プロジェクトファイルをロードし、標準カレンダーを取得します。
- 例外や稼働時間などのカレンダー データを変更します。
- 更新されたプロジェクトを、変更されたカレンダー データとともに保存します。

## ステップ 7: 分割タスクの終了日を計算する

分割タスクの終了日を計算するには、次の手順に従います。

```csharp
public void CalculateSplitTaskFinishDate()
{
    var project = new Project(DataDir + "SplitTaskFinishDate.mpp");
    var task = project.RootTask.Children.GetByUid(4);
    var calendar = project.Get(Prj.Calendar);

    Console.WriteLine(
        "Start Date: " + task.Get(Tsk.Start).ToShortDateString() + "\n+ Duration 8 hours\nFinish Date: "
        + calendar.GetTaskFinishDateFromDuration(task, new TimeSpan(8, 0, 0)));
}
```

説明：
- プロジェクト ファイルをロードし、分割タスクを取得します。
- プロジェクトカレンダーを取得します。
- カスタム期間に基づいて終了日を計算します。

## ステップ 8: カレンダーの例外を取得する

カレンダーの例外に関する情報を取得するには、次の手順に従います。

```csharp
public void RetrieveCalendarExceptions()
{
    var project = new Project(DataDir + "project_RetrieveExceptions_test.mpp");

    foreach (var calendar in project.Calendars)
    {
        foreach (var exception in calendar.Exceptions)
        {
            Console.WriteLine("From: " + exception.FromDate.ToShortDateString());
            Console.WriteLine("To: " + exception.ToDate.ToShortDateString());
        }
    }
}
```

説明：
- プロジェクトファイルをロードします。
- 各カレンダーとその例外を繰り返し処理します。
- 各例外の開始日と終了日を出力します。

## ステップ 9: 基本リソース カレンダーを取得する

リソースのカレンダーの基本カレンダーを操作するには、次の手順に従います。

```csharp
public void GetBaseResourceCalendar()
{
    var project = new Project(DataDir + "ResourceCalendar.mpp");
    var resource = project.Resources.Add("Resource1");
    var calendar = project.Calendars.Add("Resource1");
    resource.Set(Rsc.Calendar, calendar);

    foreach (var rsc in project.Resources)
    {
        if (rsc.Get(Rsc.Name) != null)
        {
            Console.WriteLine(rsc.Get(Rsc.Calendar).BaseCalendar.Name);
        }
    }
}
```

説明：
- プロジェクトファイルをロードします。
- リソースとそのカレンダーを追加します。
- すべてのリソースの基本カレンダー名を出力します。

## ステップ 10: カレンダーを削除する

プロジェクトからカレンダーを削除するには、次の手順に従います。

```csharp
public void DeleteCalendar()
{
    var project = new Project(DataDir + "BrokenCalendar.mpp");
    var calendar = project.Calendars.GetByName("Broken Calendar");
    calendar.Delete();
}
```

説明：
- プロジェクトファイルをロードします。
- カレンダーを名前で取得します。
- カレンダーを削除します。

## ステップ 11: 開始日と作業時間ごとに終了日を取得する

開始日と作業時間から終了日を計算するには、次の手順に従います。

```csharp
public void GetFinishDateByStartAndWork()
{
    var project = new Project(DataDir + "Blank2010.mpp");
    var calendar = project.Calendars.GetByName("Standard");
    var start = new DateTime(2017, 10, 26, 8, 0, 0);
    var work = project.GetWork(7);
    var finish = calendar.GetFinishDateByStartAndWork(start, work);
    Console.WriteLine("Task start date: " + start);
    Console.WriteLine("Task work: " + work);
    Console.WriteLine("Task finish date: " + finish);
}
```

説明：
- プロジェクトファイルをロードします。
- 標準カレンダーを入手します。
- 開始日と作業期間を定義します。
- 開始日と作業内容に基づいて終了日を計算します。

## ステップ 12: 次の勤務日の開始を取得する

カレンダーを使用して次の営業日を開始するには、次の手順に従います。

```csharp
public void GetNextWorking

DayStart()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var nextWorkingDayStart = calendar.GetNextWorkingDayStart(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(nextWorkingDayStart);
}
```

説明：
- プロジェクトファイルをロードします。
- UID でカレンダーを取得します。
- 翌営業日の開始時刻を取得します。

## ステップ 13: 前営業日の終了日を取得する

カレンダーを使用して前営業日の終了日を取得するには、次の手順に従います。

```csharp
public void GetPreviousWorkingDayEnd()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var previousWorkingDayEnd = calendar.GetPreviousWorkingDayEnd(new DateTime(2020, 4, 10, 13, 0, 0));
    Console.WriteLine(previousWorkingDayEnd);
}
```

説明：
- プロジェクトファイルをロードします。
- UID でカレンダーを取得します。
- 前営業日の終了時刻を取得します。

## ステップ 14: 終了日と期間から開始日を取得する

終了日および期間ごとに開始日を取得するには、次の手順に従います。

```csharp
public void GetStartDateFromFinishAndDuration()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var startDate = calendar.GetStartDateFromFinishAndDuration(new DateTime(2020, 4, 10, 9, 0, 0), project.GetDuration(16, TimeUnitType.Hour));
    Console.WriteLine(startDate);
}
```

説明：
- プロジェクトファイルをロードします。
- UID でカレンダーを取得します。
- 終了日と期間から開始日を計算します。

## ステップ 15: 労働時間を取得する

特定の日付の稼働時間を取得するには、次の手順に従います。

```csharp
public void GetWorkingHours()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingHours = calendar.GetWorkingHours(new DateTime(2020, 4, 10));
    Console.WriteLine(workingHours.Hours);
}
```

説明：
- プロジェクトファイルをロードします。
- UID でカレンダーを取得します。
- 指定した日付の稼働時間を取得します。

## ステップ 16: 作業時間を取得する

特定の日付の稼働時間を取得するには、次の手順に従います。

```csharp
public void GetWorkingTimes()
{
    var project = new Project(DataDir + "Project1.mpp");
    var calendar = project.Calendars.GetByUid(1);
    var workingTimes = calendar.GetWorkingTimes(new DateTime(2020, 4, 8, 8, 0, 0));

    foreach (var workingTime in workingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
}
```

説明：
- プロジェクトファイルをロードします。
- UID でカレンダーを取得します。
- 指定した日付の稼働時間を取得します。

## 結論

Aspose.Tasks for .NET でカレンダーを操作することは、プロジェクトのスケジュールを効果的に管理するために重要です。提供されている例とステップバイステップのガイドを使用すると、カレンダー データを簡単に操作し、タスクの期間を計算し、例外を効率的に処理できます。これらの機能をアプリケーションに統合することで、プロジェクト管理プロセスを合理化し、正確なスケジュールを確保できます。

## よくある質問

### Q1: Aspose.Tasks for .NET を使用するにはライセンスが必要ですか?

 A1: はい、アプリケーションで Aspose.Tasks for .NET を利用するには有効なライセンスが必要です。フルライセンスを購入することも、30 日間の一時ライセンスを次のサイトから取得することもできます。[ここ](https://purchase.aspose.com/temporary-license/).

### Q2: カレンダーの例外をプログラムで変更できますか?

A2: はい、Aspose.Tasks for .NET API を使用して、プログラムでカレンダーの例外を追加、更新、または削除できます。

### Q3: カスタム期間でタスクの終了日を計算するにはどうすればよいですか?

 A3: Aspose.Tasks for .NET には次のようなメソッドが用意されています。`GetTaskFinishDateFromDuration()`カスタム期間に基づいてタスクの終了日を計算します。

### Q4: 夜勤カレンダーなどのカスタムカレンダーを作成することは可能ですか?

A4: はい、Aspose.Tasks for .NET API を使用して、夜勤カレンダーなどのカスタム カレンダーを作成できます。

### Q5: カレンダーの例外に関する情報をプロジェクト ファイルから取得できますか?

A5: はい、Aspose.Tasks for .NET を使用すると、プロジェクト ファイルからカレンダーの例外に関する情報を簡単に取得できます。