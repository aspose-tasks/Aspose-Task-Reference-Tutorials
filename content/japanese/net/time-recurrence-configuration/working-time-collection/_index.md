---
title: Aspose.Tasks で作業時間をマスターする
linktitle: Aspose.Tasks の作業時間のコレクション
second_title: Aspose.Tasks .NET API
description: プロジェクトのタイムラインを効率的に管理する際の Aspose.Tasks for .NET の機能を試してください。カレンダーをカスタマイズし、作業時間を設定し、プロジェクトを簡単に合理化します。
type: docs
weight: 14
url: /ja/net/time-recurrence-configuration/working-time-collection/
---
## 導入
Aspose.Tasks for .NET で作業時間を管理する技術を習得したいと考えていますか?これ以上探さない！このステップバイステップ ガイドでは、Aspose.Tasks を使用した作業時間収集の複雑さを詳しく説明し、カスタム カレンダーを効率的に処理し、プロジェクトのタイムラインを合理化できるようにします。
## 前提条件
この作業を開始する前に、次の前提条件が満たされていることを確認してください。
-  Aspose.Tasks for .NET ライブラリ: Aspose.Tasks for .NET ライブラリを次の場所からダウンロードしてインストールします。[Aspose.Tasks リリースページ](https://releases.aspose.com/tasks/net/).
- 作業環境: 適切な開発環境をセットアップします。できれば .NET 互換の IDE を使用します。
## 名前空間のインポート
プロジェクトで、Aspose.Tasks 機能にアクセスするために必要な名前空間をインポートします。
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    
```
ここで、スムーズな学習体験を確保するために、チュートリアルを複数のステップに分けてみましょう。
## ステップ 1: カスタム カレンダーを作成する
まず、新しいプロジェクトを作成し、それにカスタム カレンダーを追加します。
```csharp
var project = new Project();
var calendar = project.Calendars.Add("Custom Calendar");
```
## ステップ 2: 稼働日を定義する
月曜日から金曜日までのデフォルトの営業日を設定します。
```csharp
foreach (var dayType in Enum.GetValues(typeof(DayType)).Cast<DayType>())
{
    if (dayType != DayType.Saturday && dayType != DayType.Sunday)
    {
        calendar.WeekDays.Add(WeekDay.CreateDefaultWorkingDay(dayType));
    }
}
```
## ステップ 3: 土曜日の勤務時間を構成する
土曜日の勤務時間を指定します:
```csharp
var saturdayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(8, 12),
    new WorkingTime(13, 15)
};
var saturday = new WeekDay(DayType.Saturday, saturdayWorkingTimes);
```
## ステップ 4: 土曜日の勤務期間を印刷する
土曜日に設定された稼働時間を出力します。
```csharp
Console.WriteLine("Saturday working period number: " + saturday.WorkingTimes.Count);
foreach (var time in saturday.WorkingTimes)
{
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## ステップ 5: 日曜日の勤務時間を構成する
日曜日の勤務時間を定義します。
```csharp
var sundayWorkingTimes = new List<WorkingTime>
{
    new WorkingTime(10, 15)
};
var sunday = new WeekDay(DayType.Sunday, sundayWorkingTimes);
```
## ステップ 6: 日曜日の勤務期間を印刷する
日曜日に設定された稼働時間を出力します。
```csharp
List<WorkingTime> workingTimes = sunday.WorkingTimes.ToList();
Console.WriteLine("Sunday working period number: " + workingTimes.Count);
for (var index = 0; index < workingTimes.Count; index++)
{
    var time = workingTimes[index];
    Console.WriteLine("From Time: " + time.From);
    Console.WriteLine("To Time: " + time.To);
}
```
## ステップ 7: カレンダーにカスタム日を追加する
設定された土曜日と日曜日をカレンダーに含めます。
```csharp
calendar.WeekDays.Add(saturday);
calendar.WeekDays.Add(sunday);
```
## ステップ 8: 勤務時間をたどる
稼働時間をたどってカレンダーに毎日表示します。
```csharp
foreach (var day in calendar.WeekDays)
{
    Console.WriteLine(day.DayType + ": ");
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine("From: " + workingTime.From);
        Console.WriteLine("To: " + workingTime.To);
    }
    Console.WriteLine();
}
```
手順を完了すると、Aspose.Tasks for .NET の機能を利用して作業時間を効果的に管理する準備が整いました。
## 結論
Aspose.Tasks で作業時間の収集をマスターすると、プロジェクト カレンダーをカスタマイズできるようになり、正確なスケジュールと効率的なリソース利用が保証されます。この包括的なガイドから得た知識を武器に、自信を持ってプロジェクトに取り組んでください。
## よくある質問
### Aspose.Tasks は大規模なプロジェクト管理に適していますか?
はい、Aspose.Tasks はさまざまなサイズのプロジェクトを処理できるように設計されており、効率的なプロジェクト管理のための堅牢な機能を提供します。
### Aspose.Tasks を他の .NET ライブラリと統合できますか?
確かに！ Aspose.Tasks は他の .NET ライブラリとシームレスに統合し、汎用性と互換性を強化します。
### Aspose.Tasks はどのくらいの頻度で更新されますか?
 Aspose.Tasks は、新機能、拡張機能、互換性の向上を組み込むために定期的に更新されます。チェックしてください[リリースページ](https://releases.aspose.com/tasks/net/)最新のアップデートについては。
### Aspose.Tasks に利用できる無料トライアルはありますか?
はい、次のサイトにアクセスして、無料トライアルで Aspose.Tasks を探索できます。[このリンク](https://releases.aspose.com/).
### Aspose.Tasks のサポートはどこに問い合わせればよいですか?
ご質問やサポートが必要な場合は、次のサイトにアクセスしてください。[Aspose.Tasks サポート フォーラム](https://forum.aspose.com/c/tasks/15).