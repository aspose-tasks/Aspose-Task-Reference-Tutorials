---
date: 2026-04-13
description: Aspose.Tasks for .NETでカレンダー例外を削除する方法と、ASP.NETのカレンダー予約管理時に例外日付を確認する方法を学びましょう。
keywords:
- delete calendar exception
- asp.net calendar scheduling
- check exception date
linktitle: Aspose.Tasksでカレンダー例外を削除
second_title: Aspose.Tasks .NET API
title: Aspose.Tasksでカレンダー例外を削除
url: /ja/net/calendar-scheduling/calendar-exceptions/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks でカレンダー例外を削除する

## はじめに

このチュートリアルでは、**カレンダー例外を削除**し、Aspose.Tasks の .NET フレームワークを使用して他のカレンダー例外を管理する方法を学びます。カレンダー例外を使用すると、祝日や一時的な閉鎖、通常の作業スケジュールが変更される特別な期間をモデル化できます。例外の追加、クエリ、削除を理解することは、特に **ASP.NET カレンダー スケジューリング** シナリオで正確なプロジェクトスケジューリングを行うために重要です。

## クイック回答
- **例外を削除する主なメソッドは何ですか？** `CalendarException` オブジェクトの `Delete()` メソッドを使用します。  
- **どのクラスが日付を例外と照合しますか？** `CalendarException.CheckException()` — **例外日付のチェック** に便利です。  
- **コード実行にライセンスは必要ですか？** はい、実稼働環境では有効な Aspose.Tasks ライセンスが必要です。  
- **1 つのカレンダーに複数の例外を追加できますか？** もちろんです。`Exceptions` コレクションは多数のエントリをサポートします。  
- **対応している .NET バージョンは？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。

## カレンダー例外とは？

**カレンダー例外** は、通常の作業カレンダーからの逸脱を表します。つまり「この日付では作業時間が異なる、または全く作業しない」というルールです。Aspose.Tasks では、各例外に独自の作業時間、繰り返しパターン、そしてその日が作業日かどうかを示すフラグを設定できます。

## ASP.NET カレンダー スケジューリングでカレンダー例外を管理する理由

- **正確なタイムライン:** プロジェクトは自動的に祝日や特別な閉鎖を考慮し、非現実的な締め切りを防ぎます。  
- **柔軟性:** 日次、週次、月次、年次のパターンを定義でき、実際のビジネスカレンダーに合わせられます。  
- **自動化:** 例外日付をプログラムでチェックすることで、ASP.NET アプリケーション内に動的なスケジューリング ロジックを構築できます。

## 前提条件

- C# の基本的な知識。  
- Visual Studio（最新バージョンのいずれか）。  
- プロジェクトに追加された Aspose.Tasks for .NET ライブラリ（NuGet または手動参照）。

## 名前空間のインポート

まず、必要な名前空間をインポートします。

```csharp
using Aspose.Tasks;
using System;
```

## 手順 1: カレンダー例外の削除

不要な例外を削除するのは簡単です。以下のコードはプロジェクトを読み込み、最初のカレンダーを選択し、基本情報を表示し、最初の例外を削除して、更新後の件数を示します。

```csharp
public void CalendarExceptionDelete()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];

    // Display calendar information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);

    // Remove the first exception
    calendar.Exceptions[0].Delete();

    Console.WriteLine("Calendar Exception Count after Deletion: " + calendar.Exceptions.Count);
}
```

> **プロのヒント:** `Delete()` を呼び出す前に、例外インデックスが存在するか必ず確認して `IndexOutOfRangeException` を回避してください。

## 手順 2: カレンダー例外の作業時間取得

例外に定義された作業時間を確認したい場合は `GetWorkingTime()` を使用します。この例では `CheckException` を使って **例外日付のチェック** も行っています。

```csharp
[Test]
public void CalendarExceptionGetWorkingTime()
{
    var project = new Project(DataDir + "CalendarExceptions.mpp");
    var calendar = project.Calendars.ToList()[0];
    var exception = calendar.Exceptions[0];

    // Display calendar and exception information
    Console.WriteLine("Calendar Name: " + calendar.Name);
    Console.WriteLine("Calendar Exception Count: " + calendar.Exceptions.Count);
    Console.WriteLine("Calendar Exception Name: " + exception.Name);

    // Get working time and display details
    var workingTime = exception.GetWorkingTime();
    Console.WriteLine("Exception Working Time: " + workingTime);

    foreach (var time in exception.WorkingTimes)
    {
        Console.WriteLine("Working Time Start: " + time.From);
        Console.WriteLine("Working Time Finish: " + time.To);
    }
}
```

