---
title: Aspose.Tasks での日型コレクションの管理
linktitle: Aspose.Tasks での日型コレクションの管理
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET で日型コレクションを効率的に管理する方法を学びます。カレンダーの例外を簡単に作成、変更、操作できます。
type: docs
weight: 28
url: /ja/net/calendar-scheduling/day-type-collection/
---
## 導入

 Aspose.Tasks for .NET は、プロジェクト管理アプリケーションで週次カレンダーの例外を定義するために重要な日型コレクションを管理するための堅牢な機能を提供します。このチュートリアルでは、`DayTypeCollection`効率的に授業を行います。 

## 前提条件

チュートリアルを進める前に、次の前提条件を満たしていることを確認してください。

1. Visual Studio: システムに Visual Studio がインストールされていることを確認します。
2.  Aspose.Tasks for .NET:Aspose.Tasks for .NET ライブラリをダウンロードしてインストールします。[ここ](https://releases.aspose.com/tasks/net/).
3. C# の基本知識: C# プログラミング言語と .NET フレームワークの概念に精通していること。

## 名前空間のインポート

まず、必要な名前空間を C# プロジェクトにインポートする必要があります。

```csharp
using Aspose.Tasks;
using System;


```

ここで、提供された例を複数のステップに分解してみましょう。

## ステップ 1: プロジェクトをロードしてカレンダーにアクセスする

```csharp
var project = new Project(DataDir + "WeeklyDayTypeException.mpp");
var calendar = project.Calendars.GetByUid(1);
```

このステップでは、新しいプロジェクト インスタンスを初期化し、UID によってカレンダーを取得します。

## ステップ 2: カレンダーの例外を反復処理する

```csharp
foreach (var calendarException in calendar.Exceptions)
{
    Console.WriteLine("Exception Name: " + calendarException.Name);
    Console.WriteLine("Days of week count: " + calendarException.DaysOfWeek.Count);
    foreach (var dayType in calendarException.DaysOfWeek)
    {
        Console.WriteLine("Day type: " + dayType);
    }
    Console.WriteLine();
}
```

ここでは、各カレンダー例外を反復処理し、その名前と関連する日の種類を出力します。

## ステップ 3: カレンダーの例外を変更する

```csharp
var exc1 = calendar.Exceptions.ToList()[0];
if (!exc1.DaysOfWeek.IsReadOnly && exc1.DaysOfWeek.IndexOf(DayType.Monday) < 0)
{
    exc1.DaysOfWeek.Insert(0, DayType.Wednesday);
}

var exc2 = calendar.Exceptions.ToList()[1];
if (exc2.DaysOfWeek.Contains(DayType.Sunday))
{
    exc2.DaysOfWeek.Remove(DayType.Sunday);
}

Console.WriteLine("Remove " + exc2.DaysOfWeek[0] + " day type from exception by index...");
exc2.DaysOfWeek.RemoveAt(0);
```

この手順では、日付の種類を追加、削除、または更新してカレンダーの例外を変更する方法を示します。

## ステップ 4: 新しいカレンダーの例外を作成および操作する

```csharp
var exc4 = new CalendarException
{
    Name = "Weekly Exception 2",
    FromDate = new DateTime(2020, 4, 13),
    ToDate = new DateTime(2020, 4, 18),
    Occurrences = 3,
    Type = CalendarExceptionType.Weekly
};
exc4.DaysOfWeek.Add(DayType.Monday);
exc4.DaysOfWeek.Add(DayType.Thursday);

calendar.Exceptions.Add(exc4);

var exc3 = calendar.Exceptions.ToList()[2];

exc3.DaysOfWeek.Clear();

var dayTypes = new DayType[exc4.DaysOfWeek.Count];
exc4.DaysOfWeek.CopyTo(dayTypes, 0);

foreach (var dayType in dayTypes)
{
    exc3.DaysOfWeek.Add(dayType);
}

Console.WriteLine("Days of week for exception: " + exc3.Name);
foreach (var dayType in exc3.DaysOfWeek)
{
    Console.WriteLine("Day type: " + dayType);
}
```

この最後のステップでは、新しいカレンダーの例外を作成し、日付の種類を追加およびコピーすることで例外を操作します。

## 結論

結論として、Aspose.Tasks for .NET で日型コレクションを管理することは、プロジェクト管理アプリケーションで週次カレンダーの例外を定義および変更するために不可欠です。このチュートリアルで提供されるステップバイステップのガイドに従うことで、`DayTypeCollection`さまざまなカレンダー操作を処理するクラス。

## よくある質問

### Q1: Aspose.Tasks for .NET を使用して、プログラムでガント チャートを作成できますか?

A1: はい、Aspose.Tasks for .NET は、.NET アプリケーションでガント チャートを作成および操作するための API を提供します。

### Q2: Aspose.Tasks for .NET は .NET Core と .NET Framework の両方と互換性がありますか?

A2: はい、Aspose.Tasks for .NET は .NET Core と .NET Framework の両方をサポートしています。

### Q3: Aspose.Tasks for .NET のサポートを受けるにはどうすればよいですか?

 A3: 次のサイトにアクセスしてサポートを受けることができます。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)質問したり、他のユーザーと交流したりできます。

### Q4: Aspose.Tasks for .NET には無料トライアルが提供されていますか?

 A4: はい、Aspose.Tasks for .NET の無料トライアルを次のサイトから入手できます。[ここ](https://releases.aspose.com/).

### Q5: Aspose.Tasks for .NET の一時ライセンスを購入できますか?

 A5: はい、一時ライセンスは以下から購入できます。[Aspose ウェブサイト](https://purchase.aspose.com/temporary-license/).