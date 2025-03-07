---
title: Aspose.Tasks で週労働時間をカスタマイズする
linktitle: Aspose.Tasks の週間労働時間のコレクション
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks for .NET で週の労働時間をカスタマイズする方法を学びます。パーソナライズされたプロジェクト カレンダーを作成するためのステップバイステップ ガイド。ダウンロード中！
weight: 17
url: /ja/net/time-recurrence-configuration/workweek-collection/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks で週労働時間をカスタマイズする

## 導入
Aspose.Tasks for .NET を使用してカスタム週間勤務時間を作成するチュートリアルへようこそ。このステップバイステップのガイドでは、プロジェクト内のカレンダーに対して個人用の週労働時間を定義するプロセスを説明します。 Aspose.Tasks は、開発者が .NET アプリケーションで Microsoft Project ドキュメントを効率的に操作できるようにする強力なライブラリです。
## 前提条件
チュートリアルに進む前に、次の前提条件を満たしていることを確認してください。
1. Visual Studio: マシンに Visual Studio がインストールされていることを確認してください。
2.  Aspose.Tasks for .NET: Aspose.Tasks ライブラリをダウンロードしてインストールします。ダウンロードリンクが見つかります[ここ](https://releases.aspose.com/tasks/net/).
3. C# の基本知識: C# プログラミング言語の基本を理解します。
## 名前空間のインポート
C# プロジェクトで、必要な名前空間を必ずインポートしてください。
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## ステップ 1: プロジェクトとカレンダーを作成する
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Standard");
Calendar.MakeStandardCalendar(calendar);
```
## ステップ 2: カスタム週労働時間を定義する
```csharp
var customWorkWeek = new WorkWeek();
customWorkWeek.Name = "My Work Week";
customWorkWeek.FromDate = new DateTime(2020, 4, 13, 8, 0, 0);
customWorkWeek.ToDate = new DateTime(2020, 4, 17, 17, 0, 0);
```
## ステップ 3: 営業日を設定する
```csharp
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
customWorkWeek.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Friday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Saturday));
customWorkWeek.WeekDays.Add(new WeekDay(DayType.Sunday));
calendar.WorkWeeks.Add(customWorkWeek);
```
## ステップ 4: 稼働週情報を表示する
```csharp
Console.WriteLine("Work Weeks Count: " + calendar.WorkWeeks.Count);
foreach (var workWeek in calendar.WorkWeeks)
{
    Console.WriteLine("Name: " + workWeek.Name);
    Console.WriteLine("Parent calendar name: " + calendar.Name);
    Console.WriteLine("From Date: " + workWeek.FromDate);
    Console.WriteLine("To Date: " + workWeek.ToDate);
    List<WeekDay> weekDays = workWeek.WeekDays.ToList();
    foreach (var day in weekDays)
    {
        Console.WriteLine(day.DayType.ToString());
        foreach (var workingTime in day.WorkingTimes)
        {
            Console.WriteLine(workingTime.From);
            Console.WriteLine(workingTime.To);
        }
    }
    Console.WriteLine();
}
```
この包括的なガイドにより、Aspose.Tasks for .NET を使用してカスタム週間労働時間を効率的に作成および管理できるようになります。
## 結論
結論として、Aspose.Tasks for .NET は、カスタムの作業週間を含むプロジェクト カレンダーを処理するための堅牢なソリューションを提供します。このチュートリアルに従うことで、プロジェクト内のカスタム稼働週に関する情報を作成および表示する方法を学習しました。
## よくある質問
### 1 つのプロジェクトに複数のカスタム作業週を含めることはできますか?
はい、プロジェクト カレンダーに複数のカスタム作業週間を追加できます。
### 既存の勤務週を変更するにはどうすればよいですか?
提供されているものを使用します`WorkWeek`既存の週の労働時間を変更するためのプロパティとメソッド。
### Aspose.Tasks は .NET Core と互換性がありますか?
はい、Aspose.Tasks は .NET Core をサポートしています。
### カスタム作業週間を含むプロジェクトを Microsoft Project ファイル形式にエクスポートできますか?
もちろん、Aspose.Tasks を使用すると、Microsoft Project を含むさまざまな形式でプロジェクトを保存できます。
### Aspose.Tasks 関連のクエリのサポートはどこに問い合わせればよいですか?
訪問[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)あらゆるサポートや援助のために。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
