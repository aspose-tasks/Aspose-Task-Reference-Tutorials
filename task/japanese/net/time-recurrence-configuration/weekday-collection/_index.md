---
title: Aspose.Tasks で平日をマスターする
linktitle: Aspose.Tasks の平日のコレクション
second_title: Aspose.Tasks .NET API
description: 平日を楽に管理できる Aspose.Tasks for .NET のパワーを実感してください。営業日をカスタマイズしたり、週末を削除したり、専用のカレンダーを簡単に作成したりできます。
type: docs
weight: 11
url: /ja/net/time-recurrence-configuration/weekday-collection/
---
## 導入
Aspose.Tasks for .NET は、プロジェクト管理データの効率的な操作を容易にする強力なライブラリです。このチュートリアルでは、Aspose.Tasks の平日のコレクションを調べて、稼働日をカスタマイズしたり、週末を削除したり、プロジェクトの要件を満たす専用のカレンダーを作成したりできるようにします。経験豊富な開発者であっても、初心者であっても、このステップバイステップのガイドでは、Aspose.Tasks for .NET で平日に作業するプロセスを順を追って説明します。
## 前提条件
チュートリアルに入る前に、次の前提条件が満たされていることを確認してください。
-  Aspose.Tasks for .NET ライブラリをインストールします。からダウンロードできます。[Aspose.Tasks for .NET ダウンロード ページ](https://releases.aspose.com/tasks/net/).
- C# プログラミング言語に精通していること。
- Visual Studio などの統合開発環境 (IDE)。
## 名前空間のインポート
まず、必要な名前空間を C# プロジェクトにインポートします。
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## ステップ 1: プロジェクト インスタンスを作成する
新しい Aspose.Tasks プロジェクトを初期化します。
```csharp
String DataDir = "Your Document Directory";
var project = new Project();
```
## ステップ 2: カレンダーにアクセスする
プロジェクト カレンダーを取得します。
```csharp
var calendar = project.Calendars.GetByName("Standard");
```
## ステップ 3: 曜日をカスタマイズする
既存の平日を消去し、デフォルトの営業日を設定します。
```csharp
calendar.WeekDays.Clear();
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
//他の平日も同様に追加してください...
```
## ステップ 4: 勤務時間を追加する
特定の平日の稼働時間を追加します。
```csharp
var fridayWorkingTimes = new List<WorkingTime> { new WorkingTime(new DateTime(2020, 4, 13, 8, 0, 0), new DateTime(2020, 4, 13, 12, 0, 0)) };
var friday = new WeekDay(DayType.Friday, fridayWorkingTimes);
calendar.WeekDays.Insert(4, friday);
```
## ステップ 5: カレンダー情報を表示する
カレンダーの詳細をコンソールに出力します。
```csharp
Console.WriteLine("Calendar: " + calendar.Name);
Console.WriteLine("Week days count: " + calendar.WeekDays.Count);
//各曜日と勤務時間を表示します...
```
## ステップ 6: 週末を削除する
平日から土曜日と日曜日を削除します。
```csharp
calendar.WeekDays.RemoveAt(5);
if (calendar.WeekDays.Contains(saturday))
{
    calendar.WeekDays.Remove(sunday);
}
```
## ステップ 7: 更新された稼働時間を表示する
週末を削除した後に更新された稼働時間を出力します。
```csharp
Console.WriteLine("Working times after weekend was removed: ");
List<WeekDay> weekDays = calendar.WeekDays.ToList();
//更新された各曜日と勤務時間を表示します...
```
## ステップ 8: 24 時間カレンダーを作成する
24 時間カレンダーを作成し、平日をコピーします。
```csharp
var hour24Calendar = project.Calendars.Add("24 Hours");
Calendar.Make24HourCalendar(hour24Calendar);
var weekDaysArray = new WeekDay[calendar.WeekDays.Count];
calendar.WeekDays.CopyTo(weekDaysArray, 0);
foreach (var weekDay in weekDaysArray)
{
    hour24Calendar.WeekDays.Add(weekDay);
}
```
## 結論
このチュートリアルでは、プロジェクト カレンダー内の平日を管理する際の Aspose.Tasks for .NET の強力な機能を検討しました。 Aspose.Tasks は、稼働日のカスタマイズから特殊な 24 時間カレンダーの作成まで、プロセスを簡素化し、プロジェクト管理における柔軟性と制御を提供します。
## よくある質問
### Q: Aspose.Tasks for .NET を他のプログラミング言語で使用できますか?
A: Aspose.Tasks は主に .NET 言語をサポートしていますが、Java 用のバージョンも提供しています。
### Q: Aspose.Tasks for .NET に利用できる無料トライアルはありますか?
 A: はい、次のサイトから無料トライアルをダウンロードできます。[Aspose.Tasks リリース ページ](https://releases.aspose.com/).
### Q: Aspose.Tasks for .NET のサポートを受けるにはどうすればよいですか?
 A: にアクセスしてください。[Aspose.Task フォーラム](https://forum.aspose.com/c/tasks/15)コミュニティ サポートが必要な場合は、サポート プランの購入を検討してください。
### Q: Aspose.Tasks for .NET の包括的なドキュメントはどこで見つけられますか?
 A: を参照してください。[Aspose.Tasks for .NET ドキュメント](https://reference.aspose.com/tasks/net/)詳細については。
### Q: Aspose.Tasks for .NET の一時ライセンスを取得するにはどうすればよいですか?
 A: 一時ライセンスは次のサイトから取得できます。[一時ライセンスのページ](https://purchase.aspose.com/temporary-license/).