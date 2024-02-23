---
title: Aspose.Tasks for .NET で平日をマスターする
linktitle: Aspose.Tasks での平日の定義
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks .NET で平日を定義する機能を試してください。詳細なチュートリアルに従って、プロジェクト カレンダーを効率的に管理したり、作業時間などをカスタマイズしたりできます。
type: docs
weight: 10
url: /ja/net/time-recurrence-configuration/defining-weekdays/
---
## 導入
Aspose.Tasks for .NET を使用してプロジェクト管理の世界に飛び込む場合、平日を理解し、操作することが重要な側面となります。プロジェクト カレンダー内の平日を効率的に管理およびカスタマイズすると、プロジェクトのタイムラインに大きな影響を与える可能性があります。このチュートリアルでは、Aspose.Tasks を使用して平日を定義するプロセスを説明し、よりわかりやすくするために段階的な手順と例を示します。
## 前提条件
この作業を開始する前に、次の前提条件を満たしていることを確認してください。
- C# プログラミング言語の基本的な理解。
-  Aspose.Tasks for .NET ライブラリがインストールされています。そうでない場合は、からダウンロードしてください[ここ](https://releases.aspose.com/tasks/net/).
## 名前空間のインポート
まず、必要な名前空間をプロジェクトにインポートします。
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
## 1. 平日の均等性を確認する
```csharp
//あなたのドキュメントディレクトリ
String DataDir = "Your Document Directory";
//プロジェクトファイルをロードする
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
//平日のアクセス
var weekDay1 = calendar.WeekDays[0];
var weekDay2 = calendar.WeekDays[1];
//さまざまなプロパティに基づいて等しいかどうかを確認します
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
//DayWorking、FromDate、ToDate、および WorkingTimes に同様の出力ステートメントを追加します。
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
```
## 2. 平日のクローンを作成する
```csharp
//プロジェクトファイルをロードする
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[0];
//平日のディープコピーを作成する
var weekDay2 = weekDay1.Clone();
//両方の平日の出力プロパティ
Console.WriteLine("WeekDay 1 Day Type: " + weekDay1.DayType);
//DayWorking、FromDate、ToDate、および WorkingTimes に同様の出力ステートメントを追加します。
Console.WriteLine("Are weekdays equal: " + weekDay1.Equals(weekDay2));
Console.WriteLine("Are weekdays equal (by reference): " + ReferenceEquals(weekDay1, weekDay2));
```
## 3. 平日のハッシュコードを取得する
```csharp
//プロジェクトファイルをロードする
var project = new Project(DataDir + "Project2.mpp");
var calendar = project.Calendars.GetByUid(1);
var weekDay1 = calendar.WeekDays[1];
var weekDay2 = calendar.WeekDays[2];
//両方の平日の出力プロパティ
//DayWorking、FromDate、ToDate、および WorkingTimes に同様の出力ステートメントを追加します。
Console.WriteLine("Week Day 1 Hash Code: {0}", weekDay1.GetHashCode());
Console.WriteLine("Week Day 2 Hash Code: {0}", weekDay2.GetHashCode());
```
## 4. 曜日を定義した新しいカレンダーを作成する
```csharp
//新しいプロジェクトを作成する
var project = new Project();
//カレンダーを定義する
var calendar = project.Calendars.Add("Calendar1");
//営業日と例外日を追加する
//FromDate と ToDate に同様の出力ステートメントを追加します。
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Monday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Tuesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Wednesday));
calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(DayType.Thursday));
//金曜日の勤務時間を設定する
//DayWorking、FromDate、ToDate、および WorkingTimes に同様の出力ステートメントを追加します。
var workingTimes = new List<WorkingTime> { new WorkingTime(9, 12), new WorkingTime(13, 16) };
var dayType = WeekDay.CastToDayType(DayOfWeek.Friday);
var weekDay = new WeekDay(dayType, workingTimes);
weekDay.DayWorking = true;
calendar.WeekDays.Add(weekDay);
```
## 5. 1 日のデフォルトの作業時間を設定する
```csharp
//新しいプロジェクトを作成する
var project = new Project();
var calendar = project.Calendars.Add("Calendar1");
calendar.WeekDays.Clear();
//月曜日から金曜日までのデフォルトの勤務時間を追加します
//DayWorking、FromDate、ToDate、および WorkingTimes に同様の出力ステートメントを追加します。
var monday = new WeekDay(DayType.Monday);
WeekDay.SetDefaultWorkingTime(monday);
calendar.WeekDays.Add(monday);
//火曜日、水曜日、木曜日、金曜日に繰り返します
//土曜日と日曜日に非稼働日を設定する
//DayWorking、FromDate、ToDate、および WorkingTimes に同様の出力ステートメントを追加します。
var saturday = new WeekDay(DayType.Saturday);
saturday.DayWorking = false;
calendar.WeekDays.Add(saturday);
var sunday = new WeekDay(DayType.Sunday);
sunday.DayWorking = false;
calendar.WeekDays.Add(sunday);
```
## 結論
このチュートリアルでは、Aspose.Tasks for .NET での平日の定義の重要な側面について説明しました。平日を管理することは、効果的なプロジェクト管理にとって重要なスキルです。提供されているサンプルを試して、プロジェクトのニーズに合わせて調整し、Aspose.Tasks の可能性を最大限に引き出してください。
## よくある質問
### 毎日のカスタムの作業時間を定義できますか?
はい、提供されている例を使用して、特定の平日のカスタム稼働時間を設定できます。
### カレンダーに複数の例外日を追加することはできますか?
絶対に。 4 番目の例のコードを変更して、追加の例外日を含めます。
### カレンダーから特定の曜日を削除するにはどうすればよいですか?
必要に応じて、Aspose.Tasks ライブラリによって提供される適切なメソッドを利用して平日を削除します。
### 平日に加えられた変更はプロジェクト ファイルに永続的に残りますか?
はい、平日への変更は保存時にプロジェクト ファイルに反映されます。
### Aspose.Tasks を他のプログラミング言語で使用できますか?
Aspose.Tasks はさまざまなプログラミング言語をサポートしていますが、ここでの例は .NET に特化しています。