## 手順 3: カレンダー例外の定義

以下は、**追加**、**チェック**、**削除** の一連の操作を示す完全な手順です。特定の瞬間に対して **例外日付のチェック** を行うために `CheckException` を使用している点に注目してください。

```csharp
[Test]
public void DefineCalendarExceptions()
{
    var project = new Project(DataDir + "project_test.mpp");
    var calendar = project.Calendars.Add("Calendar1");

    // Create a new calendar exception
    var exception = new CalendarException();
    exception.Name = "New Calendar Exception";
    // Set exception details
    exception.EnteredByOccurrences = false;
    exception.FromDate = new DateTime(2009, 12, 24, 0, 0, 0);
    exception.ToDate = new DateTime(2009, 12, 31, 23, 59, 0);
    exception.Type = CalendarExceptionType.Daily;
    exception.Month = Month.December;
    exception.DayWorking = false;

    // Check if a date is an exception (check exception date)
    Console.WriteLine("Is date an exception date: " + exception.CheckException(new DateTime(2009, 12, 26, 8, 0, 0)));

    // Add the exception to the calendar
    calendar.Exceptions.Add(exception);

    // Remove an exception if exists
    var cal = project.Calendars.ToList()[0];
    if (cal.Exceptions.Count > 1)
    {
        var excToRemove = cal.Exceptions[0];
        cal.Exceptions.Remove(excToRemove);
    }

    // Add a new exception
    var exception2 = new CalendarException();
    exception2.FromDate = new System.DateTime(2009, 1, 1);
    exception2.ToDate = new System.DateTime(2009, 1, 3);
    cal.Exceptions.Add(exception2);

    // Print exceptions
    foreach (var exc in cal.Exceptions)
    {
        Console.WriteLine("Name: " + exc.Name);
        Console.WriteLine("From: " + exc.FromDate.ToShortDateString());
        Console.WriteLine("To: " + exc.ToDate.ToShortDateString());
    }
}
```

## 一般的な問題とヒント

| 問題 | 理由 | 解決策 |
|------|------|--------|
| **`IndexOutOfRangeException` が発生する** | 存在しない例外を削除しようとした場合。 | `Delete()` を呼び出す前に `calendar.Exceptions.Count` がインデックスより大きいことを確認してください。 |
| **作業時間が正しく設定されない** | `DayWorking` または `WorkingTimes` が正しく設定されていない。 | `exception.WorkingTimes.Add(new WorkingTime(...))` を使用して明示的な期間を定義してください。 |
| **例外が認識されない** | `CheckException` が `false` を返すのは、日付が定義された範囲外だから。 | `FromDate`/`ToDate` と `Type`（Daily、Weekly など）を再確認してください。 |

## よくある質問

**Q: 1 つのカレンダーに複数の例外を追加できますか？**  
A: はい、祝日、メンテナンスウィンドウ、その他の特別なスケジュール ルールを表すために、必要なだけ例外を追加できます。

**Q: 特定の日の **例外日付のチェック** はどうやって行いますか？**  
A: `CalendarException` インスタンスの `CheckException(DateTime date)` メソッドを使用します。指定した日付が例外範囲内にある場合は `true` が返ります。

**Q: カレンダーから既存の例外を削除することは可能ですか？**  
A: もちろんです。`Exceptions` コレクションにアクセスし、`Remove()` を呼び出すか、対象の `CalendarException` オブジェクトで `Delete()` を実行してください。

**Q: サポートされているカレンダー例外のタイプは何ですか？**  
A: Aspose.Tasks は Daily、Weekly、Monthly、Yearly の例外タイプをサポートしており、ほぼすべての繰り返しパターンをモデル化できます。

**Q: 特定の例外日付に対して作業時間をカスタマイズできますか？**  
A: はい。例外を作成した後、その `WorkingTimes` コレクションに `WorkingTime` オブジェクトを追加して、その日の開始時刻と終了時刻を定義します。

## 結論

**カレンダー例外の削除** 操作の全ライフサイクルを、既存例外の確認から新規追加、日付チェックまで順に解説しました。これらのテクニックを習得すれば、プロジェクトスケジュールが実際のカレンダーを正確に反映し、ASP.NET カレンダー スケジューリング実装が堅牢で信頼性の高いものになります。

---

**最終更新日:** 2026-04-13  
**テスト環境:** Aspose.Tasks for .NET（最新リリース）  
**作成者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}