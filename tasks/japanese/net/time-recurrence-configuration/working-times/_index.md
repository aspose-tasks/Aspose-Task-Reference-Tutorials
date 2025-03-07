---
title: Aspose.Tasks での作業時間の構成
linktitle: Aspose.Tasks での作業時間の構成
second_title: Aspose.Tasks .NET API
description: Aspose.Tasks を使用して .NET でのプロジェクトのスケジュール設定を強化します。正確なリソース管理のために作業時間を簡単に設定します。今すぐライブラリをダウンロードしてください!
weight: 13
url: /ja/net/time-recurrence-configuration/working-times/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Tasks での作業時間の構成

## 導入
プロジェクト管理では、正確なスケジュール設定とリソース割り当てのために、作業時間を正確に制御することが重要です。 Aspose.Tasks for .NET は、プロジェクト内の作業時間情報を処理するための強力なソリューションを提供します。このチュートリアルでは、.NET 環境で Aspose.Tasks を使用して作業時間を構成するプロセスについて説明します。
## 前提条件
チュートリアルに入る前に、次のものが揃っていることを確認してください。
- C# プログラミング言語の基本的な理解。
-  Aspose.Tasks for .NET ライブラリがインストールされています。ダウンロードできます[ここ](https://releases.aspose.com/tasks/net/).
- Visual Studio または任意の優先 C# 開発環境のセットアップ。
## 名前空間のインポート
まず、Aspose.Tasks 機能にアクセスするために必要な名前空間をインポートします。
```csharp
    using Aspose.Tasks;
    using System;
    using System.Collections.Generic;
    using System.Diagnostics.CodeAnalysis;
    
```
## ステップ 1: カレンダーを作成する
```csharp
var project = new Project();
var calendar = CreateCalendar(project);
project.Set(Prj.Calendar, calendar);
```
ここでは、新しいプロジェクトを開始し、標準カレンダーに基づいて「MyCalendar」という名前のカレンダーを作成します。このカレンダーは、特定の作業時間を定義するために使用されます。

```csharp
        public static Calendar CreateCalendar(Project project)
        {
            var calendar = project.Calendars.Add("MyCalendar", project.Calendars.GetByName("Standard"));
            var workingTimes = new List<WorkingTime>
                                   {
                                       new WorkingTime(new DateTime(1, 1, 1, 9, 0, 0), new DateTime(1, 1, 1, 12, 0, 0)),
                                       new WorkingTime(new DateTime(1, 1, 1, 13, 0, 0), new DateTime(1, 1, 1, 18, 0, 0))
                                   };

            calendar.WeekDays.Add(new WeekDay(DayType.Monday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Tuesday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Wednesday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Thursday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Friday, workingTimes));
            calendar.WeekDays.Add(new WeekDay(DayType.Saturday));
            calendar.WeekDays.Add(new WeekDay(DayType.Sunday));

            return calendar;
        }	
```
## ステップ 2: 週稼働日情報を表示する
```csharp
Console.WriteLine("Work Week Number: " + calendar.WeekDays.Count);
```
このステップでは、指定されたカレンダーの総営業日数を出力します。
## ステップ 3: 作業時間の詳細
```csharp
List<WeekDay> weekDays = calendar.WeekDays.ToList();
foreach (var day in weekDays)
{
    Console.WriteLine(day.DayType.ToString());
    foreach (var workingTime in day.WorkingTimes)
    {
        Console.WriteLine(workingTime.From);
        Console.WriteLine(workingTime.To);
    }
}
```
この部分では、曜日ごとに繰り返し、曜日の種類と関連する作業時間を出力します。プロジェクトの要件に応じて、平日ごとの作業時間をカスタマイズできます。
## 結論
Aspose.Tasks for .NET で作業時間を効果的に構成すると、正確なプロジェクト計画とリソース管理が保証されます。このステップバイステップのガイドに従うことで、作業時間の調整をプロジェクトのワークフローにシームレスに統合できます。
## よくある質問
### Aspose.Tasks は大規模なプロジェクト管理に適していますか?
はい、Aspose.Tasks はさまざまな規模のプロジェクトを処理できるように設計されており、効率的なプロジェクト管理のための堅牢な機能を提供します。
### チームメンバーごとに異なる勤務時間を設定できますか?
絶対に。リソースごとに作業時間をカスタマイズできるため、個別のスケジュールを設定できます。
### Aspose.Tasks は他のプロジェクト管理ツールとの統合をサポートしていますか?
はい、Aspose.Tasks はさまざまなプロジェクト管理ツールとの統合を容易にし、相互運用性を強化します。
### プロジェクトデータを異なる形式でインポート/エクスポートすることはできますか?
Aspose.Tasks は複数のファイル形式をサポートしており、プロジェクト データのシームレスなインポート/エクスポート操作を可能にします。
### Aspose.Tasks アップデートはどのくらいの頻度でリリースされますか?
最新のテクノロジーとの互換性を確保し、ユーザーのフィードバックに対応するために、アップデートが定期的にリリースされます。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
